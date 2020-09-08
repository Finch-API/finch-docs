# Individual

**Info**: Read employee data, excluding income and employment data

**URL**: `POST https://api.tryfinch.com/v1.0/employer/directory`

**Product**: `individual`

**Example Request**

```curl
curl https://api.tryfinch.com/v1.0/employer/individual \
-H "Authorization: Bearer {token}" \
-X "POST" \
-H "Content-Type: application/json" \
-d '{"individual_ids": ["5d0b10a1-a09a-430f-81f1-20be735dc5e9"]}'
```

**Request Body Parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`individual_ids[]` | `array` | true | Array of individual ids.

**Example Response**

```json
{
  "individuals": [
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
}
```

**Response Body**

Name | Type | Description
-----|------|--------------
`individuals` | `array` | An array of the responses.
`individuals[].id` | `string` | A stable Finch `id` (UUID v4) for an individual in the company.
`individuals[].first_name` | `string` | The legal first name of the individual.
`individuals[].middle_name` | `string` | The legal middle name of the individual.
`individuals[].last_name` | `string` | The legal last name of the individual.
`individuals[].business` | `object` | The legal entity associated with the individual.
`individuals[].business.legal_name` | `string` | The legal name of the company.
`individuals[].business.ein` | `string` | The employer identification number.
`individuals[].photo` | `string` | URL to the profile picture of the individual.
`individuals[].emails` | `array` | An array of email objects.
`individuals[].emails[].data` | `string` | The email address associated with the email type.
`individuals[].emails[].type` | `string` | Indicates the type of email. Options: `work`, `personal`.
`individuals[].phone_numbers` | `array` | An array of phone number objects.
`individuals[].phone_numbers[].data` |  `string` | The phone number associated with the email type. Format: `XXXXXXXXXX`
`individuals[].phone_numbers[].type` | `string` | Indicates the type of phone number. Options: `work`, `personal`.
`individuals[].dob` | `string` | The birthday of the individual. ISO 8601 format.
`individuals[].is_active` | `boolean` | `true` if the individual is an active employee or contractor at the company.
`individuals[].residence` | `object` | The residence object.
`individuals[].residence.line1` | `string` | Street address or PO box.
`individuals[].residence.line2` | `string` | Apartment, suite, unit, or building.
`individuals[].residence.city` | `string` | City, district, suburb, town, or village
`individuals[].residence.state` | `string` | 2-digit state code
`individuals[].residence.postal_code` | `string` | 5-digit postal code or zip code
`individuals[].residence.country` | `string` | The name of the country
`individuals[].work_location` | `object` | The work location object.
`individuals[].work_location.line1` | `string` | Street address or PO box.
`individuals[].work_location.line2` | `string` | Apartment, suite, unit, or building.
`individuals[].work_location.city` | `string` | City, district, suburb, town, or village
`individuals[].work_location.state` | `string` | 2-digit state code
`individuals[].work_location.postal_code` | `string` | 5-digit postal code or zip code
