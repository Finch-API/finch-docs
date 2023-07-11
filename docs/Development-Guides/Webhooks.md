---
stoplight-id: 9d3cec5dd527e
---

# Introduction to Webhooks (coming soon)

Finch offers webhooks to inform you of changes to data models in a push-notification fashion, rather than you having to rely exclusively on pulling data from our API. A webhook URL is a HTTPS endpoint configured by your application to recieve requests from Finch.



## Webhook Registration
Webhook endpoints should use HTTPS and expect to receive POST requests with the following headers:
```json
{
  "Content-Type": "application/json",
  "Webhook-Id": "msg_2SFMDibF3lmRw8DzX4t1JjiEZQl",
  "Webhook-Signature": "v1,8rFENj/WpNAMx+Kh5R1NLQunmpaBx4vOntjJdbGKbvM=",
  "Webhook-Timestamp": "1688737757"
}
```

You can register for webhooks via the developer dashboard or via API

![Screen Shot 2022-08-31 at 4.08.53 PM.png](../../assets/images/addWebhook.png)


Webhooks are available for customers in our Scale tier. Please reach out to a Finch representative for more details on eligibility.

## Webhook Payload Structure
### Common Fields
Each webhook event contains the following fields in the response body:
Field Name | Type | Description
---------|----------|---------
`event_id` | string | A unique identifier for the webhook event.
`company_id` | string<uuid> | Unique Finch id of the company for which data has been updated.
`account_id` | string<uuid> | Unique Finch id of the employer account that was used to make this connection. If an employer completes authorization through Finch multiple times with different accounts or API tokens, those connections will be associated with different account_ids.
`event_type` | string | The type of webhook being delivered.
`data` | object | More information aboute the associated event. The structure of this object will vary per event type.

Finch provides two general types of webhook events: account updates and job completions.

### Account Updates
Account update events contain information about account connections, such as when a connection has been established or when a connection has entered an error state. This type of webhook has the following schema:
Field Name | Type | Description
---------|----------|---------
`event_id` | string | A unique identifier for the webhook event.
`company_id` | string<uuid> | Unique Finch id of the company for which data has been updated.
`account_id` | string<uuid> | Unique Finch id of the employer account that was used to make this connection. If an employer completes authorization through Finch multiple times with different accounts or API tokens, those connections will be associated with different account_ids.
`event_type` | string | Always `account.updated`.
`data.status` | string | The status of the account. This follows our standard connection status schema. Options are `pending`, `processing`, `connected`, `error_permissions`, `error_reauth`, `error_no_acount_setup`.
`data.authentication_method` | string | The method of authentication used to connect this account. Options follow the standard Finch enums for authentication types: `credential`, `api_token`, `oauth`, and `assisted`.

Example:
```json
{
  "event_id": "msg_1srOrx2ZWZBpBUvZwXKQmoEYga2",
  "company_id": "720be419-0293-4d32-a707-32179b0827ab",
  "account_id": "fa872170-b49d-4fb5-aa39-fb1515db0925",
  "event_type": "account.updated",
  "data": {
    "status": "connected"
    "authentication_method": "assisted"
  }
}
```

### Job Completion
Job completion events fire when a job finishes running, whether the final state is a success or an error. This type of webhook has the following schema:
Field Name | Type | Description
---------|----------|---------
`event_id` | string | A unique identifier for the webhook event.
`company_id` | string<uuid> | Unique Finch id of the company for which data has been updated.
`account_id` | string<uuid> | Unique Finch id of the employer account that was used to make this connection. If an employer completes authorization through Finch multiple times with different accounts or API tokens, those connections will be associated with different account_ids.
`event_type` | string | Follows the schema `job.{job_type}.complete`. `{job_type}` can be any valid Finch job type such as `data_sync_all`, `benefit_create`, or `benefit_enroll`.
`data.job_id`| string<uuid> | The id of the job which has completed.
`data.job_url` | string | The url to query the result of the job.

Example:
```json
{
  "event_id": "msg_1srOrx2ZWZBpBUvZwXKQmoEYga2",
  "company_id": "720be419-0293-4d32-a707-32179b0827ab",
  "account_id": "fa872170-b49d-4fb5-aa39-fb1515db0925",
  "event_type": "job.benefit_enroll.completed",
  "data": {
    "job_id": "10f249d5-c974-4ce3-979a-31164323a34f",
    "job_url": "https://api.tryfinch.com/jobs/10f249d5-c974-4ce3-979a-31164323a34f"
  }
}
```


## Webhook Verification

Finch uses HMAC webhook verification, The following are steps you can use to verify a webhook using the verification header:

1. **Extract the signature from the header** using your preferred library. The `Webhook-Signature` header consists of a list of signatures(space delimited) to account for secret rotations. During the verification process, the signature must match at least one signature in the list to be considered valid.
2. **Validate the webhook**. If the signature is not valid reject the webhook. If it is valid, extract the `timestamp` field from the webhook header, and ensure the timestamp is not greater five minutes in the past or future. Using outdated webhooks increases susceptibility to [replay attacks](https://en.wikipedia.org/wiki/Replay_attack).
<!--
title: "Webhook verification example"
lineNumbers: true
highlightLines: [[1,2], [4,5]]
-->
```typescript
const crypto = require('crypto');

const signedContent = `${svix_id}.${svix_timestamp}.${body}`
const SECRET = "5WbX5kEWLlfzsGNjH64I8lOOqUB6e8FH";

// Need to base64 decode the secret
const secretBytes = new Buffer(SECRET, "base64");
const signature = crypto
  .createHmac('sha256', secretBytes)
  .update(signedContent)
  .digest('base64');
```

## Testing Webhooks

You can send a test request to any webhook through the developer dashboard.

![Screen Shot 2022-08-31 at 4.18.15 PM.png](../../assets/images/selectEndpoints.png)


The test webhook will include the same structure as data update webhooks, with the `event_type` set to `test`

## Retries

Upon failure, Finch will retry according to the following schedule with exponential backoff:

- Immediately
- 5 seconds
- 5 minutes
- 30 minutes
- 2 hours
- 5 hours
- 10 hours
- 10 hours (in addition to the previous)

## Best Practices for Handling Webhooks

**Responding to Webhooks**

In order to prevent unnecessary retries, we recommend receiving webhook events and processing the events in separate processes. Upon receiving the event, you should immediately respond with a `200` indicating that the event was successfully delivered.

**Event delivery and ordering**

- It is possible that you may occasionally receive the same webhook event more than once. We recommend setting up idempotent event processing by using the `webhook_id`.
- Finch does not guarantee delivery of events in the order they happen. For example, you may receive an `update` event for an `individual` before a `created` event. You should also use the Finch API to occasionally fetch any missing data. For example, you can fetch an individual if you happen to receive an `update` event first.

**Event Mapping**

- Webhooks are delivered with a `company_id` and an `account_id` corresponding to the company for which the data changed. You should retrieve these ids from Finch in order to map webhooks updates to the company/account pair the data belongs to. A simple workflow for this is to call the `/introspect` endpoint after exchanging an auth code for an access token via the `/auth/token` endpoint. The `/introspect` endpoint contains the `company_id` and `account_id` for the connection a token is associated with. You can save these ids in your system to map incoming webhook events to companies.