# Providers

**Info**: Return details on all payroll and HR systems.

**URL**: `GET https://api.tryfinch.com/providers`

## Request

**Example request**

```shell
curl https://api.tryfinch.com/providers \
-H "Finch-API-Version: 2020-09-17" \
-X "GET"
```

## Response

**Example response**

```json
[
  {
    "id": "gusto",
    "display_name": "Gusto",
    "products": [
      "company",
      "directory"
    ],
    "icon": "https://finch-logos.s3.us-west-2.amazonaws.com/gustoIcon.png",
    "logo": "https://finch-logos.s3.us-west-2.amazonaws.com/gustoLogo.png",
    "mfa_required": true,
    "primary_color": "#f45d47"
  }
]
```

**Response body**

Name | Type | Description
-----|------|-------------
`[].id` | `string` | The id of the payroll provider used in Connect.
`[].display_name` | `string` | The display name of the payroll provider.
`[].products` | `array` | The list of Finch products supported on this payroll provider.
`[].icon` | `string` | The url to the official icon of the payroll provider.
`[].logo` | `string` | The url to the official logo of the payroll provider.
`[].mfa_required` | `string` | `true` if MFA is required for the provider.
`[].primary_color` | `string` | The hex code for the primary color of the payroll provider.