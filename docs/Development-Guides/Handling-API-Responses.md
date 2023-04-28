# Handling API Responses

## Finch IDs

Finch IDs (UUIDs) remain constant for all company connections that utilize the same authentication method. However, if you have multiple access tokens for a company connection, and they were generated via different authentication methods, the Finch IDs *may not* be consistent across these tokens. For instance, if an employer first authenticates with credentials (username/password), and then later authenticates again using an API token auth method, the two access tokens generated from these authentications *may* have different Finch IDs. This is because the underyling employment system IDs used to identify an employee or payment may be different depending on the authentication method, and Finch maps its UUIDs to those underlying employment system IDs. You should keep this in mind when incorporating Finch integrations into your application.

## Null Values

API responses can return `null` values for some fields. This can happen for a few different reasons—

1. The employment system does not support the field.
2. The field is supported by the employment system but the data has not been filled in by the payroll administrator of a company.
3. Finch was not able to infer a reasonable value (for example, the categorization of a tax).

<!-- theme: success -->
> Ensure your Finch integration is resilient to `null` values.

## 202 Response Codes

In some cases, requests to the Finch API may return a [`202 accepted`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/202) status code. This is often the case for async operations, such as:
* Requests for connections using [Assisted Connect](docs/Product-Guides/Assisted-Connect-Flow.md), including [Assisted Benefits](../Product-Guides/Benefits-API.md#handling-assisted-benefits-api-responses)
* Requests for [pay statements](docs/Development-Guides/Data-Syncs.md#pay-statements) which exist but have not yet been fetched
* Requests for connections utilizing [authentication fallback](docs/Product-Guides/Automated-Connect-Flow.md#authentication-fallback)

Your implementation should be built to account for these 202 responses.