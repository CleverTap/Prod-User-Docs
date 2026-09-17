---
title: Notify-Email
excerpt: >-
  Learn how to set up and trigger real-time transactional Email campaigns using
  Notify.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Notify is CleverTap's transactional messaging solution built for time-sensitive, user-specific communications such as OTPs, payment alerts, order confirmations, and password reset notifications. Notify delivers messages quickly through real-time API triggers with built-in retry logic.

<Callout icon="📘" theme="info">
  ### Private Beta

  Notify is currently released in Private Beta. The Email channel is available for the following providers: SendGrid and Infobip (with the Advanced Email Add-on).

  To enable this feature, contact your Customer Success Manager.
</Callout>

# Video Tutorial

You can watch the following video to learn more about Notify.

<HTMLBlock>{`
<div
  style="
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    border-radius: 0;
    box-shadow: 0 15px 40px rgba(63,58,79,.3);
    overflow: hidden;
    min-width:320px"><iframe
    src="https://clevertap.portal.trainn.co/share/WlZsiRC6d7xy6LYPAHy9LA/embed?autoplay=false"
    frameborder="0"
    webkitallowfullscreen
    mozallowfullscreen
    allowfullscreen
    allow="autoplay; fullscreen"
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Use Cases

The following use cases show how Notify enables real-time email communication to enhance user experience, strengthen security, and ensure operational clarity:

- **OTP Delivery for Login/Authentication**<br />Send time-sensitive OTPs to users to verify identity or enable secure login.<br />For example, a user tries to log in to a banking app and receives a 6-digit OTP via their registered email.

- **Order Confirmation and Receipts**<br />Confirm purchases or bookings immediately by sending transactional emails with order summaries.<br />For example:
  - After placing an order on an online grocery app, the user receives an email confirming the order with itemized billing details.
  - A travel booking site sends an order summary via email after successful payment.

- **Payment Success and Failure Notifications**<br />Inform users in real time about the status of their transactions to prevent confusion and avoid duplicate payments.<br />For example:
  - A credit card user receives an email notification confirming the successful payment.
  - In case of a failed transaction, the user receives an email stating that the payment was unsuccessful and providing guidance on the next steps or retrying.

- **Account and Password Reset Links**<br />Send secure password reset or account recovery links to users requesting access recovery.<br />For example:
  - When users click **Forgot Password** on a social media platform, they immediately receive an email with a password reset link that expires in 10 minutes.
  - Users trying to change their email address receive a verification link via email to confirm the change.

- **Security Notifications**<br />Alert users instantly about critical changes to their accounts to detect and prevent unauthorized access.

# Create Notify Campaign

Trigger transactional email messages in real time in response to specific user actions.

To create a Notify campaign for the Email channel, perform the following steps:

1. Go to _Notify_ from the CleverTap dashboard and click **Create Notify Campaign**. The _Enter Campaign Name_ pop-up opens.&#x20;


<Image src="https://files.readme.io/5a157b0ef34c4ab306de7ee2991dc9f10983a49cc2f8746ee8dd928d809e11f8-2025-07-16_11-54-42_1.gif" alt="Create Notify Campaign" align="center" caption="Create Notify Campaign" border={true} />


2. Enter the campaign **Name** and click **Continue**. The _Channel Setup_ page opens.

3. Select **Email** from the Channel section.


   <Image src="https://files.readme.io/5c730e7dc482d56eeb912a8d8d3e917d9536e4ec0b60f987ac24cb54ad68190c-image.png" align="center" caption="Set Up Channel" border={true} />


4) Select the email provider from the dropdown under _Provider Configuration_. You can also add a new provider by clicking **Add**. For more information, refer to [Email Provider Setup](doc:email_providers_operations).

5) Select how you want to send your Notify campaign by choosing the _Message type_.

   - **Single message**: Send the same email to all users. For example, an order confirmation that is identical for all recipients.
   - **Message by user property**: Send different email variants based on a user profile property. For example, customize the order confirmation based on the product category purchased by mapping variants to the `product_category` property. Select the property from the dropdown that appears inline. Only string-type user properties can be used for variant mapping.

     <Callout icon="📘" theme="info">
       #### Missing User Property Value

       If the value does not match any configured variant, or if the property is not set on the profile, CleverTap sends the default variant instead.
     </Callout>


   <Image src="https://files.readme.io/271fa9f15b615a6be098062f1b2acb67886cb2a8636ca19b4cf84aa322c8ed62-image.png" align="center" caption="Select Message Type" border={true} />


6) Click **Create Message** under _Content_ to create your campaign message as follows:
   1. Select a template or create your own template for your Notify email campaign.
   2. Draft a message and enter the _Sender Details_. For more information, refer to [Email Editor](doc:create-message-email). You can personalize messages in the following two ways:
      - **User Property Personalization**: Uses profile properties for personalization. For example, `{{Profile.name | default:"Shopper"}}`.
      - **Notify API Parameter Personalization**: Uses real-time values passed directly in the API request payload at the time of trigger. When you call the Notify API, you include a `notifyFields` object in the request body containing the key-value pairs you want to inject into the message. For example, if your payload includes `"notifyFields": {"orderID": "ORD-9821"}`, you can reference it in your message as `{{Notify.orderID | default:"Order number not available"}}`. CleverTap reads the value from the payload at send time and substitutes it into the message body. This is useful for personalizing emails with transaction-specific data, such as order IDs or payment amounts, that are only available at the time of the API call. For more information, refer to [Notify API](https://developer.clevertap.com/docs/notify-api).


<Image src="https://files.readme.io/d2a6a0502bef5fe08749d2cbf79e61a4d55a86e27adba01a8fe0ded77cf132b1-Personalized_Notify_Campaign.png" alt="Personalization Keys for Notify" align="center" caption="Personalization Keys for Notify" border={true} />


7. Click **Done** to return to the _Campaign Setup_ screen. You can edit your Notify message at any point before generating the Notify ID.

8. Click **Preview&#x20;**&#x74;o review how your email renders and, optionally, send a test message to an internal recipient. Test messages use the default values defined during campaign creation.

9. After creating a campaign, click **Generate ID** to create the Notify ID required to trigger your Notify campaign. Once generated, copy the ID and use it in the [Notify API](doc:notify-api) request to launch the campaign.


<Image src="https://files.readme.io/12a2419d5f1c686d3fae52451ee37403f7f28cec60b98fc42aea6ac37e206b35-image.png" alt="Generate Notify ID" align="center" width="40%" caption="Generate Notify ID" border={true} />


<Callout icon="📘" theme="info">
  #### Frequency Cap, DND, and Blocklist Behavior

  Notify messages bypass CleverTap global frequency caps and DND settings, ensuring transactional messages are always prioritized for delivery. For maximum deliverability, ensure the recipient email address is not on your service provider's DND list or blocklist, as provider-level restrictions may affect delivery. Any such failures are captured and recorded with a failure reason for full visibility.
</Callout>

## Anonymous Profiles

If the API request specifies an `identity` that does not match an existing profile, the request is rejected, and the email is not sent. If the request only supplies a raw recipient email (no `identity`), the email is still sent, but since there is no profile to attribute it to, engagement metrics such as delivered, viewed, and clicked are not tracked.

# Manage Notify Campaign

After creating a Notify campaign, you can view and manage all your Notify campaigns from the _Notify_ page. From this page, you can perform the following actions:

- [View Notify Campaign](doc:notify#view-notify-campaign)
- [Filter Notify Campaigns](doc:notify#filter-notify-campaigns)
- [Edit Column Order](doc:notify#edit-columns)


<Image src="https://files.readme.io/97c92d38c9a611f9502dce7ca84ab18837a8f36ab46285e6a812dd49897cff8a-2025-07-16_16-08-34_1.gif" alt="View Notify" align="center" caption="View Notify Campaign" border={true} />


| Column Name             | Description                                                                                                |
| :---------------------- | :--------------------------------------------------------------------------------------------------------- |
| Name                    | The title of the Notify campaign. Also displays the unique Notify ID below the name.                       |
| Channel                 | The communication channel used for the message. Currently, the feature is available for the Email channel. |
| Status                  | Indicates the current state of the campaign. For example, Draft, Running, and Stopped.                     |
| Start date              | The date and time when the campaign was created.                                                           |
| Created by              | The Email ID of the user who created the Notify campaign.                                                  |
| Total Request Received  | The number of message requests received by CleverTap via the Notify API for this campaign.                 |
| Total Request Processed | The number of requests successfully processed and sent to the email service provider.                      |
| Total Request Failed    | The number of requests that failed during processing or delivery to the Email service provider.            |

## View Notify Campaign

Click any campaign from the _Notify_ page to view it. The Notify campaign opens with the following three tabs:


<Image src="https://files.readme.io/807cb7803e5ef42e59d982ab4395a3048d73840087e4874590214fc484d967ef-image.png" alt="View Notify" align="center" caption="View Notify" border={true} />


- **Overview**: Displays a summary of the campaign setup, including the selected provider and message.
- **API Details**: Displays the Notify ID and a sample JSON for your Notify API request. You need to modify the values and keys to match your campaign-specific requirements. Use this tab to copy the Notify ID or setup details to trigger the message via the Notify API.


<Image src="https://files.readme.io/2e14f4c1e1fab9ba142e7b93d613efe266eb6fef8bf852f70853763d35d9ce53-image.png" alt="API Details" align="center" caption="API Details" border={true} />


- **Stats**: Displays a comprehensive view of your Notify campaign performance, helping you track requests, message delivery, user engagement, and any errors encountered. For more information, refer to [Notify Stats](doc:notify-stats).

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
- **Created By**: Filter campaigns by the email ID of the dashboard user who created the campaign. The default view shows campaigns created by **All users**.


<Image src="https://files.readme.io/8186102ccc8369ae2c64b214b60d6260bfe4ce65be9f26a41794030718c0a839-image.png" alt="Filter Notify Campaigns" align="center" caption="Filter Notify Campaigns" border={true} />


## Edit Columns

The _Edit Columns_ option allows you to customize the layout of your Notify campaign list page by choosing which columns to display and in what sequence. This makes it easier to focus on the most relevant information based on your workflow.


<Image src="https://files.readme.io/29d2d3f46af3ec59f2803f74f7a5050167fed51fce3fe25c2b3ce66eaad3d0a4-2025-07-16_16-11-38_1.gif" alt="Edit Column Order" align="center" width="75%" caption="Edit Column Order" border={true} />


<br />

<br />
