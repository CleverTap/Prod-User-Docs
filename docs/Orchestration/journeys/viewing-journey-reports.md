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
## Overview

You can view comprehensive reports for all Journeys. You can export these reports to analyze Journey performance with your metrics, compare performance across Journeys and understand engagement trends.

# Export Journey Reports

You can export a Journey report in a CSV file. When you choose to export a Journey report, it will be emailed to you on your registered email address. 

You can select the time period and the required Journeys from the Journeys list page. The Email report button is available on top right-hand side of the list page. 

> 📘 Note
>
> You can email reports for up to 100 Journeys at a time from the dashboard.

<Image title="Journeys_report_email.png.png" alt={1233} border={true} src="https://files.readme.io/b7bcc28-Journeys_report_email.png.png">
  Email Journey Report
</Image>

## Schedule Journey Exports

You can choose to have reports for all Journeys with the 'running' status emailed to you daily or weekly. You can choose the period and frequency from the reports section in Settings. 

<Image title="Screenshot 2020-06-10 at 1.03.23 AM.png" alt={1436} border={true} src="https://files.readme.io/57526b6-Screenshot_2020-06-10_at_1.03.23_AM.png">
  Schedule Journey Reports
</Image>

# Types of Journey Reports

There are two types of Journey Reports available:

1. Journey Summary report
2. Journey Nodewise report

## Journey Summary report

This is a Journey level report. Each row in the report represents a Journey and contains information for the Journey and all the users in it.  

Journey Summary report column headers: 

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Journey Data
      </th>

      <th>
        User Data
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Journey Start Time
      </td>

      <td>
        Qualified
      </td>
    </tr>

    <tr>
      <td>
        Journey End time
      </td>

      <td>
        Entered
      </td>
    </tr>

    <tr>
      <td>
        Journey Name
      </td>

      <td>
        Goal Met
      </td>
    </tr>

    <tr>
      <td>
        Journey ID
      </td>

      <td>
        Goal 1 Name
      </td>
    </tr>

    <tr>
      <td>
        Journey Entry type
      </td>

      <td>
        Goal 1 Conversions
      </td>
    </tr>

    <tr>
      <td>
        Reentry Allowed
      </td>

      <td>
        Goal 1 Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>
        Journey Status
      </td>

      <td>
        Goal 2 Name
      </td>
    </tr>

    <tr>
      <td>
        Journey Created by
      </td>

      <td>
        Goal 2 Conversions
      </td>
    </tr>

    <tr>
      <td>
        Journey Labels
      </td>

      <td>
        Goal 2 Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>
        Journey Number of nodes
      </td>

      <td>
        Goal 3 Name
      </td>
    </tr>

    <tr>
      <td>
        Journey URL
      </td>

      <td>
        Goal 3 Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Goal 3 Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Journey Timeout
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Force Exits
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Completed
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Control Group (Total)
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        System Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Campaign Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Custom Control Group Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Custom Control Group Name
      </td>
    </tr>
  </tbody>
</Table>

## Journey Nodewise report

This is a node level report. Each row in the report represents a node in a Journey. This report has multiple rows that represent multiple nodes in a Journey. 

> 📘 Note
>
> If a Journey has multiple Campaign OS' and Variants, they will be represented in separate rows.

This data is available for Segment and Engage nodes. The report display Journey Overview data, Node Overview data, Node user data, and campaign data.\
A Journey Node report has the following column headers: 

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Journey Overview data
      </th>

      <th>
        Node Overview data
      </th>

      <th>
        Node User Data
      </th>

      <th>
        Campaign Data
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Journey Start Time
      </td>

      <td>
        Node Type
      </td>

      <td>
        Moved Forward
      </td>

      <td>
        Campaign Type
      </td>
    </tr>

    <tr>
      <td>
        Journey End time
      </td>

      <td>
        Node ID
      </td>

      <td>
        Moved Forward via Yes
      </td>

      <td>
        Campaign Variant
      </td>
    </tr>

    <tr>
      <td>
        Journey Name
      </td>

      <td>
        Previous Node\*\*
      </td>

      <td>
        Moved Forward via No
      </td>

      <td>
        Campaign OS
      </td>
    </tr>

    <tr>
      <td>
        Journey ID
      </td>

      <td>
        Delay before Node\*\*
      </td>

      <td>
        Moved Forward via Node Timeout
      </td>

      <td>
        Global Campaign Limits Applied
      </td>
    </tr>

    <tr>
      <td>
        Journey Entry type
      </td>

      <td>
        Connector from Previous\*\*
      </td>

      <td>
        Journey Timeout
      </td>

      <td>
        Campaign Title
      </td>
    </tr>

    <tr>
      <td>
        Re-entry Allowed
      </td>

      <td>
        Qualifying window
      </td>

      <td>
        Completed
      </td>

      <td>
        Campaign Message
      </td>
    </tr>

    <tr>
      <td>
        Journey Status
      </td>

      <td>
        Campaign Name / Segment Name
      </td>

      <td>
        Goal Met
      </td>

      <td>
        Total Sent
      </td>
    </tr>

    <tr>
      <td>
        Journey Created by
      </td>

      <td>
        Campaign ID / Segment ID\*\*
      </td>

      <td>
        Goal 1 Name
      </td>

      <td>
        Total Viewed
      </td>
    </tr>

    <tr>
      <td>
        Journey Labels \*\*
      </td>

      <td>
        Channel / Segment Type
      </td>

      <td>
        Goal 1 Conversions
      </td>

      <td>
        Total Clicked
      </td>
    </tr>

    <tr>
      <td>
        Journey Number of Nodes
      </td>

      <td>
        Campaign URL
      </td>

      <td>
        Goal 2 Name
      </td>

      <td>
        Errors
      </td>
    </tr>

    <tr>
      <td>
        Journey URL
      </td>

      <td>

      </td>

      <td>
        Goal 2 Conversions
      </td>

      <td>
        Conversion Event
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Goal 3 Name
      </td>

      <td>
        Conversion Time (in minutes)
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>
        Goal 3 Conversions
      </td>

      <td>
        Unique Sent within Conversion Time
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Unique Viewed within Conversion Time
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Unique Clicked within Conversion Time
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Unique Converted within Conversion Time
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Influenced Conversions
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Influenced Revenue
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Amplified By Push
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>

      </td>

      <td>

      </td>

      <td>
        Deep link URL
      </td>
    </tr>
  </tbody>
</Table>

> 📘 \*\*
>
> Column headers with `**` can have multiple values separated by `|`
