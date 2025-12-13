---
title: Webhooks
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

CleverTap webhooks enable developers to monitor specific user events and receive push notifications to their server when those events happen. CleverTap webhooks are often used to trigger business workflows. For example, if you want to get notified every time a user looks up an international flight in business class but then doesn’t book the flight within 30 minutes. You can set up a webhook in CleverTap to monitor for this specific event, get notified when it happens, and then trigger a process in your call center to contact the user to complete the booking.

Another popular use case for CleverTap webhooks is with e-commerce companies and cart abandonment. For example, if a user abandons their cart during a high-value transaction. You can set up a webhook in CleverTap to monitor for this specific event, get notified when it happens, and then trigger a call center workflow to contact the user to solve any issues and complete the purchase. 

There are six categories of webhooks that you can create to monitor user events. The table below describes each of those categories.
[block:parameters]
{
  "data": {
    "h-0": "Type",
    "h-1": "Description",
    "h-2": "Example",
    "0-0": "Single action",
    "1-0": "Actions",
    "2-0": "Inaction within time",
    "3-0": "Inaction",
    "4-0": "Date time property",
    "5-0": "Actions with user properties",
    "5-1": "Performed an action or not, filtered by their demographic properties.",
    "4-1": "Period of time after a date time property on a user event.",
    "3-1": "Users performed an action, but did not perform another action.",
    "2-1": "User performed an action, but does not perform another action within a certain time.",
    "1-1": "User performed multiple actions.",
    "0-1": "User performed an action.",
    "0-2": "User launched the app.",
    "1-2": "User launched the app and viewed a notification.",
    "2-2": "User has not launched the app in three days.",
    "3-2": "User launched the app, but did not view a notification.",
    "4-2": "User purchased an item and three days have passed.",
    "5-2": "User purchased an item and lives in Canada."
  },
  "cols": 3,
  "rows": 6
}
[/block]
Webhooks are created in the CleverTap dashboard by defining a user segment and a callback URL on your server. CleverTap sends a webhook as an HTTP POST with information about the event when it occurs. You can customize the webhooks to use basic authentication and include any custom properties if needed.