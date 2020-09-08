# Errors

Finch uses HTTP status codes to indicate the success or failure of API requests. This includes— 
* `2XX`: indicates success
* `4XX`: indicates an invalid request (e.g. a required parameter is missing from the request body)
* `5XX`: indicates Finch-related issues (e.g. payroll provider is not responding)

**Error response**

All Finch errors contain the following fields-

Name | Type | Description
-----|------|------------
`error` | `string` | A string describing the error type
`message` | `string` | A message explaining the error

**Error types**

Error | Status | Description
------|--------|--------------
`invalid_grant_error` | 400 | The authorization code is invalid.
`invalid_token_error` | 401 | The `access_token` is incorrect.
`authentication_error` | 401 | The payroll and HR system indicated that the admin's password or MFA information has changed. They will need to [reauthenticate via Finch Connect](./4-Reauthentication.md).
`invalid_client_error` | 401 | The provided application credentials were incorrect
`unauthorized_request_error` | 401 | The application does not have access to this product.
`insufficient_scope_error` | 403 | The application credentials have insufficient permissions to access the requested product.
`resource_not_found_error` | 404 | The requested resource does not exist.
`server_error` | 500 | The server experienced an unexpected error.
