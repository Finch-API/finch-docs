# Handling API Responses

## Finch IDs

All IDs (UUIDs) returned by Finch endpoints are fixed for the same underlying employment system account. They will not change even if you have multiple `access_token`s for the company, a different payroll admin from a company logs in, etc.

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