---
title: Notify
excerpt: >-
  Learn how to use Notify to send real-time, transactional notifications such as
  One-time Passwords (OTPs), alerts, order or booking confirmations, and
  password resets via the CleverTap dashboard.
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

Notify is CleverTap’s transactional messaging solution built for time-sensitive, user-specific communications such as OTPs, payment alerts, order confirmations, and password reset notifications. Notify delivers messages quickly through real-time API triggers with built-in retry logic.

> 📘 Private Beta
>
> Notify is currently released in Private Beta for the Email channel with SendGrid as the email service provider. To enable this feature, contact your Customer Success Manager.

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

Notify is ideal for delivering critical transactional messages across multiple touchpoints. The following use cases show how Notify enables real-time communication to enhance user experience, strengthen security, and ensure operational clarity:

* **OTP Delivery for Login/Authentication**  
  Send time-sensitive OTPs to users to verify identity or enable secure login. For example, a user tries logging into a banking app and receives a 6-digit OTP on their registered email.
* **Order Confirmation and Receipts**  
  Confirm purchases or bookings immediately by sending transactional messages with order summaries.  
  For example:
  * After placing an order on an online grocery app, the user receives an email confirming the order with itemized billing details.
  * A travel booking site sends an order summary via email after successful payment.
* **Payment Success and Failure Notifications**  
  Inform users in real time about the status of their transactions to prevent confusion and avoid duplicate payments. For example:
  * A credit card user receives an email notification confirming the successful payment.
  * In case of a failed transaction, the user receives an email stating that the payment was unsuccessful and providing guidance on the next steps or retrying.
* **Account and Password Reset Links**  
  Send secure password reset or account recovery links to users requesting access recovery. For example:
  * When users click **Forgot Password** on a social media platform, they immediately receive an email with a password reset link that expires in 10 minutes.
  * Users trying to change their email addresses are sent a verification link to the new email for confirmation.
* **Security Notifications**  
  Alert users instantly about critical changes to their account to detect and prevent unauthorized access. For example, when a user logs in from a new device, the system sends an email to notify the user.

# Create Notify Campaign

Trigger transactional messages in real time based on specific user actions. For example, when a user completes a bill payment, you can trigger a confirmation email using the _Payment Success_ event.

To create a Notify campaign, perform the following steps:

1. Go to _Notify_  from the CleverTap dashboard and click **Create Notify Campaign**. The _Setup_ popup opens.

<Image align="center" alt="Create Notify Campaign" border={true} caption="Create Notify Campaign" src="https://files.readme.io/5a157b0ef34c4ab306de7ee2991dc9f10983a49cc2f8746ee8dd928d809e11f8-2025-07-16_11-54-42_1.gif" />

2. Enter the campaign **Name** and click **Continue**. The _Channel Setup_ page opens.

3. Select the provider from the dropdown under _Provider Configuration_. You can also add a new service provider by clicking **Add Provider**. For more information, refer to [Email Provider Setup](doc:email_providers_operations).

