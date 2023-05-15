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

## Handling Rate Limit Errors

Minimize the risk of hitting rate limits by batching individual requests into a single request. Several of Finch’s endpoints are “batch” endpoints (`individual`, `employment`, `pay-statement`). This means that several IDs can be sent in a single request. Finch will correspondingly return a single response with an array of objects equal to the IDs sent. Determine your optimal batch size for your use case when making batch requests to Finch APIs. Pass all the required IDs in a single batch request to optimize API usage and minimize the risk of hitting rate limits. A batch request example is as follows:

```json
{
  "requests": [
    {
      "individual_id": "772b3c4f-d764-433d-bd69-ff8bbac33ffe"
    },
    {
      "individual_id": "84364585-c2ce-40aa-bcc0-666ac9577315"
    }
  ]
}
```

## Scenarios

### Scenario 1: Hitting access token level rate limits

In this scenario, let's focus on a single access token (Token A) and assume you are making API requests to any of the the `company`, `directory`, `individual`, `employment`, `payment`, and `pay-statement` endpoints. When a request  is sent to an endpoint, a single gallon of water is added to the endpoint’s bucket each time. The first requests starts that bucket’s 60-second Time-To-Live (TTL) timer.

1. Token A makes 4 requests to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint within a minute pouring 4 gallons of water into the “directory” bucket.
    Bucket | Capacity
    -------|-------------
    `company` | 0/4
    `directory` | 4/4 (FULL)
    `individual` | 0/4
    `employment` | 0/4
    `payment` | 0/2
    `pay-statement` | 0/2
