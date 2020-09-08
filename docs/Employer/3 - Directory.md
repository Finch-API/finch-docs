# Directory

**Info**: Read company directory and organization structure

**URL**: `GET https://api.tryfinch.com/v1.0/employer/directory`

**Product**: `directory`

**Example Request**

```curl
curl https://api.tryfinch.com/v1.0/employer/directory \
-H "Authorization: Bearer {token}" \
-X "GET"
```

**Query Parameters**

Parameter | Type | Required | Description
----------|------|----------|------------0
`limit` | `integer` | false | Number of employees to return (default/max: 10).
`offset` | `integer` | false | Index to start from. (default: 0)

**Example Response**

```json
{
  "paging": {
    "count": 25,
    "offset": 10
  },
  "individuals": [
    {
      "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
      "first_name": "Jeremy",
      "middle_name": null,
      "last_name": "Zhang",
      "manager": {
        "id": "c205b3fa-b626-4346-bf0f-ca065ab88d31"
      },
      "department": {
        "name": "Product"
      },
      "is_active": true
    }
  ]
}
```

**Response Body**

Name | Type | Description
-----|------|-------------
`paging` | `object` | Metadata about the current list of elements.
`paging.count` | `integer` | The total number of elements for the entire query (not just the given page).
`paging.offset` | `integer` | The current start index of the returned list of elements.
`individuals` | `array` | The array of employees
`individuals[].id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`individuals[].first_name` | `string` | The legal first name of the individual.
`individuals[].middle_name` | `string` | The legal middle name of the individual.
`individuals[].last_name` | `string` | The legal last name of the individual.
`individuals[].manager` | `object` | The manager object.
`individuals[].manager.id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`individuals[].department` | `object` | The department object.
`individuals[].department.name` | `string` | The name of the department.
`employees[].is_active` | `boolean` | `true` if the individual is an active employee or contractor at the company.