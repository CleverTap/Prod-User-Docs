---
title: Events
excerpt: ''
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

Testing the suggest edits

Events track what individual actions users perform in your app or website. Some examples of events include a user launching an app, viewing a product, listening to a song, sharing a photo, making a purchase, or favoriting an item.

By tracking events in your app, you can better understand what users are doing. In CleverTap, you can analyze these events in many different ways, such as getting aggregating metrics of a specific event or measuring how a specific event type trends over time. You can also engage with your users based on these events by creating campaigns in CleverTap that are triggered by them.

<Image align="center" alt={898} border={true} width="80%" src="https://files.readme.io/40b874a-events1.png" title="events1.png" className="border" />

## Event Categories

CleverTap has two categories of events:

* System events: Events recorded automatically after you integrate our SDK.
* Custom events: Events you define and track with our SDK or API.

## Event Properties

Events have details that describe the action taking place called properties.

For example, while recording the _Product viewed_ event, you could also store event properties, such as product name, category, and price. Recording event properties will help you discover insights, such as which product category is more popular, and segment users based on which categories or price points they have viewed.

# System Events

> 📘 Events Changelog
>
> You can find information about the most recent changes to our existing system events or the introduction of new ones in our [Events Changelog](doc:events-changelog).

System events are events recorded automatically after you integrate our SDK.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Event Type
      </th>

      <th>
        Description
      </th>

      <th>
        How Event is Tracked
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        App Installed
      </td>

      <td>
        The event is raised when the user launches the app for the first time
      </td>

      <td>
        The event is raised when the user launches the app for the first time on any mobile device.<br /><br />There are two cases when this event will be recorded multiple times for a single user. The first case is when a user installs your app, uninstalls it, and then reinstalls it. The second case is when a user clears your app's memory and relaunches it.
      </td>
    </tr>

    <tr>
      <td>
        App Launched
      </td>

      <td>
        This event is recorded every time a user launches your application.
      </td>

      <td>
        There are two cases when this event will be recorded. The first case is a fresh app launch, which is when an app is launched from a killed state. The second case is when an app is brought to the foreground after 20 minutes of inactivity in the background.
      </td>
    </tr>

    <tr>
      <td>
        App Uninstalled
      </td>

      <td>
        This event is recorded when a user uninstalls your application.
      </td>

      <td>
        This event is tracked by sending silent push notifications which is a type of notification that is not rendered on a user’s device. We send silent push notifications to your entire install base once every 24 hours to track uninstalls. For more information, refer to [App Uninstall](https://clevertap.com/blog/track-app-uninstalls-effectively/).
      </td>
    </tr>

    <tr>
      <td>
        Web Session Started
      </td>

      <td>
        This is a web entry event similar to the App launched event. This event refers to the event triggered when a user starts a session or engages with your website.
      </td>

      <td>
        This event will be recorded in two cases: when a user opens a webpage and when a user reloads the browser after 20 minutes of inactivity.
      </td>
    </tr>

    <tr>
      <td>
        UTM Visited
      </td>

      <td>
        This event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as Branch or Singular, sends this information to CleverTap.
      </td>

      <td>
        The _UTM Visited_ event is recorded for your marketing campaigns from external sources, such as Google Adwords or AdRoll.
      </td>
    </tr>

    <tr>
      <td>
        Notification Sent
      </td>

      <td>
        This event is tracked when a campaign message is sent to a user. This event is always recorded, even if the user does not open or click on the message. This event is recorded for email, mobile push, SMS, and web push campaigns. The _Notification Sent_ event is available on the _Event_ dashboard but it is not displayed on the _User Profile_.
      </td>

      <td>
        The event is tracked when the notification is successfully sent from CleverTap to the communication channel you select for your campaign.
      </td>
    </tr>

    <tr>
      <td>
        Notification Failed
      </td>

      <td>
        This event logs campaign errors in CleverTap.
      </td>

      <td>
        Campaign ID: It helps identify the specific campaign associated with the error.<br />Campaign Type: It indicates the type of campaign (for example, WhatsApp, SMS, Email, and so on).<br />Error: It displays the error message for the error observed in the campaign.<br />Label: It denotes the specific label associated with the campaign.<br />Variant: It helps identify the errors for a specific campaign variant in the case of A/B, split delivery, or multi-variant campaigns.<br /><br />For detailed information on WhatsApp errors, refer to [WhatsApp Error Stats](doc:whatsapp-stats).<br /><br />
      </td>
    </tr>

    <tr>
      <td>
        Notification Viewed
      </td>

      <td>
        This event is tracked when a user views an email, in-app notification, native display, or a web notification sent from CleverTap.
      </td>

      <td>
        The CleverTap SDK recognizes when a notification sent via CleverTap is viewed by a user.<br /><br />_Notification Viewed_ is available for email, web push, in-app, web popup, native display, and app inbox.<br /><br />Important Properties:<br />Variant: String value containing an A/B testing campaign's variant name.<br /><br />**Note**: Native display rendering is handled by the customer. CT will only track the event for native display if the customer raises an event. For more information, refer to  [Android Native Display](https://developer.clevertap.com/docs/android-native-display#raise-events-for-tracking)   and [iOS Native Display](https://developer.clevertap.com/docs/native-display-ios)  .
      </td>
    </tr>

    <tr>
      <td>
        Notification Clicked
      </td>

      <td>
        This event is tracked only when a user clicks on a campaign sent via CleverTap. You can track or create a _Notification Clicked_ event for every _UTM Visited_ event that is tracked by CleverTap and not any other provider.<br /><br />There is no separate event storage required for the _Notification Clicked_ event because it is derived from the _UTM Visited_ event.
      </td>

      <td>
        Recorded when a user clicks on a mobile push, in-app, email, web popup, or web push message sent via the CleverTap dashboard or through the campaign API.<br /><br />The Android push notifications containing deep links to third-party apps are not tracked.<br /><br />Important Properties:<br />Variant: String value containing an A/B testing campaign's variant name.<br />wzrk_c2a: String value containing the action button name of notification clicked events.<br />button_id: Visible only when the Notification Clicked event is tracked for button clicks associated with the Image Interstitial template.<br /><br />The "Notification Clicked" event is triggered only for CleverTap BSP users if Click tracking is enabled when creating WhatsApp campaigns
      </td>
    </tr>

    <tr>
      <td>
        Push Impressions
      </td>

      <td>
        This event is tracked when a push notification sent from CleverTap is delivered on a user’s device. The funnels on the _Push_ campaign statistics page reflects the count for this event.
      </td>

      <td>
        After the toggle for _Push Impressions_ is turned on/setup from settings, the CleverTap SDK starts recording an event whenever a push notification sent via CleverTap is delivered to the user’s device.
      </td>
    </tr>

    <tr>
      <td>
        App Version Changed
      </td>

      <td>
        This event is raised when a user’s current app version is different from the user’s previous app version.
      </td>

      <td>
        This event is tracked when the _CT App version_ system property differs from one _App Launched_ event to another.
      </td>
    </tr>

    <tr>
      <td>
        Notification Replied
      </td>

      <td>
        This event is recorded when a user replies to a SMS campaign.
      </td>

      <td>
        This event is raised when the brand receives a reply from the user.<br /><br />Properties:<br />Incoming Message Type: Represents the type of message received (text, image, document, etc.)<br />Channel: String value that represents the medium of the incoming message.<br />Incoming text: String value that represents the incoming message. In the case of an SMS campaign, it includes the reply message sent by the SMS recipient. The maximum length of the message is set to 512 characters.<br />Incoming Media URL: String value that represents the URL of the media included in the message.<br />Campaign ID: String value that represents the original campaign ID to which the user has replied<br />Lat: Float value that represents the latitude of the particular location.<br />Long: Float value that represents the longitude of the particular location.
      </td>
    </tr>

    <tr>
      <td>
        Reply Sent
      </td>

      <td>
        This event is recorded when an agent (CleverTap user) replies to a message from the end user.
      </td>

      <td>
        This event is raised against the user profile of the end user.
      </td>
    </tr>

    <tr>
      <td>
        State Transitioned
      </td>

      <td>
        This event is recorded for lifecycle optimizer when a user transitions from one stage to another.
      </td>

      <td>
        This event is raised whenever a user transitions from one state to another or from unmapped to one of the states in the lifecycle optimization framework. It is meant for internal usage at CleverTap and therefore, unavailable for querying.
      </td>
    </tr>

    <tr>
      <td>
        Session Concluded
      </td>

      <td>
        This event is recorded to mark the end of a session. Session tracking must be enabled for the event to be tracked.
      </td>

      <td>
        This event is raised when there is 20 minutes of inactivity after an event is raised for a user.
      </td>
    </tr>

    <tr>
      <td>
        Geocluster Entered
      </td>

      <td>
        This event is recorded to mark when a device enters a geofence.<br /><br />The event will only be applicable for customers who have the geofence feature enabled for them.
      </td>

      <td>
        Properties:<br />1. Cluster ID<br />2. Cluster name<br />3. Geofence ID<br /><br />The event is tracked whenever a device enters a geofence.
      </td>
    </tr>

    <tr>
      <td>
        Geocluster Exited
      </td>

      <td>
        This event is recorded to mark when a device exits a geofence.<br /><br />The event will only be applicable for customers who have the geofence feature enabled for them.
      </td>

      <td>
        Properties:<br />1. Cluster ID<br />2. Cluster name<br />3. Geofence ID<br /><br />The event is tracked whenever a device exits a geofence.
      </td>
    </tr>

    <tr>
      <td>
        Channel Unsubscribed
      </td>

      <td>
        This event is raised only for Email and Push campaigns. It is raised when end-users unsubscribe from future emails and push notifications. It is also raised when the user resubscribes for the email campaigns
      </td>

      <td>
        Properties:<br />1. Campaign ID: This is the ID of the campaign from which user are updating subscriptions.<br />2. Campaign Type: Currently only present for Email Campaigns.<br />3. Group: Group name from which the user unsubscribed/resubscribed.<br />4. Identity: The user identity/email address.<br />5. Variant<br />6. Type: Valid values are bounced, dropped, and spam. Email IDs that bounce, drop, or are marked as spam are opted out of future emails.<br />7. Subscription Type: Account level and Profile level.<br />- Profile Level: The specific profile is opted out for all email campaigns in the future until they opt in again.<br />- Account Level: The specific profile and email address are opted out of all email campaigns. Even if other profiles have that email address, they will not be sent emails in the future because that email address has been unsubscribed at the account level.<br />8. Resubscribed: The value is true if the user has resubscribed, or else the value will be false.<br />9. Reason: Currently, present for email campaigns only. It is the same reason that was given by the email provider for the type of error. For example: "smtp;550 5.1.1 The email account that you tried to reach does not exist. Please try double-checking the recipient's email address for typos or unnecessary spaces."
      </td>
    </tr>

    <tr>
      <td>
        Channel Subscribed
      </td>

      <td>
        This event is raised when the user subscribes to a push notification channel for devices with Android OS version 13 and above. For devices on Android 13 and above, the event is raised when the user gives permission. For devices on Android 12, the event is raised when the user resubscribes for the push campaigns.
      </td>

      <td>
        Properties:<br />Source: Indicates if the event is raised through a device, application, or API.<br />Channel: Indicates the channel for which the user has subscribed i.e. Push Notification.<br />App Version: Indicates the app version from which the event is raised.<br />SDK Version: Indicates the SDK version installed on the device.
      </td>
    </tr>

    <tr>
      <td>
        Notification Delivered
      </td>

      <td>
        This is an event raised only for Email, WhatsApp and SMS campaigns.
      </td>

      <td>
        In the case of Email campaigns, it is raised when the provider confirms that the email campaign is delivered to the recipient mail server. In most cases, this indicates successful delivery to the end user. For campaigns sent via Generic SMTP, CleverTap should receive a [callback](doc:generic-smtp-v2-payload) to raise this event.<br /><br />**Note**: [Notification Delivered](doc:email-campaign-stats-delivered) is currently released in Private Beta for Infobip (in the case of Advanced Email add-on) and Sendgrid email providers. Contact your Customer Success Manager for access.<br /><br />In the case of SMS campaigns, it is raised when the notification is delivered to the end user, and CleverTap receives the [callback](doc:generic-sms#sms-callbacks). It includes the `Provider` event property, a string value that represents the service through which the campaign is sent. For example, Twilio.<br /><br />In the case of WhatsApp, it is raised when the provider confirms that the notification has reached the end user (double-tick of WhatsApp).
      </td>
    </tr>

    <tr>
      <td>
        App Upgraded
      </td>

      <td>
        This event is raised when a user’s current app version differs from their previous app version.
      </td>

      <td>
        This event is tracked when the _CT App version_ system property for an app launch is different from the next app launch.
      </td>
    </tr>

    <tr>
      <td>
        AB Test Enter
      </td>

      <td>
        This event helps analyze the devices that have an A/B Test running on them. It also gives you the specific variant selected for the device.
      </td>

      <td>
        This event is raised when the device qualifies for an A/B Test as part of a Product Experience (PE).
      </td>
    </tr>

    <tr>
      <td>
        AB Test Exit
      </td>

      <td>
        This event helps analyze the devices that have exited an A/B Test.
      </td>

      <td>
        This event is raised when the goal of the A/B test is achieved.
      </td>
    </tr>

    <tr>
      <td>
        AB Experiment Rendered
      </td>

      <td>
        This event indicates that the variant has reached the device.
      </td>

      <td>
        Event is raised when you are using the _Product A/B Tests _feature.
      </td>
    </tr>

    <tr>
      <td>
        AB Experiment Rolled Out
      </td>

      <td>
        This event is raised when the winner variant is sent to all devices.
      </td>

      <td>
        Event is raised when you are using the _Product A/B Tests _feature.
      </td>
    </tr>

    <tr>
      <td>
        AB Experiment Stopped
      </td>

      <td>
        This event is raised when experiment was stopped.
      </td>

      <td>
        Event is raised when you are using the _Product A/B Tests _feature.
      </td>
    </tr>

    <tr>
      <td>
        AB Experiment Disqualified
      </td>

      <td>
        This event is raised when the device is disqualified.
      </td>

      <td>
        Event is raised when you are using the _Product A/B Tests _feature.
      </td>
    </tr>

    <tr>
      <td>
        Partner Sync
      </td>

      <td>
        An event raised for each user profile that is part of cohorts imported from partners like Mixpanel.
      </td>

      <td>
        The Partner Sync event is raised every time CleverTap receives a cohort sync request from partners like Mixpanel. This event is raised for each user in the cohort sync.
      </td>
    </tr>

    <tr>
      <td>
        CT Coupon Rewarded
      </td>

      <td>
        This event is raised when the coupon is issued to a user through a Promo campaign.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about rewarding the coupon:

        * **Coupon Name**: Name of the coupon configured for bulk coupon series. Applicable when using bulk coupon codes.
        * **Coupon Code**: The unique coupon code issued. Applicable for single-code coupons.
        * **Coupon ID**: A unique identifier assigned to the coupon instance.
        * **Campaign ID**: Identifier of the campaign that issued the coupon to the user.
        * **Description**: Textual description of the coupon as configured in the campaign settings.
        * **Event Timestamp**: The exact date and time when this event was recorded in CleverTap.
        * **Terms and Conditions**: Promotional terms defined for coupon usage.
        * **Coupon Start Date**: Date and time when the coupon becomes valid for use in the `DD-MM-YYYY HH:MM:SS` format.
        * **Redemption Activation Date**: If an activation delay is configured, this field defines when redemption becomes possible in the `DD-MM-YYYY HH:MM:SS` format.
      </td>
    </tr>

    <tr>
      <td>
        CT Coupon Redeemed
      </td>

      <td>
        This event is raised when the user redeems the coupon through the redemption API.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the redemption of the coupon:

        * **Redeemed Type**: Indicates the type of benefit originally redeemed using the coupon. Values can be `discount`, or `cashback`.
        * **Order ID**: The ID of the order for which the coupon was applied and subsequently redeemed. Helps map the reversal back to the original transaction.
        * **Event Timestamp**: The exact date and time when the redeemed event was logged in CleverTap. Useful for auditing, ordering, and reporting.
        * **Discount Amount**: The monetary value of the discount that was redeemed. Applicable if the original reward was a discount coupon.
        * **Coupon Name**: Name of the coupon used during redemption. Typically configured at the coupon level.
        * **Coupon ID**: Unique identifier for the coupon that is being redeemed.
        * **Coupon Code**: Coupon code that was redeemed.
        * **Cashback Points**: Points value credited to the user's wallet linked to cashback when users redeem the cashback coupon.
        * **Discount Amount**: The amount of discount redeemed by the user. Applicable when the user redeems the discount coupon.
      </td>
    </tr>

    <tr>
      <td>
        CT Coupon Reverted
      </td>

      <td>
        This event is raised when a redeemed coupon is reversed.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the redemption of the coupon:

        * **Redeemed Type**: Indicates the type of benefit originally redeemed using the coupon. Values could include: `discount` or `cashback`.
        * **Order ID**: The ID of the order for which the coupon was applied and subsequently reverted. Helps map the reversal back to the original transaction.
        * **Event Timestamp**: The exact date and time when the reverted event was logged in CleverTap. Useful for auditing, ordering, and reporting.
        * **Discount Amount**: The monetary value of the discount that was reverted. Applicable if the original reward was a discount coupon.
        * **Coupon Name**: Name of the coupon used during reversal. Typically configured at the coupon level.
        * **Coupon ID**: Unique identifier for the coupon that is being reverted.
        * **Coupon Code**: Coupon code that was reverted.
        * **Cashback Points**: Points value debited to the user's wallet linked to cashback when users revert the cashback coupon.
        * **Discount Amount**: The amount of discount reverted by the user. Applicable when the user redeems the discount coupon.
      </td>
    </tr>

    <tr>
      <td>
        CT Points Credited
      </td>

      <td>
        This event is raised when points are added to the loyalty wallet.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the credited points to the wallet:

        * **Points Expiry**: The expiration date/time of the credited points. Defines when the awarded points will no longer be valid in the `DD-MM-YYYY HH:MM:SS` format.
        * **Wallet ID**: Unique identifier for the wallet where points are being credited. Used to distinguish between multiple wallet types if applicable.
        * **Transaction ID**: Unique ID assigned to the point credit transaction. Useful for audit trails, debugging, and reporting.
        * **Source**: Identifies how the credit was initiated. Possible values can be `API`, `Campaign`, `Manual`, or `Cashback Coupon`.
        * **Points Description**: Descriptive label for the credit transaction. Configured during a campaign or an API call to explain why points were awarded.
        * **Points**: Number of points credited to the wallet. Numeric value, e.g., 25 or 100.
        * **Event Timestamp**: Timestamp representing when the event was logged in CleverTap. Used for tracking, filtering, and campaign attribution.
        * **Campaign ID**: The ID of the campaign responsible for the point credit. Applicable only if the source of credit is a campaign.
        * **Coupon Code**: Indicates the specific coupon code whose redemption resulted in the crediting of points. Applicable when the source is a cashback coupon.
        * **Coupon ID**: Refers to the unique coupon ID associated with the redemption that triggered the points credit. Applicable when the source is a cashback coupon.
        * **Sale Channel**: The source channel for the transaction (e.g., Mobile, Web, POS). Applies to credit transactions created via API.
        * **Location ID**: Identifier for the transaction location (e.g., store code). Applies to credit transactions created via API.
        * **Sale Amount**: Gross order value tied to the transaction.
      </td>
    </tr>

    <tr>
      <td>
        CT Points Debited
      </td>

      <td>
        This event is raised when points are deducted from the loyalty wallet.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the debited points to the wallet:

        * **Wallet ID**: Unique identifier for the wallet from which points are debited. Used to map the transaction to a specific reward wallet.
        * **Transaction ID**: Unique ID associated with the debit transaction. Useful for reconciliation and debugging.
        * **Source**: Indicates how the debit was triggered. Possible values can be `API`, `Manual`, or `Campaign`.
        * **Points Description**: Descriptive text or label explaining the context of the points debit. Configured during campaign or API setup.
        * **Points**: Number of points debited from the wallet. Numeric value, e.g., 10 or 50.
        * **Event Timestamp**: The exact time when the points debit action occurred and was logged in CleverTap. Auto-recorded for chronological tracking.
        * **Campaign ID**: ID of the campaign that triggered the debit (if applicable). Helps link the debit to a promotional action.
        * **Sale Channel**: The source channel for the transaction (e.g., Mobile, Web, POS). Applies to debit transactions created via API.
        * **Location ID**: Identifier for the transaction location (e.g., store code). Applies to debit transactions created via API.
        * **Sale Amount**: Gross order value tied to the transaction.
      </td>
    </tr>

    <tr>
      <td>
        CT Partner Voucher Rewarded
      </td>

      <td>
        This event is raised when a user receives a third-party partner voucher.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the debited points to the wallet:

        * **Voucher List ID**: Unique identifier assigned to the partner voucher list. Used to associate the voucher with its originating list.
        * **Voucher Code**: The actual voucher code issued to the user. Can be redeemed on a partner platform or used for benefit claims.
        * **Source**: The origin through which the voucher was issued. Possible values can be `API` or `Campaign`.
        * **Partner**: Name of the third-party or partner platform that provided the voucher. Used for tracking and analytics of partner-level voucher distribution.
        * **List Tag**: Tag or label associated with the voucher list. Useful for categorization, segmentation, or filtering of voucher campaigns.
        * **List Expiry**: Expiration date/time for the voucher list or voucher code. Determines the validity period of the voucher in the `DD-MM-YYYY HH:MM:SS` format.
        * **List Description**: Description of the voucher list as configured in the system. May include offer details, partner terms, or redemption instructions.
        * **Event Timestamp**: The exact date and time when the voucher was rewarded to the user. Captured automatically by CleverTap for logging and analysis.
        * **Campaign ID**: ID of the campaign that rewarded the voucher. Links the voucher issuance to the triggering promo campaign.
      </td>
    </tr>

    <tr>
      <td>
        CT Custom Reward Issued
      </td>

      <td>
        This event is raised when a custom reward is issued to a user through a Promo campaign or API.
      </td>

      <td>
        The following properties are captured as part of this event to provide additional context about the issued custom reward:

        * **Reward Name**: Name of the custom reward issued to the user. Typically defined while configuring the reward.
        * **Reward Type**: Type or category of the reward. For example, physical item, experience, service, or webhook-based reward.
        * **Description**: Description of the reward as configured during setup. Provides additional details about the reward.
        * **Points**: Number of loyalty points associated with the reward, if applicable. Useful when rewards are linked to point redemption.
        * **Client Reward ID**: Identifier provided by the client system for the reward. Helps map CleverTap rewards to external systems.
        * **CleverTap Reward ID**: Unique identifier assigned to the reward within CleverTap.
        * **Campaign ID**: ID of the campaign that triggered the reward issuance. Applicable when the reward is issued via a campaign.
        * **CT Source**: Indicates how the reward was issued. Possible values can be `API`, `Campaign`, or `Manual`.
        * **Wallet ID**: Identifier of the wallet associated with the reward, if applicable.
        * **Wallet Name**: Name of the wallet associated with the reward, useful when multiple wallets exist.
        * **Event Timestamp**: The exact date and time when the reward was issued and recorded in CleverTap. Used for tracking and reporting.
      </td>
    </tr>
  </tbody>
</Table>

# Debug Events

Debug events are events recorded automatically after you integrate our SDK. These events are raised at certain lifecycle stages in your integration and help you track and manage your integration. These events are available on any profile page and _Find People_ page by adding a parameter to the end of the URL `?showDebugEvents=true`.

| Event Name        | Description                                                                                                                                                                                                                                                    | When is it raised                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Identity Set      | This debug event is raised when a new user is identified on a customer’s app or an identified user pushes another identity.                                                                                                                                    | This event monitors the status and data points that are important for the identification and engagement of users. This event is for monitoring and debugging only.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Identity Reset    | This debug event is raised when a profile is demerged (after demerged, a new profile for every device is created and identities are dropped) either from the dashboard (click on the _Profile_ page to reset identities) or through the _Demerge Profile API_. | It monitors the reset of identities and handles unnecessary merges. This event is used for monitoring and debugging only.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Identity Error    | This debug event is raised when an existing identity is associated incorrectly with another identity. The former identity is now declared as invalid for the latter's profile.                                                                                 | This event is for monitoring and debugging when identity merges are invalid.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Reachable By      | This debug event is raised when a user becomes reachable by a communication channel such as SMS, email, mobile push, or when there are changes to the existing communication channel.                                                                          | Tracked for a profile when:<br />- Push token is added/changed.<br />- Email ID is added/changed.<br />- Phone number is added/changed.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Push Unregistered | This event tracks the removal of a mobile push token. It is also raised when FCM returns a 404 Unregistered error for stale tokens from devices that have not connected to FCM for 270 days or for users who uninstall the app.                                | This event is raised when an existing mobile push token is removed for a profile.<br /><br />Tracked for a profile when:<br />- A user logs out of the device, and another user logs in. Applicable only if the `onUserLogin()` method is implemented.<br />- When a push token is removed using the `pushFcmRegisterationId("token",false)` method. Applicable only for Android.<br />- FCM returns a [404 Unregistered error](https://firebase.google.com/docs/reference/fcm/rest/v1/ErrorCode) for stale tokens from devices that have not connected to FCM for 270 days or for users who have uninstalled the app. |

# Custom Events

Custom events are events you define and track with our SDK or API. For more information, refer to the [Events](https://developer.clevertap.com/docs/events#custom-events) in the developer documentation.

## Charged Event

CleverTap also records transactions or purchases using a special event called **Charged**. Clevertap enriches this special event with additional information such as items sold, their categories, transaction amount, transaction ID, and information about your users. Recording a purchase against a user marks them as a customer in CleverTap and enables you to compare your funnel reports between customers and other users.

When recording customer purchases, you can also record the following:

* Items Sold
  You must use the Items collection to record a list of items sold. Along with the product name, you can add properties such as size, color, category, etc.

* Transaction Amount
  The transaction total or subscription charge must be recorded in an event property called Amount.

For more information about recording a Charged event, refer to [Events](https://developer.clevertap.com/docs/events#recording-customer-purchases) under developer documentation.

### Advantages of the Charged Event

The following are the advantages of Charged event:

* Helps you identify your customers and how they are using your app or website
* Run campaigns to reward loyal users or get lost customers back
* Measure customer loyalty via running a cohort analysis on repeat purchases
* Analyze paid campaign performance by total revenue earned
* Get revenue insights like – total revenue, number of transactions, count of paying users, and much more

### Charged Event Personalization

You can personalize the message for customers who purchase multiple items in a single transaction. You can do so by using liquid tags from the CleverTap dashboard, as shown in the following sample codes:

* **Using for Loops in Liquid Tags**

* **Using Manual Indexing in Liquid Tags**

`Event.items` is a custom array property that you can use to store additional information about items associated with an event. It allows you to include item-specific details when tracking events. For example, if an event called "Charged" represents a user making a purchase, you can use the `Charged.Items` array to store information about the specific items purchased within that event. Each item in the array can have its own properties, such as name, price, quantity, and so.

You can personalize the message for any number of items in the `Event.items` array. For example, you want to send an email including order details to the customers who bought three books from your e-commerce website. The `Event.items` array, in this case, would include three items, and you can send a personalized message for all three items.

![](https://files.readme.io/aef5e4b-Charged_Event_Personalization.png) Charged Event Personalization

In the case of manual indexing, you can ensure that the index is smaller than the size of the Items array using `Event.Items.size`. If the index value exceeds the size of the Items array, the message is NOT dispatched and is marked against errors.

> 📘 Charged Event Personalization for App Inbox Campaigns
>
> * In the case of App Inbox campaigns, event personalization for `Charged.Items` is not enabled.
> * However, if you use event personalization with `Charged.Items`, the default values for the items are displayed in the case of App Inbox campaigns.
> * If you use event personalization with `Charged.Items` when creating a combination of Push Notification and App Inbox campaigns, the personalized values for the items are displayed for Push and default values are displayed for App Inbox.

# Event Data Types

CleverTap supports the following data types:

* String
* Integer
* Float
* Boolean
* Mixed

# Multi-Value Array for Custom Event Properties

Multi-value arrays allow brands to capture multiple related values within a single event property. Instead of sending separate events for each item, brands can send a single event containing an array of values. This helps represent actions that involve multiple items while keeping event tracking simpler and more efficient.

CleverTap supports Multi-value arrays to help brands model richer event data. Arrays in the `eventData` payload can contain strings or integers. However, CleverTap stores all Multi-value array entries internally as strings.

## Use Cases

**E-Commerce Orders**
Multi-value arrays are beneficial in scenarios where a single purchase contains multiple items. For example, an `Order Confirmation` can include an array of product IDs or categories purchased in that transaction. This allows brands to analyze purchase patterns and create segments based on items included in past orders.

**Media and Entertainment Consumption**
Streaming platforms can capture multiple genres, tags, or content IDs associated with a user session. For example, a `Content Watched` event can include an array of genres such as Action, Thriller, Drama. This enables better audience segmentation and personalized content recommendations based on viewing preferences.

<Callout icon="📘" theme="info">
  **`Charged -> Items` is Reserved**

  Multi-value arrays do not apply to the `Charged` event’s `Items` key. The `Charged → Items` field is a reserved implementation and supports an array of objects by design.

  For more information, refer to [Charged as a Special Event](https://developer.clevertap.com/docs/events#what-makes-charged-a-special-event).
</Callout>

The following is a sample JSON showing the Multi-value array:

```json
{
  "eventName": "Order Confirmation",
  "eventData": {
    "Category Name": [
      "Milk Products",
      "Milk Products",
      "Vegetable",
      "Vegetable",
      "Vegetable"
    ],
    "Cart value": 1054.5,
    "Currency": "INR",
    "Cart items": [
      "Yogurt",
      "Ghee",
      "Cucumber",
      "Onion",
      "Green Chilli"
    ],
    "Cart items id": [78, 288, 150, 319, 109],
    "Category ID": [39, 39, 41, 41, 41]
  }
}
```

The following table summarizes the limits and ingestion behavior for Multi-value arrays in event properties

| Constraint                            | Limit          | Behavior if Limit is Exceeded                                 |
| ------------------------------------- | -------------- | ------------------------------------------------------------- |
| Maximum values per event property key | 100 items      | Additional values beyond 100 are dropped using FIFO logic     |
| Maximum length per array value        | 512 characters | Values exceeding 512 characters are dropped during ingestion. |
| Empty array after processing          | Not allowed    | The event property is removed during ingestion                |

You can use Multi-value arrays for event properties across platforms, including filtering in [NextGen Segment Builder](doc:segmentation), personalization, and conditional messaging.

The following image shows the Multi-value array in the NextGen Segment Builder:

<Image align="center" border={true} caption="Multi-Value Array in Segment Builder" src="https://files.readme.io/503b9237448b8b0fec72d319a7ca0c37e37aa2a52f642534e8c37fb7362f2649-image.png" />

The following image shows the Multi-value array for Personalization:

<Image align="center" border={true} caption="Using Multi-Value Array for Personalization" src="https://files.readme.io/5d22d18bed80e329e68567bb594016072fb40c0e3cb5e4146e72890921dad00d-image_7.png" />

# Event Metadata Recorded Automatically

For every recorded event, CleverTap records the following standard metadata:

* Information about the user who performed the event.
* Date and time when the event was recorded.
* The number of screens viewed by the user before performing the action.
* The referring site and the source of the user visit if it was from an external source.

In addition, CleverTap keeps the user profiles updated with the latest:

* Geographic information like their city, region, country, and latitude/longitude (if available).
* Browser, device make, or model used to access the website or app.

# System Properties

CleverTap tracks the following system properties automatically from the mobile SDK. All the system properties are prefixed by _CT_ indicating that they are provided by CleverTap.

The following properties are tracked automatically on all events:

| System Property | Description                                                                                                                                                                                                                                                                                                                                            |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| CT App Version  | This is the current version of your application installed on the user device.                                                                                                                                                                                                                                                                          |
| CT Latitude     | The user location identified by the latitude.                                                                                                                                                                                                                                                                                                          |
| CT Longitude    | The user location identified by the longitude.                                                                                                                                                                                                                                                                                                         |
| CT Source       | The source of the event.<br /><br />For example, the event may originate from a Mobile SDK or an API.<br /><br />All possible values:<br />- Mobile (Mobile SDK)<br />- MobileWeb (Web SDK)<br />- Web (Web SDK)<br />- API<br />- segment<br />- appsflyer<br />- apsalar<br />- branch<br />- tune<br />- System (for events generated by CleverTap) |

The following properties are available on the _App Launched_ event:

| System Property      | Description                                                                                                                                                                                                                                                                                                                                            |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| CT App Version       | This is the current version of your application installed on the user device.                                                                                                                                                                                                                                                                          |
| CT Latitude          | The user location identified by the latitude.                                                                                                                                                                                                                                                                                                          |
| CT Longitude         | The user location identified by the longitude.                                                                                                                                                                                                                                                                                                         |
| CT OS Version        | The operating system of the device.<br />For example, 1.0.0.                                                                                                                                                                                                                                                                                           |
| CT SDK Version       | The CleverTap SDK version. For example, 30501.                                                                                                                                                                                                                                                                                                         |
| CT Network Carrier   | The network carrier of the device.<br />For example, AT&T, Vodafone.                                                                                                                                                                                                                                                                                   |
| CT Network Type      | The network type of the device.<br />For example, 4G.                                                                                                                                                                                                                                                                                                  |
| CT Connected To WiFi | Indicates if the device is connected to the Wi-FI.                                                                                                                                                                                                                                                                                                     |
| CT Bluetooth Version | The Bluetooth version of the device.                                                                                                                                                                                                                                                                                                                   |
| CT Bluetooth Enabled | Indicates if Bluetooth is enabled on the device.                                                                                                                                                                                                                                                                                                       |
| CT Source            | The source of the event.<br /><br />For example, the event may originate from a Mobile SDK or an API.<br /><br />All possible values:<br />- Mobile (Mobile SDK)<br />- MobileWeb (Web SDK)<br />- Web (Web SDK)<br />- API<br />- segment<br />- appsflyer<br />- apsalar<br />- branch<br />- tune<br />- System (for events generated by CleverTap) |

> 📘 Latitude and Longitude
>
> The system properties _latitude_ and _longitude_ are captured and sent from the SDK only if the user gives consent on your app.
