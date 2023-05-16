# Rate Limits

Finch will return a rate limit error with the HTTP status code 429 when the request rate limit for an application, access token, or an individual IP address has been exceeded.

Finch's rate limits work on a per-product basis for both applications and access tokens. Rate limits are summed on a rolling 60-second basis for each unique `product`. This is commonly referred to as a Sliding or Rolling Window rate limit.

You can think of a `product` rate limit like a "bucket". Therefore, when a request is made to a `product` (which correspond directly to an API endpoint), a single gallon of water is added to that endpoint’s bucket, thus starting that bucket's 60-second Time-To-Live (TTL) timer.

After the product's rate limit is reset after 60 seconds, the first request to that `product` starts the 60-second Time-To-Live (TTL) timer again.

***

## Access Token Rate Limits

For access token rate limits, each `product` manages its own "bucket" with its own 60-second Time-To-Live (TTL) timer. The first request by an access token to a new product endpoint starts the timer for only that product's bucket, and rate limits reset only for that product endpoint after the 60-second period.

Product | Max requests initiated per minute
-------|-------------
`company` | 4
`directory` | 4
`individual` | 4
`employment` | 4
`payment` | 2
`pay-statement` | 2

If an access token rate limit is encountered, it will contain the `finch_code`: [finch_token_rl](/docs/Development-Guides/Errors/Error-Types.md#error-types-1) in the response body.

```json
// HTTP 429 response body for access token rate limit exceeded
{
    “statusCode”: 429,
    “status”: 429,
    “code”: 429,
    “message”: “Too many requests for token”,
    “name”: “rate_limit_exceeded_error”,
    “finch_code”: “finch_token_rl”
}
```

## Application Rate Limits

Similarly, multiple access tokens can be created from a single Finch application as more employers are connected. A Finch application has its own rate limits separate from the access token rate limits. You can think of an application like a development environment or application stage. Finch will assign three types of applications: `sandbox`, `development`, and `production`. Each will have their own `client_id` which represents the application.

For application-level rate limits, each `product` manages another “larger” bucket simultaneously counting all requests across all access tokens created by that application. Each bucket is still scoped to a product endpoint like with access tokens; the only difference is that the application-level bucket is larger.

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
