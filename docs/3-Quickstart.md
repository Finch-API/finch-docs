# Quickstart

Once you have your API keys, you can start interacting with Finch's API using our sandbox mode — a test environment with life-like data.

This guide will help you send your first request to Finch's API while the next guides dive deeper into the concepts and help you get started with integrating Finch into your production application.    

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

First, construct a basic authorization header for your application, you will need this in the next request. Run the following command from your terminal. Make sure to replace `{client_id}` and `{client_secret}` with your Finch application credentials, don't include the curly braces.

```bash
echo "Basic `echo -n {client_id}:{client_secret} | base64`"
```

After successfully logging in, your browser will be redirected to `[https://example.com](https://example.com)` with the query parameter `code`. Copy the `code` and the basic auth header from the previous step, and run the following.

```bash
curl https://api.tryfinch.com/auth/token \
  -X POST \
  -H 'Authorization: {basic_auth_header}' \
  -d 'code={code}' \
  -d 'redirect_uri=https://example.com'
```
```json
{ "access_token": "<your_access_token>" }
```

The authorization `code` represents a user consenting your application access to their system. You can now exchange it for an `access_token` which represents your application's access to your user's system. 

### Use the access token to send an API request

Now that you have an `access_token`, you can send API requests to Finch. Run the following command to retrieve the `largeco`'s employee directory!


```bash
curl https://api.tryfinch.com/employer/directory \
  -H 'Authorization: Bearer {access_token}' \
  -H 'Content-Type: application/json' \
  -H 'Finch-API-Version: 2020-09-17'
```
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
---  

### Next steps

That's it! Now that you have sent your first request to Finch's API, read on to dive deeper and get started with your production Finch integration.