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
-d '{"requests": [{ "individual_id": "f3ddb1f4-dfa4-4e1d-bfed-bdfd0645b613"]}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`requests` | `array` | true | The array of batch requests`
`requests[].individual_ids` | `array` | true | A stable Finch `id` (UUID v4) for an individual in the company.

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
            "data": "4077313626",
            "type": "personal"
          }
        ],
        "dob": "1995-08-15",
        "residence": {
          "line1": "628 Allentown Ave",
          "line2": "Apt C",
          "city": "Palo Alto",
          "state": "CA",
          "postal_code": "94301",
          "country": "US"
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
`business` | `object` | The legal entity associated with the individual.
`business.legal_name` | `string` | The legal name of the company.
`business.ein` | `string` | The employer identification number.
`emails` | `array` | An array of email objects.
`emails[].data` | `string` | The email address associated with the email type.
`emails[].type` | `string` | Indicates the type of email. Options: `work`, `personal`.
`phone_numbers` | `array` | An array of phone number objects.
`phone_numbers[].data` |  `string` | The phone number associated with the email type. Format: `XXXXXXXXXX`
`phone_numbers[].type` | `string` | Indicates the type of phone number. Options: `work`, `personal`.
`dob` | `string` | The birthday of the individual. ISO 8601 format.
`residence` | `object` | The residence object.
`residence.line1` | `string` | Street address or PO box.
`residence.line2` | `string` | Apartment, suite, unit, or building.
`residence.city` | `string` | City, district, suburb, town, or village
`residence.state` | `string` | 2-digit state code
`residence.postal_code` | `string` | 5-digit postal code or zip code
`residence.country` | `string` | The name of the country
