# Assisted Connect Flow

Finch Assisted Integrations are a second type of integration offered by Finch. Assisted Integrations operate through a services model, and are powered by Finch’s product operations team. 

Assisted Integrations enable Finch to offer industry-leading coverage and depth of data, while maintaining an API-first experience for developers. Automated and Assisted Integrations may also offer different [field support](../Development-Guides/Field-Support/Compatibility.md) based on the product and provider. 

Aside from coverage, the key difference for Assisted Integrations is refresh cadence. Unlike Automated Integrations that refresh data every 24 hours, Assisted Integrations refresh data every 7 days.

The table below outlines additional differences between Automated and Assisted Integrations:

|  | **Automated Integrations** | **Assisted Integrations** |
| --- | --- | --- |
| **Coverage (Read)** | 25+ Providers | 180+ Providers |
| **Coverage (Write)** | 2 Providers | 15+ Providers |
| **Default data syncs** | 24 hours | 7 days |
| **On-demand data syncs** | Yes | No |
| **Configuration period** | None | 1-2 weeks |
| **Custom fields** | Yes | No |
| **Authentication Method(s)** | OAuth, API token, or Admin Credentials | 3rd-Party Admin Credentials |
| **Connection Monitoring** | Yes | Yes |
| **Pricing** | All plans | Scale plans only |

Finch is continuously working to convert Assisted Integrations into Automated Integrations. If you’re curious about our integrations roadmap, please reach out to your account manager or developers@tryfinch.com. 

## How the Assisted Connect Flow Works

### For your user

As with our automated integrations, your user will need to go through [Finch Connect](../Integrating-with-Finch/Integrate-Finch-Connect/Overview.md). However, instead of our standard login flow, the user will need to follow a set of instructions to add Finch as a 3rd party administrator in their employment system.

### For you

Once your user connects their employment system, there is a [configuration period](#configuration-periods) where you  will be unable to pull data or push changes to your users' system. During this time, Finch’s product operations team will pull in the requested data and set up the weekly sync. After the initial pull, the data will be refreshed every 7 days.

### Configuration Periods

Assisted Integrations require a one-time configuration period before data can be retrieved. See the configuration periods for each product below.

| Product | Integration Type | Configuration Period |
| --- | --- | --- |
| **Organization** | Assisted | 2 weeks |
| **Pay** | Assisted | 2 weeks |
| **Benefits** | Assisted | 1 week |

## Integrating the Assisted Connect Flow Into Your App

### Application setup

Reach out to **`developers@tryfinch.com`** to set up the Assisted Connect Flow. Assisted Integrations are only available for customers on the [Scale](https://www.tryfinch.com/pricing) plan.

### **Launch Finch Connect with the `manual` flag**

Launch [Finch Connect](../Integrating-with-Finch/Integrate-Finch-Connect/Overview.md) with **`manual=true`** so your user can see all providers that support Assisted Integrations. After granting your application access, you can retrieve an authorization **`code`** and exchange it for an **`access_token`** as usual.

```bash
https://connect.tryfinch.com/authorize?
&client_id=<your_client_id>
&products=company directory individual employment payment pay_statement
&redirect_uri=https://example.com
&manual=true
```

<!-- theme: info -->
>For Assisted Integrations, your users will see instructions on how to manually connect their employment systems in Finch Connect.

### Handling API Responses

#### 202 status code response

With Automated Integrations, you can create an **`access_token`** and immediately use it to pull in data or push changes to your users' systems. However, with Assisted Integrations, there is a short delta from when the **`access_token`** is created to when you can use it to make data requests (`/employer`).

Until the **`access_token`** is ready for use, Finch will return an empty response from data endpoints with the HTTP status code **`202`** indicating the request is valid but data is still pending. When the **`access_token`** is ready, data endpoints will return data with the HTTP status code **`200`** as usual.

#### Finch-Data-Retrieved header

Since the data is retrieved and refreshed on a periodic cadence, you may want to know the freshness of the data returned by an API call. You can use the **`Finch-Data-Retrieved`** [header](../Development-Guides/Headers.md) to get the date and time in ISO-8601 format the data was retrieved.

### Monitoring the status of your Assisted API connections

To view the status of your connected employers, you can use the [Finch Developer Dashboard](https://dashboard.tryfinch.com/) and navigate to the connection details page for a given employer.

| STATUS | DESCRIPTION |
| --- | --- |
| Pending | The employer has created a token, and we are waiting for access to its provider. |
| Processing | We have received an invitation from the employer's provider with the correct permissions and are in the process of pulling their data for the first time. |
| No Account Set Up | The employer has created a token, but we have not received an invitation to its system. Please instruct the employer to follow the instructions in Finch Connect to add Finch as a third-party admin. |
| Improper Permissions | The employer has added Finch successfully, but with improper permissions. Please instruct the employer to re-add Finch following the instructions in Finch Connect. |
| Connected | The connection is set up and Finch is able to access the required data. |
| Disconnected | All accounts for this employer have been disconnected. |

You can also use the `connection_status` on the [`/introspect`](https://developer.tryfinch.com/docs/reference/eee6e798b0f93-introspect) endpoint to see the connection status of the assisted account.
```json
{
  ...
  "authentication_methods": [
    {
      "type": "assisted",
      "connection_status": {
        "status": "pending",
        "message": "The employer has created a token, and we are waiting for access to its provider."
      }
    },
    ...
  ],
  ...
}
```
