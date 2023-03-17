# Auth Fallback

Auth Fallback allows employers to authorize through Finch Connect even when Finch is experiencing intermittent issues with provider integrations. This feature applies only to credential authorization methods, and not to other authorization methods like direct API token entry or OAuth. 

If an employer attempts to authorize through Finch Connect’s automated flow and receives an error, after three attempts*, Finch Connect will display instructions for the employer to connect Finch manually. This entails the employer adding Finch as a third-party user to the employer’s system. Once Finch has accepted the invite and set up the account, the data for this connection will flow through the Finch API just as it does for every other automated connection. The only key difference is that until the connection is set up on Finch’s side, **your application will receive a 202 response when making requests with that token.**

For ADP Workforce Now specifically, Finch offers this auth method exclusively. These connections function exactly as above, but rather than being a fallback, there is no fully automated auth method for ADP Workforce Now.

*the number of errors before presenting the fallback screen is configurable. Currently it is set to three for every provider, but we may adjust this value over time.

**Can I opt out?**

Yes, this is an opt-in feature. If you choose not to opt in, the tradeoff is that when these intermittent issues do occur, your customers will have no way of connecting their accounts until the issues are resolved.

**Note that if you choose not to opt in, Finch’s ADP Workforce now integration not be available to your customers through Finch Connect.**

**Why do auth issues occur?**

Auth issues occur for a variety of reasons. The provider backends that Finch is integrating with are often legacy systems, meaning they can often be unreliable. Finch attempts to smooth over these gaps in provider systems with our [data sync](../Development-Guides/Data-Syncs.md) functionality for serving API requests. This fallback is intended to serve the same purpose for employer authorization.

**What is Finch doing to mitigate auth issues?**

Finch is actively working with providers to improve authentication reliability, including 1) better defining integration behavior and 2) building more robust integration access points via API. Finch also has dedicated resources on the engineering side to address issues immediately as they come up and work with providers to get to a solution as quickly as possible.