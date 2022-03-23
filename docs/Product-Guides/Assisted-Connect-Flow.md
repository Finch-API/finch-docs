# Assisted Connect Flow

Assisted Connect Flow (ACF) is our semi-automated product that expands coverage to 70+ providers. In contrast to our automated connections, the data for ACF providers is refreshed periodically. Our full list of coverage — for both API and ACF providers — can be found [here](../Development-Guides/Providers.md).

Contact our team at `developers@tryfinch.com` to get started or for more questions regarding pricing, missing providers, etc.

---

## How Assisted Connect works
### For your user
As with our automated integrations, your user will need to go through [Connect](./Product-Guides.md). However instead of providing their API credentials, they will need to follow a set of instructions, displayed on Connect, to manually connect your application to their employment system. 

### For you
Unlike our automated integrations, you will not be able to make API calls to pull data and push changes to your users' systems immediately. Instead, you will have to wait until your user manually connects their employment system followed by a predetermined number of days for the Finch team to pull in the data. After the initial pull, the data will be periodically refreshed.

Contact the Finch team at `developers@tryfinch.com` to learn more about the timelines you can expect!



## Integrating Assisted Connect into your application

### Application setup
Contact the Finch team at `developers@tryfinch.com` to setup your application to work with Assisted Connect.

### Launch Connect with the `manual` flag
<!-- theme: info -->
> For Assisted Connect [providers](../Development-Guides/Providers.md) on Connect, your users will see instructions on how to manually connect their employment systems to Finch and your application.

Launch [Connect](../Integrating-with-Finch/Integrate-Finch-Connect/Redirect-to-Connect.md) with `manual=true` so your user can view all the Assisted Connect providers Finch supports. After granting your application access, you can retrieve an authorization `code` and exchange it for an `access_token` as usual.


### Handle API responses correctly
#### `202` status code response
With automated providers, you are able to create an `access_token` and immediately use it to pull in data or push changes to your users' systems. However, with Assisted Connect providers, there is a short delta from when the `access_token` is created to when you can do anything with it.

Until the `access_token` is ready for use, Finch will return an empty response with the HTTP status code `202` indicating the request is valid but the processing is pending. When the `access_token` is ready, API calls will return data with the HTTP status code `200` as usual.

#### `Finch-Data-Retrieved` header
Since the data is retrieved and refreshed on a periodic cadence, you may want to know the freshness of the data returned by an API call. You can use the `Finch-Data-Retrieved` [header](../Development-Guides/Headers.md) to get the date and time in ISO-8601 format the data was retrieved.

### Monitoring the status of your Assisted Connect connections 
To view the status of your connected employers, you can use the [Finch Developer Dashboard](https://dashboard.tryfinch.com) and navigate to the **Employers** tab on your application's page. 

Status | Description
---------|----------
`PENDING` | The `access_token` has been created.
`PROCESSING` | The user has initiated action to connect their system.
`CONNECTED` | API calls are returning HTTP status code `200` and data.
`DISCONNECTED` | The user has disconnected their system.

