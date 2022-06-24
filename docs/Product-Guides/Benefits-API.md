# Integrating the Benefits API

Finch's [Benefits API](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MTk-create-benefit) endpoints allow users to read and write benefits information (401k, Health Savings Accounts, Loans, etc) across providers using a single, unified API.

## How do payroll benefit deductions work?

Since benefits work very differently across different providers, it is important to know a little about how payroll and benefits work in general.

Each payroll contains four important dates to know.

1. Payroll Start Date - The first day of the pay period
2. Payroll End Date - The last day of the pay period
3. Payroll Close Date - The last date to make changes for that pay period
4. Paycheck Date - The date on which employees are paid

When considering benefit deductions, it is important to submit any employee deductions before the pay close date in order to affect for the current pay period. If any deductions are submitted after the payroll close date, they will only affect the next pay period, not the current. Since each payroll close date is different per provider, it is important to know this date and set proper expectations with your customers.

Finch has two types of ways to call our API: Automated and Assisted.

- If the payroll provider is ***automated***, any deductions that are submitted via our API will be changed in the provider’s system instantaneously.
- If the payroll provider is ***assisted***, any deductions that are submitted via our API will be changed within 7-14 days. During this time, the Finch team will manually process your API request, assist in creating a benefit if necessary, enroll employees in that benefit, and send a response back to you when the request is complete. This benefits you because your team does not need to build a product operations team to make these changes yourself; Finch does this for you.

You can review [our list of valid providers](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers) to figure out which providers are automated vs assisted for the Benefits endpoints.

## Benefits submissions

Because of the manual nature of assisted benefit connections, it is important to submit payroll benefit deductions to our API 7 days before the customer’s payroll close date. This gives the Finch team a higher chance of making the change in the provider’s system so it can be processed with the current payroll period (unless explicitly specified otherwise in your API request).

For most of your customers, this is already a part of the HR admin workflow. We are just changing the location of where they make this change. It is important as the developer to make it clear to your customers what the payroll close date is so that it can be communicated properly if the benefit will take effect this pay period or next pay period.

## Example

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

### Couple of things to keep in mind

- Often there is a company contribution and an employee contribution. Some payroll systems separate these, some add them together when calculating the deduction. When validating if the deduction is successful, make sure to understand how the provider you are working with handles contributions. Our team will add the deduction based on how the provider is set up.
- Some payroll providers offer a dedicated payroll representative to help with making payroll changes. If a payroll rep is helping your customer’s HR admin with changes in their system, it is important that you make it explicitly clear who does what so that the payroll rep does not overwrite any changes Finch has previously made. Calling out Benefit Code types and thoughtful benefit descriptions help.

## Testing benefits

There are three ways we recommend testing benefits.

### Option 1 - Sandbox

