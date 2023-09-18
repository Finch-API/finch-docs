---
stoplight-id: zz1jt69h6o6be
---

# Deel Onboarding Guide

<!--
focus: false
-->
![deel-setup-diagram.png](<../../../../assets/images/deelSetupDiagram.png>)

Integrating with Deel through Finch is a simple 3-step process! To get set up, you need to:

1. Create a Deel account
1. Create a Deel OAuth application
1. Connect your Deel OAuth application to Finch

This page explains each of these steps in detail. Happy integrating!

<!-- theme: success -->
> Integrating Deel via Finch makes your organization eligible for the Deel Partner Program. This includes go-to-market motions and revenue share opportunities with Deel. If you are interested or have already built an app, [**reach out here**](mailto:talaal.burny@deel.com?subject=Deel%20API%20Partner%20via%20Finch&body=Hi%2C%0D%0A%0D%0AWe%20are%20interested%20in%20building%20on%20the%20Deel%20API%20and%20would%20like%20to%20know%20more%20about%20your%20API%20Partner%20Program.%0D%0A%0D%0AThanks.) to learn more about the program.

## Step 1: Create a Deel account

If your company does not already have an account with Deel, you’ll need to create one. To create an account, follow the instructions below.

1. Navigate to https://app.deel.com/signup in your browser
1. Select the **I’m A Business** option and click **Next**

    <!--
    focus: false
    -->
    ![deel_signup_1_whitespace.png](<../../../../assets/images/deel_signup_1_whitespace.png>)

1. Either **Sign Up Using Google SSO** or fill in the form below and select **Create Your Deel Account**

    <!--
    focus: false
    -->
    ![deel_signup_2_whitespace.png](<../../../../assets/images/deel_signup_2_whitespace.png>)

1. If your form was submitted successfully, you’ll be taken to a confirmation page. You should now have received an email confirmation in your inbox. Open this email and follow the ensuing instructions to log into your generated account.

    <!--
    focus: false
    -->
    ![deel_signup_3_whitepace.png](<../../../../assets/images/deel_signup_3_whitepace.png>)

1. After logging into your account, follow the ensuing instructions to complete your account setup. When prompted with the solutions selection page, you may select **Skip**, and proceed with the remaining steps to complete your setup.

    <!--
    focus: false
    -->
    ![deel_signup_4_whitespace.png](<../../../../assets/images/deel_signup_4_whitespace.png>)

1. Voila! Your account setup is now complete! You should now be looking at your Deel home page, which should look something like the screenshot below.

    <!--
    focus: false
    -->
    ![deel_homepage_whitespace.png](<../../../../assets/images/deel_homepage_whitespace.png>)


## Step 2: Create a Deel OAuth application

> To create a Deel OAuth application, you must be an **Organization Admin** or an **IT Developer Admin**.
>
>**Organization Admin:** The highest level of visibility and permissions. Can manage all aspects of the organization. This includes everything from members, billing, and other organization-wide settings.
>
>**IT Developer Admin:** Can build apps using Deel's API or subscribing to webhooks. They can also set up any native integration.
>
>More details can be found [**here**](https://help.letsdeel.com/hc/en-gb/articles/13916824207505-How-To-Add-Organization-Admins).

You’ll need to create and publish a Deel app for your customers to authorize your access to their data. Deel uses OAuth 2.0’s authorization code grant flow to issue access tokens that grant access to specific groups of data. Please consult [Deel’s public documentation](https://developer.deel.com/docs/oauth2) for more information on the OAuth2 flow.

Follow the instructions below to create and publish your Deel OAuth application.

1. Log into your organization’s Deel account. If you do not already have a Deel account, please follow the instructions laid out in the **Create a Deel Account** section.

1. Follow Deel’s [Create an App](https://developer.deel.com/docs/oauth2-apps#create-an-app) guide to create your app. Be sure to set your app type to **Organization**!

    <!--
    focus: false
    -->
    ![deel_createapp_form_whitespace.png](<../../../../assets/images/deel_createapp_form_whitespace.png>)
    
    > **IMPORTANT:** Copy and store your app secret (client secret) as it won't show again!

    <!--
    focus: false
    -->
    ![deel_credentials_view_whitespace.png](<../../../../assets/images/deel_credentials_view_whitespace.png>)
    
1. Follow Deel’s [Publish an App](https://developer.deel.com/docs/oauth2-apps#publish-an-app) guide to publish the app you just created. In production, all apps are submitted for review by default so you don’t need to do anything for this step to initialize the publishing process. You may need to wait a few business days for Deel to officially publish your app.


## Step 3: Connect your Deel OAuth application to Finch

The final step in your process is to configure your Deel integration with Finch. To do this, please reach out to your Developer Success representative, or reach out to **developers@tryfinch.com** with the following email subject and body.

> **Subject:** Ready to configure Deel OAuth with Finch
>
> **Body:**
> Hi Finch team!
>
> We have successfully created an OAuth application in Deel and are ready to have it connected with Finch.
>
> \- Your company name

Upon receipt of this email, Finch will initiate the process for securely submitting your OAuth app’s credentials. Once this is done and your Deel OAuth app has been connected with Finch, you’ll receive confirmation from your Developer Success representative that your integration is all set and ready to go! 🚀 🙌