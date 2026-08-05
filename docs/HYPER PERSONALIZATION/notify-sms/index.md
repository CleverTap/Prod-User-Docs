---
title: Notify-SMS
excerpt: >-
  Learn how to set up and trigger real-time transactional SMS campaigns using
  Notify.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Notify is CleverTap's transactional messaging solution built for time-sensitive, user-specific communications such as OTPs, payment alerts, order confirmations, and password reset notifications. Notify delivers messages quickly through real-time API triggers with built-in retry logic.

<Callout icon="📘" theme="info">
  #### Private Beta

  Notify is currently in Private Beta. The SMS channel is available for the following providers: Generic and Infobip (with the SMS Direct addon). To enable this feature, contact your Customer Success Manager.
</Callout>

# Use Cases

The following use cases show how Notify enables real-time SMS communication to enhance user experience, strengthen security, and ensure operational clarity:

- **OTP Delivery for Login/Authentication**<br />Send time-sensitive OTPs to users to verify identity or enable secure login.<br />For example, a user tries to log in to a banking app and receives a 6-digit OTP via SMS.

- **Order Confirmation and Receipts**<br />Confirm purchases or bookings immediately by sending transactional SMS with order summaries.<br />For example, a travel booking site sends an order summary via SMS after successful payment.

- **Payment Success and Failure Notifications**<br />Inform users in real time about the status of their transactions to prevent confusion and avoid duplicate payments.<br />For example:
  - A credit card user receives an SMS notification confirming the successful payment.
  - In case of a failed transaction, the user receives an SMS stating that the payment was unsuccessful and providing guidance on the next steps or retrying.

- **Account and Password Reset Links**<br />Send secure password reset or account recovery links to users requesting access recovery.<br />For example:
  - When users click **Forgot Password** on a social media platform, they immediately receive an SMS with a password reset link that expires in 10 minutes.
  - Users trying to change their phone number receive a verification link via SMS to confirm the change.

- **Security Notifications**<br />Alert users instantly about critical changes to their accounts to detect and prevent unauthorized access.<br />For example, when a user logs in on a new device, the system sends an SMS notification.

# Create Notify Campaign

Trigger transactional SMS messages in real time in response to specific user actions.

To create a Notify campaign for the SMS channel, perform the following steps:

1. Go to _Notify_ from the CleverTap dashboard and click **Create Notify Campaign**. The _Setup_ pop-up opens.

2) Enter the campaign **Name** and click **Continue**. The _Channel Setup_ page opens.

3) Select **SMS** from the Channel section.


   <Image src="https://files.readme.io/7fb9c9cb795acb1e97f0114b544eeb8b207ecd9b75832932a8ecf77d02a5f722-image.png" align="center" caption="Set Up Channel" border={true} />


4. Select the SMS provider from the dropdown under _Provider Configuration_. You can also add a new provider by clicking **Add**. For more information, refer to [SMS Provider Setup](doc:sms-provider-operations).


   <Image src="https://files.readme.io/a52586ea5a070077ff5675071d65f884391bd0027f2effe0eeec09fa92595878-image.png" border={true} />


6) Click **Create Message** to create your campaign message as follows:
   1. Select a template or create your own template for your Notify SMS.
   2. Draft a message. For more information, refer to [SMS Editor](doc:create-message-sms). You can personalize messages in two ways:
      - **User Property Personalization**: Uses profile properties for personalization. For example, `{{Profile.name | default:"Shopper"}}`.
      - **Notify API Parameter Personalization**: Uses real-time values passed directly in the API request payload at the time of trigger. When you call the Notify API, you include an `notifyFields` object in the request body containing the key-value pairs you want to inject into the message. For example, if your payload includes `"notifyFields": {"orderID": "ORD-9821"}`, you can reference it in your message as `{{Notify.orderID | default:"Order number not available"}}`. CleverTap reads the value from the payload at send time and substitutes it into the message body. This is useful for personalizing SMS with transaction-specific data, such as order IDs, OTPs, or payment amounts, that are only available at the time of the API call. For more information, refer to [Notify API](doc:notify-api).


        <Image src="https://files.readme.io/f599ca2ed1552e7516f81cef12ee2a06368a6ef7051660d2dc9ed258fb57e145-image.png" align="center" caption="Create Message" border={true} />


7. Click **Done** to return to the _Campaign Setup_ screen. You can edit your Notify message at any point before generating the Notify ID.

8. Click **Preview** to review how your SMS renders and, optionally, send a test message to an internal recipient. Test messages use the default values defined during campaign creation.

9. After creating a campaign, click **Generate** **ID** to create the Notify ID required to trigger your Notify campaign. Once generated, copy the ID and use it in the [Notify API](doc:notify-api) request to launch the campaign.


<Image src="https://files.readme.io/12a2419d5f1c686d3fae52451ee37403f7f28cec60b98fc42aea6ac37e206b35-image.png" alt="Generate Notify ID" align="center" width="40%" caption="Generate Notify ID" border={true} />


