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
`requests` | `array` | true | The array of batch requests. Max 50 batch requests.
`requests[].payment_id` | `array` | true | A stable Finch `id` (UUID v4) for a payment.

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
            "total_hours": 80
            "gross_pay": {
              "amount": 230000,
              "currency": "usd"
            },
            "net_pay": {
              "amount": 150000,
              "currency": "usd"
            },
            "earnings": [
              {
                "type": "salary",
                "name": "Salary",
                "amount": 1000,
                "currency": "usd"
              }
            ],
            "deductions": [
              {
                "type": "401k",
                "name": "401k Salary",
                "employer": false,
                "amount": 0,
                "currency": "usd"
              }
            ],
            "taxes": [
              {
                "type": "state",
                "name": "State Withholding - OR",
                "employer": true,
                "amount": 0,
                "currency": "usd"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

**Request body**

Name | Type | Description
-----|------|--------------
`paging` | `object` | Metadata about the current list of elements.
`paging.count` | `integer` | The total number of elements for the entire query (not just the given page).
`paging.offset` | `integer` | The current start index of the returned list of elements.
`pay_statements` | `array` | The array of pay statements for the current payment.
`pay_statements[].individual_id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`pay_statements[].type` | `string` | The type of the payment associated with the pay statement. Options: `regular_payroll`, `off_cycle_payroll`, or `one_time_payment`.
`pay_statements[].payment_method` | `string` | The payment method. Options: `check` and `direct_deposit`.
`pay_statements[].gross_pay` | `object` | The money object for the gross pay amount.
`pay_statements[].net_pay` | `object` | The money object for the net pay amount.
`pay_statements[].earnings` | `array` | The array of earnings objects associated with this pay statement.
`pay_statements[].earnings[].type` | `string` | The type of earning. Options: `salary`, `wage`, `reimbursement`, `overtime`, `severance`, `double_overtime`, `pto`, `sick`, `bonus`, `commission`, `tips`, `1099` and `other`. 
`pay_statements[].earnings[].name` | `string` | The exact name of the deduction from the pay statement.
`pay_statements[].earnings[].amount` | `integer` | The earnings amount in cents.
`pay_statements[].earnings[].currency` | `string ` | The earnings currency code.
`pay_statements[].deductions` | `array` | The array of deductions objects associated with this pay statement.
`pay_statements[].deductions[].type` | `string` | The type of deduction. Options: `medical`, `vision`, `dental`, `401k`, `403b`, `457`, `roth_401k`, `roth_403b`, `roth_457`, `fsa_medical`, `fsa_dependent_care`, `hsa`, `simple_ira`, `commuter_transit`, `commuter_parking`, `short_disability`, `long_disability`, `life`, `student_loan`, and `other`.
`pay_statements[].deductions[].name` | `string` | The exact name of deduction from the pay statement.
`pay_statements[].deductions[].employer` | `boolean` | `true` if the amount is paid by the employers.
`pay_statements[].deductions[].amount` | `integer` | The deductions amount in cents.
`pay_statements[].deductions[].currency` | `string` | The deductions currency code.
`pay_statements[].taxes` | `array` | The array of taxes objects associated with this pay statement.
`pay_statements[].taxes[].type` | `string` | The type of taxes. Options: `state`, `federal`, `local` and `fica`.
`pay_statements[].taxes[].name` | `string` | The exact name of tax from the pay statement.
`pay_statements[].taxes[].employer` | `boolean` | `true` if the amount is paid by the employers.
`pay_statements[].taxes[].amount` | `integer` | The deductions amount in cents.
`pay_statements[].taxes[].currency` | `string` | The deductions currency code.