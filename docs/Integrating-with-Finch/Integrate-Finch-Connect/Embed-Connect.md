# Your Application Embeds Finch Connect

In this method of integration, your can embed Finch Connect into your application using a Finch SDK so your user remains on your application. The authorization flow will consist of four steps—
1. **Open Finch Connect—** Your application uses a Finch SDK to launch Finch Connect and initiate the authorization flow for your user.
2. **Obtain consent—** Finch Connect prompts your user to log in to their employment system and grant your application access to the permissions you are requesting. 
3. **Retrieve the authorization code—** If the user successfully connects and grants your application access to their system, Finch Connect will call the registered `onSuccess` handler with a short-lived authorization `code`.
4. **Exchange the code for an access token—** Before sending API requests, your application will exchange the short-lived `code` for a long-lived `access_token` that represents your application's access to your user's employment system.

**Currently, Finch supports a Javascript and React SDKs.**

---

## Open Finch Connect

To make a request to Finch, an employer must connect their payroll or HRIS account using Finch Connect. Finch SDKs provides a drop-in and secure authorization flow for your users.

<!--
type: tab
title: React SDK
-->

To open Finch Connect with React, you will need to instantiate the [React SDK](https://github.com/Finch-API/react-finch-connect) with the `useFinchConnect` hook and invoke the returned `open` method to display the view for your user.

### 1. Install the React Finch Connect SDK

Inside your code base folder, use the command line to install `react-finch-connect`

```bash
npm install --save react-finch-connect
```


### 2. Import the 'useFinchConnect' Hook

 ```javascript
import React, { useState } from "react";
import { useFinchConnect } from "react-finch-connect";

const App = () => {
  const [code, setCode] = useState(null);

  const onSuccess = ({ code }) => setCode(code);
  const onError = ({ errorMessage }) => console.error(errorMessage);
  const onClose = () => console.log("User exited Finch Connect");

  // 1. Initialize Finch Connect
  const { open } = useFinchConnect({
    clientId: "<your-client-id>",
    products: ["company", "directory", "individual", "employment", "payment", "pay_statement"],
    onSuccess,
    onError,
    onClose,
  });

  // ...
};
```

`useFinchConnect` Parameters

Parameter | Required | Description
---------|----------|---------
 `clientId` | true | Your `client_id`, a unique identifier for your application.
 `category` | false | The category of integrations your applications would like to expose. Options: `hris` and `ats`. If no category is provided, defaults to `hris`.
 `products` | true | An array of permissions your application is requesting access to. See [here](../../Development-Guides/Permissions.md) for a list of valid permissions.
 `payroll_provider` | false | An optional parameter that allows you to bypass the provider selection screen by providing a valid provider `id`. Read [here](../../Development-Guides/Providers.md) for more information.
 `sandbox` | false | An optional value that allows users to switch on the sandbox mode to login with fake credentials and test applications against mock data. For more information, read our [Testing Development Guide](../../Development-Guides/Testing.md).
 `manual` | false | An optional value which when set to true displays both [Automated API](../Product-Guides/Automated-Connect-Flow.md) and [Assisted API](../Product-Guides/Assisted-Connect-Flow.md) providers on the selection screen.

### 3. Launch Finch Connect

To launch Finch Connect, use the `open` function returned by `useFinchConnect` and place this on an `onClick` handler of an HTML button.

```javascript
const App = () => {
  // ...

  // 2. Display Finch Connect
  return (
    <button type="button" onClick={() => open()}>
      Open Finch Connect
    </button>
  );
};
```


### 4. Receive the authorization code

Once a user has authorized the application to access their payroll account, the `onSuccess` function is called with an authorization `code`.

Parameter | Description
---------|---------
 `code` | An authorization code that will be used to obtain an `access_token` in the following step. The authorization `code` expires in 10 minutes.

After receiving the authorization `code`, the React application must exchange it for an `access_token`. To do so, send the `code` to the back-end service. Let's assume that your back-end service contains an endpoint `/exchange` that receives an authorization `code` as a query parameter and exchanges it for an `access_token`.

```js
const App = () => {
  // ...

  onSuccess = ({ code }) => {
    return axios.get(`${process.env.REACT_APP_SERVER}/exchange?code=${code}`);
  };

  // ...
};
```

Notice that your back-end service does not return the `access_token`. This is by design. For security, your front-end should never have access to the `access_token` and **should always be stored in the back-end**.

### 5. Get company information

Once the back-end has the `access_token`, it can send requests to a payroll provider using the Finch API. Your React app will have to send a request to the back-end service which in turn sends a request to Finch. You have to do this because your front-end does not have the `access_token`.

Assuming your back-end has a `/company` endpoint that returns information on the employer, you can make this query in your `onSuccess` function and set the state of the React app with the returned company attribute.

```js
const App = () => {
  // ...
  
  onSuccess = ({ code }) => {
    return axios.get(`${process.env.REACT_APP_SERVER}/exchange?code=${code}`)
      .then(_ => axios.get(`${process.env.REACT_APP_SERVER}/company`))
      .then(res => {
       setIdentity(res.data);
      });
  }
  
  // ...
};
```
--- 

<!--
type: tab
title: JS SDK
-->

The [Javascript SDK](https://github.com/Finch-API/finch-connect-js) can be loaded via a HTML `<script />` tag and then instantiated with some initialization code in your application.

The returned `FinchConnect` object exposes `open`, `close` and `destroy` lifecycle methods.

<!-- theme: danger -->
>Since Finch Connect is an IFrame that requires interactivity, the HTML page that is loading Finch Connect **must be served from a server**. If the page is hosted statically, Finch Connect will not work properly.

### 1. Include the Javascript SDK Script

```html
<html>
  <head>
    <script src="https://prod-cdn.tryfinch.com/v1/connect.js"></script>
  </head>
  <body>
    
  </body>
</html>
```


### 2. Initialize Finch Connect

Inside a `<script>` inside the page `<body>`, initialize the FinchConnect object.

The returned `FinchConnect` object exposes `open`, `close` and `destroy` lifecycle methods.

```html
<html>
  <body>
    <script>
      const onSuccess = ({code}) => {
        // exchange code for access token via your server
      }
      const onError = ({ errorMessage }) => {
        console.error(errorMessage);
      }
      const onClose = () => {
        console.log('Connect closed');
      }
      const connect = FinchConnect.initialize({
        clientId: '<your-client-id>',
        products: ['company', 'directory', "individual", "employment", "payment", "pay_statement"],
        sandbox: false,
        manual: false,
        onSuccess,
        onError,
        onClose,
      });
    </script>
  </body>
</html>
```

Parameter | Required | Description
---------|----------|---------
 `clientId` | true | Your `client_id`, a unique identifier for your application.
 `category` | false | The category of integrations your applications would like to expose. Options: `hris` and `ats`. If no category is provided, defaults to `hris`.
 `products` | true | An array of permissions your application is requesting access to. See [here](../../Development-Guides/Permissions.md) for a list of valid permissions.
 `payroll_provider` | false | An optional parameter that allows you to bypass the provider selection screen by providing a valid provider `id`. Read [here](../../Development-Guides/Providers.md) for more information.
 `sandbox` | false | An optional value that allows users to switch on the sandbox mode to login with fake credentials and test applications against mock data. For more information, read our [Testing Development Guide](../../Development-Guides/Testing.md).
 `manual` | false | An optional value which when set to true displays both [Automated API](../Product-Guides/Automated-Connect-Flow.md) and [Assisted API](../Product-Guides/Assisted-Connect-Flow.md) providers on the selection screen.

### 3. Open Finch Connect

To open Finch Connect, use the `open` function returned by `FinchConnect` and add an `addEventListener` on the click event of an HTML button.

```html
<html>
  <body>
    <button id="connect-button">Open Finch Connect</button>
    <script>
      const button = document.getElementById('connect-button');

      const connect = FinchConnect.initialize({
        ...
      });
      button.addEventListener('click', () => {
        connect.open();
      })
    </script>
  </body>
</html>
```


### 4. Exchange the authorization code

Once a user has authorized the application to access their payroll account, the `onSuccess` function is called with an authorization `code`.

Parameter | Description
---------|---------
 `code` | An authorization code that will be used to obtain an `access_token` in the following step. The authorization `code` expires in 10 minutes.

After receiving the authorization `code`, the front-end application must exchange it for an `access_token`. To do so, send the `code` to the back-end service. Let's assume that your back-end service contains an endpoint `/exchange` that receives an authorization `code` as a query parameter and exchanges it for an `access_token`.

```html
<html>
  <body>
    <script>
      // ...
      const onSuccess = async ({code}) => {
        return await fetch(`http://your-api.com/exchange?code=${code}`)
          .then(res => res.json());
      }
      // ...
    </script>
  </body>
</html>
```

Notice that your back-end service will not return the `access_token`. This is by design. For security, your front-end should never have access to the `access_token` and **should always be stored in the back-end**.

### 5. Request company information

Once the back-end has the `access_token`, it can send requests to a payroll provider using the Finch API. Your app will have to send a request to the back-end service which in turn sends a request to Finch. You have to do this because your front-end does not have the `access_token`.

Assuming our back-end has a `/company` endpoint that returns information on the employer, you can make this query in your `onSuccess` function and set the state of the app with the returned company attribute.

```html
<html>
  <body>
    <script>
      // ...
      const onSuccess = async ({code}) => {
        return await fetch(`http://your-api-server.com/exchange?code=${code}`)
          .then(await fetch(`http://your-api-server.com/company`)
          .then(res => {
            setCompany(res.json)
          });
      }
      // ...
    </script>
  </body>
</html>
```

<!-- type: tab-end -->


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
`client_id` | true | Your `client_id`, a public unique identifier for your application.
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
}
```
<!-- type: tab-end -->

---

## Next Steps
Once you have an `access_token`, you can begin pulling data and pushing changes into your users' employment systems! The next step is to integrate the Finch API into your back-end.



