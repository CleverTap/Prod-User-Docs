---
title: Attribution Partners
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
CleverTap can track app installations, measure attribution with third-party sources, and view reports in the CleverTap Dashboard.

CleverTap supports integrations with the following third-party attribution providers:
  * [Adjust](doc:adjust)
  * [AppsFlyer](doc:appsflyer) 
  * [Branch](doc:branch)

# Types of Data

CleverTap receives event data from the specified attribution partner and then processes and saves it. The following three types of event data are received from our attribution partners:

  * **Inorganic Install Events** - These install events are attributed to some media source, for example, paid advertisements running on some third-party applications. It implies that the application is installed as a result of engaging with any advertisement.
  * **Organic Install Events** - These install events are attributed to the website or app store or referrals. It implies that the application is installed either from the website, app store, or via referrals and not by engaging with any kind of advertisements.
  * **Custom Events** - These events can be any events (other than install events) that are provided by the attribution partner and tracked in the app. 

The following table lists the default toggle state for each event:
[block:parameters]
{
  "data": {
    "h-0": "Attribution Partner",
    "h-1": "Inorganic Intall Events",
    "h-2": "Organic Install Events",
    "h-3": "Custom Events",
    "0-0": "CleverTap",
    "1-0": "Adjust",
    "2-0": "AppsFlyer",
    "3-0": "Branch",
    "0-2": "ON",
    "0-1": "NA",
    "0-3": "NA",
    "1-1": "Always On",
    "3-1": "Always On",
    "3-2": "NA",
    "3-3": "OFF",
    "2-1": "Always On",
    "2-2": "OFF",
    "2-3": "OFF",
    "1-2": "OFF",
    "1-3": "OFF"
  },
  "cols": 4,
  "rows": 4
}
[/block]
# Enabling Attribution Data

You can enable or disable the tracking of event data from the Attribution Partners page of the CleverTap dashboard. 
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "To update the settings of this page, the user must have admin access or the required access rights."
}
[/block]
To enable event data:
1. Go to *Settings > Partners > Attribution Partners*.
2. Click the **Edit** icon to view the toggle options.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2434871-Attribution_Partners_1.png",
        "Attribution Partners_1.png",
        1946,
        484,
        "#f6f7f9"
      ],
      "border": true,
      "caption": "Clicking Edit icon"
    }
  ]
}
[/block]
The status for events can be as follows:
[block:parameters]
{
  "data": {
    "h-0": "Status",
    "h-1": "Definition",
    "0-0": "On",
    "0-1": "Accept event data when shared by the partner.",
    "1-0": "Off",
    "1-1": "Decline event data shared by the partner.",
    "2-0": "NA",
    "2-1": "Event data not shared by the partner.",
    "3-1": "Always accept event data shared by the partner.",
    "3-0": "Always On"
  },
  "cols": 2,
  "rows": 4
}
[/block]
3. Turn on the toggle to track event data for the required partner. You are prompted to save the changes.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/148c653-Click_Save.png",
        "Click Save.png",
        490,
        208,
        "#eef0f7"
      ],
      "sizing": "80",
      "border": true,
      "caption": "Saving Changes"
    }
  ]
}
[/block]
4. Click **Save**. On clicking, the respective attribution partner information is updated.
[block:callout]
{
  "type": "warning",
  "title": "Warning",
  "body": "If you enable more than one organic attribution partner, a warning for duplication of events is displayed at the top of the page as shown in the figure below. It is recommended to track the organic install event from only one attribution partner."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ad3d3e-Duplication_of_events.png",
        "Duplication of events.png",
        1976,
        644,
        "#f4f4f8"
      ],
      "caption": "Warning for duplication of events",
      "border": true
    }
  ]
}
[/block]