# Quickstart

Once you have your API keys, you can start interacting with Finch's API using our sandbox mode — a test environment with life-like data.

This guide will help you send your first request to Finch's API while the next guides dive deeper into the concepts and help you integrate Finch into your production application.    

---

### Open Finch Connect in Sandbox mode

Finch Connect provides a secure and elegant authorization flow for your users to grant your application access to their systems.

Launch Connect by constructing and navigating to the following URL on your browser.

```bash
https://connect.tryfinch.com/authorize?
&client_id=<your_client_id>
&products=company directory
&redirect_uri=https://example.com
&sandbox=true
```

### Log in to the Finch Sandbox account

Click on the Finch Sandbox employment system on the selector page and log in with the username `largeco` and password `letmein`.  

### Exchange the authorization code for an access token

After successfully logging in, your browser will be redirected to `https://example.com` with the query parameter `code`. Copy the `code`.

To exchange the `code` for a token, you will first need to construct a basic authorization header for your application to use in the next request. Run the following commands from your terminal. Don't include the angle brackets when replacing with your `client_id` and `client_secret`.

```bash
export FINCH_CLIENT_ID="<your_finch_client_id>"
export FINCH_CLIENT_SECRET="<your_finch_client_secret>"
export FINCH_BASIC_AUTH_HEADER="Basic `echo -n $FINCH_CLIENT_ID:$FINCH_CLIENT_SECRET | base64`"
```

Run the following `curl` command to retrieve your `access_token`. Don't forget to replace the `code` in the command with the one you just copied. Don't include the angle brackets when replacing with your `code` in the command.

<!--
type: tab
title: Request
-->
```bash
curl https://api.tryfinch.com/auth/token \
  -X POST \
  -H "Authorization: $FINCH_BASIC_AUTH_HEADER" \
  -d "code=<your_authorization_code>" \
  -d "redirect_uri=https://example.com"
```
<!--
type: tab
title: Response
-->
```json
{ "access_token": "<your_access_token>" }
```
<!-- type: tab-end -->

The authorization `code` represents a user consenting your application access to their system. You can now exchange it for an `access_token` which represents your application's access to your user's system. 

### Use the access token to send an API request

Now that you have an `access_token`, you can send API requests to Finch. Run the following command to retrieve the `largeco`'s employee directory!

<!--
type: tab
title: Request
-->
```bash
curl https://api.tryfinch.com/employer/directory \
  -H 'Authorization: Bearer <your_access_token>' \
  -H 'Content-Type: application/json' \
  -H 'Finch-API-Version: 2020-09-17'
```
<!--
type: tab
title: Response
-->
```json
{
  "paging": {
    "count": 2,
    "offset": 0
  },
  "individuals": [
    {
      "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9",
      "first_name": "Jane",
      "middle_name": null,
      "last_name": "Doe",
      "manager": null,
      "department": {
        "name": "Product"
      },
      "is_active": true
    },
    {
      "id": "c205b3fa-b626-4346-bf0f-ca065ab88d31",
      "first_name": "John",
      "middle_name": null,
      "last_name": "Doe",
      "manager": {
        "id": "5d0b10a1-a09a-430f-81f1-20be735dc5e9"
      },
      "department": {
        "name": "Product"
      },
      "is_active": true
    }
  ]
}
```
<!-- type: tab-end -->
---  

### Next steps

That's it! Now that you have sent your first request to Finch's API, read on to dive deeper and get started with your production Finch integration.