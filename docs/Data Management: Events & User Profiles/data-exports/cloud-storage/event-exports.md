---
title: Event Exports
excerpt: Understand how to export event data from CleverTap to cloud storage.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Event Exports allow you to securely export event data from CleverTap to analytics partners, customer data platforms, external cloud storage, and data warehouses. You can configure exports to centralize behavioral data, integrate with existing analytics workflows, and ensure your destination platform always has the latest event information.

CleverTap supports event exports to the following destinations:

- **Cloud Storage**: Amazon S3, Google Cloud Storage, and Microsoft Azure
- **Analytics**: mParticle, Mixpanel, Amplitude, and Segment
- **Data Warehouses**: Snowflake and BigQuery

<Callout icon="📘" theme="info">
  ### Note

  This document covers event exports to [Amazon S3](doc:data-export-to-aws-s3), [Google Cloud Storage](doc:data-export-to-gcp), and [Microsoft Azure](doc:microsoft-azure) only. For exports to analytics partners or data warehouses, refer to their respective documentation linked above.
</Callout>

With Event Exports, you can:

- **Export to Multiple Cloud Storage Platforms**: Send event data to Amazon S3, Google Cloud Storage, or Microsoft Azure blob storage.
- **Customize Folder and File Structure**: Organize exports using flexible sub-folder patterns and custom file naming conventions.
- **Choose File Format**: Export data as CSV, JSON, XML, or Parquet to match the requirements for your pipeline.
- **Select Which Events to Export**: Export all events, system events, engagement events, or a specific subset from your schema.
- **Configure Identity Output**: Export either a single identifier per event record, using fallback logic, all selected identifiers, or include the CleverTap ID and account-defined identities (Identity, Email, and Phone).
- **Configure Data Fields**: Choose specific event properties, user properties, device attributes, communication preferences, and timestamps to export. Rename and reorder columns to suit your data pipeline.
- **Manage Schema**: Lock the schema or auto-include new properties as your event schema evolves.
- **Schedule Exports**: Run one-time exports for a defined date range, or set up recurring exports at 4, 8, 12, or 24-hour intervals.

# Use Cases

Event Exports support a variety of use cases across analytics, data science, and compliance functions:

- **Behavioral Analytics and Business Intelligence**: Export raw event streams to your cloud storage to power funnel analysis, cohort studies, and attribution modeling. Recurring exports ensure your warehouse always reflects the latest user behavior without reprocessing the full dataset.
- **Product Analytics**: Isolate high-signal events to track feature adoption, measure activation rates, and build usage dashboards. Use event-name-based folder partitioning to simplify ingestion by event type.
- **Custom Identity Reconciliation**: Export all identity fields alongside the CleverTap ID to map CleverTap event records to user profiles in your CRM, data warehouse, or internal systems.
- **Machine Learning & Data Science**: Use exported event data to train recommendation engines, churn prediction models, or propensity models on up-to-date behavioral signals.
- **Privacy & Compliance**: Export only the event properties required for your use case. Exclude Personally Identifiable Information (PII) by deselecting sensitive properties, and lock the schema to prevent new sensitive attributes from being included in future runs.
- **Archival and Regulatory Compliance**: Schedule periodic exports to back up event data for regulatory compliance and long-term archival.

# Quick Start Guide

The following steps provide a high-level flow for setting up an event export from CleverTap to your cloud storage destination. Each step links to detailed documentation.

