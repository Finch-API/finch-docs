# Your application embeds Finch Connect

In this method of integration, your can embed Finch Connect into your application using a Finch SDK so your user remains on your application. The authorization flow will consist of four steps—
1. **Open Finch Connect—** Your application uses a Finch SDK to launch Connect and initiate the authorization flow for your user.
2. **Obtain consent—** Connect prompts your user to log in to their employment system and grant your application access to the permissions you are requesting for. 
3. **Retrieve the authorization code—** If the user successfully connects and grants your application access to their system, Connect will call the registered `onSuccess` handler with a short-lived authorization `code`.
4. **Exchange the code for an access token—** Before sending API requests, your application will exchange the short-lived `code` for a long-lived `access_token` that represents your application's access to your user's employment system.

**Currently, Finch supports only a React SDK.**

---

## Open Finch Connect

To open Finch Connect, you will need to instantiate the [SDK](https://github.com/Finch-API/react-finch-connect) with the `useFinchConnect` hook and invoke the returned `open` method to display the view for your user.

We recommend registering the `open` method with an `onClick` handler of an HTML button on your application.

<!--
type: tab
title: Parameters
-->
Parameter | Required | Description
---------|----------|---------
 `clientId` | true | Your `client_id`, a unique identifier for your application.
 `products` | true | An array of permissions your application is requesting access to. See [here](../../Development-Guides/Permissions.md) for a list of valid permissions.
 `payrollProvider` | false | An optional parameter that allows you to bypass the provider selection screen by providing a valid provider `id`. Read [here](../../Development-Guides/Providers.md) for more information.
 `sandbox` | false | An optional value that allows users to switch on the sandbox mode to login with fake credentials and test applications against mock data. For more information, read our [Testing Development Guide](../../Development-Guides/Testing.md).
 `manual` | false | An optional value which when set to true displays both [Automated API](../Product-Guides/Automated-Connect-Flow.md) and [Assisted API](../Product-Guides/Assisted-Connect-Flow.md) providers on the selection screen.

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
Connect displays the permissions your application is requesting access to. If your user approves, they are asked to select their provider and are then prompted to log in to their account.

## Retrieve the authorization code
Once the user has granted your application to access their employment system, the `onSuccess` method is invoked with an authorization `code`.

Parameter | Description
---------|---------
 `code` | An authorization code that will be used to obtain an `access_token` in the following step. The authorization `code` expires in 10 minutes.


## Exchange the code for an access token
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
`Content-Type` | Must be set to `application/json`, matching the format of the request body.

<!--
type: tab
title: Body
-->
Parameter | Required | Description
----------|----------|-------------
`clientId` | true | Your `client_id`, a public unique identifier for your application.
`client_secret` | true | Your `client_secret`, a secret value which authorizes your application with Finch. Please ensure you protect your `client_secret`.
`code` | true | The authorization code received by the `onSuccess` handler.


<!--
type: tab
title: Example
-->
```shell
curl https://api.tryfinch.com/auth/token \
  -X POST \
  -H "Content-Type: application/json" \
  --data-raw '{
    "client_id": "<your_client_id>",
    "client_secret": "<your_client_secret>",
    "code": "<your_authorization_code>"
}'
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
  "access_token": "<your_access_token>",
  "client_id": "<your_client_id>",
  "company_id": "<your_company_id>", 
  "products": "<products_associated_with_access_token>",
  "username": "<login_associated_with_access_token>",
  "payroll_provider_id": "<payroll_provider_associated_with_access_token>",
  "manual": "<uses_finch_assisted_connect"
}
```
<!-- type: tab-end -->

---

## Next steps
Once you have an `access_token`, you can begin pulling data and pushing changes into your users' employment systems! The next step is to integrate the Finch API into your back-end.



