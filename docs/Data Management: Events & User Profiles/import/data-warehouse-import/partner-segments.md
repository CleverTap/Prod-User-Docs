---
title: Partner Segments
excerpt: >-
  Learn how to import and refresh audience segments from your data warehouse in
  CleverTap.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Partner Segments enable you to import audience segments from your external data warehouse directly into CleverTap. Instead of manually exporting user lists and uploading them as CSV files, you can connect your warehouse, define segments using SQL queries or table selections, and synchronize the resulting audiences into CleverTap on a configurable schedule.

Once imported, these Partner Segments work alongside CleverTap’s native segments. You can use them to target or exclude users in Campaigns and Journeys across all messaging channels, including [Push](doc:push), [Email](doc:email), [SMS](doc:sms), [In-App](doc:in-app), [WhatsApp](doc:whatsapp), and [App Inbox](doc:app-inbox).

The following are some of the key benefits of setting up Partner Segments:

- **Automate data imports**: Connect your warehouse once and schedule automatic refreshes. This removes the need to manually export CSV files or move data between systems.
- **Keep segments up to date**: Choose a refresh frequency from every 15 minutes to weekly to keep your segments continuously updated. CleverTap automatically refreshes the segment before campaign delivery so you always target the latest audience.
- **Use insights from your warehouse**: Activate audiences based on attributes already calculated in your warehouse, such as purchase likelihood, loyalty tiers, or churn risk.
- **Maintain security and compliance**: Your data remains in the warehouse; only the segment results are updated in CleverTap. Credentials are encrypted, and all activities are tracked in audit logs.
- **Use segments across CleverTap**: Partner Segments are available in Campaigns, Journeys, and Analytics, just like any standard [CleverTap segments](doc:segmentation).

<Callout icon="📘" theme="info">
  #### Supported Data Warehouse

  Currently, CleverTap supports [Snowflake,](doc:snowflake) [Google BigQuery,](doc:bigquery) and [Databricks](doc:databricks) as the warehouse connector. Support for Amazon Redshift and Microsoft Fabric will be added in upcoming releases.
</Callout>

# Use Cases

The following examples show how Partner Segments can be used to create audiences from warehouse data and use them in CleverTap campaigns and journeys.

### E-Commerce: Retarget High-Value Cart Abandoners

A retail company computes a propensity-to-purchase score in the warehouse using ML models. They create a segment of "High-value cart abandoners in the last week" using a BigQuery query. The segment is refreshed daily. Marketers use it in CleverTap to run retargeting campaigns with special offers while excluding these users from generic broadcasts.

### FinTech: Nurture New Account Holders

A FinTech company identifies "New account holders who haven’t made their first deposit in 14 days" from their warehouse, combining onboarding data with core banking records. Users flagged by the fraud system are excluded via the SQL query. The imported segment powers a nurturing journey that encourages first-time depositors.

### Food & Delivery: Personalize by Cuisine Preference

A food delivery platform builds segments based on order history, such as "Users who prefer Italian cuisine with average order value above $50." These segments, derived from complex joins across order, restaurant, and user tables, are refreshed weekly and used for personalized partnership promotions.

### Gaming: Re-engage High-Potential Spenders

A gaming company segments players by in-game events and spend, for example, "Players who reached level 10 but haven’t made an in-app purchase". These segments are calculated in the analytics warehouse of the game and synced to CleverTap for targeted in-game promotions via push and in-app messaging.

### Subscriptions: Prevent Churn

A SaaS company scores product usage data in their warehouse to identify churn-risk users (declining login frequency and low feature adoption). The segment is imported into CleverTap and used to enroll users in a re-engagement journey with personalised tips and offers.

# Glossary

The following glossary defines the key terms used in Partner Segments.

<Table>
  <thead>
    <tr>
      <th>
        Term
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Connection**
      </td>

      <td>
        - A saved configuration that connects CleverTap to your data warehouse.
        - Includes the Warehouse Partner, Credentials (for example, a BigQuery service account key), Project and Dataset IDs, and Network Settings.
        - Each connection has an owner and is governed by Role-Based Access Control (RBAC).
      </td>
    </tr>

    <tr>
      <td>
        **Segment Import**
      </td>

      <td>
        - Definition of a segment to be imported from the warehouse.
        - Includes the SQL query or table selection, the Identity column mapping, Import Schedule, a Query Timeout Configuration, and an Import State (_Ready, Scheduled, Running, Paused, or Stopped_).
      </td>
    </tr>

    <tr>
      <td>
        **Refresh Run**
      </td>

      <td>
        - A single execution of the segment import.
        - Each run records a Start Time, an End Time, an Outcome (success or failure), the Total Records Processed, the records Added, Removed, or Dropped, and any Error details.
      </td>
    </tr>

    <tr>
      <td>
        **Partner Sync Event**
      </td>

      <td>
        - An optional event triggered in CleverTap when users are added to or removed from a Partner Segment. This event counts toward your MAU and data points usage.
        - Enabling this event allows you to use Partner Segments as Live Behavior in Campaigns and Journeys.
      </td>
    </tr>

    <tr>
      <td>
        **Identity Mapping**
      </td>

      <td>
        - Maps a column from your warehouse query results to a CleverTap user identifier.
        - You can map it to an Identity (`identity`) field.
      </td>
    </tr>
  </tbody>
