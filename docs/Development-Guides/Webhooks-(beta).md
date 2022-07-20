---
stoplight-id: 9d3cec5dd527e
---

# Introduction to Webhooks (Beta)

Finch offers webhooks to inform you of changes to data models in a push-notification fashion, rather than you having to rely exclusively on pulling data from our API. A webhook url is an HTTPS endpoint configured by your application to recieve requests from Finch.



## Webhook Registration
Webhooks should use HTTPS and expect to receive POST requests with the following headers:

Header | Content
---------|----------|
 `Content-Type` | `application/json` |
 `Finch-Signature` | `<token>` |

You can register for webhooks via the developer dashboard. 

[Screenshot]

Webhooks are available starting at Scale tier. Please reach out to a Finch representative for more details.

## Webhook Payload Structure

### Data Updates

Finch currently supports webhook updates for creation, updates, and deletion of items for the following data endpoints:

- `company`
- `directory`
- `individual`
- `employment`
- `payment`
- `pay-statement`

The body of each webhook has the following schema:

Field Name | Type | Description
---------|----------|---------
 `webhook_id` | uuid formatted string | A unique identifier for the webhook event
 `company_id` | uuid formatted string | Unique Finch id of the company for which data has been updated
 `webhook_type` | string | The type of webhook being delivered. Options are  `company`, `directory`, `individual`, `employment`, `payment`, `pay-statement`,  `management`
 `event_type` | string | The type of event being delivered for this webhook type.<br />`initial_sync` if this update is the result of a new connection via Finch Connect.<br />`update_sync` if this update is the result of a Finch data sync<br />`authentication_error` to indicate connection issues for management webhooks
 `data` | array | The payload of change data
 `data[].change_type` | string | The type of change for the object. Options are `created`, `updated`, `deleted`

Beyond the `change_type` the objects in the data array will differ slightly based on the `webhook_type`. Below are examples for each:

**company**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "initial_sync",
  "webhook_type": "company",
  "data": [
    {
      "change_type": "updated"
    }
  ]
}
```
**directory**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "initial_sync",
  "webhook_type": "directory",
  "data": [
    {
      "change_type": "created",
      "individual_id": uuid
    },
    ...
  ]
}
```
**individual**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "update_sync",
  "webhook_type": "individual",
  "data": [
    {
      "change_type": "deleted",
      "individual_id": uuid
      ...
    },
    ...
  ]
}
```
**employment**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "update_sync",
  "webhook_type": "employment"
  "data": [
    {
      "change_type": "updated",
      "individual_id": uuid,
    },
    ...
  ]
}
```
**payment**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "update_sync",
  "webhook_type": "payment",
  "data": [
    {
      "change_type": "created",
      "payment_id": uuid,
      "start_date": "07-07-2022",
      "end_date": "07-21-2022",
    },
    ...
  ]
}
```
**pay-statement**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "event_type": "update_sync",
  "webhook_type": "payment",
  "data": [
    {
      "change_type": "created",
      "payment_id": uuid,
      "start_date": "07-07-2022",
      "end_date": "07-21-2022",
    },
    ...
  ]
}
```

### Management Updates

Finch provides a `management` webhook type to deliver updates about the status of a connection. Finch will deliver a webhook if there have been any connection issues within the past 24 hours for a connection. In addition to the schema above, management updates will include a `message` field which provides more detail about the issue encountered while syncing data. The `data` field is omitted from management webhooks:

**management**
```json
{
  "webhook_id": uuid,
  "company_id": uuid,
  "webhook_type": "management",
  "event_type": "authentication_error"
  "message": "Please have the user reauthenticate"
}
```

Management update webhooks are required in order to use the webhooks feature. You will be prompted to set up exactly one endpoint to receive management updates when you set up webhooks through the developer dashboard.

## Webhook Verification

Finch uses JWTs for webhook verification, and includes this JWT in the `Finch-Verification` header. More information about JWTs can be found at [jwt.io](http://jwt.io). Libraries likely existing in your preferred language for dealing with JWTs. The following are steps you can use to verify the webhook using the verification header:

1. **Extract the header** using your preferred library. If the value of the `alg` field in the token header is not `RS256`, reject the webhook.
2. **Get the webhook verification key** using the Finch API. The  `/webhook_verification_key?client_id=<client_id>` endpoint provides a [JSON Web Key (JWK)](https://auth0.com/docs/secure/tokens/json-web-tokens/json-web-key-set-properties). This is the public key that can be used to verify a JWT. We recommended that you cache the public key on your application side and update from this endpoint only if webhook verification fails with your cached key.
3. **Validate the webhook** using your preferred JWT library. If the signature is not valid reject the webhook. If it is valid, extract the `iat` field from the JWT payload, and ensure the timestamp is not more than 5 minutes old. Using outdated webhooks increases susceptibility to [replay attacks](https://en.wikipedia.org/wiki/Replay_attack).
<!--
title: "Example of how to perform webhook verification"
lineNumbers: true
highlightLines: [[1,2], [4,5]]
-->
```javascript
const jwt_decode = require('jwt-decode');
const jose = require('jose');

const publicKey = '<YOUR_CACHED_PUBLIC_KEY>';

const signedJwt = JSON.parse(headers)['Finch-Verification'];
const decodedTokenHeader = jwt_decode(signedJwt, { header: true });

if (decodedTokenHeader.alg !== 'RS256') {
  // reject token
}

// This will throw an error if verification fails
const { payload } = await jose.jwtVerify(signedJwt, keyLike, {
     maxTokenAge: '5 min',
   });
```

## Testing Webhooks

You can send a test request to any webhook through the developer dashboard.

[Screenshot & instructions]

The test webhook will include the same structure as data update webhooks, with the `event_type` set to `test`

## Retries

Upon failure, Finch will retry an event up to 19 times with exponential backoff over 3 days.

## Best practices for handling webhooks

**Responding to Webhooks**

In order to prevent unnecessary retries, we recommend receiving webhooks events and processing the events in separate processes. Upon receiving the event, you should respond with a `200` indicating that the event was successfully delivered.

**Event delivery and ordering**

- It is possible that you may occasionally receive the same webhook event more than once. We recommend setting up idempotent event processing by using the `webhook_id`.
- Finch does not guarantee delivery of events in the order they happen. For example, you may receive an `update` event for an `individual` before a `created` event. You can also use the Finch API to occasionally fetch any missing data. For example, you can fetch an individual if you happen to receive an `update` event first.

**Event Mapping**

- Webhooks are delivered with a `company_id` corresponding to the company for which the data changed. This means you will have to retrieve the company id from Finch in order to map webhooks updates to the companies the data belongs to. A simple workflow for this is to call the `/introspect` endpoint after you exchange an auth code for an access token via the `/auth/token` endpoint. The `introspect` endpoint contains the company id for the company a token is associated with. You can save this id in your system to map to webhook events.