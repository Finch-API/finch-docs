# Introspect

**Info**: Read account information associated with an `access_token`.

**URL**: `GET https://api.tryfinch.com/instrospect`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/introspect \
-H "Finch-API-Version: 2020-09-17" \
-H "Authorization: Bearer {token}" \
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
  "username": "janedoe@work.example.com",
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