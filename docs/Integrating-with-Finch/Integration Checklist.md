# Integration Checklist

We recommend the following steps while planning and developing your Finch integration, from both a product and engineering perspective. The recommendations outlined below will ensure a seamless experience for your users, make your integration more robust and secure, and set you up for success when you launch into production.

## Integrating Finch Connect

Finch Connect is the front-end UI that allows your users to safely and securely grant your application access to their employment systems. Following these steps will optimize your Connect integration to increase conversion, improve your users’ experiences, and avoid common configuration errors.

- [ ]  Integrate Connect into your application's front end using [this](./Integrate-Finch-Connect/Overview.md) guide.

**Designing a seamless onboarding experience**

- [ ]  A well-designed user flow will carefully consider when and how to present Finch Connect to your users. We recommend you read the [Automated Connect Flow - Integrating connect into your product](../Product-Guides/Automated-Connect-Flow.md#integrating-connect-into-your-product) guide for more tips on this topic.
- [ ]  Displaying messaging to your customers prior to initiating Connect helps set expectations and increase conversion rates. You can read the [Automated Connect Flow - How to incentivize your user to connect their system](../Product-Guides/Automated-Connect-Flow.md#how-do-i-incentivize-my-user-to-connect-their-system) guide for more information.
- [ ]  If you add Connect to your users' onboarding flow as we'd recommend, read [Automated Connect Flow - Using Finch Connect in your onboarding flow](../Product-Guides/Automated-Connect-Flow.md#connect-in-your-users-onboarding) guide for recommendations on a UI flow to work around the request latencies of some systems.

**Supporting users with custom setups**

- [ ]  Some of your customers may use multiple employment systems. Read our [UI recommendations](../Best-Practices/Multi-account-Flow.md#presenting-connect) on how to best present this flow for your users.

**Configure authentication methods**

- [ ] Get in touch with your Finch representative if you would like [specific auth methods](docs/Product-Guides/Automated-Connect-Flow.md#authentication-method-configuration) displayed in Finch Connect, and we can manage it for you.

## Integrating Finch API

Given the nature of the underlying systems Finch's API is built on top of, the following steps are recommended to build a resilient integration.

- [ ]  Integrate Finch's API into your application's back-end using [this](./Integrate-the-Finch-API.md) guide.

**Sending API requests**

- [ ]  Integrate an external rate limiter into your application that respects Finch API's limits described [here](../Development-Guides/Rate-Limits.md).

**Handling API responses**

- [ ]  Most data points returned by the API are `null`able. Ensure your integration is resilient to this. You can read more [here](../Development-Guides/Handling-API-Response.md).

**Handling response headers**
- [ ] Finch syncs data with providers on a scheduled cadence, and the status of the data we return is available in the API response headers. Ensure your integration checks these response headers as needed. You can read more about data syncs and the associated response headers [here](../Development-Guides/Data-Syncs.md).

**Handling error responses**

Your application should expect and handle errors from the Finch API. You can read more about our errors [here](../Development-Guides/Errors/Error-Types.md). 

There are three important errors your application should be aware of.

- [ ]  Ensure there are user flows built to support `reauthentication_error`s, i.e. when your user needs to go through Finch Connect again to reconnect their employment system if their initial connection has gone stale. You can read more [here](../Best-Practices/Re-authentication.md).
- [ ]  Implement the troubleshooting tips to gracefully handle `server_error`s from Finch. You can read more [here](../Development-Guides/Errors/Error-Handling.md#500-internal-server-errors).
- [ ]  If you use our batch endpoints, ensure your application handles errors returned in the batch format. More information can be found [here](../Development-Guides/Errors/Error-Handling.md#batch-requests).

**Supporting users with custom setups**

- [ ]  Some of your customers may use multiple employment systems. This will involve [application logic](../Best-Practices/Multi-account-Flow.md#application-logic) and [database schema](../Best-Practices/Multi-account-Flow.md#flexible-database-schema) considerations on your end.

## Security

The data stored within your customers' systems are sensitive and should be handled using best security practices.

- [ ]  Store your `client_secret` in a back-end data store. It should never be exposed client-side. It is recommended to store it encrypted.
- [ ]  Since your `client_secret` should remain on the back-end, you should always perform an authorization `code` for an `access_token` exchange only on your back-end server and never on the client-side.
- [ ]  Save `access_token`s in a back-end data store against the users of your application. It should never be exposed client-side. It is recommended to store them encrypted.

## Storage and Logging

Storing and logging key identifiers will ensure a faster turnaround time when contacting Support about issues.

- [ ]  Each Finch `access_token` is associated with a static Finch `company_id`. You can find the id using the `/introspect` endpoint. Save this in your data store alongside the token and use it when contacting Support about an issue or while reconciling billing statements from Finch.
- [ ]  Each Finch API response returns a `Finch-Request-ID` in the headers. Use this when contacting Support about an issue.

## Auth Fallback and Email Forwarding

- [ ] Email forwarding to Finch allows you to provision a custom email address for some API integrations. Contact our team on Slack or send an email to `developers@tryfinch.com` to get started.

- [ ] With email forwarding set up, ask our team to opt in to [authentication fallback](../Product-Guides/Automated-Connect-Flow.md#authentication-fallback) to allow your customers better ability to authenticate through Finch Connect. This feature is only available to *Scale* tier customers.


## Testing Your Finch integration and Going Live

Before going live, it is valuable to know the options available for you to test your Finch integration. Below are the suggested steps. More detailed information is available [here](../Development-Guides/Testing.md).

- [ ]  Use the Finch Sandbox mode to test your integration against fake data.
- [ ]  Some payroll systems like Bamboo HR and Zenefits allow you to sign up for free demos. You can use these accounts to test against a real payroll system.
- [ ]  If your application requires write operations, send our team a message on Slack or `developers@tryfinch.com`.

Once you have tested your Finch integration with test accounts, you can go live.

- [ ]  Start small with a few, trusted customers.
- [ ]  Once your integration works as expected, launch the integration for all of your customers.

## Support

The following steps will ensure you and your team is set up for success once your Finch integration has gone live.

- [ ]  We currently use Jira to keep track of support tickets. Ensure your team is able to access a Jira-based website.
- [ ]  Learn how to use the Finch Developer Dashboard to keep track of your connected customers and the health of each connection.