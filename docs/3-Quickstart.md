# Quickstart

Once you have an application's `client_id` and `client_secret`, you can start interacting with Finch's API using our sandbox mode — a test environment with mock data.

This guide will help you send your first request to Finch's API while the following guides dive deeper into the concepts and help you integrate Finch into your production application.

---

### Open Finch Connect in sandbox mode

Finch Connect provides a secure and elegant authorization flow for your users to grant your application access to their systems.

> Note: this quickstart guide is a simplified, but manual way of generating an authorization `code` and exchanging it for an `access_token`, which can be used to subsequently call our APIs. In a true production environment, you will want to automate this process completely inside your application's code.

Since this quickstart assumes you have not built an application yet, we must make sure that a proper `redirect_uri` is set up before continuing or our authorization code generation will fail. In your [Finch Dashboard](https://dashboard.tryfinch.com), go to the "Redirect URIs" section and select `+ Add Redirect URI`. We are going to use [https://example.com](https://example.com) for testing purposes. In production, you will want to use your own application's urls for the Redirect Uris (and remove all mentions of [https://example.com](https://example.com) or [http://localhost](http://localhost)).

Redirect URIs are only needed if you are [redirecting to Finch Connect](./Integrating-with-Finch/Integrate-Finch-Connect/Redirect-to-Connect.md). If you decide to use our [embedded Finch Connect flow](./Integrating-with-Finch/Integrate-Finch-Connect/Embed-Connect.md), you do not need to specify a redirect_uri; the SDK does this for you.

> Currently, embedded flow only works with our [React SDK](https://github.com/Finch-API/react-connect). If you would like to request another embedded flow SDK language, [let us know](mailto:developers@tryfinch.com).

We will launch Finch Connect - our secure and elegant authorization flow for your users to grant your application access to their systems - by constructing and navigating to the following URL on your browser. Copy the url below, open up your favorite text editor (Notes, TextEdit, VS Code, etc), paste, and replace `<your-client-id>` with the client id found in your [Finch Dashboard](https://dashboard.tryfinch.com). Remove the angle brackets when replacing `<your-client-id>`.

```bash
https://connect.tryfinch.com/authorize?
&client_id=<your_client_id>
&products=company directory individual employment payment pay_statement
&redirect_uri=https://example.com
&sandbox=true
```

Note that we have `sandbox=true`. This is required only when calling our sandbox environment for testing purposes.

### Log in to the Finch sandbox account

Click on the Finch Sandbox mock provider on the selector page and log in with the username `largeco` and password `letmein`. For more information on the various types of mock payroll providers you can test, visit our [testing](./Development-Guides/Testing.md) page.

> This is the final interaction your end-user will have with Finch. All of the following steps will occur on your application's front-end and back-end.

### Exchange the authorization code for an access token

After successfully logging in via Finch Connect, your browser will be redirected to `https://example.com` with the query parameter `code`. Copy the `code` from the url and save it in your text editor. In a production system, however, the browser will redirect to your url and your application will automatically copy the `code` and perform the remaining steps programmatically.

To exchange the `code` for a token, we use the `curl` command below. Copy the code below, paste into your text editor, replace the `<your_authorization_code>` in the command with the one you saved above (making sure to not include the angle brackets).

<!--
type: tab
title: Request
-->
```bash
curl https://api.tryfinch.com/auth/token \
  -X POST \
  -H "Content-Type: application/json" \
  --data-raw '{
    "client_id": "<your_client_id>",
    "client_secret": "<your_client_secret>",
    "code": "<your_authorization_code>",
    "redirect_uri": "https://example.com"
}'
```

<!--
type: tab
title: Response
-->
```json
{
  "access_token": "<your_access_token>",
}
```
<!-- type: tab-end -->

Copy, paste, and run the command in your terminal. This `curl` command is going to make an HTTP POST request with a JSON encoded request body containing your:

- `client_id` (replace `<your_client_id>`),
- `client_secret` (replace `<your_client_secret>`),
- `redirect_uri`
- and our newly generated authorization `code` (replace `<your_authorization_code>`)

The response to this request will contain a JSON encoded object containing an `access_token` key, whose value will contain your newly created Finch access token (in this case `<your_access_token>`).

In [OAuth2](https://oauth.net/2/) terms, the authorization `code` represents a user consenting your application access to their system. The `access_token` represents your application's access to your user's system.

### Use the access token to send an API request

Now that you have a valid `access_token`, you will use this access token to send requests to Finch's APIs from now on. You will not have to go through the authentication process again unless you need to get a new access token or a [re-authentication](./Best-Practices/Re-authentication.md) event happens.

Run the following command to retrieve the `largeco`'s employee directory!

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

Congratulations! You have sent your first request to Finch's API. Read on to dive deeper into [Finch Connect](./Integrating-with-Finch/Integrate-Finch-Connect/Redirect-to-Connect.md) or get started with our [production integration checklist](./Integrating-with-Finch/Integration%20Checklist.md).
