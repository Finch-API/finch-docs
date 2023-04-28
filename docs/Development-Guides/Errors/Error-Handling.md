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

### 401 re-authentication errors

Authentication errors indicate an error on the end user's side. See the [re-authentication docs](../../Best-Practices/Re-authentication.md) for more on common causes and troubleshooting steps. 

## Batch Requests

A number of Finch endpoints (like `/individual`, `/employment`, and `/pay-statement`) are batch endpoints.

For such endpoints, Finch can return errors in two ways:
1. Return an error per batch request item within the response body. The error will be in the same format described in the [Error Types guide](./Error-Types.md).
    * Finch also returns an `error_name` and `error_message` in the response body. **These fields are now deprecated in favor of conforming to our standard error formatting, and will be removed entirely in June 2023.**
2. Return an error at the HTTP status code level. The error will be in the same format described in the [Error Types guide](./Error-Types.md).

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
      // this id varies by endpoint, could also be payment_id or benefit_id
      "individual_id": "fbeabe51-e6d2-45aa-a460-4c8482528f41",
      // corresponds to the `code` parameter of the error schema in the Error Types guide
      "code": 404,
      "body": {
        "name": "not_found_error",
        "code": 404,
        "finch_code": "individual_not_found",
        "message": "The individual with id 'fbeabe51-e6d2-45aa-a460-4c8482528f41' could not be found",
        // deprecated field. corresponds to the `name` parameter of the error schema in the Error Types guide
        "error_name": "not_found_error",
        // deprecated field. corresponds to the `message` parameter of the error schema in the Error Types guide
        "error_message": "The individual with id 'fbeabe51-e6d2-45aa-a460-4c8482528f41' could not be found"
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

<!-- theme: warning -->
> Refer to the API reference to ensure your application handles errors from each batch endpoint correctly as response schemas vary by endpoint.


