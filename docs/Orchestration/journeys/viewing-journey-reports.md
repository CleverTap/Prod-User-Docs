---
title: Viewing Journey Reports
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
You can view comprehensive reports for all Journeys. You can export these reports to analyze Journey performance with your metrics, compare performance across Journeys and understand engagement trends.

#Export Journey Reports
You can export a Journey report in a CSV file. When you choose to export a Journey report, it will be emailed to you on your registered email address. 

You can select the time period and the required Journeys from the Journeys list page. The Email report button is available on top right-hand side of the list page. 
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "You can email reports for up to 100 Journeys at a time from the dashboard."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b7bcc28-Journeys_report_email.png.png",
        "Journeys_report_email.png.png",
        1233,
        545,
        "#e8e9eb"
      ],
      "border": true,
      "caption": "Email Journey Report"
    }
  ]
}
[/block]
## Schedule Journey Exports
You can choose to have reports for all Journeys with the 'running' status emailed to you daily or weekly. You can choose the period and frequency from the reports section in Settings. 





[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/57526b6-Screenshot_2020-06-10_at_1.03.23_AM.png",
        "Screenshot 2020-06-10 at 1.03.23 AM.png",
        1436,
        687,
        "#f3f4f7"
      ],
      "border": true,
      "caption": "Schedule Journey Reports"
    }
  ]
}
[/block]
#Types of Journey Reports
There are two types of Journey Reports available:

1. Journey Summary report
2. Journey Nodewise report


##Journey Summary report

This is a Journey level report. Each row in the report represents a Journey and contains information for the Journey and all the users in it.  

Journey Summary report column headers: 
[block:parameters]
{
  "data": {
    "0-0": "Journey Start Time",
    "1-0": "Journey End time",
    "2-0": "Journey Name",
    "3-0": "Journey ID",
    "4-0": "Journey Entry type",
    "5-0": "Reentry Allowed",
    "6-0": "Journey Status",
    "7-0": "Journey Created by",
    "8-0": "Journey Labels",
    "9-0": "Journey Number of nodes",
    "10-0": "Journey URL",
    "0-1": "Qualified",
    "1-1": "Entered",
    "2-1": "Goal Met",
    "3-1": "Goal 1 Name",
    "4-1": "Goal 1 Conversions",
    "5-1": "Goal 1 Control Group Conversions",
    "6-1": "Goal 2 Name",
    "7-1": "Goal 2 Conversions",
    "8-1": "Goal 2 Control Group Conversions",
    "9-1": "Goal 3 Name",
    "10-1": "Goal 3 Conversions",
    "11-1": "Goal 3 Control Group Conversions",
    "12-1": "Journey Timeout",
    "13-1": "Force Exits",
    "14-1": "Completed",
    "15-1": "Control Group (Total)",
    "16-1": "System Control Group Conversions",
    "17-1": "Campaign Control Group Conversions",
    "18-1": "Custom Control Group Conversions",
    "19-1": "Custom Control Group Name",
    "h-0": "Journey Data",
    "h-1": "User Data"
  },
  "cols": 2,
  "rows": 20
}
[/block]
##Journey Nodewise report

This is a node level report. Each row in the report represents a node in a Journey. This report has multiple rows that represent multiple nodes in a Journey. 


[block:callout]
{
  "type": "info",
  "body": "If a Journey has multiple Campaign OS' and Variants, they will be represented in separate rows.",
  "title": "Note"
}
[/block]
This data is available for Segment and Engage nodes. The report display Journey Overview data, Node Overview data, Node user data, and campaign data.  
A Journey Node report has the following column headers: 

[block:parameters]
{
  "data": {
    "h-0": "Journey Overview data",
    "h-1": "Node Overview data",
    "h-2": "Node User Data",
    "h-3": "Campaign Data",
    "0-0": "Journey Start Time",
    "1-0": "Journey End time",
    "2-0": "Journey Name",
    "3-0": "Journey ID",
    "4-0": "Journey Entry type",
    "5-0": "Re-entry Allowed",
    "6-0": "Journey Status",
    "7-0": "Journey Created by",
    "8-0": "Journey Labels **",
    "9-0": "Journey Number of Nodes",
    "10-0": "Journey URL",
    "0-1": "Node Type",
    "1-1": "Node ID",
    "2-1": "Previous Node**",
    "3-1": "Delay before Node**",
    "4-1": "Connector from Previous**",
    "5-1": "Qualifying window",
    "6-1": "Campaign Name / Segment Name",
    "7-1": "Campaign ID / Segment ID**",
    "8-1": "Channel / Segment Type",
    "9-1": "Campaign URL",
    "0-2": "Moved Forward",
    "1-2": "Moved Forward via Yes",
    "2-2": "Moved Forward via No",
    "3-2": "Moved Forward via Node Timeout",
    "4-2": "Journey Timeout",
    "5-2": "Completed",
    "6-2": "Goal Met",
    "7-2": "Goal 1 Name",
    "8-2": "Goal 1 Conversions",
    "9-2": "Goal 2 Name",
    "10-2": "Goal 2 Conversions",
    "11-2": "Goal 3 Name",
    "12-2": "Goal 3 Conversions",
    "13-2": "",
    "0-3": "Campaign Type",
    "1-3": "Campaign Variant",
    "2-3": "Campaign OS",
    "3-3": "Global Campaign Limits Applied",
    "4-3": "Campaign Title",
    "5-3": "Campaign Message",
    "6-3": "Total Sent",
    "7-3": "Total Viewed",
    "8-3": "Total Clicked",
    "9-3": "Errors",
    "10-3": "Conversion Event",
    "11-3": "Conversion Time (in minutes)",
    "12-3": "Unique Sent within Conversion Time",
    "13-3": "Unique Viewed within Conversion Time",
    "14-3": "Unique Clicked within Conversion Time",
    "15-3": "Unique Converted within Conversion Time",
    "16-3": "Influenced Conversions",
    "17-3": "Influenced Revenue",
    "18-3": "Amplified By Push",
    "19-3": "Deep link URL"
  },
  "cols": 4,
  "rows": 20
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "**",
  "body": "Column headers with `**` can have multiple values separated by `|`"
}
[/block]