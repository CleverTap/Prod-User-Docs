---
title: SurveyMars
excerpt: >-
  Understand how to capture customer feedback using CleverTap integration with
  SurveyMars
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[SurveyMars](https://surveymars.com/) is an online survey platform that enables businesses to capture customer feedback through customizable forms and surveys. By integrating SurveyMars with CleverTap using Zapier, you can automatically sync survey responses with CleverTap to enrich user profiles, track engagement events, and trigger personalized campaigns based on customer feedback.

This integration enables you to:

* **Collect User Data Seamlessly**: Embed SurveyMars surveys into CleverTap campaigns (In-App, Email, or Web Popups)
* **Enrich User Profiles**
  Map survey responses to CleverTap user profiles to maintain [updated user attributes](doc:surveymars#createupdate-user-profiles).
* **Personalize Engagement**: Log survey submissions as events in CleverTap to segment users and trigger automated journeys.
* **Power Data-Driven Engagement**: Use survey responses to personalize messaging and enhance customer engagement strategies.

# Prerequisites for Integration

The following are required for this integration:

* Access to your **SurveyMars** account
* Access to an active **Zapier** account
* A CleverTap account with a valid **Account ID** and **Passcode**.

# Integrate SurveyMars with CleverTap Using Zapier

The integration involves the following four major steps:

1. [Create Passcode on CleverTap Dashboard](doc:surveymars#create-passcode-on-clevertap-dashboard).
2. [Create and Configure Survey in SurveyMars](doc:surveymars#create-and-configure-survey-in-surveymars).
3. [Configure CleverTap Campaign](doc:surveymars#configure-clevertap-campaign).
4. [Connect SurveyMars and CleverTap via Zapier](doc:surveymars#connect-surveymars-and-clevertap-via-zapier).

## Create Passcode on CleverTap Dashboard

CleverTap uses a header-based authentication model for API requests. Every CleverTap API call must include Account ID and Passcode as request headers. To create a passcode, refer to [Create Account Passcode](https://developer.clevertap.com/docs/authentication#create-account-passcode).

## Create and Configure Survey in SurveyMars

Create a survey form that captures user contact details, feedback, and preferences. To do so, perform the following steps:

1. Go to the SurveyMars dashboard and create a survey. For this example, create a simple survey that collects Name and Email ID. Save the survey.

<Image align="center" alt="Create survey" border={true} caption="Create Survey" src="https://files.readme.io/a7bd0ea5eb818ce831941ccec732f37c164a32c7bebae23cd6c8c1a6cb5af0a5-83271674-bf2c-44af-9798-14186aa55293.png" width="65% " />

2. Select the **Share** tab at the top. Here, you can find the link to the survey you created.

<Image align="center" alt="Share survey" border={true} caption="Share Survey" src="https://files.readme.io/90a281e3e8bc4b68b03545cf5dd17b9b3c5441a19ae526f1cf1e3d3b0b5e7a91-d0c1e271-a4c2-48cc-b2c7-c991d979ad8d.png" width="75% " />

3. Click **Copy Link** to copy the survey URL, which you will need for configuration in the CleverTap campaign.

<Image align="center" alt="Copy Survey Link" border={true} caption="Copy Survey Link" src="https://files.readme.io/bc3a317cf140615dfab785df938e27984014e4dc42af2eac53842c512f373e24-e3353b38-b8d6-4808-8f8d-112277b55f67.png" width="75% " />

## Configure CleverTap Campaign

Configure a CleverTap campaign to display your survey. This allows users to submit responses within the campaign. To do so, perform the following steps:

1. In the CleverTap dashboard, create a new [InApp Message](doc:create-message-in-app) campaign (you can also use [Email](doc:create-message-email) or [Web Popups](doc:create-message-web-popup) that support HTML).
2. In the _What_ section, select a **Custom HTML Template** such as _Interstitial_.

<Image align="center" alt="Custom HTML Templates" border={true} caption="Custom HTML Templates" src="https://files.readme.io/bba3ad2b5f24447d2d31901ac4b17efe32de2cadc35424f7d8ad323841e5869f-image.png" width="75% " />

3. Paste the following code below under the _Custom HTML_ section. And, replace `<survey url>` with the survey URL copied in _Step 3_ of [Create and Configure Survey in SurveyMars]().
   ```html
   <iframe src="<survey url>" style="width:100%; height:100%; border:none;"></iframe>
   ```

<Image align="center" alt="Preview and Test" border={true} caption="Preview and Test" src="https://files.readme.io/40789fed231cf5356cd66039da25d92416656f3468e05d82b2576bc1ff4ca043-90053d92-848a-4f6f-97cb-ed03663d51c7.png" width="65% " />

4. Click **Preview and Test** to verify that the form renders correctly.
5. Publish the campaign only after configuring the [Create/Update User Profiles](doc:surveymars#createupdate-user-profiles) or [Upload Event](doc:surveymars#upload-event) zap.

## Connect SurveyMars and CleverTap via Zapier

Zapier acts as the automation bridge between SurveyMars and CleverTap. Whenever a user submits a Survey response, Zapier captures the submission and forwards the data to CleverTap in real time. This allows you to:

* **Enrich or create user profiles** in CleverTap with the submitted attributes. For more information, refer to [Create/Update User Profiles](doc:surveymars#createupdate-user-profiles).
* **Track each submission as an event** for segmentation, analytics, and automated engagement campaigns. For more information, refer to [Upload Event](doc:surveymars#upload-event).

### Create/Update User Profiles

Consider an example where you want to automatically sync details captured in SurveyMars with CleverTap to drive personalized engagement. This ensures that each new submission updates the user’s CleverTap profile in real time. To do so, perform the following steps:

1. Log in to the [Zapier dashboard](https://zapier.com/app/home) and click **+ Create Zap**. Zapier can connect different applications, such as SurveyMars.

<Image align="center" alt="Create a Zap on Zapier Dashboard" border={true} caption="Create a Zap on Zapier Dashboard" src="https://files.readme.io/830b60a9c8f926bca524bfae5fa8a9aa021dad3d7e712f438b95c0486994e000-image.png" width="75% " />

2. **Set up a Trigger**. To do so, perform the following steps:
   1. Select SurveyMars from the App section. This starts the Zap when a trigger event occurs on SurveyMars.
   2. Select _Trigger Event_ from the dropdown list and then select _Get Responses_ for this use case.
   3. Select Account and sign in using your SurveyMars account credentials.

<Image align="center" alt="Set Up Trigger Event" border={true} caption="Set Up Trigger Event" src="https://files.readme.io/1a7a4bda3b2187022f9d74db43620107daf2bc7d8d0bf4a98a54ab1f8cfb7cc3-2025-09-05_21-46-52_1.gif" width="75% " />

3. Click **Test Trigger**. This ensures that the correct account is connected and the trigger is set up correctly.  
   After testing the trigger, you will see a sample of the most recent responses to the form.

<Image align="center" alt="Details of Pulled Records" border={true} caption="Details of Pulled Records" src="https://files.readme.io/09baef611e4f861daf5f6eb9865d9fc109bc3ff8cbdce20f339c6a3a8c83574d-2d296ef8-1c40-4b73-b523-0ef9bb8d06f6.png" width="50% " />

4. Click **Continue with selected record**.
5. **Select the Action** that the zap must perform after the trigger event occurs. To do so, perform the following steps:
   1. Select _CleverTap_ from the _App_ dropdown.
   2. Select _Create/Update User Profile_ from the Action event dropdown. This implies that whenever a new response is generated, a new user profile is created, or an existing user profile is updated with the new information.
   3. Select _Account_ to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account. Enter the same passcode you obtained during the [Create a Passcode on CleverTap Dashboard](doc:surveymars#create-a-passcode-on-the-clevertap-dashboard) step.
   4. Click **Continue** after successfully connecting your account.

<Image align="center" alt="Select the Action for Zap" border={true} caption="Select the Action for Zap" src="https://files.readme.io/dba482ac8138d93d8a723ee4e1d3f861a213104d5443681f213620f54b09b611-2025-09-05_21-53-23_1.gif" width="75% " />

6. **Configure the Action**. Map SurveyMars data fields to CleverTap fields as follows:

| CleverTap Field    | SurveyMars Field                                                      |
| ------------------ | --------------------------------------------------------------------- |
| Identity           | Email or unique user identifier                                       |
| Object ID          | Leave blank if Identity is provided                                   |
| Creation Date      | Submission date or timestamp                                          |
| Profile Properties | Map survey response fields such as name, email, feedback, or ratings. |

<Callout icon="🚧" theme="warn">
  #### Mapping Identity and Object ID

  You can keep the Identity field blank if you provide an Object ID, and vice versa.
</Callout>

7. Click **Continue**, and click **Test Step** to test the zap after mapping the fields.

<Image align="center" alt="Test Zap" border={true} caption="Test Zap" src="https://files.readme.io/577d4059c2ab5d94ca101e57af0a211d283959fcc408efefc45c7170276d69f3-image.png" width="65% " />

8. Click **Publish**. Also, publish the campaign you have created in [Configure CleverTap Campaign](doc:surveymars#configure-clevertap-campaign). After this, users will receive an InAapp campaign as shown below, and the responses will be sent back to CleverTap via Zapier.

<Image align="center" alt="In-app message" border={true} caption="In-App Message" src="https://files.readme.io/e1b4c3a146a142513b93c125f3c3bc4f322cb0364bfd55c1bdbbf7d515efcf5e-7e7b2a39-131c-489b-97c8-256a3da42268.png" width="25% " />

### Upload Event

Consider an example where you want to track form submissions as events in CleverTap instead of updating user profiles. This automation ensures that every submission is logged for analytics and segmentation.

1. Follow _Step 1_ through _Step 4_ from [Create/Update User Profiles](doc:surveymars#createupdate-user-profiles) to configure SurveyMars as the trigger.
2. **Select the Action** that the zap must perform after the trigger event occurs. To do so, perform the following steps:

   1. Select _CleverTap_ from the _App_ dropdown.
   2. Select _Upload Event_ from the Action event dropdown.
   3. Select the Account to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account. Enter the same passcode you obtained during the [Create Passcode on CleverTap Dashboard](doc:surveymars#create-passcode-on-clevertap-dashboard) step.
   4. Click **Continue** after successfully connecting your account.

<Image align="center" alt="Select the Action for Zap" border={true} caption="Select the Action for Zap" src="https://files.readme.io/a0c3fa9b383eddbb482fe7e7a43f5b2dec1ae81ac92b24c0497a564b41142dd6-2025-09-05_21-53-23_1.gif" width="75% " />

3. **Configure the Action**. Map SurveyMars data fields to CleverTap fields as follows:

| CleverTap Field  | SurveyMars Field                                                              |
| ---------------- | ----------------------------------------------------------------------------- |
| User ID          | Email or unique user identifier.                                              |
| Event Name       | Descriptive event name, such as "Form Submitted" or "Feedback Captured".      |
| Creation Date    | Submission timestamp.                                                         |
| Event Properties | Responses in JSON format (for example, answers, ratings, campaign reference). |

<Callout icon="🚧" theme="warn">
  #### Mapping Identity and Object ID

  You can keep the Identity field blank if you provide an Object ID, and vice versa.
</Callout>

4. Click **Continue** and click **Test Step** to test the zap after mapping the fields.
5. Click **Publish**.

Once published, every new survey response submission will automatically appear in CleverTap as an event, enabling deeper analytics, segmentation, and campaign targeting.

# FAQs

### Can I embed SurveyMars in Email or Web Popups?

Yes. The integration works with any CleverTap campaign that supports custom HTML, including **Email**, **Web Popups**, and **In-App Messages**.