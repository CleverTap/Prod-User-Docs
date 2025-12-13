---
title: Events_callback_WIP
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

Events track what individual actions users perform in your app or website. Some examples of events include a user launching an app, viewing a product, listening to a song, sharing a photo, making a purchase, or favoriting an item.

By tracking events in your app, you can better understand what users are doing. In CleverTap, you can analyze these events in many different ways, such as getting aggregating metrics of a specific event or measuring how a specific event type trends over time. You can also engage with your users based on these events by creating campaigns in CleverTap that are triggered by them. 

<Image title="events1.png" alt={898} className="border" border={true} src="https://files.readme.io/40b874a-events1.png" />

**Event Categories**

There are two categories of events in CleverTap: *System Events* and *Custom Events*. 

*System Events* are events recorded automatically after you integrate our SDK. *Custom Events* are events you define and track with our SDK or API.

**Event Properties**

Events have details that describe the action taking place called properties. 

For example, while recording the *Product viewed* event, you could also store event properties such as product name, category, and price. Recording event properties will help you discover insights, such as which category of products are more popular and help you segment users based on which categories or price points they have viewed.

# System Events

*System Events* are events recorded automatically after you integrate our SDK. 

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
        This event is recorded when a user installs your application.
      </td>

      <td>
        The event is raised when the user launches the app for the first time. 

        There are three cases when this event will be recorded multiple times for a single user. The first case is when a user installs your app, uninstalls it, and then reinstalls it. The second case is when a user clears your app's memory. The third case is when a user installs your app on multiple devices.
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
        There are two cases when this event will recorded. The first case is a fresh app launch, which is when an app is launched from a killed state. The second case is when an app is brought to the foreground after 20 minutes of inactivity in the background.
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
        This event is tracked by sending silent push notifications, which is a type of notifications that is not rendered on a user’s device. We send silent push notifications to your entire install base once every 24 hours to track uninstalls. For more information, refer to [App Uninstall](https://clevertap.com/blog/track-app-uninstalls-effectively/).
      </td>
    </tr>

    <tr>
      <td>
        UTM Visited
      </td>

      <td>
        This event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as Branch or Apsalar, sends this information to CleverTap.
      </td>

      <td>
        The *UTM Visited* event is recorded for your marketing campaigns from external sources, such as Google Adwords or AdRoll.
      </td>
    </tr>

    <tr>
      <td>
        Notification Sent
      </td>

      <td>
        This event is tracked when a campaign message is sent to a user. This event is always recorded, even if the user does not open or click on the message. This event is recorded for email, mobile push, SMS, web push, and Facebook Audience campaigns. The *Notification Sent* event is available on the *Event* dashboard but it is not displayed on the *User Profile*.
      </td>

      <td>
        The event is tracked when the notification is successfully sent from CleverTap to the communication channel you select for your campaign.
      </td>
    </tr>

    <tr>
      <td>
        Notification Viewed
      </td>

      <td>
        This event is tracked when a user views an email, in-app notification, or a web notification sent from CleverTap.
      </td>

      <td>
        The CleverTap SDK recognizes when a notification sent via CleverTap is viewed by a user.

        * Notification Viewed\* is available for Email, Web Push, InApp, Web Popup, and App Inbox.
      </td>
    </tr>

    <tr>
      <td>
        Notification Clicked
      </td>

      <td>
        This event is tracked only when a user clicks on a campaign sent via CleverTap. You can track or create a *Notification Clicked* event for every *UTM Visited* event that is tracked by CleverTap and not any other provider. There is no separate event storage required for the *Notification Clicked* event because it is derived from the *UTM Visited* event.
      </td>

      <td>
        Recorded when a user clicks on a mobile push, in-app, email, web-popup, or web push message sent via the CleverTap dashboard or through the campaign API. 

        The Android push notifications containing deep links to third-party apps are not tracked.
      </td>
    </tr>

    <tr>
      <td>
        Push Impressions
      </td>

      <td>
        This event is tracked when a push notification sent from CleverTap is delivered on a user’s device. The funnels on the *Push* campaign statistics page reflects the count for this event.
      </td>

      <td>
        After the toggle for *Push Impressions* is turned on/setup from settings, the CleverTap SDK starts recording an event whenever a push notification sent via CleverTap is delivered to the user’s device.
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
        This event is tracked when the *CT App version* system property differs from one *App Launched* event to another.
      </td>
    </tr>

    <tr>
      <td>
        Notification Replied
      </td>

      <td>
        This event is recorded when a user replies to a WhatsApp message.
      </td>

      <td>
        This event is raised when the brand receives a reply from the user.
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
        This event is recorded to mark when a device enters a geofence.\
        The event will only be applicable for customers who have the geofence feature enabled for them.
      </td>

      <td>
        Properties:

        1. Cluster id
        2. Cluster name
        3. Geofence id
      </td>
    </tr>

    <tr>
      <td>
        Geocluster Exited
      </td>

      <td>
        This event is recorded to mark when a device exits a geofence.\
        The event will only be applicable for customers who have the geofence feature enabled for them.
      </td>

      <td>
        Properties:

        1. Cluster id
        2. Cluster name
        3. Geofence id
      </td>
    </tr>

    <tr>
      <td>
        Channel Unsubscribed
      </td>

      <td>
        This event is raised when an email is not acknowledged.
      </td>

      <td>
        Properties:

        1. Campaign Id - This is the ID of\
            the campaign from which user are updating subscriptions.\
           Campaign Type - Currently only Email.
        2. Group - Group name from which the user unsubscribed/resubscribed.
        3. Identity - The user Identity/Email address.
        4. Variant
        5. Type - Valid values are bounced, dropped, and spam. Email IDs which bounce, drop or marked as spam are opted out from future emails
        6. Subscription Type - Account Level and Profile Level. Profile Level signifies that the user  who qualified for the communication is opted out. Account Level signifies that all users with the email address are opted out from future communications. 
        7. reason - Reason which was given by the email provider for the type of the error. For example : "smtp;550 5.1.1 The email account that you tried to reach does not exist. Please try double-checking the recipient's email address for typos or unnecessary spaces."
      </td>
    </tr>
  </tbody>
</Table>

# Debug Events

* *Debug Events* are events recorded automatically after you integrate our SDK. These events are raised at certain lifecycle stages in your integration and helps you track and manage your integration. These events are available on any profile page and *Find People* page by adding a parameter to the end of the URL `?showDebugEvents=true`.  

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Event Name
      </th>

      <th>
        Description
      </th>

      <th>
        When is it raised
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Identity Set
      </td>

      <td>
        This *Debug* event is raised when a new user is identified on a customer’s app or an identified user pushes another identity.
      </td>

      <td>
        This event monitors the status and data points that are important for the identification and engagement of users. This event is for monitoring and debugging only.
      </td>
    </tr>

    <tr>
      <td>
        Identity Reset
      </td>

      <td>
        This *Debug* event is raised when a profile is demerged (after demerged, a new profile for every device is created and identities are dropped) either from dashboard (click on the *Profile* page to reset identities) or through the *Demerge Profile API*.
      </td>

      <td>
        It monitors the reset of identities and handles unnecessary merges. This event is used for monitoring and debugging only.
      </td>
    </tr>

    <tr>
      <td>
        Identity Error
      </td>

      <td>
        This *Debug* event is raised when an existing identity is associated incorrectly with another identity. The former identity is now declared as invalid for the latter's profile.
      </td>

      <td>
        This event is for monitoring and debugging when identity merges are invalid.
      </td>
    </tr>

    <tr>
      <td>
        Reachable By
      </td>

      <td>
        This *Debug* event is raised when a user becomes reachable by a communication channel, such as SMS, Email, Mobile Push, or when there are changes to the existing communication channel.
      </td>

      <td>
        Tracked for a profile when:

        * Push token is added/changed.
        * Email ID is added/changed
        * Phone number is added/changed.
      </td>
    </tr>
  </tbody>
</Table>

# Custom Events

*Custom Events* are events you define and track with our SDK or API. For more information, refer to the [developer documentation](https://developer.clevertap.com/v1.0/docs/concepts-events).

# Event Metadata Recorded Automatically

For every event that is recorded, CleverTap records the following standard metadata:

* Information about the user who performed the event.
* Date and time when the event was recorded.
* The number of screens viewed by the user before performing the action.
* The referring site and the source of the user visit if it was from an external source.

Additionally, CleverTap keeps the user profiles updated with the latest:

* Geographic information like their city, region, country, and latitude/longitude (if available).
* Browser, device make, or model used to access the website or app.

# System Properties

CleverTap tracks the following system properties automatically from the mobile SDK. All the system properties are prefixed by *CT*, indicating that they are provided by CleverTap. 

The following properties are tracked automatically on all events:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        System Property
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        CT App version
      </td>

      <td>
        This is the current version of your application installed on the user device.
      </td>
    </tr>

    <tr>
      <td>
        CT Latitude
      </td>

      <td>
        The user location identified by the latitude.
      </td>
    </tr>

    <tr>
      <td>
        CT Longitude
      </td>

      <td>
        The user location identified by the longitude.
      </td>
    </tr>

    <tr>
      <td>
        CT Source
      </td>

      <td>
        The source of the event.\
        For example, the event may originate from a Mobile SDK or an API.

        All possible values:

        * Mobile (Mobile SDK)
        * MobileWeb (Web SDK)
        * Web (Web SDK)
        * API
        * segment
        * appsflyer
        * apsalar
        * branch
        * tune
        * System (for events generated by CleverTap)
      </td>
    </tr>
  </tbody>
</Table>

The following properties are available on the *App Launched* event:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        System Property
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        CT App version
      </td>

      <td>
        This is the current version of your application installed on the user device.
      </td>
    </tr>

    <tr>
      <td>
        CT Latitude
      </td>

      <td>
        The user location identified by the latitude.
      </td>
    </tr>

    <tr>
      <td>
        CT Longitude
      </td>

      <td>
        The user location identified by the longitude.
      </td>
    </tr>

    <tr>
      <td>
        CT OS Version
      </td>

      <td>
        The operating system of the device.\
        For example,  1.0.0.
      </td>
    </tr>

    <tr>
      <td>
        CT SDK Version
      </td>

      <td>
        The CleverTap SDK version. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        CT Network Carrier
      </td>

      <td>
        The network carrier of the device.\
        For example, AT\&T, Vodafone.
      </td>
    </tr>

    <tr>
      <td>
        CT Network Type
      </td>

      <td>
        The network type of the device.\
        For example, 4g.
      </td>
    </tr>

    <tr>
      <td>
        CT Connected To WiFi
      </td>

      <td>
        Indicates if the device is connected to the Wi-FI.
      </td>
    </tr>

    <tr>
      <td>
        CT Bluetooth Version
      </td>

      <td>
        The Bluetooth version of the device.
      </td>
    </tr>

    <tr>
      <td>
        CT Bluetooth Enabled
      </td>

      <td>
        Indicates if  Bluetooth is enabled on the device.
      </td>
    </tr>

    <tr>
      <td>
        CT Source
      </td>

      <td>
        The source of the event.\
        For example, the event may originate from a Mobile SDK or an API.

        All possible values:

        * Mobile (Mobile SDK)
        * MobileWeb (Web SDK)
        * Web (Web SDK)
        * API
        * segment
        * appsflyer
        * apsalar
        * branch
        * tune
        * System (for events generated by CleverTap)
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Latitude and Longitude
>
> The system properties *latitude* and *longitude* are captured and sent from the SDK only if the user gives consent on your app.
