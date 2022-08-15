# Node Tutorial

This tutorial will help you get started calling the Finch API with Node.js.

> Our other back-end SDKs are in the works. Hold tight! In the meantime, you can use a generic HTTP request library like [axios](https://www.npmjs.com/package/axios).

## Introduction

Finch is an API that allows mobile and web applications to retrieve data and make changes to payroll and HRIS systems for many providers. This tutorial will help you get up and running using Finch Connect in your React application.

***

### 1. Obtain an access token

In the [React tutorial](../Integrate-Finch-Connect/React-SDK-Tutorial.md), after a successful provider login, you receive an authorization `code`. The Node.js application must exchange the `code` for an `access_token` before making a request to Finch's API. After receiving the `access_token`, the user can be redirected to the `/identity` route which will implement in the next step.

```javascript
import axios from 'axios'

// global variable to save our accessToken
let access_token;

app.get("/exchange", async function (req, res) {
  const code = req.query.code;

  const authRes = await axios({
      method: 'post',
      url: 'https://api.tryfinch.com/auth/token',
      data: {
        code: code,
        redirect_uri: 'https://tryfinch.com',
        client_id: '<your-client-id>',
        client_secret: '<your-client-secret>'
      }
  });

  access_token = authRes.data.access_token;

  res.redirect("/company");
});
```

***

### 2. Get company information

Once the application has the `access_token`, it can send requests to a payroll account using Finch's API.

```javascript
app.get("/company", async function (req, res) {

  const companyRes = await axios({
      method: 'get',
      url: 'https://api.tryfinch.com/employer/company',
      headers: {
          Authorization: `Bearer ${access_token}`,
          'Finch-API-Version': '2020-09-17'
      },
  });

  res.status(200).json(companyRes.data);
});
```
