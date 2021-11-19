# Integration checklist

We recommend the following steps while planning and developing your Finch integration, from both a product and engineering perspective. The recommendations outlined below will ensure a seamless experience for your users, make your integration more robust and secure, and set you up for success when you launch into production. 

## Integrating Finch Connect

Finch Connect is the front-end UI that allows your users to safely and securely grant your application access to their employment systems. Following these steps will optimize your Connect integration to increase conversion, improve your users’ experiences, and avoid common configuration errors.

- [ ]  Integrate Connect into your application's front end using this guide.

**Designing a seamless onboarding experience**

- [ ]  A well-designed user flow will carefully consider when and how to present Connect to your users. We recommend you read this guide for more tips on this topic.
- [ ]  If you add Connect to your users' onboarding flow as we'd recommend, read this guide for recommendations on a UI flow to work around the request latencies of some systems.
- [ ]  Displaying messaging to your customers prior to initiating Connect helps set expectations and increase conversion rates. You can read this guide for more information.

**Supporting users with custom setups**

- [ ]  Some of your customers may use multiple employment systems. This will involve considerations on your end. This guide presents a few recommendations.

## Integrating Finch API

Given the nature of the underlying systems Finch's API is built on top of, the following steps are recommended to build a resilient integration.

- [ ]  Integrate Finch's API into your application's back-end using this guide.

**Sending API requests**

- [ ]  Integrate an external rate limiter into your application that respects Finch API's limits described here.

**Handling API responses**

- [ ]  Most data points returned by the API are `null`able. Ensure your integration is resilient to this. You can read more here.

**Handling error responses**

Your application should expect and handle errors from the Finch API. You can read more about our errors here. 

There are three important errors your application should be aware of.

- [ ]  Ensure there are user flows built to support `reauthentication_error`s, i.e. when your user needs to go through Finch Connect again to reconnect their employment system if their initial connection has gone stale. You can read more here.
- [ ]  Implement the troubleshooting tips to gracefully handle `server_error`s from Finch. You can read more here.
- [ ]  If you use our batch endpoints, ensure your application handles errors returned in the batch format. More information can be found here.

**Supporting users with custom setups**

- [ ]  Some of your customers may use multiple employment systems. This will involve application logic and database schema considerations on your end. You can read this guide for detailed guidance.

## Security

The data stored within your customers' systems are sensitive and should be handled using best security practices.

- [ ]  Store your `client_secret` in a back-end data store. It should never be exposed client-side. It is recommended to store it encrypted.
- [ ]  Since your `client_secret` should remain on the back-end, you should always perform an authorization `code` for an `access_token` exchange only on your back-end server and never on the client-side.
- [ ]  Save `access_token`s in a back-end data store against the users of your application. It should never be exposed client-side. It is recommended to store them encrypted.

## Storage and Logging

Storing and logging key identifiers will ensure a faster turnaround time when contacting Support about issues.

- [ ]  Each Finch `access_token` is associated with a static Finch `company_id`. You can find the id using the `/introspect` endpoint. Save this in your data store alongside the token and use it when contacting Support about an issue or while reconciling billing statements from Finch.
- [ ]  Each Finch API response returns a `Finch-Request-ID` in the headers. Use this when contacting Support about an issue.

## Production Setup

The following steps will help create a white-labeled experience for your users.

- [ ]  Email forwarding to Finch is an enterprise-level feature that allows you to provision a custom email address for some API integrations. Contact our team on Slack or send an email to `developers@tryfinch.com` to get started.

## Testing your Finch integration and going live

Before going live, it is valuable to know the options available for you to test your Finch integration. Below are the suggested steps. More detailed information is available here.

- [ ]  Use the Finch Sandbox mode to test your integration against fake data.
- [ ]  Some payroll systems like Bamboo HR and Zenefits allow you to sign up for free demos. You can use these accounts to test against a real payroll system.
- [ ]  If your application requires write operations, send our team a message on Slack or `developers@tryfinch.com`.

Once you have tested your Finch integration with test accounts, you can go live.

- [ ]  Start small with a few, trusted customers.
- [ ]  Once your integration works as expected, launch the integration for all of your customers.

## Support

The following steps will ensure you and your team is set up for success once your Finch integration has gone live.

- [ ]  Get comfortable with Halp, our support ticket system. Finch aims to minimize errors but every now and then issues pop up due to the nature of the underlying employment systems. We currently use Slack and Halp to keep track of support tickets.
- [ ]  Learn how to use the developer dashboard to keep track of your connected customers and the health of each connection.