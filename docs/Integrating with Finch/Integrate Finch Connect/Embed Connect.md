# Your application embeds Connect

In this method of integration, your application embeds Connect into your application using a Finch SDK to your user remains on your application. The authorization flow will consist of four steps—
1. **Open Finch Connect—** Your application uses a Finch SDK to launch Connect and initiate the authorization flow for your user.
2. **Obtain consent—** Connect prompts your user to log in to their employment system and grant your application access to the permissions you are requesting for. 
3. **Retrieve the authorization code—** If the user successfully connects and grants your application access to their system, Connect will call the registered `onSuccess` handler with a short-lived authorization `code`.
4. **Exchange the code for an access token—** Before sending API requests, your application will exchange the short-lived `code` for a long-lived `access_token` that represents your application's access to your user's employment system.

**Currently, Finch supports only a React SDK.**

---


## Open Connect

To open Connect, you will need to instantiate the SDK with the `useFinchConnect` hook and use the returned `open` method to display the view for your user.

We recommend registering the `open` method with an `onClick` handler of an HTML button on your application.

<!--
type: tab
title: Parameters
-->
Parameter | Required | Description
---------|----------|---------
 `clientId` | true | Your `client_id`, a unique identifier for your application.
 `products` | true | An array of permissions your application is requesting access to. See here for a list of valid permissions.
 `payrollProvider` | false | An optional parameter that allows you to bypass the employment system selection screen by providing a valid Provider `id`. Read here for more information.
 `sandbox` | false | An optional value that allows users to switch on the sandbox mode to login with fake credentials and test applications against mock data. Read more on testing here.
 `manual` | false | An optional value which when set to true displays both automated and Assisted Connect employment systems on the selection screen. Read more about Assisted Connect here.

<!--
type: tab
title: Example
-->
```javascript lineNumbers
import React, { useState } from "react";
import { useFinchConnect } from "react-finch-connect";

const App = () => {
  const [code, setCode] = useState(null);

  const onSuccess = ({ code }) => setCode(code);
  const onError = ({ errorMessage }) => console.error(errorMessage);
  const onClose = () => console.log("User exited Finch Connect");

  // 1. Instantiate Connect
  const { open } = useFinchConnect({
    clientId: "<your-client-id>",
    products: ["company", "directory"],
    onSuccess,
    onError,
    onClose,
  });

  // 2. Display Connect
  return (
    <button type="button" onClick={() => open()}>
      Connect your payroll account.
    </button>
  );
};
```
<!-- type: tab-end -->

## Obtain consent
Connect displays the permissions your application is requesting access to. If your user approves, they are asked to select their employment system and are then prompted to log in to their account.

## Retrieve the authorization code
Once the user has granted your application to access their employment system, the `onSuccess` method is invoked with an authorization `code`.

Parameter | Required | Description
---------|----------|---------
 `code` | true | An authorization code that will be used to obtain an `access_token` in the following step. The authorization `code` expires in 10 minutes.


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



