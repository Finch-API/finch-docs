# Reauthentication

Over time, employers need to refresh authentication information. This can happen if the admin changes a password, if MFA requirements change, or if the login becomes locked. Developers can use the [`GET /introspect`](../../reference/employer/openapi.yaml/paths/~1introspect) endpoint to determine the payroll provider associated with the `access_token` and prompt the user to re-authenticate.

***

## `/introspect`

**Example request**
```curl
curl https://api.tryfinch.com/introspect \
-H "Finch-API-Version: 2020-09-17" \
-H "Authorization: Bearer {token}"
-X "GET"
```

**Example response**
```json
{
  "client_id": "25ea8bd8-f76b-41f9-96e3-1e6162021c50",
  "products": [
    "company",
    "directory"
  ],
  "username": "jeremyzhang",
  "payroll_provider_id": "gusto"
}
```

***

## Finch Connect reauthentication

After determining the `payroll_provider` associated with the `access_token`, you can follow the authorization process to reauthenticate an admin and to retrieve and store the new `access_token`.

1. [Redirect to Connect](3-Authorization.md#redirect-to-connect) with the specified `payroll_provider`
2. [Exchange the `auth_code`](3-Authorization.md#auth-code-exchange) and store the new `access_token`