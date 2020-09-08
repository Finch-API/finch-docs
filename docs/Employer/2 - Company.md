# Company

**Info**: Read basic company data

**URL**: `GET https://api.tryfinch.com/v1.0/employer/company`

**Product**: `company`

**Response Body**

Name | Type | Description
-----|------|-------------
`id` | `string` | A stable Finch `id` (UUID v4) for the company.
`legal_name` | `string` | The legal name of the company.
`entity_type` | `string` | The tax payer type of the company. Options: `llc`, `s_corporation`, `c_corporation`, `b_corporation`, `sole_proprietor`, `non_profit`, `partnership`, and `cooperative`.
`primary_email` | `string` | The email of the main administrator on the account.
`primary_phone_number` | `string` | The phone number of the main administrator on the account. Format: `XXXXXXXXXX`
`ein` | `string` | The employer identification number.
`logo` | `string` | The picture logo of the company.
`locations` | `array` | The array of company locations.
`locations[].line1` | `string` | Street address or PO box.
`locations[].line2` | `string` | Apartment, suite, unit, or building.
`locations[].city` | `string` | City, district, suburb, town, or village
`locations[].state` | `string` | 2-digit state code
`locations[].postal_code` | `string` | 5-digit postal code or zip code
`locations[].country` | `string` | The name of the country
`bank_accounts[]` | `array` | An array of bank account objects associated with the payroll/HRIS system.
`bank_accounts[].routing_number` | `string` | A nine-digit code that's based on the U.S. Bank location where your account was opened.
`bank_accounts[].account_name` | `string` | The name of the bank associated in the payroll/HRIS system.
`bank_accounts[].institution_name` | `string` | Name of the banking institution.
`bank_accounts[].account_type` | `string` | The type of bank account. Options: `checking` and `savings`.
`bank_accounts[].account_number` | `string` | 10-12 digit number to specify the bank account

**Example Request**

```curl
curl https://api.tryfinch.com/v1.0/employer/company \
-H "Authorization: Bearer {token}" \
-X "GET"
```

**Example Response**

```json
{
  "id": "514aa2b7-898f-4ce7-bc05-c2fe993713e8",
  "legal_name": "Stark Industries, Inc.",
  "entity_type": "C-Corporation",
  "ein": "12-3456789",
  "logo": "https://www.example.com/logo400x400.png",
  "primary_email": "payroll@starkindustries.com",
  "primary_phone_number": "4155555555",
  "locations": [
    {
      "line1": "200 Park Ave",
      "line2": null,
      "city": "New York",
      "state": "NY",
      "postal_code": "10166",
      "country": "US"
    }
  ],
  "bank_accounts": [{
    "routing_number": "122101706",
    "account_name": "Aamir",
    "institution_name": "BANK OF AMERICA, N.A.",
    "account_type": "checking",
    "account_number": "19879919"
  }]
}
```