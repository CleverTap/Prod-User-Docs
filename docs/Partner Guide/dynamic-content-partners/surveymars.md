---
title: SurveyMars
excerpt: >-
  Understand how to capture customer feedback using CleverTap integration with
  SurveyMars.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[SurveyMars](https://surveymars.com/) is an online survey platform that enables businesses to capture customer feedback through customizable forms and surveys.

The integration with CleverTap works in two parts:

- **Embed a survey in a CleverTap campaign (Required):** Create a survey in SurveyMars and display it within any CleverTap campaign that supports custom HTML, such as In-App, Email, or Web Popup. Responses are collected and stored in SurveyMars.
- **Sync responses to CleverTap via Zapier (Optional):** Automatically forward every survey submission to CleverTap in real time, either as a user profile update or as an event.

This integration enables you to:

- **Collect User Data:** Embed SurveyMars surveys into CleverTap campaigns (In-App, Email, or Web Popups).
- **Enrich User Profiles:** Map survey responses to CleverTap user profiles to maintain updated user attributes. (Requires Part 2)
- **Personalize Engagement:** Log survey submissions as events in CleverTap to segment users and trigger automated journeys. (Requires Part 2)
- **Power Data-Driven Engagement:** Use survey responses to personalize messaging and enhance customer engagement strategies.

## Prerequisites

Before setting up the integration, ensure the following accounts and access are available.

**For embedding a survey in a CleverTap campaign:**

- Access to your SurveyMars account.
- A CleverTap account with permission to create campaigns.

**For syncing responses to CleverTap via Zapier (optional):**

- All of the above.
- Access to an active Zapier account.
- A CleverTap account with a valid Account ID and Passcode. To create a passcode, refer to [Create Account Passcode](doc:create-account-passcode).

## Set Up SurveyMars for Integration

The following steps walk you through creating a survey in SurveyMars and retrieving its shareable URL for use in a CleverTap campaign.

1. Go to the SurveyMars dashboard and create a survey. For this example, create a simple survey that collects Name and Email ID. Click **Save** to save the survey.


<Image src="https://files.readme.io/a7bd0ea5eb818ce831941ccec732f37c164a32c7bebae23cd6c8c1a6cb5af0a5-83271674-bf2c-44af-9798-14186aa55293.png" alt="Create survey" align="center" width="65%" caption="Create Survey" border={true} />

2. Select the **Share** tab at the top. Here, you can find the link to the survey you created.


<Image src="https://files.readme.io/90a281e3e8bc4b68b03545cf5dd17b9b3c5441a19ae526f1cf1e3d3b0b5e7a91-d0c1e271-a4c2-48cc-b2c7-c991d979ad8d.png" alt="Share survey" align="center" width="75%" caption="Share Survey" border={true} />


3. Click **Copy Link** to copy the survey URL. You will need this URL when configuring the CleverTap campaign.


<Image src="https://files.readme.io/bc3a317cf140615dfab785df938e27984014e4dc42af2eac53842c512f373e24-e3353b38-b8d6-4808-8f8d-112277b55f67.png" alt="Copy survey link" align="center" width="75%" caption="Copy Survey Link" border={true} />


## Configure SurveyMars in CleverTap

Configuring a CleverTap campaign to display your SurveyMars survey requires embedding the survey URL in a custom HTML template.

1. In the CleverTap dashboard, create a new **InApp Message** campaign. You can also use **Email** or **Web Popups** campaigns that support HTML.

2. In the **What** section, select a Custom HTML Template such as **Interstitial**.


<Image src="https://files.readme.io/bba3ad2b5f24447d2d31901ac4b17efe32de2cadc35424f7d8ad323841e5869f-image.png" alt="Custom HTML Templates" align="center" width="75%" caption="Custom HTML Templates" border={true} />


3. Paste the following code into the **Custom HTML** section. Use the survey URL copied in Step 3 of [Set Up SurveyMars for Integration](#set-up-surveymars-for-integration).

```html
<iframe src="https://surveymars.com/q/qnizAKvB" style="width:100%; height:100%; border:none;"></iframe>
```

4. Click **Preview and Test** to verify that the form renders correctly.


<Image src="https://files.readme.io/40789fed231cf5356cd66039da25d92416656f3468e05d82b2576bc1ff4ca043-90053d92-848a-4f6f-97cb-ed03663d51c7.png" alt="Preview and Test" align="center" width="65%" caption="Preview and Test" border={true} />


<Callout icon="📘" theme="info">
  #### Planning to Sync Responses to CleverTap?

  Zapier processes only responses submitted after your Zap is turned on. If you plan to complete the optional Zapier sync, publish this campaign only after your Zap is live. If you are using the survey embed on its own, you can publish the campaign immediately.
</Callout>

5. Click **Publish**.

After the campaign is published, users receive the survey within the campaign and can submit their responses directly, as shown in the following example.


<Image src="https://files.readme.io/e1b4c3a146a142513b93c125f3c3bc4f322cb0364bfd55c1bdbbf7d515efcf5e-7e7b2a39-131c-489b-97c8-256a3da42268.png" alt="In-app message" align="center" width="25%" caption="In-App Message" border={true} />


All submitted responses are available in your SurveyMars account under the **Results** tab. To send each response to CleverTap automatically, proceed to [Sync Survey Responses to CleverTap](#sync-survey-responses-to-clevertap).

## Sync Survey Responses to CleverTap

<Callout icon="📘" theme="info">
  #### Optional Section

  This section is optional. Complete it only if you want to automatically forward survey submissions to CleverTap as user profile updates or events. The survey embed in [Configure SurveyMars in CleverTap](#configure-surveymars-in-clevertap) works independently without this step.
</Callout>

Zapier acts as the automation bridge between SurveyMars and CleverTap. Whenever a user submits a survey response, Zapier captures the submission and forwards the data to CleverTap in real time. This allows you to:

- Enrich or create user profiles in CleverTap with the submitted attributes. For more information, refer to [Create/Update User Profiles](#createupdate-user-profiles).
- Track each submission as an event for segmentation, analytics, and automated engagement campaigns. For more information, refer to [Upload Event](#upload-event).

You can configure either automation or both, depending on your use case.

### Create/Update User Profiles

Configuring a Create/Update User Profiles Zap ensures that each new SurveyMars submission updates the corresponding CleverTap user profile in real time.

1. Log in to the [Zapier dashboard](https://zapier.com) and click **+ Create Zap**.


<Image src="https://files.readme.io/830b60a9c8f926bca524bfae5fa8a9aa021dad3d7e712f438b95c0486994e000-image.png" alt="Create a Zap on Zapier Dashboard" align="center" width="75%" caption="Create a Zap on Zapier Dashboard" border={true} />


2. Set up a Trigger:

   a. Select **SurveyMars** from the **App** section. This starts the Zap when a trigger event occurs on SurveyMars.

   b. Select **Trigger Event** from the dropdown list and select **Get Responses** for this use case.

   c. Select **Account** and sign in using your SurveyMars account credentials.


<Image src="https://files.readme.io/1a7a4bda3b2187022f9d74db43620107daf2bc7d8d0bf4a98a54ab1f8cfb7cc3-2025-09-05_21-46-52_1.gif" alt="Set Up Trigger Event" align="center" width="75%" caption="Set Up Trigger Event" border={true} />


3. Click **Test Trigger**. This ensures that the correct account is connected and the trigger is set up correctly.

   After testing the trigger, you will see a sample of the most recent responses to the form.


<Image src="https://files.readme.io/09baef611e4f861daf5f6eb9865d9fc109bc3ff8cbdce20f339c6a3a8c83574d-2d296ef8-1c40-4b73-b523-0ef9bb8d06f6.png" alt="Details of Pulled Records" align="center" width="50%" caption="Details of Pulled Records" border={true} />


4. Click **Continue with selected record**.

5. Select the Action the Zap performs after the trigger event occurs:

   a. Select **CleverTap** from the **App** dropdown.

   b. Select **Create/Update User Profile** from the **Action event** dropdown. Whenever a new response is generated, a new user profile is created, or an existing user profile is updated with the new information.

   c. Select **Account** to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account, including the passcode from the CleverTap dashboard. Refer to [Create Account Passcode](doc:create-account-passcode) if you have not yet created one.

   d. Click **Continue** after successfully connecting your account.


<Image src="https://files.readme.io/dba482ac8138d93d8a723ee4e1d3f861a213104d5443681f213620f54b09b611-2025-09-05_21-53-23_1.gif" alt="Select the Action for Zap" align="center" width="75%" caption="Select the Action for Zap" border={true} />


6. Configure the Action. Map SurveyMars data fields to CleverTap fields as follows:

<Callout icon="📘" theme="info">
  #### Mapping Identity and Object ID

  You can leave the Identity field blank if you provide an Object ID, and vice versa. Both fields cannot be left blank at the same time.
</Callout>

| CleverTap Field    | SurveyMars Field                                                     |
| ------------------ | -------------------------------------------------------------------- |
| Identity           | Email or unique user identifier                                      |
| Object ID          | Leave blank if Identity is provided                                  |
| Creation Date      | Submission date or timestamp                                         |
| Profile Properties | Map survey response fields such as name, email, feedback, or ratings |

7. Click **Continue**, then click **Test Step** to test the Zap after mapping the fields.


<Image src="https://files.readme.io/577d4059c2ab5d94ca101e57af0a211d283959fcc408efefc45c7170276d69f3-image.png" alt="Test Zap" align="center" width="65%" caption="Test Zap" border={true} />


8. Click **Publish** to turn on the Zap. If you have not yet published the CleverTap campaign from [Configure SurveyMars in CleverTap](#configure-surveymars-in-clevertap), publish it now. Every new survey response submitted through the campaign is sent to CleverTap via Zapier, creating or updating the corresponding user profile in real time.

### Upload Event

Configuring an Upload Event Zap logs each SurveyMars submission as a CleverTap event, enabling analytics, segmentation, and campaign targeting based on survey activity.

1. Follow Steps 1 through 4 from [Create/Update User Profiles](#createupdate-user-profiles) to configure SurveyMars as the trigger.

2. Select the Action the Zap performs after the trigger event occurs:

   a. Select **CleverTap** from the **App** dropdown.

   b. Select **Upload Event** from the **Action event** dropdown.

   c. Select **Account** to connect the CleverTap account. The Zapier window opens. Enter all the required details to connect to the CleverTap account, including the passcode from the CleverTap dashboard. Refer to [Create Account Passcode](doc:create-account-passcode) if you have not yet created one.

   d. Click **Continue** after successfully connecting your account.


<Image src="https://files.readme.io/a0c3fa9b383eddbb482fe7e7a43f5b2dec1ae81ac92b24c0497a564b41142dd6-2025-09-05_21-53-23_1.gif" alt="Select the Action for Zap" align="center" width="75%" caption="Select the Action for Zap" border={true} />


3. Configure the Action. Map SurveyMars data fields to CleverTap fields as follows:

<Callout icon="📘" theme="info">
  #### Identifying the User

  Map User ID to the same identifier, such as email or a unique user ID, that exists on the CleverTap user profile. This ensures that each event is associated with the correct user.
</Callout>

| CleverTap Field  | SurveyMars Field                                                             |
| ---------------- | ---------------------------------------------------------------------------- |
| User ID          | Email or unique user identifier                                              |
| Event Name       | Descriptive event name, such as "Form Submitted" or "Feedback Captured"      |
| Creation Date    | Submission timestamp                                                         |
| Event Properties | Responses in JSON format (for example, answers, ratings, campaign reference) |

4. Click **Continue**, then click **Test Step** to test the Zap after mapping the fields.

5. Click **Publish**.

Once published, every new survey response submission appears in CleverTap as an event, enabling deeper analytics, segmentation, and campaign targeting.

## FAQs

### Q. Do I need Zapier to use SurveyMars with CleverTap?

No. Embedding the survey in a CleverTap campaign works without Zapier. Zapier is required only for syncing survey responses back to CleverTap as user profiles or events.

### Q. Can I embed SurveyMars in Email or Web Popups?

Yes. The integration works with any CleverTap campaign that supports custom HTML, including Email, Web Popups, and In-App Messages.

### Q. Are responses submitted before the Zap was published synced to CleverTap?

No. Zapier processes only new survey responses submitted after the Zap is turned on. Earlier responses remain available in SurveyMars under the **Results** tab.

<br />