1. [Configure Storage & File Details](#configure-storage--file-details)
2. [Select User Identifiers](#select-user-identifiers)
3. [Select Data Fields & Event](#select-data-fields--event)
4. [Edit Properties & Order](#edit-properties--order)
5. [Define Schedule](#define-schedule-for-export)

Before creating an event export, ensure your cloud storage environment is ready, and your CleverTap account has the necessary permissions. Depending on the cloud platform you are using:

- [Configure Amazon S3 Integration](doc:data-export-to-aws-s3#create-an-aws-s3-bucket)
- [Configure Google Cloud Storage Integration](doc:data-export-to-gcp#integrate-gcp-with-clevertap)
- [Configure Microsoft Azure Integration](doc:microsoft-azure#setup)

You must have **write** access permissions on the cloud storage platform you use to create and manage exports.

# Create Export

An export in CleverTap is a configured job that sends your data to an external destination on a schedule you define. A destination is a cloud storage platform (such as Amazon S3, Google Cloud Storage, or Microsoft Azure) that CleverTap connects to and delivers files to on your behalf.

To create an export, perform the following steps:

1. Go to _Settings_ > _Partners_ and select _Export center_.
2. Click **Create Export**, select _Events_, and click **Next**.
3. Select the _Partner_ to which you want to send the export and click **Start**. The export setup includes the following five main steps:


   <Image src="https://files.readme.io/20bbd834568b6910208a83bc3999cf8f83958fa77c67e97e428bab06d9d1a524-2026-05-13_14-49-36_1.gif" align="center" caption="Create Export" border={true} />


   1. [Configure Storage & File Details](doc:event-exports#configure-storage--file-details): Configure the destination, folder structure, file format, and naming conventions.
   2. [Select User Identifiers](doc:event-exports#select-user-identifiers): Define which user identifiers to include alongside each event record and their order.
   3. [Select Data Fields & Events](doc:event-exports#select-data-fields--event): Choose the timestamp format, user properties, device attributes, and communication preferences to include alongside each event record.
   4. [Edit Properties & Order](doc:event-exports#edit-properties--order): Select, rename, and reorder event properties for each selected event individually.
   5. [Define Schedule](doc:event-exports#define-schedule-for-export): Set up one-time or recurring export schedules.

<Callout icon="📘" theme="info">
  ### Legacy Exports Migration

  - Legacy exports continue to run without interruption. You can view and edit legacy exports using the **Switch to legacy** option.
  - You cannot migrate legacy exports to the new flow directly. You must do the following:
    1. Stop the legacy export and create a new export using the enhanced flow with the same or improved settings. For more information about what has changed, refer to this [FAQ](doc:event-export#what-has-changed-between-the-legacy-export-and-the-new-export).
    2. Verify the new export runs successfully and produces the expected output.
    3. Update your downstream pipelines to process files from the new export location.
</Callout>

## Configure Storage & File Details

In this section, you will define the destination, folder organization, file format, and file naming for your export. Use the live _Preview_ on the screen to validate paths and filenames as you configure them.

1. **Select Storage Bucket**: Choose the cloud storage bucket or blob container where you want to export event data. The dropdown displays all integrated storage destinations configured in your account.

2. **Set Up Sub-folder Structure**: Choose how CleverTap should organize folders within your bucket or container using the following options. The folder structure preview updates in real-time as you configure each option.

   - **Bucket root**: Files are stored directly in the root of your bucket with no sub-folders. _Preview:_ `/{bucket-name}/file.csv.gz`
   - **Split by data type**: Creates top-level folders such as `events/` and `profile/`. Event exports are stored under `events/`. _Preview:_ `/{bucket-name}/events/file.csv.gz`
   - **Split by export run date**: Partitions files by the export run date so each run's data lands in its own folder. This is ideal for date-based ingestion pipelines. _Preview:_ `/{bucket-name}/2025-10-03/file.csv.gz`
   - **Split by export unique ID**: Creates a sub-folder using the unique export ID assigned to each export configuration. _Preview:_ `/{bucket-name}/1761650178/`
   - **Split by event name**: Creates a sub-folder for each event name, making it easy to isolate and process individual event types in downstream pipelines. _Preview:_ `/{bucket-name}/App-Launched/file.csv.gz`
   - **Custom**: Build your own folder structure using dynamic variables. Click `{{ }}` to insert variables and use `/` to create sub-folders. The following are the supported variables:

     - `{{Account-id}}`: Your unique CleverTap account identifier.
     - `{{Export-id}}`: Unique export ID assigned to each export run.
     - `{{Timestamp}}`: EPOCH timestamp when the export runs.
     - `{{Instance-id}}`: Database identifier for your account (typically 0–23).
     - `{{Date}}`: Export run date in `yyyy-mm-dd`.
     - `{{Event-name}}`: Name of the exported event.

     _Example_: `{{date}}/{{event-name}}/run-{{export-id}}` _Preview_: `/{bucket-name}/2025-10-03/App-Launched/run-1761650178/file.csv.gz`

     <Callout icon="📘" theme="info">
       ### Note

       Use forward slashes (/) to create sub-folders. You can include letters (a-z, A-Z), numbers (0-9), slashes (/), hyphens (-), and underscore(\_).
     </Callout>


     <Image src="https://files.readme.io/394b2e66be4967c9006fc9366df33762d79ba400a38dc4a5c4c3749c8fe6141a-event_export_s3.png" align="center" caption="Set Up Sub-Folder Structure" border={true} />


3. **Select File Format** Select the file format for your exported data. To minimize post-processing, select the format that your downstream platforms can process most efficiently. You can choose from the following formats:

   - **CSV**: Flat tabular file with a header row. All selected fields are exported, even if the values are null.

   - **JSON**: Structured JSON format, ideal for flexible data parsing.

   - **Parquet**: A compressed, column-based format designed for analytics and large-scale data storage.

   - **XML**: A structured format suited for systems that need nested data.

   <Callout icon="📘" theme="info">
     ### Note

     - Parquet files are saved as .parquet by default (without additional compression). If compression is enabled, they are saved as .parquet.gz.
     - CSV, JSON, and XML files are automatically compressed using Gzip and saved as .gz files.
   </Callout>

4. **Define File Name Convention** Define how each file is named inside the innermost folder created by _Sub-folder structure_. If you select _Default_, CleverTap applies a standard naming structure. If you select _Custom_, the input field and dynamic variable picker are enabled. Ensure that required variables are included and correctly separated. The _Preview_ shows the exact filename based on your input.

   - **Default file name**: The default format is `<event-name>-<date>-<account-id>-<export-request-id>-<timestamp>-<database-id>-<file-index>.<format>.gz`. For example, `App-Launched-2026-04-14-1517477760-1776150812-1776150812-0-0.csv.gz`.
   - **Custom**: Create a custom filename using supported dynamic variables. Click `{{ }}` to insert variables and combine them with fixed text. For example, `events-{{date}}-{{export-id}}.csv.gz` resolves to `events-2025-10-03-1761651721.csv.gz`. By default, the timestamp, instance ID and file Index are always appended to the end of the filename to ensure that file content is not overridden. EventName will also be appended in case you have not set EventName under Subfolder.

     The following are the supported variables:

     - `{{Account-id}}`: Your unique CleverTap account identifier.

     - `{{Export-id}}`: Unique export ID assigned to each export run.

     - `{{Timestamp}}`: Epoch timestamp when the export runs.

     - `{{Instance-id}}`: Database identifier for your CleverTap account (typically 0–23).

     - `{{Date}}`: Export run date in `yyyy-mm-dd`.

     - `{{Event-name}}`: Name of the exported event.

   <Callout icon="📘" theme="info">
     ### Note

     Use forward slashes (/) to create sub-folders. You can include letters (a-z, A-Z), numbers (0-9), slashes (/), hyphens (-), and underscores (\_).
   </Callout>


<Image src="https://files.readme.io/574aeb96345953e27aee4ff4e007b9362d967255ef41270d87e97b98a5e36ca5-Define_File_Name_Convention.png" alt="Select File Format and Define File Name" align="center" caption="Select File Format and Define File Name" border={true} />


5. Click **Next** to choose user identifiers.

## Select User Identifiers

Choose which user identifiers to include in each exported event record and how they appear in the output file. These settings enable downstream platforms to accurately link event records back to user profiles across multiple identifiers.

1. **Select Identity & Define Order** Use the dropdown to select which identifiers to export and click **Apply**. You must select at least one identifier. Options include:

   - **Identity**: Your account-defined user identifier.

   - **Email**: The email address stored in the user profile.

   - **Phone**: The phone number stored in the user profile.

   - **Custom**: A business-specific identifier (for example, `crm_id`).


     <Image src="https://files.readme.io/1a28ae6ee64add0430f7cbc2338843b9ff4dd7633e0bf6330e72fc70f9c97f40-Select_Identity.gif" alt="Select Identity" align="center" caption="Select Identity" border={true} />


   <Callout icon="📘" theme="info">
     ### Note

     The order in which you select identifiers sets the initial priority. You can fine-tune priority under _Values to export_ and _Fallback order_. Ensure **Phone** values use E.164 format (for example, `+15551234567`) to avoid downstream validation issues.
   </Callout>

2. **Define Export Preference**: Choose how identifier values are written and define priority, as follows:

   - **Single value with fallback**: Exports a single identifier value per event record, following your priority order. If the first identifier is unavailable, CleverTap uses the next available identifier as per your defined sequence. Use the _Reorder_ option to set priority by dragging rows or entering position numbers. For example, if the priority order is `Identity → Email → Phone → CRM ID [Custom properties]`, CleverTap exports the first available identifier in that order for each event record.


     <Image src="https://files.readme.io/4763bf86ff4c593bf96063be083efa00e9f86b24fd6e5940c7013dddd2a96a29-Choose_Export_Preference.gif" alt="Define Export Preference when Exporting Single Value for Identity" align="center" caption="Define Export Preference when Exporting Single Value for Identity" border={true} />


     - **Export all values**: Exports all selected identifiers in the **identity** column, listed in order of priority. Missing values are omitted. Select this option when reconciliation, deduplication, or identity joins are required downstream.

3. **(Optional) Select Account-Defined User Identity**: Turn ON the toggle to add **all_identities**, which exports all [account-defined identifiers](https://developer.clevertap.com/docs/developer-go-live-checklist) such as **Identity**, **Email**, **Phone**, for each event record. If a user does not have a value for one or more of these identifiers, those values are omitted from the list. _Example:_ If a profile has identities user_123, user_456, and email [user@example.com](mailto:user@example.com), the output will be: `[user_123, user_456, [user@example.com](user@example.com)]`.

4. **Select CleverTap ID**: Select this option to include **clevertapId** in your export. It is a unique, system-generated identifier assigned to each user profile. For more information, refer to [User Profile Data Model](https://docs.clevertap.com/docs/user-profiles#user-profile-data-model).&#x20;

5. **Preview Output**: Review how the selected identifiers will appear in the export. The live preview updates based on your selection and priority order, allowing you to verify the fallback behavior, data structure, and sample output format.


   <Image src="https://files.readme.io/83c21fcb8d5746607ee7dd9e52d1addcdda40efd81a7d8ea0ea4c34be246f089-Output_preview_1.png" alt="Preview Output" align="center" caption="Preview Output" border={true} />


6. Click **Next** to proceed to the _Data Fields & Event_ step.

## Select Data Fields & Event

Configure which data fields and events to include in the export. Use the live _Preview_ to verify selected fields, headers, and column order before proceeding.

1. **Select Timestamp Format** Choose how the event timestamp is represented in the exported file:

   - **EPOCH**: Exports the timestamp as a Unix epoch integer (for example, `1728000000`). Use this when your system accepts timestamps in Unix format, or you want to simplify data processing in your system's timezone.
   - **Formatted Datetime**: Exports the timestamp as a human-readable datetime string with the timezone appended based on your CleverTap account timezone. Use this when the exported file will be reviewed directly or consumed by systems that require formatted dates.

2. **Select User Properties (max. 5)**: Optionally include up to 5 user profile properties alongside each event record. These are profile-level attributes (for example, `Email`, `Phone`, `Name`, `Gender`, `DOB`) that provide user context for each exported event. Use the dropdown to search and select from available user properties, then click **Apply**.

   Once selected, use the **Rename and reorder** panel to customize column headers and reorder the selected user properties using the drag handles or the **Reorder** button.


   <Image src="https://files.readme.io/ae45778d5a6e2bbb05aaf87a881aadade28c62d7d94b2a8cccd78f55eb0994aa-2026-04-20_15-42-26_1.gif" align="center" caption="Select, Rename and Reorder User Properties" border={true} />


   <Callout icon="📘" theme="info">
     ### Note

     User properties exported here reflect the profile state at the time of export, not at the time the event occurred.
   </Callout>

3. **Select Device Attributes** Choose which device-level attributes captured at event time to include.

   1. Click the **Select device information** dropdown and select from these available attributes: `platform`, `token`, `make`, `model`, `appVersion`, `sdkVersion`, `osVersion`, `browser`, `dpi`, `dimensions`, `width`, `height`, and `unit`. `width`, `height`, and `unit` can be selected as standalone columns in addition to, or instead of, the bundled `dimensions` object. Select `dimensions` if you want the three values nested together as a single object in the export; select `width`, `height`, or `unit` individually if you want them as separate top-level columns.
   2. Click **Apply** to confirm your selection.


      <Image src="https://files.readme.io/f7873892572b155ff85de6e555f7767510c68182b5e251256e06ade017342a20-device_info.png" align="center" caption="Include Device Attributes" border={true} />


      <Callout icon="📘" theme="info">
        ### Note

        If a device attribute is unavailable for a given event record, the corresponding column appears blank in the exported file.
      </Callout>

4. **Add Communication Preferences** Include the user's opt-in/opt-out status across messaging channels alongside each event record.

   1. Click the **Select communication preference** dropdown and select one or more options: `subscriptionGroups`, `MSG-webpush`, `MSG-push`, `MSG-email`, `MSG-sms`, and `MSG-whatsapp`.
   2. Click **Apply** to confirm your selection. If a profile has no value for a selected preference, the corresponding column appears blank.


      <Image src="https://files.readme.io/dfc104f4f0466ae4fe0d7c72aad899376fdf9fbf78b1871cf7f3d4974bcd655d-commiunication_pref.png" align="center" caption="Export Communication Preferences" border={true} />


5. **Select Events to Export** Choose which events to include in the export using one of the following tabs:

   - **All events**: Exports data for every event tracked in your CleverTap account. The total count of events to be exported is shown under **Total events**.
   - **System events**: Exports only CleverTap system-generated events. For the full list of system events, refer to [System Events](doc:events#system-events). Any new system events released by CleverTap in the future are automatically included in this export.
   - **Engagement events**: Exports a fixed set of events related to campaign and messaging engagement. Use this for delivery and interaction analysis across your messaging channels. The list of engagement events is fixed and no new events are added automatically. For the full list of engagement events, refer to [Engagement Events](doc:events#engagement-events).
   - **Select events**: Exports only the specific events you choose from your account's event schema. Click the **Select events** dropdown, search for and select the events you want to export, and click **Apply**. The **Total events** counter updates to reflect your selection.

6. The total count of events to be exported is shown under **Total events**.

7. **Rename Events (optional)**: After selecting events, each event in the list displays an editable _Rename_ field on the right. You can enter a custom display name for any event to use in the export output instead of the original event name. For example, rename `Notification Sent` to `Push Notification Sent` or any name that suits your data pipeline conventions.

   <Callout icon="📘" theme="info">
     ### Note

     Renaming Events only affects the event name in the export; it does not change the original property name in CleverTap. Also, the file name will have the original filename instead of the renamed one.
   </Callout>


<Image src="https://files.readme.io/64d66dc74417bd694ea611341d2d03904f217cd391d7f069b7d7b07d5bedbc3c-2026-04-20_16-05-24_1.gif" align="center" caption="Select Events to Export" border={true} />


8. Click **Preview** to validate the configuration or click **Next** to proceed to _Edit Properties & Order_.

## Edit Properties & Order

Configure event properties for each selected event  -  choose which properties to include, rename column headers, set column order, and control schema behavior. This step uses a two-panel layout: the left panel lists all **Selected Events**, and the right panel shows **Properties to export from: \[Event Name]** for the event currently in focus. Click any event in the left panel to configure its properties.

1. **Select Event Properties** For each selected event, use the properties dropdown in the right panel to choose which event properties to include. Click the dropdown, search or browse **Available event properties**, select the properties you want, and click **Apply**. The selected properties appear in the reorder list below.

   For example, for `Notification Sent`, available properties include: `Campaign type`, `Campaign id`, `Campaign name`, `Variant`, `Campaign labels`, `Journey id`, `Journey node ID`, `Journey Version ID`, `Journey name`, and `Control Group Name`.


   <Image src="https://files.readme.io/30b339b5b09895ad9ce14528b57fdefdd8f491efe4a801340f373926c5d85bc3-properties.png" align="center" caption="Select Event Properties for the Selected Event" border={true} />


2. **Rename & Reorder Properties** For each event, use the property list in the right panel to rename or reorder the selected properties. The left column shows the original property name, and the right column shows an editable field for the export column header. Use the drag handles or the **Reorder** button to reorder the columns. Once you rename a property, click the **Copy** icon next to it to apply that rename to the same property across all other selected events in the left panel. For example:

   - To match your data warehouse naming convention, rename `Campaign id` to `campaignId` by editing the field in the right column.

   - To prioritize push notification properties, drag `Campaign type`, `Campaign id`, and `Campaign name` to the top of the list and `Journey id` and `Journey name` to the bottom.

   <Callout icon="📘" theme="info">
     ### Points to Consider

     - Renaming only affects the column header in the export; it does not change the original property name in CleverTap.
     - Use the search bar above the property list to find specific fields.
     - Drag rows to rearrange columns, or use the **Reorder** button to set the export sequence.
     - Use the **Copy** icon to apply a property rename to all other selected events that share the same property name.
     - If a property is missing for a given event record, the column still appears but remains blank. The key is removed from the JSON file.
     - Reordering does not impact data collection or internal storage  -  it only affects the file structure.
     - If two or more properties share the same name, their values are merged in data order, the first non-null value is exported. If all values are null, `null` is exported. If you rename multiple properties to the same name, the duplicate is skipped and the next property in the order is exported in its place.
   </Callout>

3. **Manage Schema Updates** At the bottom of the right panel for each event, choose how new event properties are handled in future export runs:

   - **Add new properties at the end**: Any new event properties added after the export is created are automatically appended as new columns at the end of the file. Existing columns and names remain unchanged, preventing script breaks for scripts that rely on the current column order.

   - **Lock current schema**: The file structure is fixed once the export is created. New event properties are excluded until you manually stop this export and create a new one with the updated schema. For example, if your downstream pipeline breaks when new columns appear unexpectedly, choose this option to keep the schema stable.


     <Image src="https://files.readme.io/303bdc2c551e500dcd4f7050dc9c783e334f777bb9cddde16effabdd201b8759-schema_.png" align="center" caption="Schema Updates" border={true} />


   <Callout icon="📘" theme="info">
     ### Tip

     Choose _Add new properties at the end_ if you want to capture all event data automatically. Choose _Lock current schema_ if your downstream pipelines require a fixed schema structure and cannot tolerate new columns being appended.
   </Callout>

4. Repeat steps 1 through 3 for each event in the **Selected Events** panel. Click **Preview** to review the complete data structure and click **Next** to configure the export schedule.

## Define Schedule for Export

Define how often event data should be exported to your destination.

1. **Choose Schedule Frequency** Select how often the export should run:

   - **One-time**: Runs a single export for a specific date range you define. Use this for ad-hoc analysis, backfills, or initial data migration.
   - **Recurring**: Automatically exports data on a repeating schedule. Use when downstream systems expect a regular file at a fixed cadence.

2. **Configure One-time Export** _(One-time only)_ Select the Dates to export using the date range picker. You can export data for up to the last 365 days. For historical data beyond 365 days, contact your CSM or TAM. Click **Apply** to confirm the date range selection.


   <Image src="https://files.readme.io/7a53752af8e54344663905035147d39bf793067ccce5d01e1507a23b3eaa1b41-scheduke_one_time.png" align="center" caption="One-time export" border={true} />


3. **Configure Recurring Export** _(Recurring only)_

   - **Daily**: Use the **Daily** dropdown to select how often the recurring export runs. The available options are:

     - Every 4 hours
     - Every 8 hours
     - Every 12 hours
     - Every 24 hours

     Regardless of the frequency you choose, all recurring exports are aligned to midnight of the scheduled day, not to the time you created the export. For example, a 4-hour export runs at 00:00, 04:00, 08:00, 12:00, 16:00, and 20:00 each day, not 4 hours after you clicked **Create Export**. Each recurring run works as follows:

     - **First run**: Exports all events from midnight of the scheduled day.
     - **Consecutive runs**: Exports only events that occurred after the previous run's scheduled time through the current run's scheduled time. For example, for a 4-hour export, if the previous run started at 08:00, the next run picks up events from 08:00 through 12:00.
     - **After a failed run**: The failed run is automatically retried every 5 minutes with no retry limit. The next scheduled run only starts after the current run has finished. If the next run was due while the current run was still in progress, it begins as soon as the current run completes.


     <Image src="https://files.readme.io/c0b1542b7b6b6852111e38b0f6872b19e22b37921715f68322ff5d0246650951-schedule_recurring.png" align="center" caption="Recurring Export" border={true} />


   - **Include historical data** _(optional)_: Select this checkbox to trigger a one-time export of historical event data alongside your recurring export. When you click **Create Export**, two exports are created simultaneously:

     - A recurring export that runs on your chosen schedule going forward.
     - A one-time historical export that starts immediately for the date range you select. Both exports write files to the same destination folder using the same configuration, so your storage path receives both historical and ongoing data in a consistent format.

     For example, if you set up a recurring export starting today and select a historical range of the last 90 days, the historical export immediately backfills the last 90 days of event data while the recurring export begins capturing new events going forward. This ensures there are no gaps in your data when you first set up the pipeline.

     <Callout icon="📘" theme="info">
       ### Note

       The historical date range is limited to the last 365 days. For data beyond 365 days, contact your CSM or TAM.
     </Callout>

4. Click **Create Export** to complete the creation of your export.

# File Output Structure

Exported event files follow this consistent column order:

1. **User Identifiers**: Identity, All Identities, CleverTap ID based on the configuration in Step 2.
2. **Event Timestamp**: The timestamp of when the event occurred, in the format selected (EPOCH or Formatted Datetime).
3. **User Properties**: Up to 5 user profile properties in the order you define in Step 3.
4. **Device Attributes**: Device-level attributes captured at event time, in the order you define in Step 3.
5. **Communication Preferences**: `subscriptionGroups`, `MSG-webpush`, `MSG-push`, `MSG-email`, `MSG-sms`, `MSG-whatsapp` (if selected).
6. **Event Properties**: Event properties in the order you define in Step 4.&#x20;

The following sample shows the exported file structure with all fields included:

```json
{
  "eventName": "App Launched",
  "eventTime": "2026-06-14T23:36:08-10:00",
  "identity": {
    "clevertapId": "...",
    "all_identities": [
      "..."
    ],
    "identity": "..."
  },
  "profile": {
    "Email": "...",
    "Gender": "Unknown",
    "Phone": "...",
    "Name": "..."
  },
  "deviceInfo": {
    "appVersion": "...",
    "osVersion": "...",
    "browser": "MobileApp",
    "model": "...",
    "sdkVersion": "...",
    "dpi": "...",
    "make": "...",
    "platform": "Android",
    "token": "",
    "dimensions": {
      "unit": "mm",
      "width": "...",
      "height": "..."
    }
  },
  "commPrefs": {
    "MSG-push": false,
    "MSG-whatsapp": false,
    "MSG-webpush": false,
    "subscriptionGroups": {
      "product updates": "Subscribed",
      "promotional": "Subscribed",
      "transactions comms": "Subscribed"
    },
    "MSG-email": false,
    "MSG-sms": false
  },
  "eventProps": {
    "CT Network Carrier": "...",
    "CT Source": "Mobile",
    "ct_app_version": "",
    "CT Bluetooth Version": "",
    "Keyword": "",
    "CT SDK Version": "...",
    "CT Bluetooth Enabled": "",
    "CT OS Version": "...",
    "CT Network Type": "",
    "Model": "",
    "CT Longitude": "...",
    "CT Latitude": "...",
    "CT Connected To WiFi": "",
    "CT Session Id": "...",
    "CT App Version": "..."
  }
}
```
```json Parquet
[
  {
    "column_name": "eventName",
    "column_type": "VARCHAR",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "eventTime",
    "column_type": "VARCHAR",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "identity",
    "column_type": "MAP(VARCHAR, STRUCT(member0 VARCHAR, member1 STRUCT(member0 VARCHAR, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE)[], member2 INTEGER, member3 BIGINT, member4 FLOAT, member5 DOUBLE))",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "deviceInfo",
    "column_type": "MAP(VARCHAR, STRUCT(member0 BOOLEAN, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE, member5 VARCHAR))",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "commPrefs",
    "column_type": "MAP(VARCHAR, STRUCT(member0 BOOLEAN, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE, member5 VARCHAR, member6 MAP(VARCHAR, STRUCT(member0 BOOLEAN, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE, member5 VARCHAR))))",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "profile",
    "column_type": "MAP(VARCHAR, STRUCT(member0 BOOLEAN, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE, member5 VARCHAR))",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  },
  {
    "column_name": "eventProps",
    "column_type": "MAP(VARCHAR, STRUCT(member0 BOOLEAN, member1 INTEGER, member2 BIGINT, member3 FLOAT, member4 DOUBLE, member5 VARCHAR))",
    "null": "YES",
    "key": null,
    "default": null,
    "extra": null
  }
]
```
```xml
<?xml version='1.0' encoding='UTF-8'?>
<root>
<Event>
    <eventName>Notification Viewed</eventName>
    <eventTime>2026-06-14T23:36:10-10:00</eventTime>
    <identity>
        <entry>
            <key>clevertapId</key>
            <value>...</value>
        </entry>
        <entry>
            <key>all_identities</key>
            <value>[...,...]</value>
        </entry>
        <entry>
            <key>identity</key>
            <value>...</value>
        </entry>
    </identity>
    <profile>
        <entry>
            <key>Email</key>
            <value>...</value>
        </entry>
        <entry>
            <key>Gender</key>
            <value>Unknown</value>
        </entry>
        <entry>
            <key>Phone</key>
            <value>...</value>
        </entry>
        <entry>
            <key>DOB</key>
            <value>...</value>
        </entry>
        <entry>
            <key>Name</key>
            <value>...</value>
        </entry>
    </profile>
    <deviceInfo>
        <entry>
            <key>appVersion</key>
            <value>...</value>
        </entry>
        <entry>
            <key>osVersion</key>
            <value>...</value>
        </entry>
        <entry>
            <key>browser</key>
            <value>MobileApp</value>
        </entry>
        <entry>
            <key>model</key>
            <value>...</value>
        </entry>
        <entry>
            <key>sdkVersion</key>
            <value>...</value>
        </entry>
        <entry>
            <key>dpi</key>
            <value>...</value>
        </entry>
        <entry>
            <key>make</key>
            <value>...</value>
        </entry>
        <entry>
            <key>platform</key>
            <value>Android</value>
        </entry>
        <entry>
            <key>token</key>
            <value></value>
        </entry>
        <entry>
            <key>dimensions</key>
            <value>{...}</value>
        </entry>
    </deviceInfo>
    <commPrefs>
        <entry>
            <key>MSG-push</key>
            <value>false</value>
        </entry>
        <entry>
            <key>MSG-whatsapp</key>
            <value>false</value>
        </entry>
        <entry>
            <key>MSG-webpush</key>
            <value>false</value>
        </entry>
        <entry>
            <key>subscriptionGroups</key>
            <value>{..,..}</value>
        </entry>
        <entry>
            <key>MSG-email</key>
            <value>false</value>
        </entry>
        <entry>
            <key>MSG-sms</key>
            <value>false</value>
        </entry>
    </commPrefs>
    <eventProps>
        <entry>
            <key>wzrk_acts</key>
            <value>...</value>
        </entry>
        <entry>
            <key>CT Source</key>
            <value>Mobile</value>
        </entry>
        <entry>
            <key>wzrk_cts</key>
            <value>...</value>
        </entry>
        <entry>
            <key>Client Name</key>
            <value>...</value>
        </entry>
        <entry>
            <key>Campaign name</key>
            <value>...</value>
        </entry>
        <entry>
            <key>CT Session Id</key>
            <value>...</value>
        </entry>
    </eventProps>
</Event>
</root>
```

The following is a sample of the exported CSV file with all fields included:

| eventName           | eventTime  | identity | all_identities | clevertapId | Email | Phone | Name | Gender  | DOB | platform | token | make | model | appVersion | sdkVersion | osVersion | browser   | dpi | dimensions | subscriptionGroups | MSG-webpush | MSG-push | MSG-email | MSG-sms | MSG-whatsapp | wzrk_id | Campaign type | Campaign id | wzrk_pivot   | User Agent | Client Name | Campaign name | Campaign labels | Journey id | Journey labels | Journey Version ID | Journey name |
| ------------------- | ---------- | -------- | -------------- | ----------- | ----- | ----- | ---- | ------- | --- | -------- | ----- | ---- | ----- | ---------- | ---------- | --------- | --------- | --- | ---------- | ------------------ | ----------- | -------- | --------- | ------- | ------------ | ------- | ------------- | ----------- | ------------ | ---------- | ----------- | ------------- | --------------- | ---------- | -------------- | ------------------ | ------------ |
| Notification Viewed | 1780914785 | \[...]   | \[...]         | ...         | ...   |       | ...  | Unknown |     | Android  | ...   | ...  | ...   | ...        | ...        | ...       | MobileApp | ... | `{...}`    | `{...}`            | false       | true     | true      | false   | false        | ...     | Email         | ...         | wzrk_default | ...        | ...         | ...           | \[...]          |            |                |                    |              |

# Manage Export

This section outlines how to track the status of your data exports and stop them when needed.

### Stop Export

Stop a running export by hovering over the export and clicking **Stop**. The export status on the _Export center_ page is displayed as **Stopped**.

### Export Status

Each export has a status that reflects its current state in the export lifecycle as follows:&#x20;

- **Pending**: Indicates that the export has been created and is awaiting the scheduled run to begin. For recurring exports, after each successful run, the status returns to Pending, indicating that the next scheduled run is waiting to begin. The status changes to **Running** once the next execution starts.
- **Running**: Indicates that the export is in progress, processing, and transferring event data.
- **Stopped**: Indicates that the export was manually stopped and will not run again.
- **Done**: Indicates that the one-time export finished successfully.

# Best Practices

Follow these best practices to ensure your event exports are reliable, organized, and compatible with downstream systems:

- **Use Clear File Naming Conventions**
  Create descriptive file names using dynamic date and event-name variables to help identify and process exports chronologically and by event type.

- **Structure Folders by Event Name and Date**
  Use the _Split by event name_ sub-folder option combined with date-based variables (for example, `{{Event-name}}/{{Date}}`) to partition your data warehouse ingestion by event type and run date.

- **Use Recurring Exports for Large Datasets**
  Set up recurring exports for high-volume event streams to minimize processing time, enhance performance, and reduce storage costs. Choose a higher frequency (every 4 hours) to receive data more frequently throughout the day.

- **Choose the Right Frequency**
  Match your export frequency to your downstream pipeline's ingestion cadence. Use 4-hour exports for dashboards that require frequent data refreshes and 24-hour exports for daily batch processing workflows.

- **Manage Schema Carefully**
  - Lock the schema if downstream systems require a fixed column structure.
  - Use _Add new properties at the end_ to automatically capture newly added event properties without affecting existing columns.

- **Monitor Export Delivery**
  CleverTap sends automatic alerts to help you monitor your exports. There are two types of alerts:

  - **Webhook notifications**: CleverTap sends a webhook notification when an export job starts and when it completes successfully. Webhook notifications are supported for Amazon S3, Google Cloud Storage, and Microsoft Azure destinations only.&#x20;

  - **Email notifications**: CleverTap sends system-generated email alerts for the following export states:
    - **Started**: When the export job begins running.
    - **Completed**: When the export job finishes successfully.
    - **Stopped**: When the export is manually stopped.
    - **Failed**: When the export fails due to invalid or expired storage credentials. CleverTap sends up to 3 email alerts over 3 consecutive days:

      - **Day 1**: Notifies you that your storage credentials are invalid and must be updated to resume the export.
      - **Day 2**: A follow-up reminder if the issue is not resolved.
      - **Day 3**: A final notice that your credentials are still invalid and the export has been automatically stopped.

        The following credential errors trigger email alerts:

        | Error            | Description                                          |
        | ---------------- | ---------------------------------------------------- |
        | Wrong Access Key | The username for storage access is incorrect         |
        | Wrong Secret Key | The password for storage access is incorrect         |
        | Access Disabled  | The storage account has been locked or disabled      |
        | Bucket Not Found | The destination bucket or container no longer exists |

- **Validate Exported Data**
  Run data quality checks to confirm exported files match your expectations before loading them into downstream systems.

- **Monitoring & Error Handling**: If your export fails:
  - Check that your storage credentials (IAM policy, service account key, or SAS token) are valid.
  - Ensure the bucket or container exists and is accessible.
  - For GCP exports, a 403 error often indicates that the service account key is invalid.

# FAQs

### Can I run a one-time Event Export if a recurring Event Export is already active?

Yes. You can create multiple event exports, but they run sequentially. A new export will start only after the currently running export has completed.

### How long are exported event files retained in my cloud storage?

CleverTap does not delete exported files. Your cloud storage bucket lifecycle policies control file retention.

### Can I export events for a specific user segment?

Event Exports export all events (or your selected events) across the entire account. To analyze events for a specific segment, post-process the exported files in your data warehouse, or use the [CleverTap API](https://developer.clevertap.com/docs/)  with segment filters.

### What is the maximum file size for event exports?

CleverTap automatically splits large exports into multiple files when the record count exceeds 10 million for a given database. The file index indicates the file number in the series.

### What recurring frequency options are available?

Recurring Event Exports support four frequency options: every 4 hours, every 8 hours, every 12 hours, and every 24 hours.

### What date ranges can I select for a one-time export?

You can export data for up to the last 365 days using the date range picker. For historical data beyond 365 days, contact your CSM or TAM.

### How does the Include historical data option work on recurring exports?

When enabled, this option triggers a one-time export of historical event data for a selected date range, using the same export configuration. This backfill runs alongside the recurring export, allowing you to populate your data warehouse with historical data before the regular runs resume.

### Can I export events more frequently than every 4 hours?

The minimum frequency for recurring Event Exports is every 4 hours. For more frequent access to event data, consider using the [CleverTap Events API](https://developer.clevertap.com/docs/).

### How do I handle schema changes in my data warehouse?

Use the _Add new properties at the end_ option to append new event property columns automatically. Update your warehouse schema to accommodate new columns, or use the _Lock current schema_ option to prevent unintended changes.

### Can I export events to multiple buckets simultaneously?

You can create multiple recurring event exports pointing to different destination buckets, provided each export uses a distinct configuration.

### Can I change the folder structure or file name after creating an export?

Currently, you cannot edit a new-flow event export after it is created. Stop the existing export and create a new one with the updated configuration.

### What happens if an export does not due to a system issue?

If a run gets stuck due to a system error, it is automatically retried and resumes from where it stopped once the system is back online.

### Why do I see an error when creating the export?

Check that the bucket or container name matches exactly and that the IAM policy, service account key, or SAS token is valid. Regenerate keys if necessary.

### What should I do if my export fails?

If your export fails, follow these steps to troubleshoot the issue:

- _Verify your storage credentials_ — Make sure your IAM policy (AWS), service account key (GCP), or SAS token (Azure) is valid and has the required write permissions.
- _Check bucket or container access_ — Ensure the target bucket or container exists and is reachable from CleverTap.
- _Check for the following error codes_ — A 403 error in GCP usually indicates an invalid or expired service account key.
- For other platforms, refer to your cloud provider's error documentation for further guidance.

### What other ways can I export event data from CleverTap?

- [**Export via API**](https://developer.clevertap.com/docs/): Use the CleverTap Events API to programmatically query and download event data.
- [**Find People**](doc:find-people): Download user-level data directly from the CleverTap dashboard through _Segments_ > _Find People_.

### What are the Campaign Type values in the new export?

The `Campaign type` field value has changed between the legacy export and the new export. The old format returned human-readable strings; the new format returns internal enum values.

| Channel            | Old value             | New value           |
| ------------------ | --------------------- | ------------------- |
| Android push       | Mobile Push - Android | `Push`              |
| iOS push           | Mobile Push - iOS     | `Push`              |
| Windows push       | Mobile Push - Windows | `Push`              |
| Email              | Email                 | `Email`             |
| SMS                | SMS                   | `Sms`               |
| WhatsApp           | WhatsApp              | `WhatsApp`          |
| Web push (Chrome)  | Web Push - Chrome     | `Browser`           |
| Facebook Audiences | Facebook Audiences    | `Fb`                |
| Webhook            | Webhook               | `Webhook`           |
| App Inbox          | App Inbox             | `NotificationInbox` |
| In-App (Mobile)    | Others                | `InApp`             |
| Native Display     | Others                | `NativeDisplay`     |
| Web Popup          | Others                | `Web`               |
| Web Native Display | Others                | `WebNativeDisplay`  |
| Web Exit Intent    | Others                | `WEB_EXIT_INTENT`   |
| Web Inbox          | Others                | `WebInbox`          |
| Google Adwords     | Others                | `GoogleAdWords`     |
| TikTok             | Others                | `TIKTOK`            |
| Segment            | Others                | `Partner`           |
| mParticle          | Others                | `Partner`           |
| Amazon EventBridge | Others                | `Partner`           |
| Unified Inbox      | INBOX                 | `INBOX`             |
| Promotions         | Others                | `PROMO`             |

Review the table above and update any downstream filters or logic that reference old Campaign type values before migrating to the new export.

### What has changed between the legacy export and the new export?

The new export uses a fundamentally different schema compared to the legacy export. The key differences are summarized below. For full details on the legacy export format, refer to the [Legacy Event Export](doc:event-and-profile-exports) documentation.

**Identity and profile fields**

The old `profile{}` block is now split into two separate groups: `identity{}` (who the user is) and `profile{}` (attributes of the user). Update any parsers that read from a flat `profile{}` object.

**Timestamp**

`ts` (Long in `yyyyMMddHHmmss` format) is now `eventTime` (String). The value format depends on the Timestamp Format you configured when setting up the export (EPOCH or Formatted Datetime).

**Device info**

Both old and new formats include a `deviceInfo` block with the same fields (`make`, `model`, `appVersion`, `sdkVersion`, `osVersion`, `browser`, `dpi`, `dimensions`). In the new format, only the device attributes you selected during export configuration are present.

**Communication preferences**

The old format had no `commPrefs` section. The new format adds a `commPrefs` map containing subscription groups and opt-in/opt-out state. This is entirely new with no equivalent in the legacy export.

**CSV event property headers**

The old format prefixed event property columns with their type, for example `eventproperties.product_id` or `sessionproperties.utm_source`. The new format uses a flat structure where property names appear directly as column headers, for example `product_id`. Update any downstream logic that references the old prefixed column names.

**Summary**

| Aspect                     | Old export                                                 | New export                                 |
| -------------------------- | ---------------------------------------------------------- | ------------------------------------------ |
| Schema                     | Fixed, always-present fields                               | Configurable, only selected fields present |
| Timestamp                  | `ts` (Long, root level)                                    | `timestamp` (Map, root level)              |
| Identity fields            | Inside `profile{}` object                                  | Separate `identity{}` map                  |
| Profile attributes         | Inside `profile{}` object                                  | Separate `profile{}` map                   |
| Device info                | Fixed typed fields                                         | Flexible map, same keys                    |
| Communication preferences  | Not present                                                | New `commPrefs{}` map                      |
| Campaign type field        | Human-readable string (for example, Mobile Push - Android) | Enum name (for example, Push)              |
| CSV event property headers | Prefixed (for example, `eventproperties.product_id`)       | Flat (for example, `product_id`)           |

### Can I edit an event export after creation?

No. Once a configurable event export is created, it is completely locked. No changes can be made to the schedule, destination, file format, event selection, or any other setting. The only actions available after creation are to view or stop the export. To make changes, stop the existing export and create a new one with the updated configuration.

Note that the legacy export type does support editing after creation. This limitation applies only to the new configurable export flow and editing will be available in a future release.

### Do I need special permissions to create or manage exports?

All export operations, such as viewing, creating, and stopping, require the Creator role or higher. Read-Only members have no access. For more information, refer to [Role-Based Access Control](doc:role-based-access-control).

### Will renaming an event affect the file name and folder structure?

Renaming an event during export configuration affects the `eventName` field inside the exported file but not the file name or folder structure. For example, if you rename `App Launched` to `CT App Launch` during export setup, the exported file will contain `"eventName": "CT App Launch"`, but the `{{Event-name}}` variable in your folder path and file name will still resolve to `App Launched`, which is the original event name in CleverTap.

If you rename an event in CleverTap's schema after the export is created, the `{{Event-name}}` variable in the folder and file name will reflect the new schema name from that point onwards. Files generated before the rename retain the old name in their path.
