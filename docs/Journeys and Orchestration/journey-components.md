---
title: Journey components
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
# Journey Components

A Journey is a combination of *Segment* nodes and *Engagement* nodes. You can connect *Segment* nodes and *Engagement* nodes to each other to create powerful automation.

## Types of Segment nodes <<@vishal, DK, please provide input for blank tabes>>
[block:parameters]
{
  "data": {
    "h-0": "Segment Node",
    "h-1": "What it does",
    "h-2": "Description",
    "0-0": "Action",
    "0-1": "As soon as the user performs an action, the user enters this node.",
    "0-2": "Qualification to this node occurs as soon as the user performs the said event.",
    "1-0": "Inaction",
    "2-0": "Past Behavior",
    "3-0": "Date Time",
    "4-0": "Journey Trigger",
    "4-1": "You can use this node in the entry criteria only.\nA user is qualified on this node when the same user is qualified for the corresponding node in another Journey, from where the current Journey is triggered.",
    "4-2": "For example, Journey 1 has a push message node. You want to move all users who were sent the push into another Journey. Journey trigger allows you to do this.",
    "5-0": "Page Visit",
    "6-0": "Referrer Entry",
    "7-0": "Page Count",
    "1-1": "Segment users who did the 1st event, but did not do the second event within a specified time interval.",
    "1-2": "For example, Qualify users who added to cart, but did not purchase within five mins.",
    "2-1": "Segment users who performed and did not perform a set of events in the past *n* days.",
    "2-2": "For example,Users who did Video Watched AND did not do Subscription Paid in the Last 30 days.",
    "3-1": "Segment users based on a date time property value like flight time, etc.",
    "3-2": "For example, users who have their flight after 2 hours.",
    "5-1": "Segment users as soon as they visit a specific page.",
    "6-1": "Segment users based on a referring website or campaign.",
    "7-1": "Segment users based on the number of pages visited by them.",
    "5-2": "Web based segment.",
    "6-2": "Web based segment.",
    "7-2": "Web based segment.",
    "8-0": "Custom list",
    "8-2": "Custom segment. For example, users from your Retail Point of Sale (POS).",
    "8-1": "You can use this node in the entry criteria only.  You can upload custom lists of users for engage in the Journey."
  },
  "cols": 3,
  "rows": 9
}
[/block]
## Types of Engagement nodes

[block:parameters]
{
  "data": {
    "h-0": "Engagement Node",
    "h-1": "What it does",
    "h-2": "Description",
    "0-0": "Push",
    "1-0": "SMS",
    "2-0": "Email",
    "3-0": "Webhook",
    "4-0": "Web Push",
    "5-0": "Web Pop-up",
    "6-0": "Exit Intent",
    "7-0": "In-app",
    "8-0": "Inbox",
    "9-0": "Facebook",
    "10-0": "Google",
    "11-0": "Amazon event bridge",
    "12-0": "Segment",
    "13-0": "mParticle"
  },
  "cols": 3,
  "rows": 14
}
[/block]
# Controllers

[block:parameters]
{
  "data": {
    "h-0": "Controller Node",
    "h-1": "What it does",
    "h-2": "Description",
    "0-0": "Force exit",
    "1-0": "User profile update"
  },
  "cols": 3,
  "rows": 2
}
[/block]