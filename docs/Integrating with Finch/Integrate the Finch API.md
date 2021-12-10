# Integrate the Finch API

Once you have an `access_token` representing your application's access to your user's employment system, you can begin sending API requests. 

---

## Sending a request
Every request to Finch's API requires the following headers—


Header | Description
---------|----------
 `Authorization` | Bearer authorization header, which is formed by concatenating the word “Bearer” with the `access_token`, separated by a space.
 `Finch-API-Version` | Header used to specify the version for a given API request. Current version is 2020-09-17.

<!--
type: tab
title: Request
-->
```bash
curl https://api.tryfinch.com/employer/directory \
  -H 'Authorization: Bearer d22a16a5-27da-4b49-955c-352229ccfa8d' \
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

## Next steps
Now that you have integrated the Finch API into your back-end, you are ready to interact with your users' employments systems. Read our integration checklist to learn about the steps needed to launch your integration live!
