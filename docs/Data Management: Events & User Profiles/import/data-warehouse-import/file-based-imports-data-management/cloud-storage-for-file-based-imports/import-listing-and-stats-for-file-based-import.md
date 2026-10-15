---
title: Import Listing and Stats
excerpt: Understand how to import data into CleverTap from files.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

You can view your File-Based Imports by selecting the _Import Center_ tab on the _Partners_ page. This page lists every import, its current state, run health, and per-file statistics, and is where you operate imports after creation.

The Import Listing page displays all import jobs and their current state. The following table lists the details that the page displays for each import:

| **Field**  | **Description**                                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------------------------------- |
| Nickname   | The unique name assigned to each import. This helps easily identify and differentiate between multiple import jobs. |
| Partner    | The cloud storage partner used for the import (for example, Amazon S3, Google Cloud Platform, or Azure).            |
| Status     | The current status of the import: Draft, Ready, Scheduled, Running, Paused, or Stopped.                             |
| Sync Type  | Indicates whether the import is for user profile data or event data.                                                |
| Frequency  | The configured schedule (Repeat Intervals, Custom Schedule, or Manually Trigger).                                   |
| Health     | The overall health of the import run. For more information, refer to [Health Indicator](#health-indicator).         |
| Last Run   | The date and time when the import was last triggered.                                                               |
| Created On | The date and time when the import was created.                                                                      |
| Created By | The user who created the import.                                                                                    |
| Updated On | The date and time when the import configuration was last modified.                                                  |
| Updated By | The user who last modified the import.                                                                              |

# Health Indicator

The health indicator provides an at-a-glance view of the success rate of each import run.

| **Health**          | **Description**                                                                                                               |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| 100% (Green)        | All records in all processed files were imported successfully.                                                                |
| 50%–99.99% (Yellow) | Some records failed during processing. Review the failed records in the detail pane to identify the affected files or fields. |
| Below 50% (Red)     | A majority of records failed to process. Review file size, data format, and field mappings for potential issues.              |
| Blank               | No data was processed. This may occur if no matching files were found in the bucket.                                          |
| No indicator        | The first run has not yet completed processing all the files.                                                                 |

# Stats

**Stats** provides a detailed view of each import run, broken down by individual file. You can track import performance over time, understand the quality of your source data, and make informed adjustments to your import configuration with the help of these stats.

To access Stats, go to _Settings_ > _Partners_ > _Import Center_. Click an import to open its details, and then select the _Stats_ tab.

Each import run may process multiple files. The Stats table displays one row per file processed during the run, with the following details:

| **Field**        | **Description**                                                                                            |
| ---------------- | ---------------------------------------------------------------------------------------------------------- |
| Imported On      | The date and time when the file was processed.                                                             |
| Filename         | The name of the file processed during the import run.                                                      |
| Status           | The processing status of the file: Processing, Completed, or Failed.                                       |
| Health           | The health percentage for that file. For more information, refer to [Health Indicator](#health-indicator). |
| Total Records    | The total number of records the import attempted to process from that file.                                |
| Successful Syncs | The number of records successfully imported without errors.                                                |
| Failed Syncs     | The number of records that could not be imported due to validation or processing issues.                   |

<Callout icon="📘" theme="info">
  #### Note

  Stats are refreshed after each file is processed. If a run is in progress, the stats displayed may not yet reflect all files in that run. Refresh the page to view the latest results.
</Callout>

## File Processing Rules

CleverTap applies the following rules when processing files during an import run:

- **File size limit**: CleverTap does not process CSV files larger than 5 GB or Parquet files larger than 1 GB, and it marks them as Failed.
- **File modified during fetching from your cloud storage**: If a file changes (its size in bytes changes) while CleverTap is actively fetching it, CleverTap marks the file as Failed to ensure data integrity.
- **File modified after CleverTap fetches it**: If a file changes in the cloud storage after CleverTap has already fetched it, CleverTap processes the version that it fetched at the time of the run. CleverTap does not reflect changes made after the fetch in that run.

## Import Stats

Click a file row in the _Stats_ table to open the detailed record view for that file. Detailed record data is available only for import runs completed within the last 30 days.

Each record in the detail pane displays the following:

| **Field**             | **Description**                                                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Result                | Indicates whether the record was imported successfully or failed.                                                                                                             |
| CleverTap ID/Identity | The identifier associated with the user profile or event, such as the CleverTap ID or the identity used to match the user (for example, email, phone number, or a custom ID). |
| Event Name            | For event imports, the name of the event processed.                                                                                                                           |

You can filter the records displayed in the detail pane using the **All Records** dropdown. The following filter options are available:

- **All Records**: Displays all records processed from the file, regardless of result.
- **Sync Successes**: Displays only records that were successfully imported.
- **Sync Fails**: Displays only records that failed to import.

You can also search for a specific record using the **Search identity** field to look up a record by its identity or CleverTap ID.

To view the full user profile associated with a record, click the **View profile** icon next to the record. This is available for both user profile and event data imports.

## Recommendation for Using Stats to Improve Sync

Stats works best as a feedback loop to actively improve the quality and reliability of future imports. The following are recommended ways to get the most out of Stats.

- **Track health trends across runs**: Review the health percentage across multiple runs to spot patterns. A consistent green health indicates a stable, well-mapped import. A declining trend often signals a change in the source file structure, unexpected values in a column, or storage bucket credentials that need updating.
- **Use failed records to refine your mappings**: When a run shows failed syncs, click into the file row and review the failed records in the detail pane. If the same field fails across many records, the issue is likely in how it is mapped or formatted in the source file. Addressing the root cause in the source data or remapping the field will improve health across future runs.
- **Monitor file-level failures**: If a file row shows a Failed status with zero records processed, the file may have exceeded the 5 GB size limit or was modified during fetching. Review your data pipeline to ensure files are fully written and within the size limit before they are picked up by CleverTap.
- **Prioritize identity errors**: Records without a valid identity cannot be linked to a user profile in CleverTap and will not be usable for segmentation or engagement. Resolve identity-related failures before addressing property-level errors.
- **Compare runs over time**: If health drops suddenly after a period of consistent performance, check whether anything changed in your source files around that time, such as the file structure, column names, or data types.

# Best Practices

The following best practices help ensure your File-Based Imports run smoothly and your data remains clean and reliable.

Before configuring and running your import, ensure your source files are ready for a successful sync by reviewing the following:

- Validate your source data before configuring the import. Ensure that identity fields such as email, phone, or custom ID contain clean, non-null values, and that data types in your source columns match the mappings you intend to configure.
- Ensure phone numbers include a valid country code in E.164 format (for example, +919876543210) and that email addresses are properly formatted.
- Avoid including system event names, such as App Launched, in the event name column of your source files, as these cannot be imported from external sources.
- Remove or replace reserved or placeholder identity values such as null, 0, N/A, undefined, or none in the source before the import runs.
- Ensure each file is fully written and closed before it is placed in the storage bucket. CleverTap picks up files based on the timestamp in the file name and marks a file as Failed if the file is still being written when CleverTap starts fetching it.
- Keep each file under its size limit: 5 GB for CSV and 1 GB for Parquet. CleverTap marks larger files as Failed and does not process them.
- Confirm that your storage bucket credentials are valid and have not been rotated or updated since the import was last configured.

# Monitor Imports

Review the following practices to ensure better import health and catch issues early:

- Review Stats after each run, especially for scheduled imports, to confirm the health percentage is at expected levels.
- For imports scheduled at short intervals, such as every 15 minutes, be aware that if a run takes longer than the scheduled interval to complete, the next run will be skipped automatically and resume from the one after. This will appear as a gap in the Stats table and is expected behavior.
- Stats are available for runs completed within the last 30 days. For long-term monitoring, note down or export health and record counts periodically if historical tracking is important for your team.
- If an import in a running state is manually stopped, stats will not be available for that run, even if some records were partially ingested. Allow imports to complete before stopping them where possible.

# Error Reference

Use this section to identify and resolve validation errors that appear in the detail pane for failed records. Errors are grouped by import type.

## Common Errors

The following errors apply to both user profiles and event imports:

| **Error**                                                                      | **Cause**                                                                                                                                            | **Resolution**                                                                                                                                                                                                       |
| :----------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Invalid identity or CleverTap ID                                               | The value is invalid or reserved (for example, null, undefined, 0, or empty) or exceeds 1024 characters.                                             | Remove or replace invalid values in the identity column. Ensure each value is valid and within the character limit.                                                                                                  |
| Value should be an Integer or a Float, but a different data type was received. | A field mapped as Integer or Float contains a non-numeric value.                                                                                     | Ensure the source column contains only numeric values or remap the field to the correct data type.                                                                                                                   |
| Value for Boolean data type needs to be 0, 1, true, or false                   | A Boolean field contains unsupported values.                                                                                                         | Use only 0, 1, true, or false in the source column.                                                                                                                                                                  |
| Field mapped as Date contains invalid values                                   | A field mapped as Date contains non-date values.                                                                                                     | Ensure the source column contains valid date values or remap the field to the correct data type. For more information, refer to [Supported Date Formats](doc:map-data-for-file-based-import#supported-date-formats). |
| File exceeds maximum size limit                                                | The CSV file is larger than 5 GB or the Parquet file is larger than 1 GB                                                                             | Split the file into smaller files, each under 5 GB or 1 GB, and re-upload them to the storage bucket.                                                                                                                |
| File was modified during processing                                            | The file was modified while CleverTap was fetching the file, such as the number of records changed, added, or removed, file size changed, and so on. | Ensure files are fully written and closed before they are placed in the storage bucket. Do not overwrite or modify files while CleverTap is fetching the file.                                                       |

## User Profile Import Errors

The following errors may appear for failed records in a user profile import:

| **Error**                                                                        | **Cause**                                                                         | **Resolution**                                                                          |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Email is not valid                                                               | The email value is missing required components or is incorrectly formatted.       | Ensure all email values follow a valid format (for example, include an @ and a domain). |
| Phone number must start with a valid country code and contain more than 4 digits | The phone number is missing a country code or has fewer than 4 digits.            | Store phone numbers in E.164 format (for example, +91XXXXXXXXXX).                       |
| Communication preferences contain unsupported values                             | A communication preference field contains values other than 0, 1, true, or false. | Standardize values in the source column to 0, 1, true, or false.                        |

## Event Import Errors

The following errors may appear in the detail pane for failed records in an event import:

| **Error**                                                      | **Cause**                                                                                                                                                                                                                      | **Resolution**                                                                                                      |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| Event name contains a prohibited character                     | The event name contains one or more prohibited characters, including percent, greater than, less than, exclamation point, pipe, ampersand, dot, colon, semicolon, dollar sign, single quote, double quote, backslash, or hash. | Remove or replace prohibited characters in the event name column of the source file.                                |
| The system event name cannot be processed from the data source | A record in the event name column contains the name of a CleverTap system event, such as App Launched, which cannot be imported from external sources.                                                                         | Exclude system event names from the event name column or filter them out in the source file before the import runs. |
| Timestamp value is in an unsupported format or data type       | The Created On field contains a value that does not match any of the supported date formats.                                                                                                                                   | Use a supported format. If blank, CleverTap uses the processing timestamp.                                          |
