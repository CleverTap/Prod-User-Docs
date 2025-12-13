---
title: Data Retention Policy_Deprecated_Do_Not_Share_needs_update
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
#Overview
This page describes CleverTap's data retention policy (DRP) for user profiles and events. 

User profile data includes [identifiers, system properties, and custom properties](https://docs.clevertap.com/docs/user-profiles). The data retention policy for user profiles is store a current snapshot of a user profile forever. 

Event data includes [system events and custom events](https://docs.clevertap.com/docs/events). The data retention policy for events depends on both your plan type and settings you define in the CleverTap dashboard.

# Data Retention Policy by Plan Type
[block:parameters]
{
  "data": {
    "h-0": "Plan Type",
    "0-0": "**Business Plan** ",
    "1-0": "**Enterprise Plan** ",
    "h-1": "User Profile DRP",
    "h-2": "Event DRP",
    "0-2": "Automatically set to the maximum DRP of 10 years for all events. \n\nWhen an event surpasses the DRP, the oldest event will be deleted first.",
    "h-3": "Can Modify Event DRP",
    "0-3": "Yes. Able to update the DRP for each event type. The minimum DRP that can be set is 3 months.",
    "0-1": "Current snapshot stored forever.",
    "1-1": "Current snapshot stored forever.",
    "1-3": "Yes. Able to update the DRP for each event type. The minimum DRP that can be set is 3 months.",
    "1-2": "Automatically set to the maximum DRP of 10 years for all events.\n\nWhen an event surpasses the DRP, the oldest event will be deleted first."
  },
  "cols": 4,
  "rows": 2
}
[/block]