---
stoplight-id: laumymk97efgi
---

# Gusto Onboarding and Migration Guide

> **📣 Attention: Finch customers migrating to the new integration** 
> 
> To avoid interruptions to your service, please complete the migration process outlined below and have your customers reauthorize by **November 30th, 2023**.

In order to access to Gusto’s production API, all developers are subject to Gusto’s standard security and compliance review. As an official Gusto development partner, Finch will work closely with you to support you through your onboarding journey. The onboarding process consists of the following steps:

**[Step 1](#step-1-create-an-account-in-gustos-developer-portal):** Create an account in Gusto’s Developer Portal

**[Step 2](#step-2-complete-gustos-onboarding-questionnaire):** Complete the Gusto Onboarding Questionnaire

**[Step 3](#step-3-assist-gusto-security-review):** Complete Gusto's Security Review (VISO Trust)

**[Step 4](#step-4-id-migration-for-existing-users):** (Optional) Finch ID migration for existing users.

**[Step 5](#step-5-connect-your-employers):** Connect (or re-connect) employers.

If you have questions at any point during this onboarding or migration process, please don't hesitate to reach out to your Developer Success representative or developers@tryfinch.com.

---

### Step 1: Create an account in Gusto’s Developer Portal

**[5 minutes]**

Gusto requires that all developers be set up in their Developer Portal. Please [sign up for a DevPortal account here](https://dev.gusto.com/accounts/sign_up), and Finch will create and manage your Gusto DevPortal "organization" on your behalf.

<!--
focus: false
-->
![gusto-signup.gif](../../../../assets/images/gusto-signup.gif)

### Step 2: Complete Gusto’s Onboarding Questionnaire

**[30 minutes to 1 hour]**

The next step in the onboarding process is to fill out the [Finch + Gusto Onboarding Questionnaire](https://gusto.az1.qualtrics.com/jfe/form/SV_1Oob0rNZpUwhSoS?Partner=Finch). The questionnaire will ask you about your company, Gusto integration requirements, and your security and control environment (if you have physical security controls, if data is encrypted, etc.). Please **be sure to include all supporting documents** as they will be necessary for Gusto to complete the review.

The security requirements for each developer will depend upon the sensitivity of the data access requested. If you have a SOC 2 Type 2 Report, ISO 27001 Certificate, or PCI Certificate, you will be shown a simplified questionnaire and your review process will be expedited. **If you do not have one of these reports, and you require data access to sensitive PII (e.g., benefits data), please contact your Developer Success representative to discuss further.**

In rare cases, Gusto may not approve an application for production access for a reason other than security concerns, such as for a use case Gusto prohibits on their platform (e.g. mature content, etc.). We understand that answering the questionnaire can be time-consuming but it is a necessary step in ensuring that your application meets Gusto’s data security requirements.

### Step 3: Complete Gusto's Security Review (VISO Trust)

**[1 to 2 weeks]**

Once you've submitted the questionnaire, Gusto will conduct a security review via a third party called VISO Trust. The VISO Trust process typically takes one week. In most cases, nothing further will be needed from you; however, VISO Trust may reach out for additional information or clarification. Please respond to these requests timely, as any delays could impact when production access will be made available to you. 

Once you have been approved, the Gusto team will enable production access and issue credentials within their Developer Portal. Gusto will then apply your requested data scopes to your configuration, adhering to the security principle of least privilege. Finch will then activate the API integration for your account, and notify you once your integration has been successfully activated.

If you are not approved for production access for security reasons, Gusto will work with us and you to resolve those issues within a reasonable timeframe.

### Step 4: Finch ID Migration for Existing Users

**[1 to 2 weeks]**

> **Optional:** If you do not require Finch to maintain the same Finch IDs when migrating to the new integration, this step can be skipped and Finch can make your new Gusto integration available to employers immediately.

With the new integration, there will be some changes to the underlying data that Finch uses for generating [Finch IDs (UUIDs)](https://developer.tryfinch.com/docs/reference/82e937086502a-handling-api-responses) for employees, payments, and benefits. As such, you may experience a change in the Finch IDs that represent these entities. If you require that these Finch IDs remain stable, please follow the steps below:

1. Let your Developer Success representative know you wish to preserve the existing Finch IDs. Once we receive your Gusto OAuth credentials, we will temporarily pause new connections by removing Gusto from Finch Connect and discontinue any recurring data syncs.
1. We will work with Gusto to map your old IDs to new IDs, so that existing references are compatible with the API integration.
1. We will then reactivate your Gusto integration, add Gusto back as an integration option to Finch Connect, and invite your users to reauthorize the Finch connection.

### Step 5: Connect (or re-connect) Employers

Finch will be notified by Gusto as soon as your account credentials are ready. Finch will tehn notify you once your integration has been activated. Your employers can then go through Finch Connect and connect to their Gusto account to authorize your application for data access!

>**📣 Attention: Finch customers migrating to the new integration** 
>
> We suggest you notify employers that they will need to reauthorize through Finch Connect before November 30th, 2023 to avoid any service disruptions. 
>
> We understand that these changes may cause some inconvenience, and appreciate your partnership during this transition.


---

If you have questions at any point during this onboarding or migration process, please don't hesitate to reach out to your Developer Success representative or developers@tryfinch.com. We understand that this process can be complex and we are here to help you every step of the way. We look forward to working with you to provide a seamless integration with Gusto!