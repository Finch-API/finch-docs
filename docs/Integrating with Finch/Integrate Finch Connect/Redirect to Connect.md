# Your application redirects to Connect

In this method of integrating Connect, your application redirects your user's browser to Connect hosted by Finch on `https://connect.tryfinch.com`. The authorization flow will consist of four steps—

1. **Open Finch Connect—** Your application redirects your user's browser to Connect to initiate the authorization flow.
2. **Obtain consent—** Connect prompts your user to log in to their employment system and grant your application access to the permissions you are requesting for. 
3. **Retrieve the authorization code—** If your user successfully connects and grants your application access to their system, Connect will redirect their browser to a specified `redirect_uri` with a short-lived authorization `code`.
4. **Exchange the code for an access token—** Before sending API requests, your application will exchange the short-lived `code` for a long-lived `access_token` that represents your application's access to your user's employment system.

---



## Open Connect
When your application needs access to your user's employment system redirect them to Connect.

Construct the Connect redirect with the parameters below—

<!--
type: tab
title: Parameters
-->
Parameter | Required | Description
---------|----------|---------
 `client_id` | true | Your `client_id`, a unique identifier for your application.
 `redirect_uri` | true | The URI your user is redirected to after successfully granting your application access to their system. This value must match one of your application's configured redirect URIs. Read more here.
 `products` | true | A space-separated list of permissions your application is requesting access to. See here for a list of valid permissions.
 `state` | false | An optional value included as a query parameter in the `redirect_uri` back to your application. This value is often used to identify a user and/or prevent cross-site request forgery.
 `payroll_provider` | false | An optional parameter that allows you to bypass the employment system selection screen by providing a valid Provider `id`. Read here for more information.
 `sandbox` | false | An optional value that allows users to switch on the sandbox mode to login with fake credentials and test applications against mock data. Read more on testing here.
 `manual` | false | An optional value which when set to true displays both automated and Assisted Connect employment systems on the selection screen. Read more about Assisted Connect here.

<!--
type: tab
title: Example
-->
```curl
https://connect.tryfinch.com/authorize?
&client_id={client_id}
&products=company directory
&redirect_uri=https://tryfinch.com
```
<!-- type: tab-end -->

## Obtain consent
Connect displays the permissions your application is requesting access to. If your user approves, they are asked to select their employment system and are then prompted to log in to their account.

## Retrieve the authorization code

Connect sends the end user’s approval or denial back to your application’s server via the specified redirect URI.

If the user grants your application access and successfully connects their account, they are redirected to the specified `redirect_uri` with the query parameters below.

<!--
type: tab
title: Parameters
-->
Parameter | Required | Description
---------|----------|---------
 `code` | true | An authorization code that will be used to obtain an `access_token` in the following step. The authorization `code` expires in 10 minutes.
 `state` | false | If the redirect to Finch Connect contains a `state` parameter, the same parameter will be returned here.

<!--
type: tab
title: Example
-->
```curl
HTTP/1.1 302 Found
Location: https://tryfinch.com?
code=90abecb6-e7ab-4b85-864a-e1c8bf67f2ad
```
<!-- type: tab-end -->


## Exchange the code for an access token
<!-- theme: info -->
> An authorization `code` is valid for only 10 minutes. Therefore, the exchange must occur within 10 minutes of receiving the `code` via the redirect.

To interact with the Finch API, you will need to exchange your short-lived authorization `code` for a long-lived `access_token`. 


### Request

<!-- theme: danger -->
> The exchange step should always take place in your back-end to ensure your `client_secret` and `access_token` are never publicly exposed.

<!--
type: tab
title: Headers
-->
Header | Description
-------|--------------
`Authorization` | [HTTP Basic Auth header](https://en.wikipedia.org/wiki/Basic_access_authentication#Client_side) containing the `client_id` and `client_secret`. The header is formed by concatenating the word “Basic”, followed by a space, and a base64 encoded string of the `client_id`, a colon `:`, and the `client_secret`.
`Content-Type` | Must be set to `application/x-www-form-urlencoded`, matching the format of the request body.

<!--
type: tab
title: Body
-->
Parameter | Required | Description
----------|----------|-------------
`code` | true | The authorization code received from the query parameter of the `redirect_uri`.
`redirect_uri` | true | The `redirect_uri` the `code` was parsed from.

<!--
type: tab
title: Example
-->
```shell
curl https://api.tryfinch.com/auth/token \
  -X POST \
  -H 'Authorization: Basic base64({client_id}:{client_secret})' \
  -d 'code=90abecb6-e7ab-4b85-864a-e1c8bf67f2ad' \
  -d 'redirect_uri=https://tryfinch.com'
```
<!-- type: tab-end -->

### Response
<!-- theme: success -->
> A Finch `access_token` is long-living, i.e. it does not expire.

<!--
type: tab
title: Schema
-->
Parameter | Description
----------|-------------
`access_token` | The `access_token` used to make requests to the Finch API. It has does not expire and should be stored securely in your database.

<!--
type: tab
title: Example
-->
```json
{
  "access_token": "cf7ba7e9-8c5d-417d-a99f-c386cfc235cc",
}
```
<!-- type: tab-end -->

---

## Next steps
Once you have an `access_token`, you can begin pulling data and pushing changes into your users' employment systems! The next step is to integrate the Finch API into your back-end.
