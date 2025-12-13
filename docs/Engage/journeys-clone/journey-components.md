---
title: Journey Components
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
A Journey is a combination of Segment nodes, Engagement nodes, and Operator nodes. You can connect segment nodes and engagement nodes to each other to create powerful automation.

#Segment Nodes
[block:parameters]
{
  "data": {
    "h-0": "Segment Node",
    "h-1": "Description",
    "h-2": "Connectors from this node",
    "0-0": "Action",
    "0-1": "A user enters this node immediately after performing an action.",
    "0-2": "1.Yes \n2.Node Timeout",
    "1-0": "Inaction",
    "2-0": "Past Behaviour",
    "3-0": "Date Time",
    "4-0": "Journey Trigger",
    "4-1": "This node can only be used in the entry criteria. \nA Journey is triggered from another Journey. The users enter the triggered Journey from another Journey.  \n\nFor example, Journey 1 has a Push message node. You want to move all users who are sent the push into Journey 2.  You can use the Journey trigger to move these users.",
    "4-2": "Yes",
    "5-0": "Page Visit",
    "6-0": "Referrer Entry",
    "7-0": "Page Count",
    "1-1": "These are segment users who performed the first event, but did not perform  the second event within a specified time interval.\n\nFor example,  users who added to cart, but did not purchase within 5 minutes.",
    "1-2": "1.Yes \n2.No\n3.Node Timeout",
    "2-1": "These are segment users who performed an event but did not  another set of events in the past 'n' number of  days.\n\nFor example, users who watched Video AND did not pay for subscription  in the past 30 days.",
    "2-2": "1.Yes \n2.No\n3.Node Timeout",
    "3-1": "These are segment users based on a date time property value such as flight time.\n\nFor example, users who have their flight scheduled after 2 hours.",
    "3-2": "1.Yes \n2.Node Timeout",
    "5-1": "These are segment users who enter the Journey as soon as they visit a specific page.\n\nThis is a web-based segment",
    "6-1": "These are the segment users who enter the Journey from a referring website or campaign.\n\nThis is a web-based segment.",
    "7-1": "These are the segment users who enter a Journey when they visit a specified number of pages.  \n\nThis is a web-based segment.",
    "5-2": "1.Yes \n2.Node Timeout",
    "6-2": "1.Yes \n2.Node Timeout",
    "7-2": "1.Yes \n2.Node Timeout",
    "h-3": "Exceptions"
  },
  "cols": 4,
  "rows": 8
}
[/block]
#Engagement Nodes
[block:parameters]
{
  "data": {
    "h-0": "Engage Node",
    "h-1": "Description",
    "h-2": "Connectors",
    "h-3": "Exceptions",
    "0-0": "Push",
    "1-0": "SMS",
    "2-0": "Email",
    "3-0": "Web Push",
    "4-0": "Webhook",
    "5-0": "In-app",
    "6-0": "Web Pop-up",
    "7-0": "Inbox",
    "8-0": "Exit Intent",
    "0-2": "1.Sent\n2.Failed\n3.Clicked \n4.Unreachable",
    "1-2": "1.Sent\n2.Failed\n3.Unreachable",
    "2-2": "1.Sent\n2.Failed\n3.Viewed\n4.Clicked \n5.Unreachable",
    "3-2": "1.Sent\n2.Failed\n3.Viewed\n4.Clicked \n5.Unreachable",
    "4-2": "Sent",
    "5-2": "1.Sent\n2.Viewed\n3.Clicked",
    "6-2": "1.Sent\n2.Viewed\n3.Clicked",
    "7-2": "1.Sent\n2.Viewed\n3.Clicked",
    "8-2": "1.Sent\n2.Viewed\n3.Clicked"
  },
  "cols": 5,
  "rows": 9
}
[/block]

#Operator Nodes
[block:parameters]
{
  "data": {
    "h-0": "Operator Node",
    "h-1": "Description",
    "h-2": "Connectors",
    "h-3": "Exceptions",
    "0-0": "Force exit",
    "0-2": "None"
  },
  "cols": 4,
  "rows": 1
}
[/block]
#Segment Timer
TBD

#Flow Timer
TBD

#Connectors
TBD