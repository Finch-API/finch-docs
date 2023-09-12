---
stoplight-id: laumymk97efgi
---

# Gusto Onboarding and Migration Guide

Before gaining access to Gusto’s production API, all developers are subject to Gusto’s standard security and compliance review. As an official Gusto development partner, Finch will work closely with you to support you through your onboarding journey. The onboarding steps are outlined below.

> If you are a current Finch customer using the existing Gusto integration, please note that end users must reauthorize into the improved integration by **November 30, 2023**. Finch’s legacy integration will be deprecated on that date.

### Step 1: Setup in Gusto’s Developer Portal

**[5 minutes]**

Gusto requires that all developers be set up in their Developer Portal. Finch offers a managed service by default where we will create and manage your DevPortal "organization" - all you need to do is [sign up for a DevPortal account](https://dev.gusto.com/accounts/sign_up), provide us with the corresponding email address and we’ll take it from there. Please reach out to your Success manager or developers@tryfinch.com if you have any questions.

### Step 2: Complete Gusto’s Onboarding Questionnaire

**[30 minutes to 1 hour]**

Please fill out this [Finch-specific onboarding questionnaire](https://gusto.az1.qualtrics.com/jfe/form/SV_1Oob0rNZpUwhSoS?Partner=Finch). The questionnaire will ask you about your company, Gusto integration requirements, and your security and control environment (such as whether you have physical security controls, if data is encrypted, etc.). Please ensure to include all supporting documents as they will be necessary for Gusto to complete the review.

The requirements for each developer will depend upon the sensitivity of the data access requested. If you have a SOC 2 Type 2 Report, ISO 27001 Certificate, or PCI Certificate, you will be shown a simplified questionnaire and your review process will be expedited. 
We understand that answering the questionnaire can be time-consuming but it is a necessary step in ensuring that your application meets Gusto’s data security requirements. In rare cases, Gusto may not approve an application for production access for a reason other than security concerns, such as for a use case Gusto prohibits on their platform (e.g. mature content, etc.). If you have questions on how to respond to a specific question, please don’t hesitate to reach out to  our Developer Success team.

### Step 3: Gusto Security Review

**[1-2 weeks]**

After you submit the questionnaire, Gusto will conduct a security review via a third party called VISO Trust. The VISO Trust process typically takes one week. In most cases, nothing further will be needed from you; however, in certain cases VISO Trust may reach out for additional information or clarification. 

Once you have been approved, the Gusto team will enable production access and issue credentials within their Developer Portal. Gusto will then apply the appropriate data scopes that were requested as part of the security questionnaire to your configuration, thereby adhering to the security principle of least privilege. Finch will be notified by Gusto to take those credentials and activate the API integration for your account. Finch will notify you once your integration has been successfully activated.

If you are not approved for production access for security reasons, Gusto will work with us and you to resolve those issues within a reasonable timeframe.

### Step 4: ID Migration for Existing Users

**[1 to 2 weeks]**

> **Optional:** If you do not require Finch to maintain the same Finch IDs when migrating to the new integration, the steps above can be skipped and Finch can make your new Gusto integration available to end users immediately.

Please note that with this migration, there will be some changes to the underlying data that Finch uses for generating [Finch IDs (UUIDs)](https://developer.tryfinch.com/docs/reference/82e937086502a-handling-api-responses) for employees, payments, and benefits. As such, your integration may experience a change in the Finch IDs that represent the aforementioned entities. If you currently rely on Finch IDs remaining stable, please follow the steps below to ensure their stability while migrating to the new integration:

1. Let your Developer Success representative know you wish to preserve the existing Finch IDs. Once we receive your Gusto OAuth credentials, we will temporarily pause new connections by removing Gusto from Finch Connect and discontinue any recurring data syncs.
1. We will work with Gusto to map your old IDs to new IDs, so that existing references are compatible with the API integration.
1. We will then reactivate your Gusto integration, add Gusto back as an integration option to Finch Connect, and invite your users to reauthorize the Finch connection.

### Step 5: Connect Your Clients!

Finch will be notified by Gusto as soon as your account credentials are ready for use to activate your API integration. Finch will notify you once your integration has been activated. Your clients can then go through Finch Connect and connect to their Gusto account to authorize your application for data access!


We understand that these changes may cause some inconvenience, and appreciate your partnership during this transition.

We hope this onboarding process guide is helpful. If you have any questions, please do not hesitate to reach out to your Finch Developer Success representative. We look forward to working with you to provide a seamless integration with Gusto. We understand that this process can be complex and we are here to help you every step of the way.