---
title: Viewing Journey Reports
excerpt: >-
  Learn how to export CleverTap journey performance data as CSV reports,
  delivered by email or to Amazon S3, Google Cloud Platform, or Azure Blob
  Storage on a one-time or recurring schedule.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Journey reports provide detailed insights into how your users move through journeys. You can analyze metrics such as entries, exits, goal conversions, and engagement trends to understand the effectiveness of your journeys over time.

For multiple journey versions, it also provides performance insights for each version. Whether you are analyzing a live journey or reviewing how an older version performed, the reports help you make data-driven decisions and track engagement trends over time. You can do the following:

- Track metrics for the current published version in real time.
- Access historical data for previously published versions.
- Compare engagement, conversions, and goal completions across versions.&#x20;

# Export Journey Reports

You can export performance data for one or more journeys as a CSV file, directly from the Journeys list. Reports can be delivered to one or more email addresses or to a pre-configured cloud storage bucket (Amazon S3, Google Cloud Platform, or Azure Blob Storage). You can generate a one-time export or set up a recurring subscription.

## Before You Begin

- You can select up to 20 journeys in a single report for both email and Partner Export delivery.
- To deliver reports to a cloud storage bucket, configure your cloud storage credentials in **Settings** > **Partner Export** before setting up the report.

## Set Up Journey Report

To set up a journey report, complete the following nine steps:

1. Go to _Journeys_ from the left navigation.

2. Select the journeys you want to include in the report.&#x20;

3. Click the <img src="https://files.readme.io/6ebe7ff9d9fd0298735dcf535f24dda429e4460884bfd033578853cee22270db-Email_Report_icon.png" valign="middle" height=“30”> icon. The _Journey Reports_ panel opens.

<Image src="https://files.readme.io/4cfcd6f8a3dd1a708e6a51c3609acb1af6d22076b7c0513b819ba6e0c44084b3-Screenshot_2026-10-28_at_15.34.03.png" alt="The All Journeys page showing all the listed Journeys" align="center" border={true} />

4. In the _Report name_ field, enter a name for the report.
5. Under _Versions_, choose which journey versions to include:
   - **All journey versions**: includes all versions of each selected journey. Use this to:
     - Analyze how the journey evolved over time.
     - Compare performance trends across multiple published versions.
     - Build a comprehensive dataset for audit, reporting, or analytics.
     - Export long-running journeys edited and republished multiple times. Only active versions within the selected date range are included.
   - **Currently selected version**: includes only the currently active version. Use this to:
     - Review performance for the most recent version only.
     - Pull data for a specific published version that was live during a particular campaign or test.
6. Under _Versions_, choose which journey versions to include:

   - **All journey versions**: includes all versions of each selected journey.
   - **Currently selected version**: includes only the currently active version.