1. Token A makes 2 requests to the [/employer/payment](https://developer.tryfinch.com/docs/reference/b811fdc2542ca-payment) endpoint within the same minute pouring 2 gallons of water into the `payment` bucket.
    Bucket | Capacity
    -------|-------------
    `company` | 0/4
    `directory` | 4/4 (FULL)
    `individual` | 0/4
    `employment` | 0/4
    `payment` | 2/2 (FULL)
    `pay-statement` | 0/2
1. At this point, no rate limits have been encountered yet.
1. Within the same minute, Token A makes 1 request to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint then 1 request to the [/employer/pay-statement](https://developer.tryfinch.com/docs/reference/d5fd02c41e83a-pay-statement) endpoint.
    Bucket | Capacity
    -------|-------------
    `company` | 0/4
    `directory` | 4/4 (FULL)
    `individual` | 0/4
    `employment` | 0/4
    `payment` | 2/2 (FULL)
    `pay-statement` | 1/2
1. The request to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint will fail and receive a 429 rate limit error, but the request to the [/employer/pay-statement](https://developer.tryfinch.com/docs/reference/d5fd02c41e83a-pay-statement) endpoint will succeed. This is because the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint bucket is already full (4/4 gallons), but the [/employer/pay-statement](https://developer.tryfinch.com/docs/reference/d5fd02c41e83a-pay-statement) endpoint bucket is not full so it adds another gallon (1/2 gallons).
1. Assume 60 seconds passes. All endpoint buckets reset.
    Bucket | Capacity
    -------|-------------
    `company` | 0/4
    `directory` | 0/4
    `individual` | 0/4
    `employment` | 0/4
    `payment` | 0/2
    `pay-statement` | 0/2

### Scenario 2: Hitting application level rate limits

In this scenario, let's assume your application has six access tokens (Token A, Token B, Token C, Token D, Token E, Token F) and you are making API requests to any of the the `company`, `directory`, `individual`, `employment`, `payment`, and `pay-statement` endpoints.  Using the same bucket analogy, each application-level product endpoint manages another “larger” bucket counting all requests across all access tokens  (Token A, Token B, Token C, Token D, Token E, Token F).

1. Token A makes 4 requests to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint, 3 requests to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint, and 2 requests to the [/employer/payment](https://developer.tryfinch.com/docs/reference/b811fdc2542ca-payment) endpoint within a minute.
    - Access Token A rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 4/4 (FULL)
        `directory` | 3/4
        `individual` | 0/4
        `employment` | 0/4
        `payment` | 2/2 (FULL)
        `pay-statement` | 0/2
    - Application-level rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 4/20
        `directory` | 3/20
        `individual` | 0/20
        `employment` | 0/20
        `payment` | 2/12
        `pay-statement` | 0/12
1. Token B makes 5 requests to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint, 3 requests to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint, and 2 requests to the [/employer/payment](https://developer.tryfinch.com/docs/reference/b811fdc2542ca-payment) endpoint within the same minute. Token B’s first 4 requests to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint will succeed, but the 5th will fail and return a 429 rate limit error. Note: Only succeeded requests count towards the application level rate limits.
    - Access Token B rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 4/4 (FULL)
        `directory` | 3/4
        `individual` | 0/4
        `employment` | 0/4
        `payment` | 2/2 (FULL)
        `pay-statement` | 0/2
    - Application-level rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 8/20
        `directory` | 6/20
        `individual` | 0/20
        `employment` | 0/20
        `payment` | 4/12
        `pay-statement` | 0/12
1. Token C, D, and E repeats the same process as Token B making 5 requests to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint, 3 requests to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint, and 2 requests to the [/employer/payment](https://developer.tryfinch.com/docs/reference/b811fdc2542ca-payment) endpoint all within the same minute. Similarly, every 5th request to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint for each token fails and returns a 429 rate limit error.
    - Access Token C, D, and E individual rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 4/4 (FULL)
        `directory` | 3/4
        `individual` | 0/4
        `employment` | 0/4
        `payment` | 2/2 (FULL)
        `pay-statement` | 0/2
    - Application-level rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 20/20 (FULL)
        `directory` | 15/20
        `individual` | 0/20
        `employment` | 0/20
        `payment` | 12/12 (FULL)
        `pay-statement` | 0/12
1. If Token F makes 1 request to the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint and 1 request to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint. The `company` request will fail and return a 429 rate limit error even though Token F has not maxed out its access-token specific `company` bucket. That is because the application-level bucket is now full. No requests from any token will succeed calling the [/employer/company](https://developer.tryfinch.com/docs/reference/33162be1eed72-company) endpoint until the `company` bucket’s 60-second Time-To-Live (TTL) timer resets. However, Token F’s request to the [/employer/directory](https://developer.tryfinch.com/docs/reference/12419c085fc0e-directory) endpoint will succeed because its access-token specific `directory` bucket is not full AND the application-level `directory` bucket is not full either.
    - Access Token F rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 1/4
        `directory` | 1/4
        `individual` | 0/4
        `employment` | 0/4
        `payment` | 0/2
        `pay-statement` | 0/2
    - Application-level rate limits
        Bucket | Capacity
        -------|-------------
        `company` | 20/20 (FULL)
        `directory` | 16/20
        `individual` | 0/20
        `employment` | 0/20
        `payment` | 12/12 (FULL)
        `pay-statement` | 0/12

## Code Enforcement Example

Suppose the rate limit for a particular Finch `product` is 20 requests per minute. You can use the following JavaScript code example to enforce this rate limit quota in your application. The `RateLimiter` class implements a simple rate limiter that allows you to make requests up to the specified rate limit (20 requests per minute) and pauses further requests until the rate limit resets. The `request` method of the rate limiter is used to make API requests to Finch's endpoints, ensuring that you stay within the rate limit "bucket" quota for that endpoint. Simply initialize a new `RateLimiter` class for each Finch `product` endpoint being called.

```js
class RateLimiter {
  constructor(limit) {
    this.limit = limit;
    this.requests = [];
  }

  async request(fn) {
    const now = Date.now();
    this.requests = this.requests.filter((timestamp) => now - timestamp < 60000);

    if (this.requests.length >= this.limit) {
      const delay = this.requests[0] + 60000 - now;
      await new Promise((resolve) => setTimeout(resolve, delay));
      this.requests.shift();
    }

    this.requests.push(now);
    return fn();
  }
}

const directoryRateLimiter = new RateLimiter(20); // 20 requests per minute
const url = 'https://api.tryfinch.com/employer/directory'; // Replace with the desired endpoint
const accessToken = '<your_access_token>';

const fetchIndividualData = (
) =>
  fetch(url, {
    method: 'GET',
    headers: {
      Authorization: `Bearer ${accessToken}`,
      'Content-Type': 'application/json',
    },
  });

// Use the rate limiter to make API requests
directoryRateLimiter
  .request(fetchIndividualData)
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error('Error:', error));
```
