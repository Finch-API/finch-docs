# Company

**Info**: Read basic company data

**URL**: `GET https://api.tryfinch.com/employer/company`

**Product**: `company`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/employer/company \
-H "Authorization: Bearer {token}" \
-H "Finch-API-Version: 2020-09-17" \
-X "GET"
```

***

## Response

**Example response**

```json
{
  "id": "514aa2b7-898f-4ce7-bc05-c2fe993713e8",
  "legal_name": "Profound Platform, Inc.",
  "entity": {
    "type": "corporation",
    "subtype": "s_corporation"
  }
  "ein": "12-3456789",
  "primary_email": "founders@joinprofound.com",
  "primary_phone_number": "1234567890",
  "departments": [
    {
      "name": "Engineering",
      "parent": null,
    },
    {
      "name": "Platform",
      "parent": {
        "name": "Engineering",
      },
    },
  ],
  "locations": [
    {
      "line1": "628 Forest Ave",
      "line2": "Apt A",
      "city": "Palo Alto",
      "state": "NY",
      "postal_code": "94301",
      "country": "US"
    }
  ],
  "accounts": [{
    "routing_number": "122104726",
    "account_name": "CHECKING ACCOUNT",
    "institution_name": "BANK OF AMERICA, N.A.",
    "account_type": "checking",
    "account_number": "39472919"
  }]
}
```

**Response body**

Name | Type | Description
-----|------|-------------
`id` | `string` | A stable Finch `id` (UUID v4) for the company.
`legal_name` | `string` | The legal name of the company.
`entity` | `object` | The entity type object.
`entity.type` | `string` | The tax payer type of the company. Options: `llc`, `corporation`, `sole_proprietor`, `non_profit`, `partnership`, and `cooperative`.
`entity.subtype` | `string` | The tax payer subtype of the company. Options: `s_corporation`, `c_corporation`, and `b_corporation`.
`primary_email` | `string` | The email of the main administrator on the account.
`primary_phone_number` | `string` | The phone number of the main administrator on the account. Format: `XXXXXXXXXX`
`ein` | `string` | The employer identification number.
`departments` | `array` | The array of company departments.
`departments[].name` | `string` | The department name.
`departments[].parent` | `object` | The parent department, if present.
`departments[].parent.name` | `string` | The parent department's name.
`locations` | `array` | The array of company locations.
`locations[].line1` | `string` | Street address or PO box.
`locations[].line2` | `string` | Apartment, suite, unit, or building.
`locations[].city` | `string` | City, district, suburb, town, or village.
`locations[].state` | `string` | The state  code.
`locations[].postal_code` | `string` | The postal code or zip code.
`locations[].country` | `string` | The 2-letter ISO 3166 country code.
`account[]` | `array` | An array of bank account objects associated with the payroll/HRIS system.
`accounts[].routing_number` | `string` | A nine-digit code that's based on the U.S. Bank location where your account was opened.
`accounts[].account_name` | `string` | The name of the bank associated in the payroll/HRIS system.
`accounts[].institution_name` | `string` | Name of the banking institution.
`accounts[].account_type` | `string` | The type of bank account. Options: `checking` and `savings`.
`accounts[].account_number` | `string` | 10-12 digit number to specify the bank account