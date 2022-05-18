# Automated Connect Flow

Finch Connect is a front-end UI that allows your users to safely and securely grant your application access to their employment systems. Connect can be displayed in any part of your application and handles credential validation, multi-factor authentication, and error handling for each system we support.

<!--
focus: false
-->
![](../../assets/images/finchConnectIntro.png)

---

## Integrating Finch Connect into your product

To create the best experience for your users and ensure maximum conversion, you will want to consider the following questions when designing your user journey—

1. When should my user connect their employment system?
2. How should I launch Finch Connect for my user?
3. How do I incentivize my user to connect their system?

### When should my user connect?

We recommend asking your user to connect when they are onboarding onto your application for the first time because prompting them to connect later takes considerable effort to have them log on again. Since Finch maintains long-lived access, your users will not need to go through any additional effort after the initial onboarding.

### How should I display Finch Connect?

#### Default flow
In the default flow, your user is shown an employment system selector page where they can choose which system they use. 

<!--
focus: false
-->
![](../../assets/images/integratingConnect1B.png)

#### Selector bypass flow
If you already know which system your user uses or want to build your own selector page, you can bypass the selector page by using the `payroll_provider` option while opening Finch Connect.

<!--
focus: false
-->
![](../../assets/images/integratingConnect2B2X.png)

### How do I incentivize my user to connect their system?

To improve conversion, it is important to set user expectations before opening Finch Connect. We recommend letting the user know they will be asked to connect their employment system and, importantly, why connecting is beneficial for them.

<!--
focus: false
-->
![](../../assets/images/improvingConnectConversion.png)

## Finch Connect in your user's onboarding

If you are integrating Finch into your onboarding flow, we recommend taking the request latencies of the underlying employment systems into consideration while designing the onboarding flow. You can read more about latencies [here](../Development-Guides/Response-Times.md).

Based on the data points your application needs during onboarding, we recommend the following flows—

1. For `/company` and/or `/directory` data points, you can design a synchronous flow where your user goes through Finch Connect, your application sends API requests to Finch, waits for the responses, and then renders the UI.
2. For data from other endpoints, we recomment _simulating_ a sychronous flow. Here, your user goes through Finch Connect and your application kicks off API requests in the background. While the requests are being resolved, your user goes through the rest of the onboarding flow. Finally, once the API requests are resolved, your application renders the appropriate UI, creating a sense of immediacy.
