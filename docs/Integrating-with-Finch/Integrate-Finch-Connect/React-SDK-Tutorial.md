# React Tutorial

This tutorial will help you get started using Finch Connect with the React SDK.

## Introduction

Finch is an API that allows mobile and web applications to retrieve data and make changes to payroll and HRIS systems for many providers. This tutorial will help you get up and running using Finch Connect in your React application.

## Setup

Make sure to [register](../../2-Registration.md) for a free Finch account before getting started.

## Authorization

To make a request to Finch, your end-employer must connect their payroll or HRIS account using Finch Connect. Finch Connect provides a drop-in and secure authorization flow for your users.

***

### 1. Install the React Finch Connect SDK

Head over to your React client application's codebase and install `react-finch-connect`.

```bash
npm install --save react-finch-connect
```

***

### 2 Import the `useFinchConnect` hook

Import the `useFinchConnect` hook in your application.

```javascript
import React, { useState } from "react";
import { useFinchConnect } from "react-finch-connect";

const App = () => {
  const [code, setCode] = useState(null);

  const onSuccess = ({ code }) => setCode(code);
  const onError = ({ errorMessage }) => console.error(errorMessage);
  const onClose = () => console.log("User exited Finch Connect");

  const { open } = useFinchConnect({
    clientId: "<your-client-id>",
    // payrollProvider: '<payroll-provider-id>',
    products: ["company", "directory"],
    onSuccess,
    onError,
    onClose,
  });

  // ...
};
```

***

### 3. Launch Connect

A single-page application will launch an iFrame window with Finch Connect to request access to a user's payroll account. Using Finch Connect, the user logs in with their username and password for their payroll account which grants the application access to the requested product permissions.

To launch Finch Connect, you can use the `open` function returned by `useFinchConnect`. You can place this on an `onClick` handler of an HTML button.

```javascript
const App = () => {
  // ...

  return (
    <button type="button" onClick={() => open()}>
      Open Finch Connect
    </button>
  );
}; 
```

***

### 4. Receive the authorization code

Once a user has authorized the application to access their payroll account, the `onSuccess` function is called with an authorization `code`.

> The authorization `code` represents a user consenting your application access to their payroll account. It does not grant access to the payroll account itself. The authorization `code` has to be exchanged from your back-end for an `access_token`.

After receiving the authorization `code`, the React application must exchange it for an `access_token`. To do so,  send the `code` to your back-end service. Let's assume that our back-end service contains an endpoint `/exchange` that receives an authorization `code` as a query parameter and exchanges it for an `access_token`.

```javascript
const App = () => {
  // ...

  onSuccess = ({ code }) => {
    return axios.get(`${process.env.REACT_APP_SERVER}/exchange?code=${code}`);
  };

  // ...
}; 
```

Notice that our back-end service does not return the `access_token`. This is by design. For security, our front-end should never have access to the `access_token` and should always be stored in the back-end.

***

### 5. Get company information

Once the back-end has the `access_token`, it can send requests to a payroll provider using the Finch API. The React app will have to send a request to the back-end service which in turn sends a request to Finch. You must do this because our front-end does not have the `access_token`.

Assuming our back-end has a `/company` endpoint that returns information on the employer, you can make this query in our `onSuccess` function and set the state of the React app with the returned company attribute.

```javascript
const App = () => {
  // ...
  
  onSuccess = ({ code }) => {
    return axios.get(`${process.env.REACT_APP_SERVER}/exchange?code=${code}`)
      .then(_ => axios.get(`${process.env.REACT_APP_SERVER}/company`)
      .then(res => {
       setIdentity(res.data);
      });
  }
  
  // ...
}; 
```
