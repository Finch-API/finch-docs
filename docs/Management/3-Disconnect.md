# Disconnect


**Info**: Disconnect an employer from your application and invalidate all `access_token`s associated with the employer. We require applications to implement the Disconnect endpoint for billing and security purposes.

**URL**: `POST https://api.tryfinch.com/disconnect`

***

## Request

**Example request**

```shell
curl https://api.tryfinch.com/disconnect \
-H "Finch-API-Version: 2020-09-17" \
-H 'Authorization: Bearer {token}' \
-X "POST" 
```

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