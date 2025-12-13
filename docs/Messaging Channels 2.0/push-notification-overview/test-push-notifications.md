---
title: Test Push Notifications
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
## Overview

This section covers how to send test notifications in operations in two ways as well as test push notifications with multiple logins.

# Send Test Notifications in Operations

In the first approach, if the requirement is to send the push notification to a user for a specific campaign content, the push notification can be sent during the campaign creation. 

Under the *What* section of the campaign creation flow, you have the option to send a test push notification to any CleverTap user profile you have marked as a test profile.

![454](https://files.readme.io/6c24488-1.png "1.png")

In the second approach, on a specific user profile page, you can initiate *Send Push* for the required device to send test push notifications to the user. 

![1999](https://files.readme.io/4bd5d33-2.png "2.png")

# Send Test Notifications with Multiple Logins

When there are multiple logins during a test push notification, the token moves to the latest profile. 

If a user has multiple devices associated with a profile, then the push notification from the campaign that the user has qualified into will be received by the latest device. The event is being captured in real-time as the campaign sends notifications to the latest active device. 

If a user does multiple logins after clearing the cache every time, then a new firebase token is created for the device.
