# Employment

**Info**: Read individual employment and income data

**URL**: `POST https://api.tryfinch.com/employer/employment`

**Product**: `employment`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/employer/employment \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"requests": [{ "individual_id": "f3ddb1f4-dfa4-4e1d-bfed-bdfd0645b613"}]}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`requests` | `array` | true | The array of batch requests.
`requests[].individual_ids` | `array` | true | A stable Finch `id` (UUID v4) for an individual in the company. There is no limit to the number of  `individual_id` to send per request. It is preferantial to send all ids in a single request for Finch to optimize provider rate-limits.

***

## Response

**Example response**

```json
{
  "responses": [
    {
      "individual_id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
      "code": 200,
      "body": {
        "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
        "first_name": "Jeremy",
        "middle_name": null,
        "last_name": "Zhang",
        "title": "Customer Support",
        "manager": {
          "id": "c205b3fa-b626-4346-bf0f-ca065ab88d31"
        },
        "department": {
          "name": "Product"
        },
        "employment": {
          "type": "employee",
          "subtype": "full_time"
        },
        "start_date": "2019-03-01",
        "end_date": null,
        "is_active": true,
        "location": {
          "line1": "628 Forest Ave",
          "line2": null,
          "city": "Palo Alto",
          "state": "CA",
          "postal_code": "94301",
          "country": "US"
        },
        "income": {
          "unit": "yearly",
          "amount": 10000000,
          "currency": "usd"
        }
      }
    }
  ]
}
```

**Response body**

Name | Type | Description
-----|------|--------------
`id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`first_name` | `string` | The legal first name of the individual.
`middle_name` | `string` | The legal middle name of the individual.
`last_name` | `string` | The legal last name of the individual.
`title` | `string` | The current title of the individual.
`manager` | `object` | The manager object representing the manager of the individual within the org.
`manager.id` | `string` |  A stable Finch `id` (UUID v4) for an individual in the company.
`department` | `object` | The department object.
`department.name` | `string` | The name of the department associated with the individual.
`employment` | `object` | The employment object.
`employment.type` | `string` | The main employment type of the individual. Options: `employee` and `contractor`.
`employment.subtype` | `string` | The secondary employment type of the individual. Options: `full_time`, `part_time`, `intern`, `temp`, `seasonal` and `individual_contractor`.
`start_date` | `string` | The start date of an individual. ISO 8601 format.
`end_date` | `string` | The end date of an individual. ISO 8601 format.
`is_active` | `string` | `true` if the individual an an active employee or contractor at the company.
`location` | `object` | The work location object.
`location.line1` | `string` | Street address or PO box.
`location.line2` | `string` | Apartment, suite, unit, or building.
`location.city` | `string` | City, district, suburb, town, or village.
`location.state` | `string` | The state code.
`location.postal_code` | `string` | The postal code or zip code.
`location.country` | `string` | The 2-letter ISO 3166 country code.
`income` | `object` | The income object.
`income.unit` | `string` | The income unit of payment. Options: `yearly`, `monthly`, `hourly`, and `fixed`.
`income.amount` | `integer` | The income amount in cents.
`income.currency` | `string` | The currency code.
