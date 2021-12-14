# Re-authentication

Finch aims to ensure your application maintains long-lived access to your users' employment systems. However, when a user changes security settings on their account or an employment system makes changes to its infrastructure, Finch's connection can get disconnected. This will result in an error with the HTTP status code of `401` and `finch_code` of `reauthenticate_user`. When an access token returns this, your user will need to re-authenticate by going through Finch Connect again. 

---

## General re-authentication flow

Finch recommends the following steps to handle re-authentication—

1. Catch `401` HTTP status code errors responses with the `finch_code` `reauthenticate_user` (see Finch API errors here) in your application while handling Finch API responses.
2. Construct the correct Finch Connect authorization URL for your user to re-authenticate. To create a more seamless experience, you can bypass the employment system selection page by using the `payroll_provider` parameter. You can find the `payroll_provider` of your user by calling the `/introspect` endpoint with their `access_token`.
3. Notify your user their connection has gone stale and they can resolve it by re-connecting their account. To increase conversion, we recommend letting your user know why re-connecting is beneficial to them and the services they will miss out on in the interim.
4. Once your user goes through Connect successfully, an authorization `code` is generated that you will need to exchange for a new `access_token` that you will use to send requests to the Finch API. Make sure to save this new token in your database. 

<!-- theme: info -->
> While you will have a new `access_token` for your user, everything else will remain the same. All Finch identifiers, like `individual_id` or `benefit_id`, are the same across tokens.

---
## Considerations

You will need to decide how to notify your users they have to re-connect and where you want to present the Finch Connect flow.

**Notifying users**

Finch recommends either using in-app or email notifications to notify your user there is an issue with their connection, why re-connecting is beneficial, and the steps they need to follow to re-connect.

**Presenting Finch Connect**

Below are a couple of options to present the re-connection flow to your users—

1. Prompt your user to log on to their application dashboard where you can present them UI to go through Finch Connect again. 
2. Send your user an authorization URL with a `redirect_uri` that redirects them back to their application dashboard after a successful reconnection. Learn more about redirecting your users to Connect here.