</Table>

# Prerequisites for Integration

Before setting up Partner Segments, ensure the following requirements are met:

- **BigQuery/Snowflake/Databricks access**: You must have access to your data warehouse.
- **BigQuery**: You need a Google Cloud project with BigQuery enabled and a [service account created](doc:bigquery#create-service-account) with read access to the datasets and tables you want to query.
- **Snowflake**: Access to a [Snowflake account](doc:snowflake#prerequisites-for-integration) with the _Account Identifier_, _Warehouse_, _Database_, and _Schema_ available, and a user role with permissions to run queries and read/write to the specified database and schema. Authentication can be configured using _Password Authentication_ or _Key Pair Authentication_.
- **Databricks**: Access to a [Databricks workspace](doc:databricks#prerequisites-for-integration) with the _Host_, _HTTP Path_, _Personal Access Token (PAT)_, _Catalog_, and _Schema_ available. The PAT identity (user or service principal) must have _USAGE_ on the selected catalog and schema, and _SELECT_ on the tables you plan to query.
- **User identifier column**: Your SQL query results or selected table must contain a column that maps to a CleverTap Identity field (such as email, phone number, or customer identity).
- **CleverTap dashboard access**: You need appropriate permissions in CleverTap to create connections and segment imports. Contact your CleverTap admin if you do not have the required access.
- **Feature enablement**: Partner Segments must be enabled for your account. Contact your Account Manager to activate this feature.

<Callout icon="🚧" theme="warn">
  #### Important

  Running queries on your data warehouse (for example, BigQuery or Snowflake)  may incur charges according to your warehouse provider pricing. These costs are billed directly by the provider.
</Callout>

# Set Up Partner Segments

Setting up Partner Segments consists of the following five main steps:

1. [Set up a connection](doc:partner-segments#set-up-warehouse-connection) to your data warehouse by providing your BigQuery/Snowflake credentials and configuration details.
2. [Create a segment](doc:partner-segments#create-segment-import) import by writing an SQL query or selecting a table. Map a result column to a CleverTap user identifier.
3. [Map the Identity Column](do:cpartner-segments#map-identity-column).
4. [(Optional) Enable Partner Sync Event](doc:partner-segments#enable-partner-sync-event).
5. [Configure a refresh schedule (recurring or manual)](doc:partner-segments#schedule-segment-refresh) to keep the segment updated automatically.

You can monitor and manage Imports, and also use the segment in your Campaigns, Journeys, and Analytics.

## Set Up Warehouse Connection

A connection stores the credentials and configuration that CleverTap needs to access your data warehouse. You must create at least one connection before you can import segments.

Use the following options to configure and manage your connections:

- [Create Connection](doc:partner-segments#create-connection)
- [Manage Connections](doc:partner-segments#manage-connections)

### Create Connection

Create a connection to allow CleverTap to securely access your data warehouse and run queries for Partner Segments. Once configured, the connection can be used to define and refresh segment imports.

1. Go to _Partners_ > _Select Partner_ (Snowflake or BigQuery) from your CleverTap dashboard
2. Enter the required configuration details based on your warehouse:
   - For **BigQuery**, refer to [BigQuery connection setup](doc:bigquery#use-existing-bigquery-credentials).
   - For **Snowflake**, refer to [Snowflake connection setup](doc:snowflake#set-up-snowflake-for-integration).
3. Click **Test Connection** to verify that CleverTap can reach your warehouse. If the test succeeds, a _Connected_ status is displayed. If it fails, review the error message (for example, _Invalid credentials_ or _Network timeout_) and correct the configuration.
4. Click **Save** to store the connection.

<Callout icon="📘" theme="info">
  #### Note

  Credentials are encrypted and stored securely. Only users with appropriate permissions can view or edit connection details.
</Callout>

### Manage Connections

The Connections tab lists all saved warehouse connections, including _Connection name_, _Warehouse type_, _Creator_, _Last updated time_, and _Connection status_.

From this list, you can **Edit** or **Delete** a connection. If you attempt to delete a connection that is used by active segment imports (in _Ready, Scheduled, Running, or Paused_ state), the system displays those imports and prompts you to stop them before proceeding.

## Create Segment Import

A segment import defines which users to pull from your warehouse and how to map them to CleverTap profiles.

The following steps explain how to create and configure a segment import:

1. [Start Import](doc:partner-segments#start-import)
2. [Define Segment](doc:partner-segments#define-segment)
3. [Preview and Validate](doc:partner-segments#preview-and-validate)
4. [Configure Query Timeout](doc:partner-segments#configure-query-timeout)

### Start Import

Create a segment import to fetch audience data from your connected warehouse and build Partner Segments in CleverTap.

1. Go to the _Segment Imports_ tab and click **Create Import**.
2. Select the _Warehouse connection_ you want to use from the dropdown list.
3. Select **Partner segments**.

The system checks your account’s segment import limits. If you have reached the maximum number of active imports (in _Ready_, _Scheduled_, _Running_, or _Paused_ state), an error message is displayed, and you cannot proceed until you stop or delete an existing import.

<Callout icon="📘" theme="info">
  #### Note

  The default limit is 50 active Partner segments imports. Contact your Account Manager if you require a higher limit.
</Callout>

### Define Segment

You can define your segment in one of two ways:

1. [Write an SQL Query](doc:partner-segments#write-an-sql-query)
2. [Select a Table](doc:partner-segments#select-a-table)

#### Option A: Write an SQL Query

Enter your SQL query in the _Query editor_. The query must return at least one column that contains user identifiers (such as email addresses, phone numbers, or Customer ID). `JOIN`queries and complex subqueries are supported, as long as the final result set includes an identifiable user column. Use the query editor’s formatting tools to improve readability for complex queries.

#### Option B: Select a Table

If your audience is pre-computed and stored in a specific table or view, choose the table selection option. Browse the available tables within your selected database and select the appropriate one.

### Preview and Validate

After entering your query or selecting a table, click **Preview** to see a sample of 15–20 rows from the result set. This lets you verify that the query returns the expected results before saving.

If your SQL query contains syntax errors or lacks permissions, the system displays an error message. Correct the query and preview again.

<Callout icon="🚧" theme="warn">
  #### Important

  You cannot save a segment import until validation is successful.
</Callout>

### Configure Query Timeout

Set the maximum duration CleverTap will wait for your warehouse query to complete. The default timeout is 5 minutes. You can adjust it between 1 and 60 minutes depending on the complexity and size of your query.

## Map Identity Column

After previewing your query results, you must map one column from the result set to a CleverTap user identifier. The system fetches the available columns from your SQL query or selected table and presents them in a dropdown.

Select the identifier column and choose the column name, such as an email address, phone number, or custom ID.

<Callout icon="❗️" theme="error">
  #### Important

  If you attempt to save a segment import without selecting an identity column or with an unsupported format, the system blocks the action and displays a descriptive error.
</Callout>

## Enable Partner Sync Event

You can optionally enable the Partner Sync event. When enabled, CleverTap raises an event each time a user is added to or removed from the segment. This enables you to use Partner Segments as Live Behavior in Campaigns and Journeys.
By default, the Partner Sync event is disabled. Consider the following differences when enabling or disabling the event:

| Event Enabled                                                                 | Event Disabled                                    |
| ----------------------------------------------------------------------------- | ------------------------------------------------- |
| You can use the segment as a Live Behavior in Campaigns and Journeys.         | The segments can only be used as include/exclude. |
| Events count toward your MAU and data points usage, which may affect billing. | No impact on MAU or data points usage.            |

## Schedule Segment Refresh

Configure how often CleverTap should pull updated data from your warehouse. You can choose from the following options:

- [Recurring Schedule](doc:partner-segments#recurring-schedule)
- [Custom Schedule](doc:partner-segments#custom-schedule)
- [Manual Sync](doc:partner-segments#manual-sync)

### Recurring Schedule

Set an automatic refresh frequency. Recurring schedules support the following intervals:

- **Minutes**: Minimum interval of 15 minutes.
- **Hours**: Refresh every N hours.
- **Days**: Refresh every N days.
- **Weeks**: Refresh every N weeks.

### Custom Schedule

For more specific timing, use a custom schedule:

- **Days of the week**: Select one or more days (for example, Monday, Wednesday, Friday) and a time.
- **Days of the month**: Select specific dates (for example, the 1st and 15th) and a time.

### Manual Sync

If you prefer to control when the segment refreshes, set the frequency to manual. You have three sub-options:

- **Run Immediately**: The import runs as soon as it is created. Subsequent runs occur when you manually click the **refresh** button.
- **Run on a Specific Date and Time**: The first run executes at the date and time you specify. Subsequent runs are manual.
- **Run Later**: The segment is created, but no data is fetched until you manually trigger a refresh.

<Callout icon="📘" theme="info">
  #### Note

  If you need a refresh frequency below 15 minutes, contact your Customer Support team to know more about enablement options.
</Callout>

# Manage Imports

After creating a segment import, you can monitor its execution, check its health, and perform operational actions such as refreshing, editing, or stopping the import. The Segment Imports page in the CleverTap dashboard provides visibility into the current status of each import and allows you to manage them as needed.

The following sections explain the lifecycle statuses, health indicators, and management actions available for segment imports:

- [Import Status](doc:partner-segments#import-status)
- [Health Status](doc:partner-segments#health-status)
- [Edit Import](doc:partner-segments#edit-import)
- [Send Alerts](doc:partner-segments#send-alerts)

## Import Status

Each segment import has a lifecycle status visible on the Segment Imports listing page:

| Status    | Description                                                                                           |
| --------- | ----------------------------------------------------------------------------------------------------- |
| Ready     | The import is configured with manual frequency and is waiting for a manual trigger.                   |
| Scheduled | The import is configured with a recurring or custom schedule and will run at the next scheduled time. |
| Running   | The import is currently fetching records from the data warehouse.                                     |
| Paused    | The import has been paused by the user. No refreshes will occur until it is resumed.                  |
| Stopped   | The user has permanently stopped the import.                                                          |

## Health Status

Each import displays a color-coded health indicator based on the most recent refresh run:

| Indicator | Meaning                                                                                    |
| --------- | ------------------------------------------------------------------------------------------ |
| Green     | All records were processed without errors.                                                 |
| Yellow    | The error rate is between 50% and 99.9% of records processed successfully.                 |
| Red       | The error rate exceeds 50%, or a connection error or exception prevented record retrieval. |
| Blank     | No new records were retrieved during the last run.                                         |

<Callout icon="📘" theme="info">
  #### Note

  Records that are added, removed, already present, or dropped (because the identity is not found in CleverTap) are all counted as processed. Only records with null or invalid identity values count toward the error rate.
</Callout>

## Manual Refresh

Partner segments are refreshed according to the configured sync schedule (for example, every 3 days). If the segment is updated at the partner’s end and you want to use the latest data before the next scheduled sync, you can trigger a manual refresh.

To trigger an immediate refresh for any partner segments, click **Run** on the _Import Listing_ page. The import status changes to Running while data is being fetched.

## Edit Import

You can edit a segment import in the Ready or Scheduled state. Editable fields include the segment description, SQL query or table selection, identity mapping, refresh frequency, and timeout configuration.

## Send Alerts

CleverTap sends email and dashboard notifications for the following events:

- Start and completion of an import run (with success or failure summary).
- Errors while fetching records, such as connection errors or exceptions.
- When an import is _Stopped_, _Paused_, or _Resumed_.
- When a manual run is triggered.
- When an import is delayed beyond the expected completion time.

Alerts are sent to the account admin and the import creator. Each alert includes the _Segment name_, _Timestamp_, and an _Error_ or _Success_ summary.

# Use Partner Segments in Campaigns

Once a segment import has completed at least one successful refresh, you can use the resulting Partner Segment in the following campaigns:

- [Past Behavior Campaigns](doc:partner-segments#past-behavior-campaigns)
- [Live Behavior Campaigns](doc:partner-segments#live-trigger-campaigns)

## Past Behavior Campaigns

When creating or editing a campaign, navigate to the target segment selection. Partner Segments are available in two ways:

- **Include/Exclude**: Add a Partner Segment as an inclusion or exclusion filter alongside other segment criteria. For example, include users in a _High-Value Cart Abandoners_ Partner Segment AND exclude users in a _Recent Purchasers_ segment.
- **Standalone**: Use a Partner Segment directly as your Campaign’s target audience by selecting it from the Partner Segment option in the audience picker.

Partner Segments work with all messaging channels: Push, Email, SMS, In-App, WhatsApp, App Inbox, and more.

## Live Behavior Campaigns

If the Partner Sync event is enabled on the segment import, you can create live behavior campaigns using the _Partner Sync_ event. The event includes the following properties:

- **Segment Name**: The name of the Partner Segment.
- **Action**: Whether the user was Added or Removed from the segment.
  This allows you to trigger real-time messaging when users enter or exit a warehouse-defined audience.

If the Partner Sync event is disabled on the segment import, you can create live behavior campaigns using the Include/Exclude segments in _Past behaviour_.

# Use Partner Segments in Journeys

Partner Segments integrate with CleverTap Journeys in the same way as campaigns.

- **Entry Criteria**: Journey entry supports both past behaviour and live trigger options. When a journey is triggered, CleverTap refreshes the Partner Segments linked to the journey, similar to how it handles native segments.
- **Past Behaviour Nodes**: Within a journey, you can use Partner Segments in any past behaviour node to include or exclude users from subsequent steps. The behaviour and targeting capabilities are identical to those available in campaigns.
- **Live Behavior Nodes**: If the Partner Sync event is enabled, you can use the _Partner Sync_ event as a trigger within journey nodes. Event properties (Segment Name and Action) are available for conditional branching.
- **Goals (Exit Criteria)**: You can use Partner Segments under past behaviour or live trigger conditions for journey exit goals.

# Use Partner Segments in Analytics

Partner Segments are available across CleverTap’s analytics modules, including Trends, Cohorts, Flows, Funnels, Pivots, and Boards. You can include or exclude Partner Segments when filtering analytics reports. Additionally, if the Partner Sync event is enabled, it appears as a selectable event in analytics queries.

Use the _Filter by segment_ dropdown in any analytics view to select a Partner Segment and analyze the behavior of warehouse-defined audiences within CleverTap.

# Best Practices

Use summarized tables or materialized views for large datasets. Running complex queries against raw tables with hundreds of millions of rows may cause timeouts. Pre-aggregate your data in the warehouse for better performance.
Preview before saving. Always use the Preview feature to verify that your query returns the expected data and that the identity column maps correctly to CleverTap profiles.

Choose an appropriate refresh frequency. If your segment data only changes daily, there is no need to refresh every 15 minutes. Match the frequency to how often your underlying data changes.

Monitor health indicators. Regularly check the health status of your imports. A yellow or red indicator may suggest identity mapping issues, stale credentials, or query errors that need attention.

Be mindful of Partner Sync event costs. If you enable the Partner Sync event, each user addition or removal counts toward your MAU and data points. For very large or frequently changing segments, this can significantly affect your usage.

Test in a staging environment first. Before running an import against production data, validate your query and identity mapping against a small test dataset to confirm correct behaviour.

# Frequently Asked Questions

Find answers to the following common questions about Partner Segments:

### Can I use complex SQL queries with JOINs or subqueries?

Yes. Any valid BigQuery/Snowflake SQL query is supported, as long as the final result set includes a column that can be mapped to a CleverTap user identifier. Performance depends on your warehouse configuration and query complexity.

### What happens if a refresh run fails?

The system retains the audience from the last successful refresh. Your segment does not become empty or outdated. The dashboard shows the failure status and error details, and you receive an alert notification.

### Who pays for the warehouse query costs?

Query execution costs are incurred on your Google Cloud account. CleverTap does not charge separately for warehouse queries, but your cloud provider’s standard pricing applies.

### Can I use the same connection for multiple segment imports?

Yes. A single warehouse connection can be used across multiple segment imports. Each import can reference different SQL queries or tables within the same connection.

### How do I know if my segment data is fresh?

The segment import listing and the campaign/journey audience picker both show the last refresh timestamp. If the segment is stale (not refreshed recently), a warning icon is displayed. This warning is non-blocking—you can still proceed with the campaign.

### Does enabling the Partner Sync event affect my billing?

Yes. Each Partner Sync event (user added or removed) counts toward your MAU and data points usage. Evaluate the trade-off between live trigger capability and billing impact before enabling this option.

### What happens to a Partner Segment if I delete a user profile from CleverTap?

If a user profile is deleted from CleverTap, their reference is removed from all segments. On the next refresh, if the warehouse query still returns that identifier, it will be treated as a dropped record (since the profile no longer exists in CleverTap).

### Can I use Partner Segments in analytics?

Yes. Partner Segments are available in Trends, Cohorts, Flows, Funnels, Pivots, and Boards. You can use the "Filter by segment" option to analyze behaviour for warehouse-defined audiences.

If you encounter an issue not covered here, contact CleverTap Support with the following details:

- Your account ID
- Import name
- Timestamp of the failed run, and
- Error messages displayed in the dashboard

<br />