7. Under _Report type_, select the level of detail:

   - **Summary**: One row per journey version with aggregate performance stats. For more information, refer to [Journey Summary Report](doc:journey-reports#journey-summary-report).
   - **Node wise**: One row per node with a per-node breakdown across the journey. For more information, refer to the [Journey Nodewise Report](doc:journey-reports#journey-nodewise-report).


   <Image src="https://files.readme.io/0e0fa7c110d77f3e7c3aafd0aef6da63b2cd06e621ee5173f347de9c7409d956-Screenshot_2026-10-28_at_15.04.03.png" alt="Journey Reports section showing the Name, Version and Report Type fields" align="center" caption="Journey Reports Section" border={true} />


7) Under _Report frequency_, choose how often the report runs:
   - **One-Time Report**: Generates the report and sends it to your email.
   - **Recurring Report Subscription**: Runs on a schedule. Select **Daily** or **Weekly**. For Weekly, select the day of the week from the dropdown (default is Monday).
8) Under _Delivery_, select how the report is sent:
   - **Email**: Delivered as a CSV to one or more email addresses. For more information, refer to [Deliver by Email](#deliver-by-email).
   - **Partner Export**: Delivered as a CSV to a cloud storage bucket. For more information, refer to [Deliver to Cloud Storage](#deliver-to-cloud-storage).
9) Click **Create** to generate your request.

<Image src="https://files.readme.io/725dcf9b822bc8638e31bf40531f4bc693612e7f4449602fb4f1081309671bf2-Screenshot_2026-10-30_at_15.41.55.png" alt="The Email Option for Delivery in Journey Report" align="center" caption="Email Option for Journey Report" border={true} />

## Deliver by Email

To deliver the report by email, complete the following five steps:

1. Under _Delivery_, select **Email**.

2. To add more recipients, click **+**. A picker appears showing your team's email addresses.

3. Search or scroll to find an address. To add an address, click **Select** next to it. To add all addresses, click **Select All**. Selected addresses appear in the _Selected Emails_ column on the right.

4. Click **Apply** to confirm your selection.

<Image src="https://files.readme.io/ff77299433a513a9827f813dd65d6668724abead22477599eea1ad0735a0abaf-Email_Selection_Popover.png" alt="The Email Selector Pop-Up for Journey Reports" align="center" caption="Email Selector Pop-Up for Journey Reports" border={true} />

## Deliver to Cloud Storage

<Callout icon="🚧" theme="warn">
  #### Configure Cloud Storage Credentials First

  You must have at least one cloud storage partner configured in **Settings** > **Partner Export** before completing these steps. If no partners are configured, select **Add Credentials** in the panel to open Partner Export settings.
</Callout>

To deliver the report to cloud storage, complete the following four steps:

1. Under _Delivery_, click **Partner Export**.

2. Select your cloud storage provider:
   - [Amazon S3](doc:aws-s3-configuration)
   - [Google Cloud Platform](doc:gcp-configuration)
   - [Azure Blob Storage](doc:microsoft-azure-configuration)

3. Under _Select bucket_, select the destination bucket from the dropdown.
   - Select **Add Credentials** to configure them in Partner Export settings, then return to this panel and refresh.

4. Click **Create**.

<Image src="https://files.readme.io/a7624dbf81dd6911865ffa7d5b47255b7244b8574f16c6144f6d6a055b9517ff-Screenshot_2026-10-28_at_15.19.44.png" align="center" caption="Delivery Type - Partner Export" border={true} />

## View Subscriptions

To view your recurring report subscriptions, open the **Journey Reports** panel and select the _Subscriptions_ tab. The tab lists all recurring subscriptions with the following details:


<Image src="https://files.readme.io/5de0d4de102a686d0ffa3856c2683cf0033bf80fa51856bfc32bfba9bc281680-Screenshot_2026-10-28_at_15.21.23.png" alt="Journey Reports Subscription Tab" align="center" caption="View Subscription" border={true} />

| Column | Description |
|---|---|
| **Report Name** | Name of the report and its unique subscription ID. |
| **Data Type** | Report type: Summary or Node wise. |
| **Created On** | Date and time the subscription was created. |
| **Export Type** | Delivery method: Email or Partner Export. |

Use the *Search by ID/Name* field to find a specific subscription.

<Callout icon="📘" theme="info">
  #### Existing Subscriptions are not affected

  Recurring subscriptions set up from **Settings** > **Setup** > **Reports** continue to work and are not affected by this update.
</Callout>

# Types of Journey Reports

There are two types of Journey Reports available:

- Journey Summary Report
- Journey Nodewise Report

## Journey Summary Report

This report provides a high-level summary of each journey. If a journey has multiple published versions, each version is listed as a separate row in the report.

Each row includes journey metadata, user engagement, goal conversion, and control group statistics. The data included in the report can be broadly categorized as: Journey Data and User Data.

### Journey Data

This section contains journey-level metadata and configuration details. It helps identify the version and setup context for each report row.

| Report Column                      | Description                                                                                             |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Journey Start Time**             | Timestamp when the journey started.                                                                     |
| **Journey End Time**               | Timestamp when the journey ended.                                                                       |
| **Journey Name**                   | Name of the journey.                                                                                    |
| **Journey ID**                     | Unique identifier for the journey.                                                                      |
| **Journey Labels**                 | Tags or labels associated with the journey.                                                             |
| **Version Number**                 | Version number of the journey.                                                                          |
| **Version Name**                   | Display name for the journey version.                                                                   |
| **Version Entry Type**             | Entry criteria type: Live or Past Behavior.                                                             |
| **Re-entry Allowed**               | Indicates whether users can re-enter the journey. Possible values: TRUE or FALSE.                       |
| **Version Status**                 | Status of the version. Possible values: Scheduled, Running, Paused, Stopped, Completed, and Restricted. |
| **Version Created by**             | User who created the journey version.                                                                   |
| **Version Created on**             | Date and time the version was created.                                                                  |
| **Version Published by**           | User who published the version.                                                                         |
| **Version Published on**           | Date and time the version was published.                                                                |
| **Number of Nodes in the version** | Total number of nodes present in this version.                                                          |
| **Journey version URL**            | Link to access the version in the dashboard.                                                            |

### User Data

This section includes user-level metrics such as entries, completions, goal conversions, and control group stats, which reflect how users engaged with a specific journey version.

| Report Column                                 | Description                                   |
| :-------------------------------------------- | :-------------------------------------------- |
| **Qualified**                                 | Total users who qualified for the journey.    |
| **Entered**                                   | Total users who entered the journey.          |
| **Goal Met**                                  | Total users who met any goal.                 |
| **Goal 1 Name**                               | Name of the first goal.                       |
| **Goal 1 Conversions**                        | Users converted for goal 1.                   |
| **Goal 1 Control Group Conversions**          | Control group users who converted for goal 1. |
| **Goal 2 Name**                               | Name of the second goal.                      |
| **Goal 2 Conversions**                        | Users converted for goal 2.                   |
| **Goal 2 Control Group Conversions**          | Control group users who converted for goal 2. |
| **Goal 3 Name**                               | Name of the third goal.                       |
| **Goal 3 Conversions**                        | Users converted for goal 3.                   |
| **Goal 3 Control Group Conversions**          | Control group users who converted for goal 3. |
| **Journey Timeout**                           | Users who timed out of the journey.           |
| **Force Exits**                               | Users exited using the Force Exit node.       |
| **Version Exit**                              | Users who exited the version from this node.  |
| **Completed**                                 | Users who completed the journey.              |
| **Control Group (Total)**                     | Total users in all control groups.            |
| **System Control Group Conversions**          | Conversions in the system control group.      |
| **Journey version Control Group Conversions** | Conversions in journey-level control group.   |
| **Custom Control Group Conversions**          | Conversions in a custom control group.        |
| **Custom Control Group Name**                 | Name of the custom control group.             |

## Journey Nodewise Report

Each row in the report represents a node from a specific journey version, including logic nodes (for example, Segment, Delay) and engagement nodes (for example, Push, Email, WhatsApp).

If a journey includes multiple campaigns, variants, or connector paths, each variation is shown as a separate row in the report.

The data included in the Nodewise Report can be broadly categorized into: Journey Data, Node Data, Node User Data, and Campaign Data.

<Callout icon="📘" theme="info">
  #### Multiple Values for Report Column

  #### The columns may contain multiple values separated by delimiters `|`, depending on the node configuration (for example, multiple variants, paths, or goal definitions). Such columns have been marked with \* in the tables included in the sections to follow.
</Callout>

### Journey Data

This section contains journey-level metadata and configuration details. It helps identify the version and setup context for each report row.

| Report Column                      | Description                                                                                             |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Start Date / Start Time**        | Timestamp when the journey started.                                                                     |
| **End Date / End Time**            | Timestamp when the journey ended.                                                                       |
| **Journey Name**                   | Name of the journey.                                                                                    |
| **Journey ID**                     | Unique identifier for the journey.                                                                      |
| **Journey Labels**                 | Tags associated with the journey.                                                                       |
| **Version Number**                 | Version number of the journey.                                                                          |
| **Version Name**                   | Display name for the journey version.                                                                   |
| **Version Entry Type**             | Entry criteria: Live or Past Behaviour.                                                                 |
| **Re-entry Allowed**               | Indicates whether users can re-enter the journey.                                                       |
| **Version Status**                 | Status of the version. Possible values: Scheduled, Running, Paused, Stopped, Completed, and Restricted. |
| **Version Created by/on**          | Creator and creation timestamp for the version.                                                         |
| **Version Published by/on**        | User who recently published the version and the time.                                                   |
| **Number of Nodes in the version** | Total number of nodes in this version.                                                                  |
| **Journey version URL**            | URL to open the journey version in the dashboard.                                                       |

### Node Data

This section describes the node-specific attributes within a journey version.

| Report Column                            | Description                                                                    |
| ---------------------------------------- | ------------------------------------------------------------------------------ |
| **Node Type**                            | Type of node, for example, Segment, Email, SMS, Push, and so on.               |
| **Node ID**                              | Unique identifier of the node.                                                 |
| **Previous Node\***                      | IDs of preceding nodes connected to this node.                                 |
| **Delay before Node\***                  | Time delay before this node is executed.                                       |
| **Connector from Previous\***            | Connector logic used to enter the node. Possibe values: Yes, No, and  Timeout. |
| **Qualifying Window**                    | Time window to meet entry conditions at the segment node.                      |
| **Campaign / Segment / Controller Name** | Name of the campaign, segment, or controller associated with the node.         |
| **Campaign / Segment / Controller ID**   | Unique ID for the associated campaign or segment.                              |
| **Channel / Segment / Controller Type**  | Type of messaging or segmentation logic, for example, Push, Email, and so on.  |
| **Campaign URL**                         | Link to the campaign in the dashboard.                                         |

### Node User Data

This section includes metrics for user movement through this node and outcomes recorded.

| Column                                          | Description                                                           |
| ----------------------------------------------- | --------------------------------------------------------------------- |
| **Moved Forward**                               | Total users who progressed from this node.                            |
| **Moved Forward via Yes / No / Node Timeout\*** | Users moved along specific connector paths.                           |
| **Journey Timeout**                             | Users who timed out at or before this node.                           |
| **Completed**                                   | Users who completed the journey starting from this node.              |
| **Goal Met**                                    | Total users who achieved any goal.                                    |
| **Goal 1–3 Name\***                             | for up to three defined goals.                                        |
| **Goal 1–3 Conversions\***                      | Number of users who have been converted by achieving respective goals |
| **Version Exit**                                | Users who exited the version from this node.                          |

### Campaign Data

This section is available for engagement nodes and captures delivery and interaction metrics.

| Report Column                                                         | Description                                                                                                                                                                 |
| --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Campaign Type**                                                     | Campaign configuration details.                                                                                                                                             |
| **Campaign Variant\***                                                | Campaign configuration details.<br />If multiple variants are tested (for example, A/B test), multiple variant IDs may be shown, though typically each row reflects one.    |
| **Campaign OS\***                                                     | Campaign configuration details. Lists targeted platforms, often shown as Android \| iOS.                                                                                    |
| **Global Campaign Limits Applied**                                    | Whether global send limits were applied.                                                                                                                                    |
| **Campaign Title / Message**                                          | Campaign title and message content.                                                                                                                                         |
| **Total Sent / Viewed / Clicked**                                     | Message delivery and interaction counts.                                                                                                                                    |
| **Total Delivered / Replied**                                         | Delivery confirmation and replies (where applicable).                                                                                                                       |
| **Total Unsubscribes**                                                | Total users who unsubscribed via this campaign.                                                                                                                             |
| **Conversion Event / Time**                                           | Event considered as conversion and the window duration.                                                                                                                     |
| **Unique Sent / Viewed / Clicked / Converted within Conversion Time** | Unique users counted within the conversion window.                                                                                                                          |
| **Influenced Conversions / Revenue**                                  | Indirect conversions and attributed revenue.                                                                                                                                |
| **Amplified by Push**                                                 | Whether push messaging influenced engagement.                                                                                                                               |
| **RenderMax Enabled**                                                 | Indicates if RenderMax (rich content optimization) was used.                                                                                                                |
| **Template Name / Provider Name**                                     | Template and provider details for Email or SMS.                                                                                                                             |
| **WABA Number**                                                       | WhatsApp Business Account number in the case of the WhatsApp campaign.                                                                                                      |
| **Total HTML/AMP Viewed/Clicked/Unsubscribed\***                      | Email stats segmented by HTML and AMP versions. Values can include HTML and AMP email format subfields, often tracked in separate columns (for example, Total AMP Clicked). |

### Conversion Stats for WhatsApp Nodes

CleverTap BSP enables tracking clicks on WhatsApp messages. The stats for these clicks are available under the Campaigns > Stats page. If Click Tracking is enabled, the Journey Report will display the node stats for the _sent > delivered > viewed > clicked > converted_ funnel. However, if Click Tracking is not enabled, only the viewed data is reported for your campaign. Therefore, the funnel in this case is, _sent> delivered > viewed > converted_ .


<Image src="https://files.readme.io/b139aea-sent_delivered_funnel.jpg" alt="Click Tracking Funnel" align="center" border={true} />


| Campaign/Journey Data                   | Click Tracking Enabled                          | Click Tracking Disabled               |
| :-------------------------------------- | :---------------------------------------------- | :------------------------------------ |
| Unique Sent within Conversion Time      | sent > delivered > viewed > clicked > converted | sent > delivered > viewed >converted  |
| Unique Viewed within Conversion Time    | sent > delivered > viewed > clicked > converted | sent > delivered > viewed > converted |
| Unique Clicked within Conversion Time   | sent > delivered > viewed >clicked > converted  | sent > delivered > viewed > converted |
| Unique Converted within Conversion Time | sent > delivered > viewed >clicked > converted  | 0.                                    |

<br />

<br />