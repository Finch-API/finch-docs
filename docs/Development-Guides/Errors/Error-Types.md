# Error Types

In case of an error, Finch's API will respond with an appropriate HTTP status code and error body.

Finch uses HTTP status codes to indicate the success or failure of an API request. 

- `2xx`: indicates success
- `4xx`: indicates developer or user-related errors
- `5xx`: indicates Finch-related issues

## Error Schema
Name | Type | Description
-----|------|------------
`code` | `integer` | The HTTP status code of the response.
`name` | `string` | An identifier, safe for programmatic use, describing the broad error category.
`finch_code` | `string` | An optional identifier describing the error in more detail. It is safe for programmatic use.
`message` | `string` | A developer friendly message explaining the error.

## Error Types
Name | Finch Code | Code | Description
-----|------------|------|------------
`invalid_grant_error` | | 400 | The authorization code is invalid.
`invalid_token_error` | | 401 | The `access_token` is incorrect.
`invalid_request_error` | | 401 | The request does not match the docs. Example: the request is missing a query parameter.
`authentication_error` | `reauthenticate_user` | 401 | The user will need to reconnect their employment system. See more here.
`invalid_client_error` | | 401 | The provided application credentials were incorrect. Relevant to the `/auth/token` endpoint.
`unauthorized_request_error` | | 401 | The `access_token` is missing from the header.
`insufficient_scope_error` | | 403 | The application credentials have insufficient permissions to access the requested product.
`not_found_error` |`item_not_found`| 404 | The requested resource does not exist. Relevant to the `/employer/benefits/*` endpoints.
`not_found_error` |`benefit_not_found`| 404 | The requested benefit does not exist. Relevant to the `/employer/benefits/*` endpoints.
`not_found_error` |`individual_not_found`| 404 | The requested individual does not exist. Relevant to the `/employer/benefits/*` endpoints.
`unprocessable_request_error` |`unsupported_parameters`| 422 | Parameters provided are not supported by the provider or benefit. Relevant to the `/employer/benefits/*` endpoints.
`unprocessable_request_error` |`invalid_employee_enrollment`| 422 | The employee is unable to be enrolled in a benefit due specific to constraints on the provider side. Relevant to the `/employer/benefits/*` endpoints.
`server_error` | | 500 | The server experienced an unexpected error.