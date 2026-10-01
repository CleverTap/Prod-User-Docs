---
title: Optimize your Monthly Active Users
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Monthly Active User (MAU)

An MAU is an end-user who has recorded one or more events in a calendar month. All user-initiated events, server-side events, or CSV uploads contribute to the MAU count. The system events that denote the user action like *App Launched* or *Notification Clicked* also contribute towards MAU. And other system events like *Notification Sent* that do not represent active user activity do not contribute towards the MAU count for that month.

When tracking mobile apps and websites, a user active on both devices with the same identity token counts as one MAU.

For more information about how billing works for Monthly Active Users in CleverTap Essentials, refer to [Billing for Monthly Active Users](https://docs.clevertap.com/docs/billing#billing-for-monthly-active-users).

# Ensure your MAU is Optimized

You can ensure your MAU is optimized in the following ways:

* Ensure that the **identity of a user profile is set correctly** so that a user does not have multiple profiles in case multiple devices/browsers are used.

* Ensure that you are mindful of the **server-side events** sent and CSV uploads events as they contribute to the MAU count.

* If you have a web platform and see anonymous visitors via paid campaigns, it can contribute to your MAU due to the *UTM Visited* event. If you do not want to track these users on CleverTap, you can initialize the CleverTap SDK after the users perform any activity that helps identify them, for example, logging in.
