# Employment

**Info**: Read employee employment and income data

**URL**: `POST https://api.tryfinch.com/v1.0/employer/employment`

**Product**: `employment`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/v1.0/employer/employment \
-H "Authorization: Bearer {token}" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"individual_ids": ["5d0b10a1-a09a-430f-81f1-20be735dc5e9"]}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`individual_ids[]` | `array` | true | Array of individual ids.

***

## Response

**Example response**

```json
[
  {
    "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
    "title": "Underwater Basket Weaver",
    "manager": {
      "id": "c205b3fa-b626-4346-bf0f-ca065ab88d31"
    },
    "department": {
      "name": "Product"
    },
    "employment": {
      "type": "employee",
      "subtype": "full_time",
    },
    "start_date": "2019-03-01",
    "termination_date": null,
    "is_active": true,
    "income": {
      "unit": "yearly",
      "amount": 10000000,
      "currency": "usd"
    }
  }
]
```

**Response body**

Name | Type | Description
-----|------|--------------
`[].id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`[].title` | `string` | The current title of the employee.
`[].manager` | `object` | The manager object representing the manager of the individual within the org.
`[].manager.id` | `string` |  A stable Finch `id` (UUID v4) for an individual in the company.
`[].department` | `object` | The department object.
`[].department.name` | `string` | The name of the department associated with the individual.
`[].employment` | `object` | The employment object.
`[].employment.type` | `string` | The main employment type of the individual. Options: `employee` and `contractor`.
`[].employment.sub_type` | `string` | The secondary employment type of the individual. Options: `full_time`, `part_time`, `intern`, `temp`, and `contractor`.
`[].start_date` | `string` | The start date of an individual. ISO 8601 format.
`[].termination_date` | `string` | The termination date of an individual. ISO 8601 format.
`[].is_active` | `string` | `true` if the individual an an active employee or contractor at the company.
`[].income` | `object` | The income object.
`[].income.unit` | `string` | The income unit of payment. Options: `yearly`, `monthly`, `hourly`, and `fixed`.
`[].income.amount` | `string` | The income amount in cents.
`[].income.currency` | `string` | The currency code.