<Callout icon="📘" theme="info">
  #### Frequency Cap, DND, and Blocklist Behavior

  Notify messages bypass CleverTap global frequency caps and DND settings, ensuring transactional messages are always prioritized for delivery. For maximum deliverability, ensure the recipient phone number is not on your service provider's DND list or blocklist, as provider-level restrictions may affect delivery. Any such failures are captured and recorded with a failure reason for full visibility.
</Callout>

## Anonymous Profiles

If the API request specifies an `identity` that does not match an existing profile, the request is rejected, and the SMS is not sent. If the request only supplies a raw recipient phone number (no `identity`), the SMS is still sent, but since there is no profile to attribute it to, engagement metrics such as delivered, viewed, and clicked are not tracked.

# Manage Notify Campaign

After creating a Notify campaign, you can view and manage all your Notify campaigns from the _Notify_ page. From this page, you can perform the following actions:

- [View Notify Campaign](doc:notify#view-notify-campaign)
- [Filter Notify Campaigns](doc:notify#filter-notify-campaigns)
- [Edit Column Order](doc:notify#edit-columns)


<Image src="https://files.readme.io/97c92d38c9a611f9502dce7ca84ab18837a8f36ab46285e6a812dd49897cff8a-2025-07-16_16-08-34_1.gif" alt="View Notify" align="center" caption="View Notify Campaign" border={true} />


| Column Name       | Description                                                                                              |
| :---------------- | :------------------------------------------------------------------------------------------------------- |
| Name              | The title of the Notify campaign. Also displays the unique Notify ID below the name.                     |
| Channel           | The communication channel used for the message. Currently, the feature is available for the SMS channel. |
| Status            | Indicates the current state of the campaign. For example, Draft, Running, and Stopped.                   |
| Start date        | The date and time when the campaign was created.                                                         |
| Created by        | The phone number of the user who created the Notify campaign.                                            |
| Request Received  | The number of message requests received by CleverTap via the Notify API for this campaign.               |
| Request Processed | The number of requests successfully processed and sent to the SMS service provider.                      |
| Request Failed    | The number of requests that failed during processing or delivery to the SMS service provider.            |

## View Notify Campaign

Click any campaign from the _Notify_ page to view it. The Notify campaign opens with the following three tabs:


<Image src="https://files.readme.io/807cb7803e5ef42e59d982ab4395a3048d73840087e4874590214fc484d967ef-image.png" alt="View Notify" align="center" caption="View Notify" border={true} />


- **Overview**: Displays a summary of the campaign setup, including the selected provider and message.
- **API Details**: Displays the Notify ID and a sample JSON for your Notify API request. You need to modify the values and keys to match your campaign-specific requirements. Use this tab to copy the Notify ID or setup details to trigger the message via the Notify API.


  <Image src="https://files.readme.io/cdbe3987059fa8d2d59fac6f445eb1c7ea02992260b3125d92f73bd5cd8b49f0-image.png" align="center" caption="API Details" border={true} />


* **Stats**: Displays a comprehensive view of your Notify campaign performance, helping you track requests, message delivery, user engagement, and any errors encountered. For more information, refer to [Notify Stats](doc:notify-stats).

## Edit Notify Campaign

You can edit the campaign content for a _Running_ or _Draft_ Notify campaign.

- **Draft campaigns**: Changes are saved to the existing campaign, and the Notify ID remains unchanged.
- **Running campaigns**: Editing a Running campaign creates a new version of the campaign with a new Notify ID and stops the previous campaign. Update your API integration with the new Notify ID before the previous campaign is terminated to avoid delivery failures.

## Filter Notify Campaigns

Use the **Filters** panel on the Notify dashboard to narrow results and quickly find the campaigns you need.

You can toggle between **Active** and **Archived** campaigns:

- **Active**: Includes campaigns in Running, Draft, or Stopped states.
- **Archived**: Includes campaigns that are no longer active but are available for reference. To make changes, such as Edit or Stop, you must unarchive the campaign.

You can filter campaigns by:

- **Status**: The [Status](doc:notify#notify-campaign-status) filter is only available when viewing Active campaigns. When the _Archived_ tab is selected, all campaigns shown are in the Archived state, and the Status filter is not displayed.
- **Time Period**: Select a date range to filter campaigns by the creation date.
- **Created By**: Filter campaigns by the phone number of the dashboard user who created the campaign. The default view shows campaigns created by **All users**.


<Image src="https://files.readme.io/8186102ccc8369ae2c64b214b60d6260bfe4ce65be9f26a41794030718c0a839-image.png" alt="Filter Notify Campaigns" align="center" caption="Filter Notify Campaigns" border={true} />


## Edit Columns

The _Edit Columns_ option allows you to customize the layout of your Notify campaign list page by choosing which columns to display and in what sequence. This makes it easier to focus on the most relevant information based on your workflow.


<Image src="https://files.readme.io/29d2d3f46af3ec59f2803f74f7a5050167fed51fce3fe25c2b3ce66eaad3d0a4-2025-07-16_16-11-38_1.gif" alt="Edit Column Order" align="center" width="75%" caption="Edit Column Order" border={true} />


<br />

<br /><br />