You can [use the benefits endpoints in the Finch Sandbox](https://developer.tryfinch.com/docs/reference/ZG9jOjMxOTg1NTMw-testing#testing-benefits). This supports read operations (`GET` requests) and stubbed out write operations (`POST` requests), meaning writes will not actually change any internal state and reads will always return the same responses.

### Option 2 - Automated

If you need to test reading back the data you write into the system, you can use our test Gusto instance (using the company Cisticola LLC that we set up) for testing our benefits endpoints. At the time of writing (6/22/22), this Gusto instance currently has two active employees, one active contractor, and two inactive employees. The active employees can be enrolled in any of the benefits that Gusto supports. The compatibility matrices of support benefit types and benefit features can be found below - [Gusto Compatibility Matrices]().

> Please keep in mind that this is a live account for a real LLC that our company runs. This means that there are tax implications to actually moving money.
> - Please DO NOT EVER RUN PAYROLL ON THIS ACCOUNT.
> - Please do not edit anything in the Gusto dashboard.
> - Please do not hire or fire any employees or contractors.
> - Please do not add any additional admins to this account.

### Option 3 - Assisted

Assisted Benefits via API allows you to use the Finch API to enroll employees in benefits for providers which are not yet fully automated. Because benefits work very differently across different systems, Finch offers a few test accounts to help explore assisted benefits connections. However, because assisted connections requires some manual work for our product operations team to complete the requests, we will only be able to perform a few test requests.

- Zenefits
- Paychex Flex
- JustWorks (coming soon)

## Calling Finch’s API

Before creating and enrolling employees in benefits, you must create an access token using our Finch Connect flow. If the provider is listed as an [Automated API Provider](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers#automated-api-providers), you will the [Automated Connect Flow](https://developer.tryfinch.com/docs/reference/a2c944f1041f6-automated-connect-flow). If the provider is listed as an [Assisted API Provider](https://developer.tryfinch.com/docs/reference/96f5be9e0ec1a-providers#assisted-api-providers), you will use our [Assisted Connect Flow](https://developer.tryfinch.com/docs/reference/8c540ddeca222-assisted-connect-flow). Once you have an access token, you can call the Finch API normally.

1. Both **Automated** and **Assisted** Benefits connections can call these endpoints
    - `POST /employer/benefits` to create a new company-wide benefit or individual deduction
    - `POST /employer/benefits/{benefit_id}/individuals` to enroll employee(s) in an existing benefit or deduction
    - `POST /employer/benefits/{benefit_id}` to update an existing company-wide benefit or individual deduction
    - `GET /employer/benefits/meta` to list the available benefit types and configurations for the provider associated with the access token
    - `DELETE /employer/benefits/{benefit_id}/individuals` to unenroll individuals from a benefit
2. Only **Automated** Benefits connections can call these endpoints**
    - `GET /employer/benefits` to list all company-wide benefits
    - `GET /employer/benefits/{benefit_id}` to list benefit information for a given benefit
    - `GET /employer/benefits/{benefit_id}/enrolled` to list individuals currently enrolled in a given benefit
    - `GET /employer/benefits/{benefits_id}/individuals` to get enrolled benefit information for the given individuals

** Gusto is our only automated benefits provider as of 6/22/22.

If you are using **Assisted** Benefits connections, if you try to call the automated-only endpoints, you will receive a 501 error code `Not Implemented`. This is expected. As of right now, since Assisted Benefits is an “assisted” process, Finch’s product operations team can only create, update, and enroll benefits; we do not keep track of all the benefits in an Assisted provider. If you would like to learn more about how Assisted Connections work, you can view our [Assisted Connect Flow](/docs/Product-Guides/Assisted-Connect-Flow.md) product guide.

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

The types and features of each benefit can vary between payroll systems, and even between users of the same payroll system, depending on the configuration that the company has set up. For this reason, we provide a `/employer/benefits/meta` endpoint, which will provide the types and features available for the employer whose benefits you are managing.

On request, we can also provide written documentation about supported features and benefit types at the provider level. Please reach out to your account representative for that information.

**Note: One-time post-tax deductions are not currently supported for benefits yet.**

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

## Gusto Compatibility Matrices

<!--
type: tab
title: Supported Operations
-->

>`✓` - supported
>
>`x` - not supported by Finch
>
>`n/a` - not supported by provider

Benefit | Read Company Benefits | Create Company Benefits | Read Individual Benefits | Enroll/Unenroll Individual Benefits
--------|----------|---------|------------|------------
**401(k)** | ✓ | ✓ | ✓ | ✓ |
**Roth 401(k)** | ✓ | ✓ | ✓ | ✓ |
**403(b)** | ✓ | ✓ | ✓ | ✓ |
**Roth 403(b)** | ✓ | ✓ | ✓ | ✓ |
**457** | n/a | n/a | n/a | n/a |
**Roth 457**  | n/a | n/a | n/a | n/a |
**Simple IRA** | ✓ | ✓ | ✓ | ✓ |
**HSA (post-tax)** | n/a | n/a | n/a | n/a |
**HSA (pre-tax)** | ✓ | ✓ | ✓ | ✓ |
**FSA Dependent** | ✓ | ✓ | ✓ | ✓ |
**FSA Medical** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Dental** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Medical** | ✓ | ✓ | ✓ | ✓ |
**Section 125 Vision** | ✓ | ✓ | ✓ | ✓ |
**Commuter (pre-tax)** | ✓ | ✓ | ✓ | ✓ |
**Custom pre-tax** | n/a | n/a | n/a | n/a |
**Custom post-tax** | ✓ | ✓ | ✓ | ✓ |

<!--
type: tab
title: Supported Features
-->

Benefit | Features
--------|----------
**401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 401(k)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**403(b)** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 403(b)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**457**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Roth 457** | `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**Simple IRA**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`
**HSA (pre-tax)**| `company_contribution`: `fixed`, `percent`<br>`employee_deduction`: `fixed`, `percent`<br>`catch_up`<br>`annual_maximum`<br>`hsa_contribution_limit`: `individual`, `family`
**FSA Dependent** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**FSA Medical** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Dental** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Medical**| `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Section 125 Vision** | `company_contribution`: `fixed`<br>`employee_deduction`: `fixed`
**Commuter (pre-tax)** | `company_contribution`: `fixed` <br>`employee_deduction`: `fixed`
**Custom post-tax** | `employee_deduction`: `fixed`, `percent`<br>`annual_maximum`

<!-- type: tab-end -->

## Getting access to the test Gusto instance

1. When you request access to the test Gusto instance, you will be added as an admin by Finch. Check your email for the Gusto invite titled `Cisticola LLC has been added as a client on Gusto`

1. You should have received an email that looks like this:
    
    ![Gusto Login Email](/assets/images/gustoLoginEmail.png)
    
1. Right-click `Login` and open in incognito browser.
1. Select `Having trouble signing in?` and then `I forgot my password`.
1. Input your email address.
1. Navigate back to your inbox where an email will be sent to set up a new password.
1. Right-click `Change my password` and open in incognito browser
1. Click `Change Password`

1. [optional] Once logged in, set up the Multi-factor authentication on the account. Select the option of using the **Authenticator App**.

Once you have the credentials, you can enter them into Finch Connect in your own test environment using your dev keys (these are different from sandbox keys. If you don’t have dev keys yet, please ask your Finch representative) and proceed to get an access token to use the API as normal.
