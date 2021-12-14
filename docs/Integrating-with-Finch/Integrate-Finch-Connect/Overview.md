# Overview

The first step to read data and push changes to your users employment systems is to integrate Finch Connect into your front-end. Connect provides a secure and elegant authorization flow for your users to grant your application access to their systems. 

The authorization flow on Connect consists of four steps—

1. **Open Finch Connect—** Your application launches Connect for your user to initiate the authorization flow.
2. **Obtain consent—** Connect prompts your user to log in to their employment system and grant your application access to the permissions you are requesting for.
3. **Retrieve the authorization code—** If your user successfully connects and grants your application access to their system, Connect will provide a short-lived authorization `code`.
4. **Exchange the code for an access token—** Before sending API requests to Finch, your application will exchange the short-lived `code` for a long-lived `access_token` that represents your application's access to your user's employment system.
**** 

## Adapter Connect to your front-end

There are two ways to integrate Connect into your application's UI. 

1. Your application can redirect your user's browser to Connect hosted by Finch on `https://connect.tryfinch.com`. To integrate with Connect like this, read more [here](./Embed-Connect.md).
2. Your application can open Connect in an embedded iframe using a Finch SDK. Your user will remain on your application's domain the entire time. To integrate with Connect like this, read more [here](./Redirect-to-Connect.md).