# Integrating the Benefits API

Once an employer has connected their system to your application, you can use Finch's [Benefits API](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MTk-create-benefit) to manage benefits (401k, HSA, Loans, etc).

Working with benefits through the Finch API is a simple two-phase process:
1. Benefits are configured at the company level. When a new benefit is created or an existing benefit is read from the system, you will receive a `benefit_id` for it.
2. You can use the `benefit_id` to manage the enrollment of employees in that benefit.

----

## Getting and Creating Company Benefits
Our API allows you to both [create new benefits](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MTk-create-benefit) in a payroll system and [get existing benefits](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MTg-get-all-benefits) from the system. Both of these requests will respond with a `benefit_id` in the response body. For example, a creation request will respond with:
```json
{
  "benefit_id": "e8b90071-0c11-471c-86e8-e303ef2f6782"
}
```
You can reference a benefit with its `benefit_id` to perform any action on the benefit (for example, update the benefit configuration, enroll an employee into the benefit, etc).


### Using benefit metadata
The types and features of each benefit can vary between payroll systems, and even between users of the same payroll system, depending on the configuration that the company has set up. For this reason, we provide a [`/employer/benefits/meta`](https://developer.tryfinch.com/docs/reference/b3A6MTg4Mzc2MjA-get-benefits-metadata) endpoint, which will provide the types and features available for the employer whose benefits you are managing.

On request, we can also provide written documentation about supported features and benefit types at the provider level. Please reach out to your account representative for that information.

## Enrolling and Unenrolling Individuals

### Enrolling individuals into a benefit
Enroll individuals into a benefit using [`POST /employer/benefits/{benefit_id}/individuals`](https://developer.tryfinch.com/docs/reference/b3A6MjE4NDU0NTU-enroll-individuals-in-benefits). The request allows you to uniquely configure each individuals enrollment into a benefit.

The schema of the configuration varies depending on the type of benefit you are enrolling, so please refer to the docs to ensure you are using the right schema.


### Updating existing enrollments
To update enrollment configurations for currently enrolled individuals, you can use the same [`POST /employer/benefits/{benefit_id}/individuals`](https://developer.tryfinch.com/docs/reference/eb8994494966c-enroll-individuals-in-benefits) endpoint that you use to enroll new individuals.

When updating an existing enrollment for an individual, the enrollment configuration will be completely overwritten with the new configuration provided in the request, so please make sure to include the entire desired configuration. 

### Unenrolling indiviudals from a benefit
You can unenroll individuals by using the [`DELETE /employer/benefits/{benefit_id}/individuals`](https://developer.tryfinch.com/docs/reference/b3A6MjE4NDU0NTY-unenroll-individuals-from-benefits) endpoint.