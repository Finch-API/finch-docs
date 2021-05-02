# Testing

Finch offers two types of test environments for developers -

1. Finch Sandbox
2. Live Account Testing

## Finch Sandbox

The Finch Sandbox allows you to login to a fake payroll system and test your application against mock data.

To use the sandbox environment, simply [open](https://developer.tryfinch.com/docs/reference/docs/%20Finch%20API/4%20-%20Authorization.md#redirect-to-connect) Finch Connect with the `sandbox` query parameter set to `true`.

### Scenarios

The Sandbox allows for various scenarios based on your testing needs. The credentials you use while logging in determine the behavior of the API.

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

## Live Account Testing

Finch also provides developers access to real payroll accounts. Send an email to developers@tryfinch.com for access.


