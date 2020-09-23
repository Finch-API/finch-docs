# Disconnect


**Info**: Disconnect an employer from your application and invalidate all `access_token`s associated with the employer. We require applications to implement the Disconnect endpoint for billing and security purposes.

**URL**: `POST https://api.tryfinch.com/disconnect`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/disconnect \
-H "Finch-API-Version: 2020-09-17" \
-H 'Authorization: Basic base64({client_id}:{client_secret})' \
-X "POST" \
-d '{"access_token": "46203a0c-26ed-43c4-9e13-aaa607832f5b"}'
```

**Request body parameters**

Parameter | Type | Required | Description
----------|------|----------|-------------
`access_token` | `string` | true | The `access_token` associated with the employer to be disconnected.

***

**Example response**

```json
{
  "status": "success"
}
```

** Response body**


Name | Type | Description
-----|------|-------------
`status` | `string` | If the request is successful, Finch will return “success” (HTTP 200 status).