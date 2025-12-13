---
title: Events
excerpt: ''
deprecated: false
hidden: false
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

There are two categories of events in CleverTap: System Events and Custom Events. 

System Events are events recorded automatically after you integrate our SDK. Custom Events are events you define and track with our SDK or API.

**Event Properties**

Events have details that describe the action taking place called properties. 

For example, while recording the “Product viewed” event, you could also store event properties like product name, category, and price. Recording event properties will help you answer questions like which category of products are more popular, and help you segment users based on which categories or price points they’ve viewed.

# System Events

System Events are events recorded automatically after you integrate our SDK. 

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

        There are three cases when this event will be recorded multiple times for a single user. The first case is when a user installs your app, uninstalls it, and then reinstalls it. The second case is when clear your app's memory. The third case is when a user installs your app on multiple devices.
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
        There are two cases when this event will recorded. The first case is a fresh app launch, which is when an app is launched from a killed state. The second case is when a app is brought to the foreground after 20 minutes of inactivity in the background.
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
        This event is tracked by sending silent push notifications, which are type of notification that is not rendered on a user’s device. We send silent push notifications to your entire install base once every 24 hours to track uninstalls. For more information, please see [App Uninstall](https://clevertap.com/blog/track-app-uninstalls-effectively/).
      </td>
    </tr>

    <tr>
      <td>
        UTM Visited
      </td>

      <td>
        This event is tracked when user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as Branch or Apsalar, sends this information to CleverTap.
      </td>

      <td>
        The UTM Visited event is recorded for your marketing campaigns from external sources, such as Google Adwords or AdRoll.
      </td>
    </tr>

    <tr>
      <td>
        Notification Sent
      </td>

      <td>
        This event is tracked when a campaign message is sent to a user. This event is always recorded, even if the user does not open or click on the message. This event is recorded for email, mobile push, SMS, web push, and Facebook Audience campaigns.
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

        Notification Viewed is available for Email, Web Push, InApp, Web Popup and App Inbox.
      </td>
    </tr>

    <tr>
      <td>
        Notification Clicked
      </td>

      <td>
        This event is tracked only when a user clicks on a campaign sent via CleverTap. You can track or create a Notification Clicked event for every UTM Visited event that is tracked by CleverTap and not any other provider. There is no separate event storage required for the Notification Clicked event because it is derived from the UTM Visited event.
      </td>

      <td>
        Recorded when a user clicks on a mobile push, in-app, email, web-popup or web push message sent via the CleverTap dashboard, or through the campaign API. 

        The Android Push notifications containing deep links to third-party apps are not tracked.
      </td>
    </tr>

    <tr>
      <td>
        Identity Set
      </td>

      <td>
        This DEBUG event is raised when a new user is identified on a customer’s app or an identified user pushes another identity.
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
        This DEBUG event is raised when a profile is de-merged (after de-merge a new profile for every device is created and identities are dropped) either from dashboard (“reset identities” click on profile page) or through the Demerge Profile API.
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
        This DEBUG event is raised when an existing identity is associated incorrectly with another identity. The former identity is now declared as invalid for the latter's profile.
      </td>

      <td>
        This event is for monitoring and debugging only.
      </td>
    </tr>
  </tbody>
</Table>

# Custom Events

Custom Events are events you define and track with our SDK or API. For more information, please visit our [developer documentation](https://developer.clevertap.com/v1.0/docs/concepts-events).

# Event Metadata Recorded Automatically

For every event that’s recorded, CleverTap records the following standard metadata:

* Information about the user who performed the event.
* Date and time when the event was recorded.
* The number of screens viewed by the user before performing the action.
* The referring site and the source of the user visit if it was from an external source.

Additionally, CleverTap keeps the user profiles updated with the latest:

* Geographic information like their city, region, country, and latitude/longitude (if available).
* Browser or device make, model, etc. used to access the website or app.

# System Properties

CleverTap tracks the following system properties automatically from the mobile SDK. All the system properties are prefixed by ‘CT’, indicating that they are provided by CleverTap. 

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
        * System (For events generated by CleverTap)
      </td>
    </tr>
  </tbody>
</Table>

The following properties are available on the App Launched event:

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
        The Operating system of the device.\
        For example,  1.0.0
      </td>
    </tr>

    <tr>
      <td>
        CT SDK Version
      </td>

      <td>
        The CleverTap SDK version. For example, 30501
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
        The network type of the device\
        For example, 4g
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
        The Bluetooth version of the device
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
        * System (For events generated by CleverTap)
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Latitude and Longitude
>
> The system properties 'latitude' and 'longitude' are captured and sent from the SDK only if the user gives consent on your app.
