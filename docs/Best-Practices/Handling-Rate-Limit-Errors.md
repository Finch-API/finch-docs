# Handling Rate Limit Errors

If you are experiencing rate limits, there are several ways to minimize the risk of hitting rate limits.

## Implement batched requests

Minimize the risk of hitting rate limits by batching individual requests into a single request. Several of Finch’s endpoints are “batch” endpoints ([/individual](https://developer.tryfinch.com/docs/reference/9d6c83b09e205-individual), [/employment](https://developer.tryfinch.com/docs/reference/1ba5cdec4c979-employment), and [/pay-statment](https://developer.tryfinch.com/docs/reference/d5fd02c41e83a-pay-statement)). These batch endpoints allow you to send a list of IDs in a single request and receive a response with an array of objects matching the IDs sent.

There is no limit to the amount of IDs that can be sent in a single request. Determine your optimal batch size for your use case when making batch requests to Finch APIs. By passing all the required IDs in a single batch request optimizes your API usage and minimizes the risk of hitting rate limits.

A batch request example is as follows:

```json
{
  "requests": [
    {
      "individual_id": "772b3c4f-d764-433d-bd69-ff8bbac33ffe"
    },
    {
      "individual_id": "a7a77065-0f68-418d-a85a-da24fb2139b7"
    },
    ...
    {
      "individual_id": "84364585-c2ce-40aa-bcc0-666ac9577315"
    }
  ]
}
```

## Implement a Rate Limiter Enforcer

Suppose the rate limit for a particular Finch `product` is 20 requests per minute. You can use the following JavaScript code example to enforce this rate limit quota in your application. The `RateLimiter` class implements a simple rate limiter that allows you to make requests up to the specified rate limit (20 requests per minute) and pauses further requests until the rate limit resets . As an alternative, you can implement a “back off and retry” strategy. The `request` method of the rate limiter is used to make API requests to Finch's endpoints, ensuring that you stay within the rate limit "bucket" quota for that endpoint. Simply initialize a new `RateLimiter` class for each Finch `product` endpoint being called.

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

## Scenarios

Still confused about how rate limits work? Here a couple of theoretical examples on how rate limits work for both access tokens and applications.

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
