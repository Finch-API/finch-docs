# Errors

Finch uses HTTP status codes to indicate the success or failure of API requests. This includes— 
* `2XX`: indicates success
* `4XX`: indicates an invalid request (e.g. a required parameter is missing from the request body)
* `5XX`: indicates Finch-related issues (e.g. payroll provider is not responding)

**Error response**

All Finch errors contain the following fields-

Name | Type | Description
-----|------|------------
`code` | `integer` | The status code of the request
`name` | `string` | An identifier describing the broad error type
`finch_code` | `string` | A descriptive identifier for the error that occurred
`message` | `string` | A message explaining the error

**Error types**

Name | Finch Code | Code | Description
------|--------|--------------
`invalid_grant_error` || 400 | The authorization code is invalid.
`invalid_token_error` || 401 | The `access_token` is incorrect.
`invalid_request_error` || 401 | The request does not match the docs. Example: the request is missing a query parameter.
`authentication_error` | `reauthenticate_user` | 401 | The payroll and HR system indicated that the admin's password or MFA information has changed. They will need to [reauthenticate via Finch Connect](./4-Reauthentication.md).
`authentication_error` | `no_valid_accounts` | 401 | The credentials provide do not have access to valid payroll admin accounts.
`authentication_error` | `locked_out` | 401 | The account associated with the credentials provided is locked.
`invalid_client_error` || 401 | The provided application credentials were incorrect
`unauthorized_request_error` || 401 | The `access_token` is missing from the header.
`invalid_client_error` || 401 | The application does not have access to this product.
`insufficient_scope_error` || 403 | The application credentials have insufficient permissions to access the requested product.
`not_found_error` |`item_not_found`| 404 | The requested resource does not exist.
`not_found_error` |`benefit_not_found`| 404 | The requested benefit does not exist.
`not_found_error` |`individual_not_found`| 404 | The requested individual does not exist.
`unprocessable_request_error` |`unsupported_parameters`| 422 | Parameters provided are not supported by the provider or benefit.
`unprocessable_request_error` |`invalid_employee_enrollment`| 422 | The employee is unable to be enrolled in a benefit due specific to constraints on the provider side.
`server_error` || 500 | The server experienced an unexpected error.

