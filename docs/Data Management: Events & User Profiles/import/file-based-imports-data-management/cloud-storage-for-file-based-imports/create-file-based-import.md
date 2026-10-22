---
title: Create Import
excerpt: >-
  Learn how to import data from Cloud Storage into CleverTap to enable
  personalized targeting and optimized campaigns.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

You can import CSV or Parquet files from your connected cloud storage partner into CleverTap to keep user profiles and event data up to date. The import job defines the file name convention that CleverTap uses to identify and process files on each run.

This document covers the following:

- [Prerequisites](#prerequisites)
- [Create Import](#create-import)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

## Prerequisites

Before you create an import, ensure that a connected storage bucket and correctly formatted files are available.

- A connected storage bucket from a supported cloud storage partner. For more information, refer to the configuration document for your partner: [AWS S3](doc:aws-s3-configuration), [Google Cloud Platform](doc:gcp-configuration), or [Microsoft Azure](doc:microsoft-azure-configuration).
- Files in CSV or Parquet format that meet the requirements in [Review File Requirements](#review-file-requirements)

### Review File Requirements

To import data from your cloud storage bucket, files in CSV or Parquet format must meet the following formatting requirements.

<Tabs>
  <Tab title="CSV">
    | Specification          | Requirement                                                 |
    | ---------------------- | ----------------------------------------------------------- |
    | **Header Row**         | Required. CleverTap treats the first row as column headers. |
    | **Delimiter**          | Comma                                                       |
    | **Character Encoding** | UTF-8                                                       |
    | **Maximum File Size**  | 5 GB                                                        |
  </Tab>

  <Tab title="Parquet">
    | Specification                | Requirement                                                                                                                                                |
    | ---------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | **Library**                  | Uses the `parquet-avro` library (Apache Parquet), which reads the footer (schema and row-group index) first and then fetches only the parts that it needs. |
    | **Schema/Header Validation** | Every column that you map should exist in the file. CleverTap checks column names case-insensitively.                                                      |
    | **Maximum File Size**        | 1 GB                                                                                                                                                       |
  </Tab>
</Tabs>

<Callout icon="🚧" theme="warn">
  ### Important

  CleverTap picks up files based on file prefix, timestamp, format, and size. If your pipeline is still writing a file when CleverTap begins copying it, the file size changes during the process, and CleverTap marks the file as failed. Ensure that each file is fully written and closed before you place it in the bucket.
</Callout>

## Create Import

Creating an import defines the bucket, the file name format, and the nickname that CleverTap uses to find and process your files.

### Configure Import

Configuring the import involves selecting a cloud storage partner and entering the import details.

1. Go to _Settings > Partners > Import Center_ and click **Create Import**.

2. Select a cloud storage partner from the _Create Import_ popup.


   <Image src="https://files.readme.io/bc2a6d3ff4f282c86759010fe98ad6b423feaaf4cb30d0d4a2ef66895fe9d474-Screenshot_2026-10-05_at_6.21.46_PM.png" align="center" caption="Create Import" border={true} />


3. Under _Configure Import_, add the details in the following table:


   <Image src="https://files.readme.io/787b17fb970204fecc1efb20362141fe9f71e54437091b545aee90e7bb10f232-Screenshot_2026-10-05_at_6.22.22_PM.png" align="center" caption="Configure Import" border={true} />


   | Field            | Description                                                                                                                                                                                                                                                                       |
   | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | _Nickname_       | A unique name that identifies the import job in CleverTap. Choose a name that reflects the purpose of the import, for example, `Events Daily`.                                                                                                                                    |
   | _Storage Bucket_ | Select a connected storage bucket from the dropdown. CleverTap populates the storage URL automatically based on the selected bucket. For more information about setting up a connection, refer to the partner-specific configuration document.                                    |
   | _File Name_      | Define the file name format that CleverTap processes. The file name is case-sensitive. CleverTap imports only files whose names exactly match the specified file name, timestamp, and format. For more information, refer to [Define File Name Format](#define-file-name-format). |

4. (Optional) Click **Preview Results** to validate your configuration.

5. Click **Next** to open the _Select and Map Data_ page, where you set the mapping preference, configure identity mapping, and map your file columns to CleverTap fields. For more information, refer to [Map Data for Import](doc:map-data-for-file-based-import).

<Callout icon="📘" theme="info">
  ### Preview Results

  _Preview Results_ does not import any data into CleverTap. It displays the first few records from the first file in the bucket that matches your configured file prefix, timestamp, and file format.
</Callout>

### Define File Name Format

CleverTap recognizes and processes only files that use the following name format:

```text
<File Prefix><Date Time Format>.<File Format>
```

- _File Prefix_: Enter the exact leading portion of the file name in the text field.
- _Date-Time Format_: Select the timestamp format used in your file names. CleverTap uses this format to parse the timestamp and determine which files to process on each run. For more information, refer to [Review Supported Date-Time Formats](#review-supported-date-time-formats).
- _File Format_: Select **CSV** or **Parquet** to match the format of your files.

#### Review File Selection for Each Run

CleverTap selects files whose names begin with the configured file prefix, end with a timestamp, and use the selected format (`.csv` or `.parquet`). On the first run, CleverTap processes all matching files in the bucket. On each subsequent run, CleverTap processes only files with a timestamp newer than the previous run.

<Callout icon="🚧" theme="warn">
  ### Timezone Mismatch

  CleverTap evaluates file name timestamps against your CleverTap account timezone, not your cloud storage account timezone. For example, if your CleverTap account uses IST and your file-generation pipeline stamps file names in PST, the timestamps do not match, and CleverTap skips the files. Generate file name timestamps in your CleverTap account timezone to avoid missed files.
</Callout>

### Review Supported Date-Time Formats

CleverTap supports the following timestamp formats for file name matching, and you select the format that matches your files from the _Date-time format_ dropdown.

<Table>
  <thead>
    <tr>
      <th>
        Type
      </th>

      <th>
        Description
      </th>

      <th>
        Format
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Epoch
      </td>

      <td>
        10-digit Unix timestamp (seconds since January 1, 1970).
      </td>

      <td>
        `1745000000`
      </td>

      <td>
        `1745000000`
      </td>
    </tr>

    <tr>
      <td>
        Epoch Milliseconds
      </td>

      <td>
        13-digit Unix timestamp (milliseconds since January 1, 1970).
      </td>

      <td>
        `1745000000000`
      </td>

      <td>
        `1745000000000`
      </td>
    </tr>

    <tr>
      <td>
        Date First
      </td>

      <td>
        Timestamp that begins with the day, followed by the month, year, hour, minute, and second.
      </td>

      <td>
        - ddMMyyyyHHmmss
        - ddMMyyyy_HHmmss
        - ddMMyyyy HHmmss
        - dd_MM_yyyy_HH_mm_ss
        - dd-MM-yyyy-HH-mm-ss
        - dd-MM-yyyy HH-mm-ss
        - dd-MM-yyyy HH:mm:ss
        - dd_MM_yyyy HH_mm_ss
        - dd_MM_yyyy HH:mm:ss
      </td>

      <td>
        - 17042025143000
        - 17042025_143000
        - 17042025 143000
        - 17_04_2025_14_30_00
        - 17-04-2025-14-30-00
        - 17-04-2025 14-30-00
        - 17-04-2025 14:30:00
        - 17_04_2025 14_30_00
        - 17_04_2025 14:30:00
      </td>
    </tr>

    <tr>
      <td>
        Month First
      </td>

      <td>
        Timestamp that begins with the month, followed by the day, year, hour, minute, and second.
      </td>

      <td>
        - MMddyyyyHHmmss
        - MMddyyyy_HHmmss
        - MMddyyyy HHmmss
        - MM_dd_yyyy_HH_mm_ss
        - MM-dd-yyyy-HH-mm-ss
        - MM-dd-yyyy HH-mm-ss
        - MM-dd-yyyy HH:mm:ss
        - MM_dd_yyyy HH_mm_ss
        - MM_dd_yyyy HH:mm:ss
      </td>

      <td>
        - 04172025143000
        - 04172025_143000
        - 04172025 143000
        - 04_17_2025_14_30_00
        - 04-17-2025-14-30-00
        - 04-17-2025 14-30-00
        - 04-17-2025 14:30:00
        - 04_17_2025 14_30_00
        - 04_17_2025 14:30:00
      </td>
    </tr>

    <tr>
      <td>
        Year First
      </td>

      <td>
        Timestamp that begins with a four-digit year, followed by the month, day, hour, minute, and second.
      </td>

      <td>
        - yyyyMMddHHmmss
        - yyyyMMdd_HHmmss
        - yyyyMMdd HHmmss
        - yyyy_MM_dd_HH_mm_ss
        - yyyy-MM-dd-HH-mm-ss
        - yyyy-MM-dd HH-mm-ss
        - yyyy-MM-dd HH:mm:ss
        - yyyy_MM_dd HH_mm_ss
        - yyyy_MM_dd HH:mm:ss
      </td>

      <td>
        - 20250417143000
        - 20250417_143000
        - 20250417 143000
        - 2025_04_17_14_30_00
        - 2025-04-17-14-30-00
        - 2025-04-17 14-30-00
        - 2025-04-17 14:30:00
        - 2025_04_17 14_30_00
        - 2025_04_17 14:30:00
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  ### Note

  These formats apply to the timestamp in the file name. For the date formats that apply to values inside a column, such as a _Date property_ or the _event Created On_ field, refer to _Supported Date Formats_ in [Map Data for Import](doc:map-data-for-file-based-import).
</Callout>

## FAQs

### What happens if my file exceeds the maximum file size?

CleverTap marks files that exceed the maximum file size (5 GB for CSV and 1 GB for Parquet) as failed and does not process them. Ensure that your files stay within the limit before you upload them to your cloud storage bucket.

## Next Steps

After you configure the import, CleverTap saves the import job, and you can view and manage all import jobs from the _Import Center_.

- Map your file columns to CleverTap fields. For more information, refer to [Map Data for Import](doc:map-data-for-file-based-import).
- Schedule the import. For more information, refer to [Schedule Import](doc:schedule-file-based-import).