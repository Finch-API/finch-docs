# Employment

**Info**: Read employee employment and income data

**URL**: `POST https://api.tryfinch.com/v1.0/employer/employment`

**Product**: `employment`

***

## Request

**Example Request**

```shell
curl https://api.tryfinch.com/v1.0/employer/employment \
-H "Authorization: Bearer {token}" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"individual_ids": ["5d0b10a1-a09a-430f-81f1-20be735dc5e9"]}'
```

**Request Body Parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`individual_ids[]` | `array` | true | Array of individual ids.

***

## Response

**Example Response**

```json
{
  "individuals": [
    {
      "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
      "title": "Underwater Basket Weaver",
      "manager": {
        "id": "c205b3fa-b626-4346-bf0f-ca065ab88d31"
      },
      "department": {
        "name": "Product"
      },
      "type": "full_time",
      "start_date": "2019-03-01",
      "termination_date": null,
      "is_active": true,
      "filingStatus": "single",
      "income": {
        "unit": "yearly",
        "amount": 10000000,
        "currency": "usd"
      }
    }
  ]
}
```

**Response Body**

Name | Type | Description
-----|------|--------------

`individuals` | `array` | An array of the responses.
`individuals[].id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`individuals[].title` | `string` 