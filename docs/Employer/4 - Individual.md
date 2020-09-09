# Individual

**Info**: Read employee data, excluding income and employment data

**URL**: `POST https://api.tryfinch.com/v1.0/employer/individual`

**Product**: `individual`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/v1.0/employer/individual \
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
    "first_name": "Jeremy",
    "middle_name": null,
    "last_name": "Zhang",
    "business": {
      "legal_name": "Smartcar Inc.",
      "ein": "xx-xxxxxx"
    },
    "photo": "https://s3-us-west-2.amazonaws.com/com.rippling.images/4728f747-53e8-4505-8373-a35abc9696ab",
    "emails": [
      {
        "data": "jeremy@tryfinch.com",
        "type": "work"
      },
      {
        "data": "jeremyziyuzhang@gmail.com",
        "type": "personal"
      }
    ],
    "phone_number": [
      {
        "data": "4077413626",
        "type": "mobile"
      }
    ],
    "dob": "1995-08-15",
    "is_active": true,
    "residence": {
      "line1": "628 Allentown Ave",
      "line2": "Apt C",
      "city": "Palo Alto",
      "state": "CA",
      "postal_code": "94301",
      "country": "US"
    },
    "work_location": {
      "line1": "200 Forham Ave",
      "line2": null,
      "city": "Palo Alto",
      "state": "CA",
      "postal_code": "94301",
      "country": "US"
    }
  }
]
```

**Response body**

Name | Type | Description
-----|------|--------------
`[].id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`[].first_name` | `string` | The legal first name of the individual.
`[].middle_name` | `string` | The legal middle name of the individual.
`[].last_name` | `string` | The legal last name of the individual.
`[].business` | `object` | The legal entity associated with the individual.
`[].business.legal_name` | `string` | The legal name of the company.
`[].business.ein` | `string` | The employer identification number.
`[].photo` | `string` | URL to the profile picture of the individual.
`[].emails` | `array` | An array of email objects.
`[].emails[].data` | `string` | The email address associated with the email type.
`[].emails[].type` | `string` | Indicates the type of email. Options: `work`, `personal`.
`[].phone_numbers` | `array` | An array of phone number objects.
`[].phone_numbers[].data` |  `string` | The phone number associated with the email type. Format: `XXXXXXXXXX`
`[].phone_numbers[].type` | `string` | Indicates the type of phone number. Options: `work`, `personal`.
`[].dob` | `string` | The birthday of the individual. ISO 8601 format.
`[].is_active` | `boolean` | `true` if the individual is an active employee or contractor at the company.
`[].residence` | `object` | The residence object.
`[].residence.line1` | `string` | Street address or PO box.
`[].residence.line2` | `string` | Apartment, suite, unit, or building.
`[].residence.city` | `string` | City, district, suburb, town, or village
`[].residence.state` | `string` | 2-digit state code
`[].residence.postal_code` | `string` | 5-digit postal code or zip code
`[].residence.country` | `string` | The name of the country
`[].work_location` | `object` | The work location object.
`[].work_location.line1` | `string` | Street address or PO box.
`[].work_location.line2` | `string` | Apartment, suite, unit, or building.
`[].work_location.city` | `string` | City, district, suburb, town, or village
`[].work_location.state` | `string` | 2-digit state code
`[].work_location.postal_code` | `string` | 5-digit postal code or zip code
