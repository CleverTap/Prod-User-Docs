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
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/40b874a-events1.png",
        "events1.png",
        898,
        704,
        "#fcfcfc"
      ],
      "border": true
    }
  ]
}
[/block]
**Event Categories**

There are two categories of events in CleverTap: System Events and Custom Events. 

System Events are events recorded automatically after you integrate our SDK. Custom Events are events you define and track with our SDK or API.

**Event Properties**

Events have details that describe the action taking place called properties. 

For example, while recording the “Product viewed” event, you could also store event properties like product name, category, and price. Recording event properties will help you answer questions like which category of products are more popular, and help you segment users based on which categories or price points they’ve viewed.

# System Events 

System Events are events recorded automatically after you integrate our SDK. 
[block:parameters]
{
  "data": {
    "h-0": "Event Type",
    "h-1": "Description",
    "h-2": "How Event is Tracked",
    "0-0": "App Installed",
    "1-0": "App Launched",
    "2-0": "App Uninstalled",
    "4-0": "Notification Sent",
    "5-0": "Notification Viewed",
    "5-1": "This event is tracked when a user views an email, in-app notification, or a web notification sent from CleverTap.",
    "5-2": "The CleverTap SDK recognizes when a notification sent via CleverTap is viewed by a user.\n\nNotification Viewed is available for Email, Web Push, InApp, Web Popup and App Inbox.",
    "4-1": "This event is tracked when a campaign message is sent to a user. This event is always recorded, even if the user does not open or click on the message. This event is recorded for email, mobile push, SMS, web push, and Facebook Audience campaigns. The Notification Sent event is available on the Event dashboard but it is not displayed on the User Profile.",
    "4-2": "The event is tracked when the notification is successfully sent from CleverTap to the communication channel you select for your campaign.",
    "2-1": "This event is recorded when a user uninstalls your application.",
    "2-2": "This event is tracked by sending silent push notifications, which are type of notification that is not rendered on a user’s device. We send silent push notifications to your entire install base once every 24 hours to track uninstalls. For more information, please see [App Uninstall](https://clevertap.com/blog/track-app-uninstalls-effectively/).",
    "1-1": "This event is recorded every time a user launches your application.",
    "1-2": "There are two cases when this event will recorded. The first case is a fresh app launch, which is when an app is launched from a killed state. The second case is when a app is brought to the foreground after 20 minutes of inactivity in the background.",
    "0-1": "This event is recorded when a user installs your application.",
    "0-2": "The event is raised when the user launches the app for the first time. \n\nThere are three cases when this event will be recorded multiple times for a single user. The first case is when a user installs your app, uninstalls it, and then reinstalls it. The second case is when clear your app's memory. The third case is when a user installs your app on multiple devices.",
    "6-0": "Notification Clicked",
    "6-1": "This event is tracked only when a user clicks on a campaign sent via CleverTap. You can track or create a Notification Clicked event for every UTM Visited event that is tracked by CleverTap and not any other provider. There is no separate event storage required for the Notification Clicked event because it is derived from the UTM Visited event.",
    "6-2": "Recorded when a user clicks on a mobile push, in-app, email, web-popup or web push message sent via the CleverTap dashboard, or through the campaign API. \n\nThe Android Push notifications containing deep links to third-party apps are not tracked.",
    "3-0": "UTM Visited",
    "3-1": "This event is tracked when user clicks on a link from a marketing campaign that has a UTM parameter defined on it. This event is also tracked when a CleverTap-integrated attribution platform, such as Branch or Apsalar, sends this information to CleverTap.",
    "3-2": "The UTM Visited event is recorded for your marketing campaigns from external sources, such as Google Adwords or AdRoll.",
    "7-0": "Push Impressions",
    "7-1": "This event is tracked when a Push notification sent from CleverTap is delivered on a user’s device. The funnels on the Push campaign statistics page reflects the count for this event.",
    "7-2": "After the toggle for Push Impressions is turned on/setup from settings, the CleverTap SDK starts recording an event whenever a Push notification sent via CleverTap is delivered to the user’s device.",
    "8-0": "App Version Changed",
    "8-1": "This event is raised when a user’s current app version is different from the user’s previous app version.",
    "8-2": "This event is tracked when the \"CT App version\" system property differs from one \"App Launched\" event to another.",
    "9-0": "Notification Replied",
    "9-1": "This event is recorded when a user replies to a WhatsApp message.",
    "9-2": "This event is raised when the brand receives a reply from the user.",
    "10-0": "Reply Sent",
    "10-1": "This event is recorded when an agent (CleverTap user) replies to a message from the end user.",
    "10-2": "This event is raised against the user profile of the end user."
  },
  "cols": 3,
  "rows": 11
}
[/block]
# Debug Events
Debug Events are events recorded automatically after you integrate our SDK. These events are raised at certain lifecycle stages in your integration and helps you track and manage your integration
These events are available on any profile page and Find People page by adding a parameter to the url '*?showDebugEvents=true*'
[block:parameters]
{
  "data": {
    "0-0": "Identity Set",
    "0-1": "This DEBUG event is raised when a new user is identified on a customer’s app or an identified user pushes another identity.",
    "0-2": "This event monitors the status and data points that are important for the identification and engagement of users. This event is for monitoring and debugging only.",
    "h-0": "Event Name",
    "h-1": "Description",
    "h-2": "When is it raised",
    "1-0": "Identity Reset",
    "1-1": "This DEBUG event is raised when a profile is de-merged (after de-merge a new profile for every device is created and identities are dropped) either from dashboard (“reset identities” click on profile page) or through the Demerge Profile API.",
    "1-2": "It monitors the reset of identities and handles unnecessary merges. This event is used for monitoring and debugging only.",
    "2-0": "Identity Error",
    "2-1": "This DEBUG event is raised when an existing identity is associated incorrectly with another identity. The former identity is now declared as invalid for the latter's profile.",
    "2-2": "This event is for monitoring and debugging when identity merges are invalid",
    "3-0": "Reachable By",
    "3-1": "This DEBUG event is raised when a user becomes reachable by a communication channel, such as SMS, Email, Mobile Push, or there are changes to the existing communication channel.",
    "3-2": "Tracked for a profile when\n- Push token is added/changed.\n- Email ID is added/changed\n- Phone number is added/changed."
  },
  "cols": 3,
  "rows": 4
}
[/block]
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
[block:parameters]
{
  "data": {
    "1-0": "CT Latitude",
    "h-0": "System Property",
    "0-0": "CT App version",
    "h-1": "Description",
    "0-1": "This is the current version of your application installed on the user device.",
    "1-1": "The user location identified by the latitude.",
    "2-0": "CT Longitude",
    "2-1": "The user location identified by the longitude.",
    "3-0": "CT Source",
    "3-1": "The source of the event.\nFor example, the event may originate from a Mobile SDK or an API.\n\nAll possible values:\n  * Mobile (Mobile SDK)\n  * MobileWeb (Web SDK)\n  * Web (Web SDK)\n  * API\n  * segment\n  * appsflyer\n  * apsalar\n  * branch\n  * tune\n  * System (For events generated by CleverTap)"
  },
  "cols": 2,
  "rows": 4
}
[/block]
The following properties are available on the App Launched event:
[block:parameters]
{
  "data": {
    "h-0": "System Property",
    "h-1": "Description",
    "0-0": "CT App version",
    "0-1": "This is the current version of your application installed on the user device.",
    "1-0": "CT Latitude",
    "1-1": "The user location identified by the latitude.",
    "2-0": "CT Longitude",
    "2-1": "The user location identified by the longitude.",
    "3-0": "CT OS Version",
    "3-1": "The Operating system of the device. \nFor example,  1.0.0",
    "4-0": "CT SDK Version",
    "4-1": "The CleverTap SDK version. For example, 30501",
    "5-0": "CT Network Carrier",
    "5-1": "The network carrier of the device.\nFor example, AT&T, Vodafone.",
    "6-0": "CT Network Type",
    "6-1": "The network type of the device\nFor example, 4g",
    "7-0": "CT Connected To WiFi",
    "7-1": "Indicates if the device is connected to the Wi-FI.",
    "8-0": "CT Bluetooth Version",
    "8-1": "The Bluetooth version of the device",
    "9-0": "CT Bluetooth Enabled",
    "9-1": "Indicates if  Bluetooth is enabled on the device.",
    "10-0": "CT Source",
    "10-1": "The source of the event.\nFor example, the event may originate from a Mobile SDK or an API.\n\nAll possible values:\n  * Mobile (Mobile SDK)\n  * MobileWeb (Web SDK)\n  * Web (Web SDK)\n  * API\n  * segment\n  * appsflyer\n  * apsalar\n  * branch\n  * tune\n  * System (For events generated by CleverTap)"
  },
  "cols": 2,
  "rows": 11
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Latitude and Longitude",
  "body": "The system properties 'latitude' and 'longitude' are captured and sent from the SDK only if the user gives consent on your app."
}
[/block]