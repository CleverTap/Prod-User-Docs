---
title: Outgrow
excerpt: >-
  Learn how to connect Outgrow with CleverTap to sync responses and enrich user
  profiles.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Outgrow](https://outgrow.co/) is an interactive content platform designed to create surveys, quizzes, calculators, and forms that drive engagement and generate qualified leads. With its no-code builder and customizable templates, Outgrow enables marketers to capture user data seamlessly across engagement channels.

Integrating Outgrow with CleverTap via Zapier allows you to:

- Automatically sync user responses from Outgrow into CleverTap.
- Create or update user profiles based on Outgrow submissions.
- Trigger CleverTap journeys, such as follow-up or thank-you campaigns, based on user actions.
- Enrich profiles by adding response attributes to CleverTap profiles for improved segmentation and personalization.

# Prerequisites for Integration

The following are the prerequisites for this integration:

- Access to your **Outgrow** account
- Access to an active **Zapier** account
- A CleverTap account with a valid **Account ID** and **Passcode**

# Integrate Outgrow with CleverTap Using Zapier

This integration connects Outgrow, Zapier, and CleverTap, ensuring that every user submission is automatically sent to CleverTap as profile updates or events. This enables real-time segmentation, automated campaigns, and personalized user engagement.

For example, you want to capture user details such as Name, Email, and Feedback through an Outgrow survey. The responses are then automatically sent to CleverTap via Zapier, enabling them to be used instantly for segmentation or campaign triggering.

The integration consists of the following four key steps:

1. [Create Passcode on CleverTap Dashboard](doc:outgrow#create-passcode-on-clevertap-dashboard)
2. [Create Interactive Content in Outgrow](doc:outgrow#create-interactive-content-in-outgrow)
3. [Configure CleverTap Campaign](doc:outgrow#configure-clevertap-campaign)
4. [Connect Outgrow and CleverTap via Zapier](doc:outgrow#connect-outgrow-and-clevertap-via-zapier)

## Create Passcode on CleverTap Dashboard

CleverTap uses a header-based authentication model to authenticate API requests. Every CleverTap API call must include Account ID and Passcode as request headers. To create a passcode, refer to [Create Account Passcode](https://developer.clevertap.com/docs/authentication#create-account-passcode).

## Create Interactive Content in Outgrow

You can capture user details such as Name, Email, and Feedback through an Outgrow survey embedded in a CleverTap campaign. To do so, perform the following steps:

1. Log in to your Outgrow dashboard and create the content type you want (such as a survey, quiz, or poll). For more information on creating interactive content in Outgrow, refer to [Introduction to The Outgrow Builder](https://support.outgrow.co/docs/studio).
2. Once the content is ready, select the _CONFIGURE_ tab.
3. Select _Launch in an Email_ and click **Copy** to copy the HTML Snippet\*\*.


<Image src="https://files.readme.io/cdfafb464c859f586d3110d9865d16072fa7beb5f2f727f883fdaf4a3e30429f-Screen_Recording_2025-07-14_at_12.31.29_PM_1.gif" alt="Copy HTML Snippet" align="center" width="75% " caption="Copy HTML Snippet" border={true} />


The snippet can be used to embed your Outgrow content in a CleverTap campaign.

## Configure CleverTap Campaign

Configure a CleverTap campaign to display your survey form inside the CleverTap campaign so users can respond directly without leaving the app or email. To do so, perform the following steps:

1. In the CleverTap dashboard, create a new [Email](doc:create-message-email) or [In-App Message](doc:create-message-in-app) campaign that supports HTML.
2. In the _What_ section, select _Email with rich media_ template and click **Source**.


<Image src="https://files.readme.io/91d335af2bd4a6a53d06c594d0be17ddbf64e3de5feeb190f7e973c2c55ed6e9-Screen_Recording_2025-07-14_at_12.36.30_PM_1.gif" alt="Custom HTML Template in CleverTap" align="center" width="75% " caption="Custom HTML Template in CleverTap" border={true} />


3. Replace the existing code with the HTML snippet copied from _Step 3_ of [Create Interactive Content in Outgrow](doc:outgrow#create-interactive-content-in-outgrow).
4. Add dynamic personalization using [Liquid tags](https://docs.clevertap.com/docs/personalize-message-webhooks#liquid-tags) to insert CleverTap profile attributes such as name and email.

   The following example shows how to populate query parameters using Liquid tags for CleverTap profile attributes:

```html
<iframe width="100%" height="900px" src="<outgrow_link>?name={{ Profile.name | default: \"User\" }}&email={{ Profile.Email | default: \"user@example.com\" }}"></iframe>
```

5. Click **Preview and Test** to verify that the content renders correctly.
6. After verifying, publish the campaign only after configuring the Zap as [Create/Update User Profiles](doc:outgrow#createupdate-user-profiles) or [Upload Event](doc:outgrow#upload-event).

## Connect Outgrow and CleverTap via Zapier

Zapier acts as a bridge between Outgrow and CleverTap. When a user submits a response, Zapier captures it and sends the data to CleverTap in real time. You can either update user profiles or log submissions as events.

The integration supports the following two use cases:

- [Create/Update User Profiles](doc:outgrow#createupdate-user-profiles)
- [Upload Event](doc:outgrow#upload-event)

### Create/Update User Profiles

Use this option to update user profiles in CleverTap with Outgrow responses for personalization and segmentation. To do so, perform the following steps:

1. Log in to the [Zapier dashboard](https://zapier.com/app/home) and click **+ Create Zap**. Zapier can connect various applications, including Outgrow.


<Image src="https://files.readme.io/830b60a9c8f926bca524bfae5fa8a9aa021dad3d7e712f438b95c0486994e000-image.png" alt="Create a Zap on Zapier Dashboard" align="center" width="75% " caption="Create a Zap on Zapier Dashboard" border={true} />


2. **Set up a Trigger** in Zapier to start the workflow when a user submits a response in Outgrow. To do so, perform the following steps:
   1. Select Outgrow from the App section. This starts the Zap when a trigger event occurs on Outgrow.
   2. Select _Trigger Event_ from the dropdown list, then select the appropriate event for this use case.
   3. Select Account and sign in using your Outgrow account credentials.


<Image src="https://files.readme.io/2c5275b198e5947496f2e668b05c22c5a8bfda877fc0e28969f806c49e5e551c-image.png" alt="Set Up Trigger Event" align="center" width="75% " caption="Set Up Trigger Event" border={true} />


3. Click **Test Trigger**. This ensures that the correct account is connected and the trigger is set up correctly.<br />After testing the trigger, you will see a sample of the most recent responses to the form.


<Image src="https://files.readme.io/05746faf45694c70d54370287a2e6be540c990239babc49f8b720cfd36154814-dd84be73-d931-4fd4-b519-0ed7892c2747.png" alt="Details of Pulled Records" align="center" width="50% " caption="Details of Pulled Records" border={true} />


4. Click **Continue with selected record**.
5. **Select the Action** that the zap must perform after the trigger event occurs. To do so, perform the following steps:
   1. Select _CleverTap_ from the _App_ dropdown.
   2. Select _Create/Update User Profile_ from the Action event dropdown. This implies that whenever a new response is generated, a new user profile is created, or an existing user profile is updated with the new information.
   3. Select _Account_ to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account. Enter the same passcode you obtained during the [Create a Passcode on CleverTap Dashboard](doc:outgrow#create-passcode-on-clevertap-dashboard) step.
   4. Click **Continue** after successfully connecting your account.


<Image src="https://files.readme.io/56eca313456b36ad4977c1ad6ae44025ddb3ddb09334ce3e143c72eb36c61c54-2025-10-05_12-17-25_1.gif" alt="Select the Action for Zap" align="center" width="75% " caption="Select the Action for Zap" border={true} />


6. **Configure the Action**. Map Outgrow data fields to CleverTap fields as follows:

| CleverTap Field    | Outgrow Field                                                                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Identity           | Outgrow user ID field, the email ID, or any Unique identity field corresponding to the user.                     |
| Object ID          | Unique identifier for the user.                                                                                  |
| Creation Date      | Date of the user’s creation in Outgrow.                                                                          |
| Profile Properties | Responses in JSON format (for example: `{"name": "Alex", "email": "alex@example.com", "interests": "Webinars"}`) |

<Callout icon="🚧" theme="warn">
  #### Mapping Identity and Object ID

  You can keep the Identity field blank if you provide an Object ID, and vice versa.
</Callout>

7. Click **Continue**, and click **Test Step** to test the Zap after mapping the fields.


<Image src="https://files.readme.io/577d4059c2ab5d94ca101e57af0a211d283959fcc408efefc45c7170276d69f3-image.png" alt="Test Zap" align="center" width="75% " caption="Test Zap" border={true} />


8. Click **Publish**. Also, publish the campaign you have created in [Configure CleverTap Campaign](doc:outgrow#configure-clevertap-campaign). After this, users will receive the survey you have created, and the responses will be reflected in your CleverTap dashboard. If the user doesn’t exist, a new user will be created.


<Image src="https://files.readme.io/7dbb8c68c217ef474abdc60133cfab4ad64e55ee6b30271693989ef06af97d81-image.png" alt="Verify on the CleverTap dashboard" align="center" width="75% " caption="Verify on the CleverTap dashboard" border={true} />


### Upload Event

Consider an example where you want to track form submissions as events in CleverTap instead of updating user profiles. This automation ensures that every submission is logged for analytics and segmentation.

1. Follow _Step 1_ to _Step 4_ from [Create/Update User Profiles](doc:outgrow#createupdate-user-profiles) to configure Outgrow as the trigger.
2. **Select the Action** that the zap must perform after the trigger event occurs. To do so, perform the following steps:

   1. Select _CleverTap_ from the _App_ dropdown.
   2. Select _Upload Event_ from the Action event dropdown.
   3. Select _Account_ to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account. Enter the same passcode you obtained during the [Create a Passcode on CleverTap Dashboard](doc:outgrow#create-passcode-on-the-clevertap-dashboard) step.
   4. Click **Continue** after successfully connecting your account.


<Image src="https://files.readme.io/f0cf2f86c09089d9993dd29b8ca95ff5c2fff6f8e467dfccf3a2733f40ff5bca-2025-10-05_12-26-06_1.gif" alt="Select the Action for Zap" align="center" width="75% " caption="Select the Action for Zap" border={true} />


3. **Configure the Action**. Map Outgrow data fields to CleverTap fields as follows:

| CleverTap Field  | Outgrow Field                                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------------ |
| User ID          | Outgrow user ID field or email                                                                                     |
| Object ID        | Unique identifier for the user.                                                                                    |
| Creation Date    | Date of the user’s creation in Outgrow.                                                                            |
| Event Name       | Select a descriptive event name (for example: `"Form Submitted"` or `"Webinar Registered"`)                        |
| Event Properties | Responses in JSON format (for example: `{"name": "Alex", "email": "alex@example.com", "topic": "AI Trends 2025"}`) |

<Callout icon="🚧" theme="warn">
  #### Mapping Identity and Object ID

  You can keep the Identity field blank if you provide an Object ID, and vice versa.
</Callout>

4. Click **Continue** and click **Test Step** to test the Zap after mapping the fields.
5. Click **Publish**. Also, publish the campaign you have created in [Configure CleverTap Campaign](doc:outgrow#configure-clevertap-campaign). Each submission will now be logged as an event in CleverTap.

# FAQs

### Can I use both profile updates and events together?

Yes. You can set up multiple Zaps: one to update user profiles and another to upload events. This way, you can both enrich CleverTap profiles with attributes and log submissions for analytics and campaign triggers.
