# Headers

Finch supports additional HTTP headers in both requests and responses. Our headers are prefixed with `Finch-`.

***

## Request headers

Finch uses HTTP request headers for authorization and configuration of API responses.

Header | Description
-------|-------------
`Authorization` | Bearer authorization header, which is formed by concatenating the word “Bearer” with the access token, separated by a space.

***

## Response headers

Finch’s additional response headers provide additional information about the data contained in responses.

Header | Description
-------|--------------
`Finch-Request-Id` |	Each response from Finch's API has a unique request identifier. If you need to contact us about a specific request, providing the request identifier will ensure the fastest possible resolution.


