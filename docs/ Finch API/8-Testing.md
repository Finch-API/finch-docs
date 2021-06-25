# Testing

Finch offers two types of test environments for developers -

1. Finch Sandbox
2. Live Account Testing

## Finch Sandbox

The Finch Sandbox allows you to login to a fake payroll system and test your application against mock data.

### Auth

To use the sandbox environment, simply [open](https://developer.tryfinch.com/docs/reference/docs/%20Finch%20API/4%20-%20Authorization.md#redirect-to-connect) Finch Connect with the `sandbox` query parameter set to `true`.

You'll want to make sure you include `payment` and `pay_statement` scopes, if you will be requesting these products with the sandbox logins. You'll also want to change the `client_id` with your test client id. Here is an example:

[https://connect.tryfinch.com/authorize?client_id=<your_client_id>&redirect_uri=https://tryfinch.com&sandbox=true&products=company%20directory%20individual%20employment%20payment%20pay_statement%20deduction](https://connect.tryfinch.com/authorize?client_id=<your_client_id&redirect_uri=https://tryfinch.com&sandbox=true&products=company%20directory%20individual%20employment%20payment%20pay_statement%20deduction)

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

### Examples

Payments  endpoint for `smallco`:

```
curl "https://api.tryfinch.com/employer/payment?start_date=2020-01-01&end_date=2020-12-31" \
-H "Authorization: Bearer [uuid obtainted during auth]" \
-H "Finch-API-Version: 2020-09-17" \
-X "GET"
```
This will return a list of `payment_id`s, which you can then query with the `pay-statements` endpoint:

```
curl https://api.tryfinch.com/employer/pay-statement \
-H "Authorization: Bearer [uuid obtained during auth]" \
-H "Finch-API-Version: 2020-09-17" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"requests": [{ "payment_id": "[uuid obtained from /payments call]" }]}'
```

## Live Account Testing

Finch also provides developers access to real payroll accounts. Send an email to [developers@tryfinch.com](mailto:developers@tryfinch.com) for access.


