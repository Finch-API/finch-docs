# Integrating the Benefits API

Finch's [Benefits API](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MTk-create-benefit) endpoints allow users to read and write benefits information (401k, Health Savings Accounts, Loans, etc) across providers using a single, unified API.

## Calling Finch’s API

Before creating and enrolling employees in benefits, you must create an access token using our Finch Connect flow. If the provider is listed as an [Automated API Provider](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers#automated-api-providers), you will the [Automated Connect Flow](https://developer.tryfinch.com/docs/reference/a2c944f1041f6-automated-connect-flow). If the provider is listed as an [Assisted API Provider](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers#assisted-api-providers), you will use our [Assisted Connect Flow](https://developer.tryfinch.com/docs/reference/8c540ddeca222-assisted-connect-flow). Once you have an access token, you can call the Finch API normally.

1. Both **Automated** and **Assisted** Benefits connections can call these endpoints
    - `POST /employer/benefits` to create a new company-wide benefit or individual deduction
    - `POST /employer/benefits/{benefit_id}/individuals` to enroll employee(s) in an existing benefit or deduction
    - `POST /employer/benefits/{benefit_id}` to update an existing company-wide benefit or individual deduction
    - `GET /employer/benefits/meta` to list the available benefit types and configurations for the provider associated with the access token
    - `DELETE /employer/benefits/{benefit_id}/individuals` to unenroll individuals from a benefit
2. Only **Automated** Benefits connections can call these endpoints
    - `GET /employer/benefits` to list all company-wide benefits
    - `GET /employer/benefits/{benefit_id}` to list benefit information for a given benefit
    - `GET /employer/benefits/{benefit_id}/enrolled` to list individuals currently enrolled in a given benefit
    - `GET /employer/benefits/{benefits_id}/individuals` to get enrolled benefit information for the given individuals

For a list of which providers are automated or assisted, please reference our [Providers](/docs/Development-Guides/Providers.md) guide.

If you are using **Assisted** Benefits connections and you try to call the automated-only endpoints, you will receive a 501 error code `Not Implemented`. This is expected. The assisted flow does currently not support read endpoints. If you would like to learn more about how Assisted Connections work, you can view our [Assisted Connect Flow](/docs/Product-Guides/Assisted-Connect-Flow.md) product guide.

Example `Not Implemented` response:

```json
{
  "statusCode": 501,
  "status": 501,
  "code": 501,
  "message": "Not Implemented",
  "name": "not_implemented_error"
}
```

### Using benefit metadata

The types and features of each benefit can vary between payroll systems, and even between users of the same payroll system, depending on the configuration that the company has set up. For this reason, we provide a [`/employer/benefits/meta`](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MjA-get-benefits-metadata) endpoint, which will provide the types and features available for the employer whose benefits you are managing.

On request, we can also provide written documentation about supported features and benefit types at the provider level. Please reach out to your account representative for that information.

**Note: One-time post-tax deductions are not currently supported for benefits.**

### Handling Assisted Benefits API responses

For Automated connections that have Assisted Benefits enabled, the response you receive from the `/employer/benefits` endpoints will contain a `job_id`. While our dedicated product operations team makes the necessary changes in the provider's system, you can continue to call the `GET /jobs/{job_id}` to get the status of the job. The valid job status responses will be either `pending`, `in_progress`, `complete`, or `error` with a response body further explaining the response.

Example `POST /employer/benefits` response:

```json
{
  "benefit_id": "264122c0-0216-4f21-a4cd-7b3bcddbe3fc",
  "job_id": "497d98f3-580a-4ab9-830a-af2346d029b2"
}
```

Example `POST /employer/benefits/{benefit_id}/individuals` Response:

```json
{
  "job_id": "3a82a144-d168-4207-942a-a5852b11df1c"
}
```

This will be the same for `DELETE /employer/benefits/{benefit_id}/individuals`

Example `GET /jobs/{job_id}` response after initial job submission:

```json
{
  "job_id": "3a82a144-d168-4207-942a-a5852b11df1c",
  "code": 202,
 "status": "pending"
}
```

Example `GET /jobs/{job_id}` response after job is completed for a `POST /employer/benefits/individuals` request with multiple individuals:

```json
{
 "job_id": "3a82a144-d168-4207-942a-a5852b11df1c",
  "code": 207,
  "status": "complete",
 "body": [
    {
      "individual_id": "430f9d95-1dcf-4b99-b616-45f814416890",
      "code": 201,
      "message": "Successfully enrolled individual in benefit",
    },
    {
      "individual_id": "647975ac-1e0f-4e9c-b705-e3042da48581",
      "code": 200,
      "message": "Successfully updated enrollment for individual",
    },
    {
      "individual_id": "4a0a3b15-d3d6-41c2-a4a4-ca4ed1b68cf8",
      "code": 404,
      "message": "Individual not found"
    },
    ...
  ]
}
```
## General Benefits Information

Since enrolling benefits can be a sensitive activity, it is helpful to understand some of the nuances around payroll and benefits in general.

### How do payroll benefit deductions work?

Each payroll contains four important dates to know.

1. Payroll Start Date - The first day of the pay period
2. Payroll End Date - The last day of the pay period
3. Payroll Close Date - The last date to make changes for that pay period
4. Paycheck Date - The date on which employees are paid

When considering benefits, it is important to submit any employee benefit changes before the pay close date in order to take affect for the current pay period. If any changes are submitted after the payroll close date, they will only affect the next pay period, not the current. Since each payroll close date is different per provider, it is important to know this date and set proper expectations with your customers.

Finch offers two API modes: Automated and Assisted.

You can review [our list of valid providers](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers) to see which providers are automated vs assisted for the Benefits endpoints.

### Benefits submissions

For assisted benefits connections, it is important to submit payroll benefit deductions to our API 7 days before the customer’s payroll close date. This will help ensure that changes can be processed within the current payroll period (unless explicitly specified otherwise in your API request).

**Example**

As an example, if the payroll period is **June 1 - 15**. The payroll close date might be **June 16** so payroll can be processed before **Friday, June 17**.  Therefore, it would be important to submit payroll deductions via the Finch API by **June 9** for those to take effect during the June 1 - 15 payroll.

<pre>
June 2022
Su Mo Tu We Th Fr Sa
          <mark style="background-color: lightblue">1  2  3  4
 5  6  7  8  9 10 11
12 13 14 15</mark> <mark style="background-color: yellow">16</mark> <mark style="background-color: green">17</mark> 18
19 20 21 22 23 24 25
26 27 28 29 30
</pre>

Some payroll providers offer a dedicated payroll representative to help with making payroll changes. If a payroll rep is helping your customer’s HR admin with changes in their system, it is important that you make it explicitly clear who does what so that the payroll rep does not overwrite any changes Finch has previously made. Calling out Benefit Code types and using thoughtful benefit descriptions (e.g. with your company name) help.

## Testing benefits


### Sandbox

You can [use the benefits endpoints in the Finch Sandbox](https://developer.tryfinch.com/docs/reference/ZG9jOjMxOTg1NTMw-testing#testing-benefits). This supports read operations (`GET` requests) and stubbed out write operations (`POST` requests), meaning writes will not actually change any internal state and reads will always return the same responses.

### Live Accounts

If you would like to test our Benefits product against a real account, please reach out to a Finch representative so we can set you up with a testing environment.