# Error handling

## Errors

### 500 Internal Server Errors

Server errors indicate an error on Finch's side and return an HTTP response with a `500` status code.

**Common causes**

- Finch is experiencing internal system issues. This is rare.
- The underlying employment system is experiencing internal system issues.
- Finch received an unsupported response from the underlying employment system and is unable to process it. These are usually quickly resolved by our support team.
- The end-user has intentionally or unintentionally revoked Finch's access to their system. This is usually returned as a `401 - reauthenticate_user` error but can sometimes be returned as `500 - server_error`.

**Troubleshooting steps**

- Retrying immediately usually will not resolve the issue. We recommend retrying the API request in a few hours.
- If the error persists, submit a support ticket with the `Finch-Request-ID` present in the headers of the response.

### 401 Re-authentication Errors

Authentication errors indicate an error on the end user's side. See the re-authentication docs for more on common causes and troubleshooting steps. 

## Batch requests

A number of Finch endpoints (like `/individual`, `/employment`, and `/pay-statement`) are batch endpoints.

For such endpoints, Finch can return errors in two ways:
1. Return an error per item within a batch API call response. The error will be in the same format described in the Error Types guide.
2. Return an error at the HTTP status code level. The error will be in the same format desribed in the Error Types guide.

<!-- theme: info -->
> Ensure your application can handle both types of errors from a batch API call.


<!--
type: tab
title: Response level
-->
```jsx
Response HTTP Status Code: 200

Response Body:
{
  "responses": [
    {
      "individual_id": "fbeabe51-e6d2-45aa-a460-4c8482528f41", // this field varies by endpoint
      "code": 500, // corresponds to the `code` parameter of the error schema in the Error Types guide
      "body": {
        "error_name": "server_error", // corresponds to the `name` parameter of the error schema in the Error Types guide
        "error_message": "Internal Server Error" // corresponds to the `message` parameter of the error schema in the Error Types guide
      }
    }
  ]
}
```

<!--
type: tab
title: Status code level
-->
```jsx
Response HTTP Status Code: 500

Error Body:
{
  "code": 500,
  "name": "server_error",
  "message": "Internal server error"
}
```
<!-- type: tab-end -->

Refer to the API reference for each endpoint to ensure your application handles errors from each batch endpoint correctly.


