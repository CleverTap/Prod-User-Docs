---
title: Send Test Personalization
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

In modern marketing, creating personalized campaigns is crucial for connecting with audiences. The Send Test Personalization feature streamlines this by enabling marketing teams to test campaigns with personalized values, ensuring a seamless display of tailored content. This empowers marketers to scrutinize individualized elements within the message with precision.

For example, if your campaign includes customized promotions, event details, or tailored offers, this feature helps you test and preview the seamless functionality of these personalized elements with an internal audience before sending them to your customers.

You can send test campaigns with personalized values using the _Preview & Test_ option from the campaign page. These values apply only to the test campaign and are not applied to campaigns sent to users.

<Image align="center" alt="Preview & Test Popup" border={true} caption="Preview & Test Popup" src="https://files.readme.io/2597389-Preview__Test.gif" width="90% " />

<Callout icon="📘" theme="info">
  #### Personalize _From_ and _Reply-to_ Fields

  You can also [personalize From and Reply-to fields](doc:create-message-sender-details#sender-details), a feature released in Private Beta, for the following providers: SendGrid, Amazon SES, and Generic SMTP setup. If you want access to this feature, contact your Customer Success Manager.
</Callout>

# Send Personalized Test Message

CleverTap provides the following three ways to select the users to send a personalized test message:

* **Select from Test Profiles**: In this case, you can select multiple [profiles that are marked as test profiles](doc:user-profiles#mark-a-user-profile-as-a-test-profile) and send a test message to them. In the preview section on the right, you can select a profile to view how the campaign renders for that specific user with their personalized values.

<Image align="center" alt="Select a Profile from the Test Profiles" border={true} caption="Select a Profile from the Test Profiles" src="https://files.readme.io/de6383f-Select_Test_Profiles-_1.png" width="95% " />

* **Search and Add from All Profiles**: In this case, you can select the email address, CleverTap ID, or identity of profiles already on your dashboard, and send them a test message.

<Image align="center" alt="Search and Add from All Profiles on the CleverTap Dashboard" border={true} caption="Search and Add from All Profiles on the CleverTap Dashboard" src="https://files.readme.io/212a96f-image.png" />

* **Email Address**: In this case, you can manually enter the email addresses of the profiles, not present on the CleverTap dashboard, to which you want to send a test message.

<Image align="center" alt="Manually Add Email Address " border={true} caption="Manually Add Email Address" src="https://files.readme.io/23fd956-Email_Address.png" width="95% " />

After configuring all the required fields, you can preview the campaign with personalized values for the selected user profile before sending. If you select multiple profiles for sending test messages, you can select the user from the dropdown under the _Preview_ section on the right to preview the message for that user.

<Image align="center" alt="Select User Profile to Preview Campaign with Personalized Values" border={true} caption="Select User Profile to Preview Campaign with Personalized Values" src="https://files.readme.io/4cbf819-image.png" />

<Callout icon="📘" theme="info">
  #### Note

  * You can add a maximum of 20 profiles in total for sending test messages using the following options: _Select From Test Profiles_ and _Search and Add from All Profiles_.
  * When using the _Email Address_ option, personalization placeholders render default values (except for Linked Content), as these email addresses are not associated with any user profiles on the CleverTap dashboard.
  * The _Inbox Previews_ and _Spam Reports_ will use default values.
</Callout>

# Send Test with Custom User Property Value

Consider a scenario where your message includes user properties, and you want to send a specific value for each property. For test emails, you can override the existing user property value by setting a custom value.

To send test messages with a custom user property value, perform the following steps:

1. Select the _Custom user property value for preview_ option. The profile properties used in the campaign message are displayed along with the default values.
2. Enter the Property Value you want to use for the test email. For example, if you want to personalize a campaign based on the user’s Language property, you can enter a specific value (such as English) to preview how the email renders for users with that language preference.
3. Click **Send Test**. The custom value you provide will be used to personalize the test email for all selected recipients, regardless of the actual value stored in the user profile.

<Image align="center" border={true} caption="Enable Custom User Property Value for Personalization" src="https://files.readme.io/9dd08a5d429d929c74deec580a41ee0fc1133087d135777100f7e729efb8dd2a-Enable_Custom_User_Property_Value_for_Personalization.gif" />

# Send Test with Event Personalization

Consider a scenario where your message includes event personalization, that is, you want to send a personalized value for the event properties in your message. You can only use the event properties of the triggering event you selected in the WHO section.

For sending test messages using selected profiles, CleverTap introduces Event Personalization features. There are two options for event personalization:

* **Default property**: This option allows the utilization of default values established in the campaign content. You can also modify the default value for the test message only.
* **Sample Property**: The top 20 event property values associated with the same event that occurred within the last five days are listed under the _Event Personalization_ section. You can select from the list or add the value that you want to send in your test message.

The value that you select here will be sent to all the selected profiles.

For example, if you are a subscription platform and you want to send a reminder campaign to your subscribers to resume watching the series from where they left off. Here, the event will be _Video Watched_, and the event property will be Series Name.

<Image align="center" alt="Event Personalization Example " border={true} caption="Event Personalization Example" src="https://files.readme.io/d75767a-Send_test_personalization_-_Email.gif" />

# Send Test Response

You can view the response details as soon as you send the test message. To do so, click **Send Test** from the _Preview & Test_ popup. The Send Test Response window opens, where all the response details are classified into the following categories. Click the + sign against each user to view all the details (refer to the following image):

* Details of the message sent successfully
* General Errors, if any
* Linked Content Response: You can copy the responses by clicking the ![](https://files.readme.io/7534549-Copy_icon.png) icon against the respective response.
* Liquid Tags Error, if any

<Image align="center" alt="Send Test Reponse" border={true} caption="Send Test Response Per User" src="https://files.readme.io/b3918f4-Send_Test_Response_Per_User_.png" />

This ensures a thorough examination of the test response, offering valuable insights into the success and potential errors associated with the sent test messages.
