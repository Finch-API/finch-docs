# Rate Limits

Finch will return a rate limit error with the HTTP status code 429 when the request rate limit for an application, access token, or an individual IP address has been exceeded.

Finch's rate limits work on a per-endpoint basis for applications, and we refer to each distinct endpoint as a unique `product`. Rate limits are summed on a rolling 60-second basis for each unique `product`. This is commonly referred to as a Sliding or Rolling Window rate limit.

<!-- theme: info -->
> **Access Token rate limits** Finch previously enforced rate limits at the access token level but this is not longer the case as of August 2023.

You can think of a `product` rate limit like a "bucket". Therefore, when a request is made to a `product` (which corresponds directly to an API endpoint), a single gallon of water is added to that endpoint’s bucket, thus starting that bucket's 60-second time-to-live (TTL) timer.

After the product's rate limit is reset after 60 seconds, the first request to that `product` starts the 60-second TTL again.

***

## Application Rate Limits

A Finch application has its own rate limits and all access tokens associated with the application will be subject to the application's rate limits. For application-level rate limits, each `product` manages a bucket simultaneously counting all requests across all access tokens created by that application. Multiple access tokens can be created from a single Finch application as more employers are connected. (A Finch application corresponds to a unique `client_id`. You may have several `client_id`s if you use a development or sandbox application in addition to production).

Product | Max requests initiated per minute
-------|-------------
`company` | 20
`directory` | 20
`individual` | 20
`employment` | 20
`payment` | 12
`pay-statement` | 12

If an application rate limit is encountered, it will contain the `finch_code`: [finch_application_rl](/docs/Development-Guides/Errors/Error-Types.md#error-types-1) in the response body.

```json
// HTTP 429 response body for application rate limit exceeded
{
    "statusCode": 429,
    "status": 429,
    "code”: 429,
    "message": "Too many requests for token",
    "name": "rate_limit_exceeded_error",
    "finch_code": "finch_application_rl"
}
```

## IP Address Rate Limits

Finch also enforces individual IP Address rate limits. An IP address is a unique address that identifies a device on the internet or a local network. If the number of `max requests` are sent from the same IP Address within the `duration` time set, a `penalty` is enforced. No more requests are allowed once the penalty is enforced. Once the penalty duration is complete, requests will be accepted again.

Type | Max requests | Duration | Penalty
-------|-------------|-------|-------------
`API` | 1000 | 5 minutes | 60 minutes

If an IP Address rate limit is encountered, it will contain the `finch_code`: [finch_api_ip_rl](/docs/Development-Guides/Errors/Error-Types.md#error-types-1) in the response body.

```json
// HTTP 429 response body for application rate limit exceeded
{
    "statusCode": 429,
    "status": 429,
    "code”: 429,
    "message": "Too many requests for token",
    "name": "rate_limit_exceeded_error",
    "finch_code": "finch_api_ip_rl"
}
```

***

## Handling Rate Limit Errors

If you are experiencing rate limits, there are several ways to minimize the risk of hitting rate limits highlighted in our [Handling Rate Limit Errors](/docs/Best-Practices/Handling-Rate-Limit-Errors.md) Best Practices guide.
