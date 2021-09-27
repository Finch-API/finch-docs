# Testing

Finch offers two types of test environments for developers -

1. Finch Sandbox
2. Live Account Testing

## Finch Sandbox

The Finch Sandbox allows you to login to a fake payroll system and test your application against mock data.

To use the sandbox environment, simply [open](https://tryfinch.stoplight.io/docs/reference/ZG9jOjIyMzQyODQx-authorization#finch-connect) Finch Connect with the `sandbox` query parameter set to `true`.

### Scenarios

The sandbox allows for various scenarios based on your testing needs. The credentials you use while logging in determine the behavior of the API.

**Small Company**

Login             | Password
---------------------|-------------
 `smallco`           | `letmein` 

The most basic example to develop against is the simple scenario - a company with a single employee.

**Large Company**

Login              | Password
----------------------|-------------
 `largeco`            | `letmein` 

This scenario provides a much larger dataset to test against. Some attributes of this scenario are -
* a single company with multiple employees,
* employees with managers,
* multiple departments and work locations, and
* payments with various earning types, deductions, and employer contributions.

### Testing Benefits

The sandbox supports read access only for all benefits endpoints. For write endpoints, the sandbox will return a `success` status code, but no information will be updated. This allows you to get a feel for how the API works without modifying any state. Example:

Request:
```shell
curl https://api.tryfinch.com/employer/benefts \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-X "POST"
-H "Content-Type: application/json" \
-d '{"type":"401k", "description": "Sample 401k", "frequency": \ "every_paycheck", "employee_deduction": {"type": "fixed",\ "amount": 100}, "company_contribution": {"type": "fixed", \ "amount": 100}}'
```
Response:
```json
{
  "benefit_id": "12345"
}
```

## Live Account Testing

Finch also provides developers access to real payroll accounts. Send an email to [developers@tryfinch.com](mailto:developers@tryfinch.com) for access.