4. Click **Create Message** under _Content_ to create your campaign message as follows:
   1. Select an email template or create your own template for your Notify message.
   2. Draft a message and enter the _Sender Details_. For more information, refer to [Email Editor](doc:create-message-email). You can personalize messages in two ways:
      * **User Property Personalization**: Uses profile properties for personalization, for example, `{{Profile.name | default:"Shopper"}}`.
      * **Notify API Parameter Personalization**: Uses a key from the `notifyFields` object in the API payload, for example, `{{Notify.orderID | default:"Order number not available"}}`.  
        When the campaign is triggered via API, CleverTap pulls the value from the object in your payload and injects it into the message. This enables you to personalize email order details based on real-time values. For more information, refer to [Notify API](https://developer.clevertap.com/docs/notify-api).

<Image align="center" alt="Personalization Keys for Notify" border={true} caption="Personalization Keys for Notify" src="https://files.readme.io/d2a6a0502bef5fe08749d2cbf79e61a4d55a86e27adba01a8fe0ded77cf132b1-Personalized_Notify_Campaign.png" />

> 📘 Anonymous Profile
>
> When the recipient profile does not exist on the dashboard, the message is still sent. But delivery or engagement metrics are not tracked for such profiles.

5. Click **Done** to return to the _Channel Setup_ screen. You can choose to edit your Notify message or review the content layout using Preview before generating the Notify ID without sending a test message.
6. Click **Preview & Test** to check how your message renders and appears in the recipient's inbox. You can use this option to send a test message to an internal recipient for validation. Test messages display the default values defined during campaign creation.
7. After creating an Email campaign, Click **Generate** to create the transaction ID or script required to trigger your Notify campaign. Once generated, copy the ID/script and use it in the [Notify API](https://developer.clevertap.com/docs/notify-api) request to launch the campaign.

<Image align="center" alt="Generate " border={true} caption="Generate Notify ID" src="https://files.readme.io/12a2419d5f1c686d3fae52451ee37403f7f28cec60b98fc42aea6ac37e206b35-image.png" width="40% " />

> 📘 No Frequency Cap or DND Limits
>
> Notify messages are exempt from global frequency caps and DND settings, ensuring timely delivery of critical transactional messages.

# Manage Notify Campaign

After creating a Notify campaign, you can view and manage all your Notify campaigns from the _Notify_ page. From this page, you can perform the following actions:

* [View Notify Campaign](doc:notify#view-notify-campaign)
* [Filter Notify Campaign](doc:notify#filter-notify-campaigns)
* [Edit Columns](doc:notify#edit-columns)

<Image align="center" alt="View Notify" border={true} caption="View Notify Campaign" src="https://files.readme.io/97c92d38c9a611f9502dce7ca84ab18837a8f36ab46285e6a812dd49897cff8a-2025-07-16_16-08-34_1.gif" />

| Column Name             | Description                                                                                                |
| :---------------------- | :--------------------------------------------------------------------------------------------------------- |
| Name                    | The title of the Notify campaign. Also displays the unique Notify ID below the name.                       |
| Channel                 | The communication channel used for the message. Currently, the feature is available for the Email channel. |
| Status                  | Indicates the current state of the campaign. For example, Draft, Running, and Stopped.                     |
| Start date              | The date and time when the campaign was published                                                          |
| Created by              | The Email ID of the user who created the Notify campaign.                                                  |
| Total Request Received  | The number of message requests received by CleverTap via the Notify API for this campaign.                 |
| Total Request Processed | The number of requests successfully processed and sent to the email service provider.                      |
| Total Request Failed    | The number of requests that failed during processing or delivery to the email service provider.            |

## View Notify Campaign

Click any campaign from the _Notify_ page to view it. The Notify campaign opens with the following three tabs:

<Image align="center" alt="View Notify" border={true} caption="View Notify" src="https://files.readme.io/807cb7803e5ef42e59d982ab4395a3048d73840087e4874590214fc484d967ef-image.png" />

* **Overview**: Displays a summary of the campaign setup, including the selected email provider and message.
* **API Details**: Displays the Notify ID and a sample JSON for your Notify API request. You need to modify the values and keys to match your campaign-specific requirements. Use this tab to copy the Notify ID or setup details to trigger the message via the Notify API.

<Image align="center" alt="API Details" border={true} caption="API Details" src="https://files.readme.io/2e14f4c1e1fab9ba142e7b93d613efe266eb6fef8bf852f70853763d35d9ce53-image.png" />

* **Stats**: Displays a comprehensive view of your Notify campaign performance, helping you track requests, message delivery, user engagement, and any errors encountered. For more information, refer to [Notify Stats](doc:notify#stats).

## Edit Notify Campaign

You can edit the campaign content for a _Running_ or _Draft_ Notify campaign. For the _Running_ campaigns, all changes apply to the subsequent API requests.

## Filter Notify Campaigns

Use the **Filters** panel on the Notify dashboard to narrow results and quickly find the campaigns you need.

You can toggle between **Active** and **Archived** campaigns:

* **Active**: Includes campaigns in Running, Draft, or Stopped states.
* **Archived**: Includes campaigns that are no longer active but are available for reference. To make changes, such as Edit, Clone, or Stop, you must unarchive the campaign.

You can filter campaigns by: _Status_, _Time Period_, and _Created By_.

<Image align="center" alt="Filter Notify Campaigns" border={true} caption="Filter Notify Campaigns" src="https://files.readme.io/8186102ccc8369ae2c64b214b60d6260bfe4ce65be9f26a41794030718c0a839-image.png" />

### Status

Select from the following status types:

* **Running**: Published; ready to receive Notify API triggers.
* **Draft**: The campaign has been created and saved but is not yet enabled to receive API trigger requests.
* **Stopped**: Campaign is manually stopped and no longer accepts API-triggered requests..

### Time Period

Select a date range to filter campaigns by the creation date.

### Created By

Filter campaigns by creator email ID. The default view shows campaigns created by **All users**.

## Edit Columns

The _Edit Columns_ option allows you to customize the layout of your Notify campaign list page by choosing which columns to display and in what sequence. This makes it easier to focus on the most relevant information based on your workflow.

<Image align="center" alt="Edit Column Order" border={true} caption="Edit Column Order" src="https://files.readme.io/29d2d3f46af3ec59f2803f74f7a5050167fed51fce3fe25c2b3ce66eaad3d0a4-2025-07-16_16-11-38_1.gif" width="75% " />

# Stats

The **Stats** tab provides a comprehensive view of your Notify campaign performance, helping you track requests, message delivery, user engagement, and any errors encountered. This data is vital for understanding message flow health, diagnosing issues, and optimizing delivery outcomes.

The _Stats_ section can be classified into two parts:

* [Request-Level Stats](doc:notify#request-level-stats)
* [Channel Performance](doc:notify#channel-performance)

## Request-Level Stats

The Request-Level Stats provide a high-level summary of the requests made to the Notify API within a selected time period. These metrics help you track the flow of incoming requests and understand how many were successfully processed or failed.

* **Total Requests Received**: Number of API requests received by CleverTap to trigger the Notify message.
* **Total Requests Processed**: Number of requests successfully processed and sent to the Email service Provider.
* **Total Requests Failed**: Number of requests that failed during processing or delivery to the ESP.

The **Trend** section, below the metric cards, displays a request timeline, helping you track performance patterns such as volume spikes or error bursts. You can toggle between the following tabs:

* **Trend**: Graphical view of total received, processed, and failed requests over a selected time range. You can click the ![](https://files.readme.io/2c2ca5affab31cbb70db7e89ac65e65e04219bfe463755836373077b5f63f049-Hide_icon.png) icon to view or hide a specific metric, as shown in the image below.
* You can view select metrics by clicking the view icon, as shown in the image below.
* **Errors**: Lists failed Notify API requests, detailed error messages, and count. This helps identify the root cause of failures.

Use the date range selector to filter stats for a specific time window and export the data for audits or internal analysis.

<Image align="center" alt="Request-Level Stats" border={true} caption="Request-Level Stats" src="https://files.readme.io/b93a1b1365899978747cd2e7a67132b08a6e71e0e20509c4c17c1383d2601522-2025-07-16_16-34-29_1.gif" />

## Channel Performance

The _Channels_ section provides a detailed breakdown of channel-specific performance, helping you understand how recipients interact with transactional messages post-delivery.

<Image align="center" alt="Channel-wise Performance" border={true} caption="Channel Performance" src="https://files.readme.io/ef00347e4433aa3e205007696649510a23b7fce0ab661c7a42db80f4456fb9fe-2025-07-16_16-29-33_1.gif" />

### Trends

Use the Trends view to analyze how performance changes over time, including spikes in message volume, engagement rates, and delivery failures, helping you uncover behavior patterns. Use the date range selector to filter stats for a specific time window and export the data for audits or internal analysis.

* **Total Sent**: Number of emails sent to the ESP.
* **Total Delivered**: Number of emails delivered to the recipient.
* **Total Viewed**: Number of times users opened the email.
* **Total Clicked**: Number of times users clicked on any links within the email.

Each metric provides insight into user engagement and message effectiveness for the selected time range. As shown in the above image, you can click the ![](https://files.readme.io/94031640d02b525c886f55910f9367fc3e7798ed5cf84387a8d8456277239892-Hide_icon.png) icon to view or hide a specific metric.

### Errors

The _Errors_ section provides visibility into issues while delivering the email to the user. Common error types include soft bounces, hard bounces, and provider-related errors.

* **Total Errors**: Total number of delivery errors.
* **Total Email Errors**: Total number of errors during email delivery, such as soft bounce, hard bounce.
* **Total Unclassified Errors**: Total number of errors that do not fall into known error categories.

<Image align="center" border={true} caption="Email Campaign Errors" src="https://files.readme.io/47f7269750211e103d0c18a84996da02928167eb0ee15618a99c0f6c4695ead9-image.png" />

<br />
