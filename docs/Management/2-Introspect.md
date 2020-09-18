# Introspect

**Info**: Read account information associated with an `access_token`.

**URL**: `GET https://api.tryfinch.com/v1.0/instrospect`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/v1.0/introspect \
-H "Authorization: Bearer {token}" \
-H "Finch-Version: 2020-09-17" \
-X "GET"
```

## Response

**Example response**

```json
{
  "client_id": "25ea8bd8-f76b-41f9-96e3-1e6162021c50",
  "products": [
    "company",
    "directory"
  ],
  "username": "jeremy@tryfinch.com",
  "payroll_provider_id": "gusto"
}
```

** Response body**


Name | Type | Description
-----|------|-------------
`client_id` | `string` | The client id of the application associated with the `access_token`.
`products` | `array` | An array of the authorized products associated with the `access_token`.
`username` | `string` | The account username used for login associated with the `access_token`
`payroll_provider_id` | `string` | The payroll provider associated with the `access_token`