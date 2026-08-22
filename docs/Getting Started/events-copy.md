---
title: Events Copy
excerpt: >-
  Events track what individual actions users perform in your app or website.
  Learn about system events, custom events, and event properties in CleverTap.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Events track what individual actions users perform in your app or website. Some examples of events include a user launching an app, viewing a product, listening to a song, sharing a photo, making a purchase, or favoriting an item. 

By tracking events in your app, you can better understand what users are doing. In CleverTap, you can analyze these events in many different ways, such as getting aggregating metrics of a specific event or measuring how a specific event type trends over time. You can also engage with your users based on these events by creating campaigns in CleverTap that are triggered by them. 

<Image align="center" border={true} caption="Events" src="https://files.readme.io/40b874a-events1.png" />

## Event Categories

CleverTap has two categories of events:

* System events: Events recorded automatically after you integrate our SDK. 
* Custom events: Events you define and track with our SDK or API.

## Event Properties

Events have details that describe the action taking place called properties. 

For example, while recording the _Product viewed_ event, you could also store event properties, such as product name, category, and price. Recording event properties will help you discover insights, such as which product category is more popular, and segment users based on which categories or price points they have viewed.

# System Events

<Callout icon="📘">
  **Events Changelog**

  You can find information about the most recent changes to our existing system events or the introdu[tion of new ones in our [Events Changelog](doc:events-changelog).
</Callout>

System events are events recorded automatically after you integrate our SDK.

<Table align={["left", "left", "left"]}>
  <thead>
    <tr>
      <th>Event Type</th>
      <th>Description</th>
      <th>How Event is Tracked</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>App Installed</td>
      <td>
        The event is raised when the user launches the app for the first time.
      </td>
      <td>
        <p>
          The event is raised when the user launches the app for the first time on any mobile device.
        </p>
        <p>
          This event can be recorded multiple times for a single user in these cases:
        </p>
        <ul>
          <li>The user installs your app, uninstalls it, and then reinstalls it.</li>
          <li>The user clears your app's memory and relaunches it.</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>App Launched</td>
      <td>
        This event is recorded every time a user launches your application.
      </td>
      <td>
        <p>Recorded in two cases:</p>
        <ul>
          <li>Fresh app launch (from a killed state).</li>
          <li>
            When an app is brought to the foreground after 20 minutes of inactivity in the background.
          </li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>App Uninstalled</td>
      <td>
        This event is recorded when a user uninstalls your application.
      </td>
      <td>
        <p>
          Tracked using silent push notifications (not rendered on the user's device). CleverTap sends silent push notifications
          to your entire install base once every 24 hours to track uninstalls.
        </p>
        <p>
          For more information, refer to
          [App Uninstall](https://clevertap.com/blog/track-app-uninstalls-effectively/).
        </p>
      </td>
    </tr>

    <tr>
      <td>Web Session Started</td>
      <td>
        Web entry event similar to the App Launched event. Triggered when a user starts a session or engages with your website.
      </td>
      <td>
        <p>Recorded in two cases:</p>
        <ul>
          <li>When a user opens a webpage.</li>
          <li>When a user reloads the browser after 20 minutes of inactivity.</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>UTM Visited</td>
      <td>
        Tracked when a user clicks a link from a marketing campaign that has a UTM parameter or when a CleverTap-integrated
        attribution platform (such as Branch or Singular) sends this information to CleverTap.
      </td>
      <td>
        The <em>UTM Visited</em> event is recorded for your marketing campaigns from external sources such as Google Ads or AdRoll.
      </td>
    </tr>

    <tr>
      <td>Notification Sent</td>
      <td>
        <p>
          Tracked when a campaign message is sent to a user. Always recorded, even if the user does not open or click the message.
        </p>
        <p>
          Recorded for email, mobile push, SMS, and web push campaigns.
          The <em>Notification Sent</em> event is available on the <em>Event</em> dashboard but is not displayed on the
          <em> User Profile</em>.
        </p>
      </td>
      <td>
        The event is tracked when the notification is successfully sent from CleverTap to the selected communication channel.
      </td>
    </tr>

    <tr>
      <td>Notification Failed</td>
      <td>
        This event logs campaign errors in CleverTap.
      </td>
      <td>
        <p>Important properties include:</p>
        <ul>
          <li><strong>Campaign ID</strong>: Identifies the specific campaign associated with the error.</li>
          <li><strong>Campaign Type</strong>: Indicates the type of campaign (WhatsApp, SMS, Email, etc.).</li>
          <li><strong>Error</strong>: The error message observed in the campaign.</li>
          <li><strong>Label</strong>: The label associated with the campaign.</li>
          <li>
            <strong>Variant</strong>: Helps identify errors for a specific variant in A/B, split delivery,
            or multi-variant campaigns.
          </li>
        </ul>
        <p>
          For detailed information on WhatsApp errors, refer to
          [WhatsApp Error Stats](doc:whatsapp-stats)
        </p>
        <p>
          <strong>Note:</strong> This event is currently in Private Beta for Email Campaigns. Contact your account manager to enable it.
        </p>
      </td>
    </tr>

    <tr>
      <td>Notification Viewed</td>
      <td>
        This event is tracked when a user views an email, in-app notification, or web notification sent from CleverTap.
      </td>
      <td>
        <p>
          The CleverTap SDK recognizes when a notification sent via CleverTap is viewed by a user.
        </p>
        <p>
          <em>Notification Viewed</em> is available for email, web push, in-app, web popup, and app inbox.
        </p>
        <p>Important properties:</p>
        <ul>
          <li><strong>Variant</strong>: String value containing an A/B testing campaign's variant name.</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>Notification Clicked</td>
      <td>
        <p>
          This event is tracked when a user clicks on a campaign sent via CleverTap.
        </p>
        <p>
          You can track or create a <em>Notification Clicked</em> event for every <em>UTM Visited</em> event tracked by CleverTap.
          It is derived from the <em>UTM Visited</em> event and does not require separate event storage.
        </p>
      </td>
      <td>
        <p>
          Recorded when a user clicks on a mobile push, in-app, email, web popup, or web push message sent via the CleverTap
          dashboard or the campaign API.
        </p>
        <p>Android push notifications with deep links to third-party apps are not tracked.</p>
        <p>Important properties:</p>
        <ul>
          <li><strong>Variant</strong>: A/B testing campaign variant name.</li>
          <li><strong>wzrk_c2a</strong>: Action button name for notification clicked events.</li>
          <li>
            <strong>button_id</strong>: Visible only when the event is tracked for button clicks associated with
            the Image Interstitial template.
          </li>
        </ul>
        <p>
          The <em>Notification Clicked</em> event is triggered for CleverTap BSP users only if click tracking is enabled
          when creating WhatsApp campaigns.
        </p>
      </td>
    </tr>

    <tr>
      <td>Push Impressions</td>
      <td>
        This event is tracked when a push notification sent from CleverTap is delivered on a user's device.
        Funnels on the <em>Push</em> campaign statistics page reflect the count for this event.
      </td>
      <td>
        After the <em>Push Impressions</em> toggle is turned on in Settings, the CleverTap SDK starts recording
        this event whenever a push notification sent via CleverTap is delivered to the device.
      </td>
    </tr>

    <tr>
      <td>App Version Changed</td>
      <td>
        This event is raised when a user's current app version is different from the user's previous app version.
      </td>
      <td>
        Tracked when the <em>CT App version</em> system property differs from one <em>App Launched</em> event to another.
      </td>
    </tr>

    <tr>
      <td>Notification Replied</td>
      <td>
        This event is recorded when a user replies to an SMS campaign.
      </td>
      <td>
        <p>This event is raised when the brand receives a reply from the user.</p>
        <p>Properties:</p>
        <ul>
          <li><strong>Incoming Message Type</strong>: Type of message received (text, image, document, etc.).</li>
          <li><strong>Channel</strong>: Medium of the incoming message.</li>
          <li>
            <strong>Incoming Text</strong>: The incoming message content. For SMS campaigns, this is the reply message
            sent by the recipient (max length 512 characters).
          </li>
          <li><strong>Incoming Media URL</strong>: URL of any media in the message.</li>
          <li><strong>Campaign ID</strong>: ID of the original campaign to which the user replied.</li>
          <li><strong>Lat</strong>: Latitude of the particular location.</li>
          <li><strong>Long</strong>: Longitude of the particular location.</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>Reply Sent</td>
      <td>
        This event is recorded when an agent (CleverTap user) replies to a message from the end user.
      </td>
      <td>
        This event is raised against the user profile of the end user.
      </td>
    </tr>

    <tr>
      <td>State Transitioned</td>
      <td>
        This event is recorded for Lifecycle Optimizer when a user transitions from one stage to another.
      </td>
      <td>
        This event is raised whenever a user transitions from one state to another or from unmapped to a state
        in the lifecycle optimization framework. It is meant for internal usage and is not available for querying.
      </td>
    </tr>

    <tr>
      <td>Session Concluded</td>
      <td>
        This event is recorded to mark the end of a session. Session tracking must be enabled for the event to be tracked.
      </td>
      <td>
        This event is raised when there is 20 minutes of inactivity after an event is raised for a user.
      </td>
    </tr>

    <tr>
      <td>Geocluster Entered</td>
      <td>
        This event is recorded when a device enters a geofence. Applicable only for customers with the geofence feature enabled.
      </td>
      <td>
        <p>Properties:</p>
        <ol>
          <li>Cluster ID</li>
          <li>Cluster Name</li>
          <li>Geofence ID</li>
        </ol>
        <p>Tracked whenever a device enters a geofence.</p>
      </td>
    </tr>

    <tr>
      <td>Geocluster Exited</td>
      <td>
        This event is recorded when a device exits a geofence. Applicable only for customers with the geofence feature enabled.
      </td>
      <td>
        <p>Properties:</p>
        <ol>
          <li>Cluster ID</li>
          <li>Cluster Name</li>
          <li>Geofence ID</li>
        </ol>
        <p>Tracked whenever a device exits a geofence.</p>
      </td>
    </tr>

    <tr>
      <td>Channel Unsubscribed</td>
      <td>
        Raised for Email and Push campaigns when end-users unsubscribe from (or resubscribe to) future emails and push notifications.
      </td>
      <td>
        <p>Properties include:</p>
        <ol>
          <li>Campaign ID and Campaign Type.</li>
          <li>Group: Name of the group from which the user unsubscribed/resubscribed.</li>
          <li>Identity: User identity or email address.</li>
          <li>Variant.</li>
          <li>
            Type (bounced, dropped, spam): Email IDs that bounce, drop, or are marked as spam are opted out of future emails.
          </li>
          <li>
            Subscription Type: Account-level or Profile-level.
            <ul>
              <li>Profile Level: The profile is opted out of all email campaigns until they opt in.</li>
              <li>Account Level: The email address is opted out across the account (even for other profiles using it).</li>
            </ul>
          </li>
          <li>Resubscribed: <code>true</code> if the user resubscribed, otherwise <code>false</code>.</li>
          <li>
            Reason: For email campaigns, the provider's detailed reason for the error (for example, mailbox does not exist).
          </li>
        </ol>
      </td>
    </tr>

    <tr>
      <td>Channel Subscribed</td>
      <td>
        Raised when the user subscribes to a push notification channel.
        For Android 13+, it is raised when the user grants permission.
        For Android 12, it is raised when the user resubscribes for push campaigns.
      </td>
      <td>
        <p>Properties:</p>
        <ul>
          <li><strong>Source</strong>: Device, application, or API.</li>
          <li><strong>Channel</strong>: Channel for which the user subscribed (for example, Push Notification).</li>
          <li><strong>App Version</strong>: App version from which the event is raised.</li>
          <li><strong>SDK Version</strong>: SDK version installed on the device.</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>Notification Delivered</td>
      <td>
        This event is raised only for Email, WhatsApp, and SMS campaigns.
      </td>
      <td>
        <ul>
          <li>
            <strong>Email</strong>: Raised when the provider confirms that the email is delivered to the recipient mail server.
            For Generic SMTP, CleverTap must receive a callback to raise this event.
          </li>
          <li>
            <strong>SMS</strong>: Raised when the notification is delivered to the end user and CleverTap receives the callback.
            Includes the <em>Provider</em> event property indicating the sending service (for example, Twilio).
          </li>
          <li>
            <strong>WhatsApp</strong>: Raised when the provider confirms that the notification has reached the end user
            (double-tick on WhatsApp).
          </li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>App Upgraded</td>
      <td>
        This event is raised when a user's current app version differs from their previous app version.
      </td>
      <td>
        Tracked when the CT App version system property for an app launch is different from the next app launch.
      </td>
    </tr>

    <tr>
      <td>AB Test Enter</td>
      <td>
        Helps analyze devices that have an A/B Test running on them and shows the specific variant selected.
      </td>
      <td>
        This event is raised when the device qualifies for an A/B Test as part of a Product Experience.
      </td>
    </tr>

    <tr>
      <td>AB Test Exit</td>
      <td>
        Helps analyze devices that have exited an A/B Test.
      </td>
      <td>
        This event is raised when the goal of the A/B Test is achieved.
      </td>
    </tr>

    <tr>
      <td>AB Experiment Rendered</td>
      <td>
        Indicates that the variant has reached the device.
      </td>
      <td>
        Raised when you are using the Product A/B Tests feature and a variant is rendered on the device.
      </td>
    </tr>

    <tr>
      <td>AB Experiment Rolled Out</td>
      <td>
        Raised when the winner variant is sent to all devices.
      </td>
      <td>
        Raised when using the Product A/B Tests feature and the winning variant is rolled out.
      </td>
    </tr>

    <tr>
      <td>AB Experiment Stopped</td>
      <td>
        Raised when an experiment is stopped.
      </td>
      <td>
        Raised when using the Product A/B Tests feature and the experiment is stopped.
      </td>
    </tr>

    <tr>
      <td>AB Experiment Disqualified</td>
      <td>
        Raised when the device is disqualified from an experiment.
      </td>
      <td>
        Raised when using the Product A/B Tests feature and a device is disqualified.
      </td>
    </tr>

    <tr>
      <td>Partner Sync</td>
      <td>
        Event raised for each user profile that is part of cohorts imported from partners like Mixpanel.
      </td>
      <td>
        Raised every time CleverTap receives a cohort sync request from partners (for example, Mixpanel) for each user in the cohort.
      </td>
    </tr>

    <tr>
      <td>CT Coupon Rewarded</td>
      <td>
        Raised when a coupon is issued to a user through a Promo campaign.
      </td>
      <td>
        <p>
          Captures properties such as:
        </p>
        <ul>
          <li>Coupon Name, Coupon Code, Coupon ID</li>
          <li>Campaign ID, Description, Terms and Conditions</li>
          <li>Event Timestamp</li>
          <li>Coupon Start Date (format: <code>DD-MM-YYYY HH:MM:SS</code>)</li>
          <li>Redemption Activation Date (format: <code>DD-MM-YYYY HH:MM:SS</code>)</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>CT Coupon Redeemed</td>
      <td>
        Raised when the user redeems the coupon through the redemption API.
      </td>
      <td>
        <p>
          Captures properties such as:
        </p>
        <ul>
          <li>Redeemed Type (for example, <code>discount</code>, <code>cashback</code>)</li>
          <li>Order ID</li>
          <li>Event Timestamp</li>
          <li>Discount Amount</li>
          <li>Coupon Name, Coupon ID, Coupon Code</li>
          <li>Cashback Points</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>CT Coupon Reverted</td>
      <td>
        Raised when a redeemed coupon is reversed.
      </td>
      <td>
        <p>
          Captures properties such as:
        </p>
        <ul>
          <li>Redeemed Type (for example, <code>discount</code>, <code>cashback</code>)</li>
          <li>Order ID</li>
          <li>Event Timestamp</li>
          <li>Discount Amount</li>
          <li>Coupon Name, Coupon ID, Coupon Code</li>
          <li>Cashback Points</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>CT Points Credited</td>
      <td>
        Raised when points are added to the loyalty wallet.
      </td>
      <td>
        <p>Captures properties such as:</p>
        <ul>
          <li>Points Expiry (format: <code>DD-MM-YYYY HH:MM:SS</code>)</li>
          <li>Wallet ID, Transaction ID</li>
          <li>
            Source (for example, <code>API</code>, <code>Campaign</code>, <code>Manual</code>, <code>Cashback Coupon</code>)
          </li>
          <li>Points Description</li>
          <li>Points (numeric)</li>
          <li>Event Timestamp</li>
          <li>Campaign ID (if source is a campaign)</li>
          <li>Coupon Code and Coupon ID (if source is a cashback coupon)</li>
          <li>Sale Channel, Location ID, and Sale Amount</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>CT Points Debited</td>
      <td>
        Raised when points are deducted from the loyalty wallet.
      </td>
      <td>
        <p>Captures properties such as:</p>
        <ul>
          <li>Wallet ID, Transaction ID</li>
          <li>Source (for example, <code>API</code>, <code>Manual</code>, <code>Campaign</code>)</li>
          <li>Points Description</li>
          <li>Points (numeric)</li>
          <li>Event Timestamp</li>
          <li>Campaign ID (if applicable)</li>
          <li>Sale Channel, Location ID, and Sale Amount</li>
        </ul>
      </td>
    </tr>

    <tr>
      <td>CT Partner Voucher Rewarded</td>
      <td>
        Raised when a user receives a third-party partner voucher.
      </td>
      <td>
        <p>Captures properties such as:</p>
        <ul>
          <li>Voucher List ID</li>
          <li>Voucher Code</li>
          <li>Source (for example, <code>API</code>, <code>Campaign</code>)</li>
          <li>Partner (third-party provider name)</li>
          <li>List Tag</li>
          <li>List Expiry (format: <code>DD-MM-YYYY HH:MM:SS</code>)</li>
          <li>List Description</li>
          <li>Event Timestamp</li>
          <li>Campaign ID</li>
        </ul>
      </td>
    </tr>
  </tbody>
</Table>

# Debug Events

Debug events are events recorded automatically after you integrate our SDK. These events are raised at certain lifecycle stages in your integration and help you track and manage your integration. These events are available on any profile page and _Find People_ page by adding a parameter to the end of the URL `?showDebugEvents=true`.  

<Table>
  <thead>
    <tr>
      <th>Event Name</th>
      <th>Description</th>
      <th>When is it raised</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Identity Set</td>
      <td>
        This debug event is raised when a new user is identified on a customer's app or an identified user pushes another identity.
      </td>
      <td>
        This event monitors the status and data points that are important for the identification and engagement of users.
        This event is for monitoring and debugging only.
      </td>
    </tr>
    <tr>
      <td>Identity Reset</td>
      <td>
        This debug event is raised when a profile is demerged (after demerged, a new profile for every device is created and identities are dropped)
        either from the dashboard (click on the <em>Profile</em> page to reset identities) or through the <em>Demerge Profile API</em>.
      </td>
      <td>
        It monitors the reset of identities and handles unnecessary merges.
        This event is used for monitoring and debugging only.
      </td>
    </tr>
    <tr>
      <td>Identity Error</td>
      <td>
        This debug event is raised when an existing identity is associated incorrectly with another identity.
        The former identity is now declared as invalid for the latter's profile.
      </td>
      <td>
        This event is for monitoring and debugging when identity merges are invalid.
      </td>
    </tr>
    <tr>
      <td>Reachable By</td>
      <td>
        This debug event is raised when a user becomes reachable by a communication channel such as SMS, email, mobile push,
        or when there are changes to the existing communication channel.
      </td>
      <td>
        <p>Tracked for a profile when:</p>
        <ul>
          <li>Push token is added/changed.</li>
          <li>Email ID is added/changed.</li>
          <li>Phone number is added/changed.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Push Unregistered</td>
      <td>
        This event tracks the removal of a mobile push token.
        It is also raised when FCM returns a 404 Unregistered error for stale tokens from devices that have not connected
        to FCM for 270 days or for users who uninstall the app.
      </td>
      <td>
        <p>This event is raised when an existing mobile push token is removed for a profile.</p>
        <p>Tracked for a profile when:</p>
        <ul>
          <li>
            A user logs out of the device, and another user logs in.
            Applicable only if the <code>onUserLogin()</code> method is implemented.
          </li>
          <li>
            When a push token is removed using the
            <code>pushFcmRegisterationId("token",false)</code> method.
            Applicable only for Android.
          </li>
          <li>
            FCM returns a [404 Unregistered error](https://firebase.google.com/docs/reference/fcm/rest/v1/ErrorCode)
            for stale tokens from devices that have not connected to FCM for 270 days or for users who have uninstalled the app.
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</Table>

# Custom Events

Custom events are events you define and track with our SDK or API. For more information, refer to the [Events](https://developer.clevertap.com/docs/events#custom-events)  in the developer documentation.

## Charged Event

CleverTap also records transactions or purchases using a special event called **Charged**. Clevertap enriches this special event with additional information such as items sold, their categories, transaction amount, transaction ID, and information about your users. Recording a purchase against a user marks them as a customer in CleverTap and enables you to compare your funnel reports between customers and other users.

When recording customer purchases, you can also record the following: 

* Items Sold  
    You must use the Items collection to record a list of items sold. Along with the product name, you can add properties such as size, color, category, etc.
  * Transaction Amount  
      The transaction total or subscription charge must be recorded in an event property called Amount.

For more information about recording a Charged event, refer to [Events](https://developer.clevertap.com/docs/events#recording-customer-purchases)  under developer documentation.

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
  ```
  ```
* **Using Manual Indexing in Liquid Tags**
  ```
  ```

`Event.items` is a custom array property that you can use to store additional information about items associated with an event. It allows you to include item-specific details when tracking events. For example, if an event called "Charged" represents a user making a purchase, you can use the `Charged.Items` array to store information about the specific items purchased within that event. Each item in the array can have its own properties, such as name, price, quantity, and so.

You can personalize the message for any number of items in the `Event.items` array. For example, you want to send an email including order details to the customers who bought three books from your e-commerce website. The `Event.items` array, in this case, would include three items, and you can send a personalized message for all three items. 

<Image align="center" border={true} caption="Charged Event Personalization" src="https://files.readme.io/aef5e4b-Charged_Event_Personalization.png" />

In the case of manual indexing, you can ensure that the index is smaller than the size of the Items array using `Event.Items.size`. If the index value exceeds the size of the Items array, the message is NOT dispatched and is marked against errors.

> 📘 Charged Event Personalization for App Inbox Campaigns
> 
> - In the case of App Inbox campaigns, event personalization for `Charged.Items` is not enabled. 
> - However, if you use event personalization with `Charged.Items`, the default values for the items are displayed in the case of App Inbox campaigns.
> - If you use event personalization with `Charged.Items` when creating a combination of Push Notification and App Inbox campaigns, the personalized values for the items are displayed for Push and default values are displayed for App Inbox.

# Event Data Types

CleverTap supports the following data types:

* String
* Integer
* Float
* Boolean
* Mixed

You can use an array only with the Charged event. All others will return an incorrect data type if using an array.

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

<Table>
  <thead>
    <tr>
      <th>System Property</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>CT App Version</td>
      <td>This is the current version of your application installed on the user device.</td>
    </tr>
    <tr>
      <td>CT Latitude</td>
      <td>The user location identified by the latitude.</td>
    </tr>
    <tr>
      <td>CT Longitude</td>
      <td>The user location identified by the longitude.</td>
    </tr>
    <tr>
      <td>CT OS Version</td>
      <td>The operating system of the device.<br />For example,  1.0.0.</td>
    </tr>
    <tr>
      <td>CT SDK Version</td>
      <td>The CleverTap SDK version. For example, 30501.</td>
    </tr>
    <tr>
      <td>CT Network Carrier</td>
      <td>The network carrier of the device.<br />For example, AT&amp;T, Vodafone.</td>
    </tr>
    <tr>
      <td>CT Network Type</td>
      <td>The network type of the device.<br />For example, 4G.</td>
    </tr>
    <tr>
      <td>CT Connected To WiFi</td>
      <td>Indicates if the device is connected to the Wi-FI.</td>
    </tr>
    <tr>
      <td>CT Bluetooth Version</td>
      <td>The Bluetooth version of the device.</td>
    </tr>
    <tr>
      <td>CT Bluetooth Enabled</td>
      <td>Indicates if Bluetooth is enabled on the device.</td>
    </tr>
    <tr>
      <td>CT Source</td>
      <td>
        <p>The source of the event.</p>
        <p>For example, the event may originate from a Mobile SDK or an API.</p>
        <p>All possible values:</p>
        <ul>
          <li>Mobile (Mobile SDK)</li>
          <li>MobileWeb (Web SDK)</li>
          <li>Web (Web SDK)</li>
          <li>API</li>
          <li>segment</li>
          <li>appsflyer</li>
          <li>apsalar</li>
          <li>branch</li>
          <li>tune</li>
          <li>System (for events generated by CleverTap)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Latitude and Longitude
> 
> The system properties _latitude_ and _longitude_ are captured and sent from the SDK only if the user gives consent on your app.