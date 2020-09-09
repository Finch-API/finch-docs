# Pay Statement

**Info**: Read detailed pay statements for each employee.

**URL**: `GET https://api.tryfinch.com/v1.0/employer/payment-statement`

**Product**: `pay-statement`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/v1.0/employer/payment-statement \
-H "Authorization: Bearer {token}" \
-X "GET"
```

## Response

**Example request**

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
            "pay_period": {
              "start_date": "2020-06-20",
              "end_date": "2020-06-30"
            },
            "pay_date": "2020-06-30",
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
                "type": "xyz",
                "name": "Salary",
                "amount": 1000,
                "currency": "usd"
              }
            ],
            "deductions": [
              {
                "type": "401k",
                "name": "401k Salary",
                "amount": 0,
                "currency": "usd"
              }
            ],
            "taxes": [
              {
                "type": "state",
                "name": "State Withholding - OR",
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
`pay_statements[].pay_period` | `string` | The pay period object.
`pay_statements[].pay_period.start_date` | `string` | The start date for the pay period corresponding with this payment.
`pay_statements[].pay_period.end_date` | `string` | The end date for the pay period corresponding with this payment.
`pay_statements[].pay_date` | `string` | The date at which individual will be paid for this payment.
`pay_statements[].type` | `string` | The type of the payment associated with the pay statement. Options: `regular_payroll`, `off_cycle_payroll`, or `one_time_payment`.
`pay_statements[].payment_method` | `string` | The payment method. Options: `check` and `direct_deposit`.
`pay_statements[].gross_pay` | `object` | The money object for the gross pay amount.
`pay_statements[].net_pay` | `object` | The money object for the net pay amount.
`pay_statements[].earnings` | `array` | The array of earnings objects associated with this pay statement.
`pay_statements[].earnings[].type` | `string` | The type of earning. Options: `regular`, `overtime`, `double_overtime`, `pto`, `sick`, `bonus`, `commission`, `paycheck_tips`, `1099` and `other`. 
