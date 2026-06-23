---
title: Mixpanel Export
excerpt: >-
  Understand how you can export event data from CleverTap to the Mixpanel
  dashboard. To learn more about the import feature, refer to [Mixpanel
  Import](https://docs.clevertap.com/docs/mixpanel-integration).
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

This section provides information about exporting event data from CleverTap to the Mixpanel dashboard. CleverTap also offers to import Mixpanel cohorts. To learn more about this feature, refer to [Mixpanel Import](doc:mixpanel-integration).

> 📘 Export Limit Per Event
>
> Mixpanel supports exporting only 255 event properties per event. If the number of event properties exceeds the Mixpanel limit, the CleverTap exports the first 255 event properties.

# Setup

The setup involves adding Mixpanel project details to the CleverTap dashboard. To add the project details:

1. Log in to your CleverTap account.
2. Navigate to _Settings_ > _Partners_ > _Partner List_.


<Image src="https://files.readme.io/54ea074-PartnersList.jpg" alt="2850" align="center" width="90% " border={true} />


3. Hover on the _Mixpanel_ icon and click **Integrate**.


<Image src="https://files.readme.io/0102041-IntegrateMixpanel.jpg" alt="2372" align="center" width="90% " border={true} />


On clicking, the _Integrate analytics partner - Mixpanel_ popup opens on the right side of the screen.

4. Enter the following details and click **Integrate**:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <p>Field</p>
      </th>

      <th>
        <p>Description</p>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <p>Mixpanel Project ID</p>
      </td>

      <td>
        <p>The Project token is used to send event data to Mixpanel. For more information, refer to <a href="https://help.mixpanel.com/hc/en-us/articles/115004490503-Project-Settings#project-id">Project ID</a>.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Service Account Username</p>
      </td>

      <td>
        <p>A descriptive name for the service account in Mixpanel. For more information, refer to <a href="https://developer.mixpanel.com/reference/service-accounts#authenticating-with-a-service-account">Service Account Username</a>.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Service Account Secret</p>
      </td>

      <td>
        <p>The secret API is the key that corresponds to your project. For more information, refer to <a href="https://developer.mixpanel.com/reference/service-accounts#authenticating-with-a-service-account">Service Account Secret</a>.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Data Residency</p>
      </td>

      <td>
        <ul><li>The Data Residency is the physical/geographical storage location of data (EU, IN, or Standard) for each project.</li><li>For more information, refer to <a href="https://help.mixpanel.com/hc/en-us/articles/115004490503-Project-Settings#data-residency">Data Residency</a>.</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        Mixpanel Distinct ID Mapping
      </td>

      <td>
        This user property is used as an identifier when sending event data to Mixpanel. For more information, refer to

        [Distinct ID](https://help.mixpanel.com/hc/en-us/articles/115004509406-Distinct-IDs-)
      </td>
    </tr>
  </tbody>
</Table>


<Image src="https://files.readme.io/9d32e591a3f0642e718520bf22fae57d986e1db042753d93765175c99dfe9b7c-Screenshot_2026-06-22_at_8.21.48_PM.png" alt="Enter Mixpanel Project Details to Integrate" align="center" width="70% " caption="Integrate Partner - Mixpanel" border={true} />


After successful integration, the _Integrated_ tag displays against Mixpanel on the _Partner List_ page.


<Image src="https://files.readme.io/13059cb-image.png" alt="Successful Mixpanel Integration" align="center" border={true} />


# Create New Export

To create a new export:

1. Navigate to **Settings** > **Partners** > **Exports**.
2. Click **Create Export** and select **Mixpanel**.


<Image src="https://files.readme.io/2b7000c-CreateMixpanelExport.jpg" alt="2376" align="center" width="90% " border={true} />


The **Export to Mixpanel** popup displays.


<Image src="https://files.readme.io/ba2ad2e-ExportToMixpanel.jpg" alt="2346" align="center" width="90% " border={true} />


3. Configure the settings as required.
   - **Partner Nickname**: Nickname for the partner. To edit the nickname, go to **Partner List**.
   - **DATA TYPE & IDENTIFIER PRIORITY**: Select the events from the available options to export. For more information, refer to [Export Details](https://docs.clevertap.com/docs/mixpanel-export#export-details).
   - **FREQUENCY**: Select from one of the following options:
     - **One time**: A single export for the selected export type. You can export data up to the last **60 days**. You create an export for a specific day, date range, previous month, current month, and more.
     - **Recurring**: Set up a recurring export that exports all the new events captured in the last window. You can export data as frequently as every 4 hours and up to once every 24 hours.
     - **Live Datastreaming**: Exports data continuously in real-time.
     - **Date to export data**: The export starts at 12:00 a.m. on the specified date by default.

> 📘 Rate Limits
>
> If you are a Mixpanel enterprise customer and require a higher limit for a one-time backfill, contact [apis@mixpanel.com](mailto:apis@mixpanel.com) with your project\_id and use-case.

4. Click **Export**. On clicking, the popup closes, and the following message displays at the top of the _Exports_ page:


<Image src="https://files.readme.io/724549a-MixpanelExportInitiated.jpg" alt="2442" align="center" width="90% " border={true} />


CleverTap processes the export, and you can now see the newly created export for Mixpanel.

The status for each export is displayed as **PENDING** as soon as the export is created. The status changes to **RUNNING** after the processing starts. It changes to **DONE** when the export is complete.

# Stop Export

You can also stop the running export. Hover over the export. Click the **Stop**  ![Stop export](https://files.readme.io/203208a-StopExport.jpg) button.


<Image src="https://files.readme.io/623b663-StopMixpanel.jpg" alt="2376" align="center" width="90% " border={true} />


The **Stop export?** window appears. Click **Stop** to confirm your action.


<Image src="https://files.readme.io/8f7a2ee-StopMixpanelWindow.jpg" align="center" width="60% " border={true} />


You are navigated back to the **Exports** page. The _Mixpanel data export stopped_ message displays at the top. The status of export is now displayed as **STOPPED**.


<Image src="https://files.readme.io/ecfcc6b-MixpanelExportStopped.jpg" alt="2368" align="center" width="90% " border={true} />


# Edit an Export

You might need to modify an export to meet specific business requirements or while waiting for the next run. This section describes editing a Live Data Streaming and Recurring export in the **RUNNING** and **PENDING**(awaiting next run) state.

> 📘 Points to Remember
>
> - In case of running exports, the new changes will apply to the next run.
> - You cannot edit a One-time export, regardless its status (RUNNING, PENDING, DONE, or STOPPED).
> - You cannot change the export from User Profile to Event and vice-versa.
> - You cannot modify exports marked as **DONE** or **STOPPED**.
> - Export changes for Live DataStreaming take 10-15 minutes to take effect.

To edit an export:

1. On the CleverTap dashboard, go to **Partners** > **Exports**.
2. Hover over the required export. The **View**, **Edit**, and the **Stop** buttons appear.


<Image src="https://files.readme.io/4ef3467-EditMixpanel.jpg" alt="Click the Edit Export Icon" align="center" width="90% " border={true} />


3. Click the **Edit** button. The **Export to Mixpanel** section appears.


<Image src="https://files.readme.io/5cb8482-UpdateMixpanelExport.jpg" alt="Edit the Export" align="center" width="90% " border={true} />


4. Edit the export details and click **Update export**.

# Filter Exports

This section describes the different ways you can filter exports.

## Filter by Export Details

To filter by export details:

1. Click the **Filter** button at the top right corner.
2. You can filter exports by **Partner**, **Type**, **Format**, **Status**, or **Frequency**.
3. To clear the filter, click **Reset all**.


<Image src="https://files.readme.io/6499e90-FilterButton.jpg" alt="Filter Exports" align="center" width="90% " border={true} />


## Filter Exports by Date Range

You can also filter the exports based on the export date.

To filter exports by export date range:

1. Click the **Filter** button at the top right corner.
2. Click the **Exported on** button.<br />The **Calendar** widget appears.


<Image src="https://files.readme.io/74ce34b-Amplitude_Exports_-_Calendar_Widget.png" alt="Calendar Widget" align="center" width="90% " border={true} />


1. Choose the custom date range and click **Apply**.<br />The exports are filtered accordingly.

## Filter Exports by Pagination

To choose how many export items you view per page:

1. Use the **Items per page** drop-down at the bottom of the **Exports** page.
2. Options include 10, 20, 30, or 40. By default, the **Exports** page shows 20 exports.

# Export Details

Select from one of the following options to export events from CleverTap to the Mixpanel dashboard:

- [All events](doc:mixpanel-export#all-events)
- [Selected events](doc:mixpanel-export#selected-events)
- [Engagement events](doc:mixpanel-export#engagement-events)

## All Events

Export data for all defined events, including _System_ and _Custom_ events.

## Selected Events

Select the specific events to export.

## Engagement Events

Export the following engagement events:

| <p>CleverTap Event Name</p>     | <p>Description</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| :------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>Notification Sent</p>        | <ul><li>The event is tracked when the notification is successfully sent from CleverTap to the communication channel you select for your campaign. </li><li>This event is always recorded, even if the user does not open or click the message. </li><li>This event is recorded for Email, Mobile Push, SMS, and Web Push campaigns. </li><li>This event is available on the Event dashboard but not on the User Profile.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <p>Notification Viewed</p>      | <ul><li>The event is tracked when a user views an email, in-app, or web notification sent from CleverTap.</li><li>The event is available for Email, Web Push, In-App, Web Popup, and App Inbox.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <p>Notification Clicked</p>     | <p>The event is tracked when a user clicks on a Mobile Push, In-App, Email, Web Popup, or Web Push message sent via the CleverTap dashboard or through the campaign API.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| <p>Push Impressions</p>         | <ul><li>After the Push Impression is implemented in the SDK, the toggle must be turned on from the CleverTap dashboard.</li><li>This event is recorded whenever a push notification sent via CleverTap is delivered to the user’s device.</li><li>The funnels on the Push campaign statistics page reflect the count for this event.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <p>Notification Replied</p>     | <p>This event is tracked when the brand receives a reply from the user for WhatsApp.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| <p>Push Unregistered</p>        | <ul><li>This debug event is tracked when an existing mobile push token is removed for a profile.</li><li>The event is tracked for a profile when:<ul><li>A user logs out of the device, and another user logs in. Applicable only if the onUserLogin() method is implemented.</li><li>When a push token is removed using the pushFcmRegisterationId("token",false) method. Applicable only for Android.</li></ul></li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| <p>Control Group</p>            | <p>The event is tracked when a campaign is activated with a Control group.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <p>Channel Unsubscribed</p>     | <ul><li><p>The event is raised when an email is not acknowledged.</p></li><li><p>The following are the event properties:</p><ul><li>Campaign ID: This is the ID of<br />the campaign from which users are updating subscriptions.<br />Campaign Type: Currently only email.</li><li>Group: Group name from which the user unsubscribed/resubscribed.</li><li>Identity: The user identity/email address.</li><li>Variant Type: Valid values are bounced, dropped, and spam. Email IDs that bounce, drop or marked as spam are opted out from future emails</li><li>Subscription Type: Account level and profile level. Profile level signifies that the user who qualified for the communication is opted out. Account level signifies that all users with the email address are opted out from future communications.</li><li>Reason: Reason which was given by the email provider for the type of the error. For example: "smtp;550 5.1.1 The email account that you tried to reach does not exist. Please try double-checking the recipient's email address for typos or unnecessary spaces."</li></ul></li></ul> |
| <p>Reachable By</p>             | <p>The event is tracked for a profile when:</p><ul><li>Push token is added/changed.</li><li>Email ID is added/changed.</li><li>Phone number is added/changed.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <p>Notification Delivered</p>   | <p>The event is tracked when the WhatsApp provider confirms that the notification has reached the end user (double-tick of WhatsApp).</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <p>AB Experiment Rendered</p>   | <p>The event is tracked when you are using the Product A/B Tests feature and the variant reaches the device.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| <p>AB Experiment Stopped</p>    | <p>The event is tracked when you are using the Product A/B Tests feature and the AB experiment is stopped.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <p>AB Experiment Rolled Out</p> | <p>The event is tracked when you are using the Product A/B Tests feature and the winner variant is sent to all the devices.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <p>Geocluster Entered</p>       | <p>The event is tracked when you enable the geofence feature and your device enters a geofence.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <p>Geocluster Exited</p>        | <p>The event is tracked when you enable the geofence feature and your device exits a geofence.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <p>Reply Sent</p>               | <p>The event is tracked against the user profile of the end-user when an agent (CleverTap user) replies to a WhatsApp message from the end user.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| <p>App Uninstalled</p>          | <ul><li><p>The event is tracked when the user uninstalls the application.</p></li><li><p>There are three cases when this event is tracked multiple times for a single user:</p><ul><li>The first case is when a user installs your app, uninstalls it, and then reinstalls it. </li><li>The second case is when a user clears the app's memory. </li><li>The third case is when a user installs your app on multiple devices.</li></ul></li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| <p>Webhook Delivered</p>        | <p>The event is tracked when a webhook campaign is delivered successfully.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <p>State Transitioned</p>       | <ul><li>The event is tracked whenever a user transitions from one state to another or from an unmapped state to one of the states in the lifecycle optimization framework.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| <p>UTM Visited</p>              | <ul><li>The event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it.</li><li>The event is also tracked when a CleverTap-integrated attribution platform, such as Branch or Apsalar, sends this information to CleverTap.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

# FAQs

### Q. Do CleverTap data exports allow special characters?

A. Yes, CleverTap data exports allow the following special characters:

- CleverTap's export system supports Unicode (UTF-8)  character encoding. It facilitates the accurate representation of text in various languages and scripts. For example, Indian regional languages, Arabic, Korean, Russian, Japanese, Chinese, Spanish, Greek, Indonesian, etc.
- It replaces the following characters with a hyphen to avoid issues in output file generation:
  - Whitespace
  - Tab
  - Slash
  - null (\0)
- Control characters are replaced with ?. For more information, refer to [Control Character](https://en.wikipedia.org/wiki/Control_character).
- Supports emoji characters; however, some emojis (UTF-16) may not render properly.

<br />
