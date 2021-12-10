# Testing

Finch offers two types of test environments for developers -

1. Finch Sandbox
2. Live Account Testing

---

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
  
---

## Live Account Testing

There are a few options available to you to if you want to test your integration against real accounts.

### Bamboo HR

You can sign up for a free Bamboo HR demo account [here](https://www.bamboohr.com/signup/) and use your newly created administrator credentials to log in through Connect.

### Zenefits

You can sign up for a free Zenefits account [here](https://www.zenefits.com/learn/trial-signup/) and use your newly created administrator credentials to log in through Connect.

### Testing benefits

If you want to test our Benefits product against a real account, reach out to us on Slack or at [`developers@tryfinch.com`](mailto:developers@tryfinch.com).
