# Pay Statement

**Info**: Read detailed pay statements for each individual.

**URL**: `POST https://api.tryfinch.com/employer/pay-statement`

**Product**: `pay_statement`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/employer/pay-statement \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"requests": [{ "payment_id": "fc8b024e-d373-4c9c-80fc-f1625383d142"}]}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`requests` | `array` | true | The array of batch requests.
`requests[].payment_id` | `array` | true | A stable Finch `id` (UUID v4) for a payment.
`requests[].limit` | `integer` | false | Number of pay statements to return (defaults to all).
`requests[].offset` | `integer` | false | Index to start from (defaults to 0).

## Response

**Example response**

```json
{
  "responses": [
    {
      "payment_id": "fc8b024e-d373-4c9c-80fc-f1625383d142",
      "code": 200,
      "body": {
        "paging": {
          "count": 25,
          "offset": 10
        },
        "pay_statements": [
          {
            "individual_id": "be7b048c-a6f3-4194-a017-2f537d4f3565",
            "type": "regular_payroll",
            "payment_method": "check",
            "total_hours": 80.67,
            "gross_pay": {
              "amount": 230000,
              "currency": "usd"
            },
            "net_pay": {
              "amount": 180000,
              "currency": "usd"
            },
            "earnings": [
              {
                "type": "salary",
                "name": "Salary",
                "amount": 230000,
                "currency": "usd",
                "hours": 80.67
              }
            ],
            "taxes": [
              {
                "type": "state",
                "name": "State Withholding - OR",
                "employer": false,
                "amount": 0,
                "currency": "usd"
              }
            ],
            "employee_deductions": [
              {
                "name": "Pre-Tax 401k",
                "amount": 50000,
                "currency": "usd",
                "pre_tax": true
              }
            ],
            "employer_contributions": [
              {
                "name": "Employee Medical Insurance",
                "amount": 23272,
                "currency": "usd",
              }
            ],
          }
        ]
      }
    }
  ]
}
```

**Response body**

Name | Type | Description
-----|------|--------------
`paging` | `object` | Metadata about the current list of elements.
`paging.count` | `integer` | The total number of elements for the entire query (not just the given page).
`paging.offset` | `integer` | The current start index of the returned list of elements.
`pay_statements` | `array` | The array of pay statements for the current payment.
`pay_statements[].individual_id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`pay_statements[].type` | `string` | The type of the payment associated with the pay statement. Options: `regular_payroll`, `off_cycle_payroll`, or `one_time_payment`.
`pay_statements[].payment_method` | `string` | The payment method. Options: `check` and `direct_deposit`.
`pay_statements[].total_hours` | `number` | The number of hours worked for this pay period.
`pay_statements[].gross_pay` | `object` | The money object for the gross pay amount in cents.
`pay_statements[].net_pay` | `object` | The money object for the net pay amount in cents.
`pay_statements[].earnings` | `array` | The array of earnings objects associated with this pay statement.
`pay_statements[].earnings[].type` | `string` | The type of earning. Options: `salary`, `wage`, `reimbursement`, `overtime`, `severance`, `double_overtime`, `pto`, `sick`, `bonus`, `commission`, `tips`, `1099` and `other`.
`pay_statements[].earnings[].name` | `string` | The exact name of the deduction from the pay statement.
`pay_statements[].earnings[].amount` | `integer` | The earnings amount in cents.
`pay_statements[].earnings[].currency` | `string ` | The earnings currency code.
`pay_statements[].earnings[].hours` | `string ` | The hours earned for the relevant earning amount, if applicable.
`pay_statements[].employee_deductions` | `array` | The array of deductions objects associated with this pay statement.
`pay_statements[].employee_deductions[].name` | `string` | The deduction name from the pay statement.
`pay_statements[].employee_deductions[].amount` | `integer` | The deduction amount in cents.
`pay_statements[].employee_deductions[].currency` | `string` | The deductions currency code.
`pay_statements[].employee_deductions[].pre_tax` | `boolean` | Boolean indicating if the deduction is pre tax.
`pay_statements[].employer_contributions[].name` | `string` | The contribution name from the pay statement.
`pay_statements[].employer_contributions[].amount` | `integer` | The contribution amount in cents.
`pay_statements[].employer_contributions[].currency` | `string` | The contribution currency code.
`pay_statements[].taxes` | `array` | The array of taxes objects associated with this pay statement.
`pay_statements[].taxes[].type` | `string` | The type of taxes. Options: `state`, `federal`, `local` and `fica`.
`pay_statements[].taxes[].name` | `string` | The exact name of tax from the pay statement.
`pay_statements[].taxes[].employer` | `boolean` | `true` if the amount is paid by the employers.
`pay_statements[].taxes[].amount` | `integer` | The deductions amount in cents.
`pay_statements[].taxes[].currency` | `string` | The deductions currency code.
