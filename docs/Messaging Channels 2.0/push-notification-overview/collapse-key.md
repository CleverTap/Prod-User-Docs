---
title: Collapse Key
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

A collapse notification key or collapse key is used to avoid multiple push notifications which are sent to Android devices. 

> 📘 Android Only
>
> The collapse key feature is only specific to Android devices.

When this feature is set, it replaces the already-rendered notification in the notification drawer with the same key instead of creating a new notification. 

The collapse key that is added in the Android manifest file must be added under the collapse notification field in the *What* section of the campaign creation under the advanced subsection. 

![989](https://files.readme.io/73ae9f0-Collapse_Key.png "Collapse Key.png")

If all campaigns have the same collapse key specified, then the first notification is replaced by the second one which is then replaced by the third one, and so on.

# Use Case

Following is a use case flow:

Push notification 1 (general notification) → Replace notification 1 with a limited validity notification (promo code or coupon) → Replace notification 2 with a longer validity notification. 

Coupon code to avail free snacks with orders above $20 at 5:00 PM → Promotional code valid for one hour can be sent at 7:00 PM → Replace it with a thank you notification for ordering and status tracking notification.
