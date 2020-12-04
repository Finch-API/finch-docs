# Payment

**Info**: Read payroll and contractor related payments by the company.

**URL**: `GET https://api.tryfinch.com/employer/payment`

**Product**: `payment`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/employer/payment?start_date=2019-08-01&end_date=2019-08-15 \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-X "GET"
```

**Query parameters**

Parameter | Type | Required | Description
----------|------|----------|------------
`start_date` | `string` | true | The start date to retrieve payments by a company (inclusive).
`end_date` | `string` | true | The end date to retrieve payments by a company (inclusive). 

***

## Response

**Example response**

```json
[
  {
    "id": "20aa7cf2-949d-4d4e-9c01-499b59501ded",
    "pay_period": {
      "start_date": "2019-08-01",
      "end_date": "2019-08-15"
    },
    "pay_date": "2019-08-22",
    "debit_date": "2019-08-22",
    "company_debit": {
      "amount": 360000,
      "currency": "usd"
    },
    "gross_pay": {
      "amount": 4000000,
      "currency": "usd"
    },
    "net_pay": {
      "amount": 3200000,
      "currency": "usd"
    },
    "employer_taxes": {
      "amount": 200000,
      "currency": "usd"
    },
    "employee_taxes": {
      "amount": 350000,
      "currency": "usd"
    },
    "individual_ids": [
      "54719e14-5ea7-4fda-9898-f4d9ccb83c1a",
      "0ab620fc-203e-44ad-916c-facc69250f6f"
    ]
  }
]
```

**Response body**

Name | Type | Description
-----|------|--------------
`[].id` | `string` | The unique id for the payment.
`[].pay_period` | `string` | The pay period object.
`[].pay_period.start_date` | `string` | The start date for the pay period corresponding with this payment.
`[].pay_period.end_date` | `string` | The end date for the pay period corresponding with this payment.
`[].pay_date` | `string` | The date at which individual will be paid for this payment.
`[].debit_date` | `string` | The date the company is debited for this payment.
`[].company_debit` | `object` | The money object for the total company debit for the payment.
`[].gross_pay` | `object` | The money object for the gross pay amount for the payment.
`[].net_pay` | `object` | The money object for the net pay amount for the payment.
`[].employer_taxes` | `object` | The money object for the employer paid taxes for the payment.
`[].employee_taxes` | `object` | The money object for the employee paid taxes for the payment.
`[].individual_ids` | `array` | Array of every individual on this payment.
