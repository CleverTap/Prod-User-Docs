---
title: Profile and Events (Legacy)
excerpt: Learn how to export data from CleverTap to different Data Warehouse platforms.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

CleverTap supports exporting raw event and profile data to cloud storage platforms such as Amazon S3, Google Cloud Storage, and Microsoft Azure.

These exports allow you to:

* Move platform data into your existing data lakes, warehouses, or Business Intelligence (BI)  tools.
* Maintain independent backups for compliance and audits.
* Help personalize engagements using raw user and event data.

Exports can be scheduled or triggered as one-time deliveries and are available in standard file formats, including JSON, CSV, XML, and Parquet, to support a wide range of downstream systems.

# Create export

To begin, you first create a new export from the CleverTap dashboard. This step connects your CleverTap account with a partner destination and sets the context for the following configuration.

1. Go to *Settings* > *Partners* and click **Create Export**.

<Image align="center" alt="Create Export" border={true} caption="Create Export" src="https://files.readme.io/6d308e01cc3dc940760f1c76ee5cecffda32a57b8db946c62d3e125af9c15d75-export_center_profile_1.png" />

2. Under *Data type*, select **Events** or **Profiles**. Click **Next**.

<Image align="center" alt="Data Type - Profiles" border={true} caption="Data Type" src="https://files.readme.io/5c7972185b625c21e9b8e3dd538630e7c917584f95c90cccca70fb876021f7fa-data_type_profiles_.png" width="65% " />

3. Under *Partner*, select where you want to send the export and click **Start**. Selecting a partner affects the first field you’ll see in **Storage & file details**: it appears as **Storage bucket** for Amazon S3 and Google Cloud, and as **Storage blob** for Microsoft Azure.

   * **Amazon S3**
   * **Google Cloud**
   * **Microsoft Azure**

<Image align="center" alt="Select Partner" border={true} caption="Select Partner" src="https://files.readme.io/353438c2d86d5c956db69fb1e54c319b25ace89c7951fe05772d9768e3692f2c-partner_export_profile.png" width="65% " />

The partner export window displays. If you are exporting user profiles and using enhanced export flow, refer to [Profile Exports](doc:profile-exports).

<Image align="center" alt={1008} border={true} caption="Enter Export Details" title="Enter export details and click Export" src="https://files.readme.io/13a408d-CreateAmazonS3Export.jpg" width="90% " />

4. Configure the following *Export details*:
   * **Partner Bucket name**: Name of the partner bucket. Choose the required partner bucket from the drop-down list.
   * **DATA TYPE & IDENTIFIER PRIORITY**: Select the data to export.
     * **Events**: **All events** or **Select events**.
     * **Profiles**: **All user profiles**.
   * **Fallback priority order for identifiers**: Set priorities 1, 2, and 3 for **Identity**, **Email**, and **Phone Number**. (Applies to **All events** and **All user profiles**.)
   * **FREQUENCY**:
     * **One time**: A single export for the selected export type. You can export data up to the last **60 days**. You can create an export for a specific day, date range, previous month, current month, and more.
     * **Recurring**: Set up a recurring export that exports all the new events or user profiles captured in the last window. You can export data as frequently as every **4 hours** and up to once every **24 hours**.
   * **Dates to export data**: The export starts at **12:00 a.m.** on the specified date by default.
   * **FORMAT**: **JSON**, **XML**, **CSV**, and **Parquet**.
   * **Export Data**: If you choose **As string**, the data is sent as a string. If you do not select the box, data is sent in its original format.

> 🚧 **Profiles one-time export**
>
> Before running a one-time profile export, stop any scheduled recurring profile export.

5. Click **Export**. A confirmation message displays at the top of the *Exports* page. The status for each export is displayed as **PENDING** as soon as the export is created, changes to **RUNNING** after processing starts, and to **DONE** when the export is complete.

> 📘 **Stop Export**
>
> You can also stop the export that you have created. Click the ![](https://files.readme.io/203208a-StopExport.jpg) icon for the export request you want to stop, and then click **Stop** to confirm.

You can verify if the export is created on your cloud platform using **Request ID** as follows:

* **Amazon S3**\
  a. Log in to your AWS account and navigate to the *S3* console.\
  b. Search your *Bucket* from the *Buckets* page and then click the bucket name.\
  c. Copy the *Request ID* from the activity log and search with that ID. You should see your respective file there.

<Image align="center" alt={2842} border={true} caption="New Amazon S3 Export Displays on Amazon S3 Dashboard" title="Search for new Amazon S3 export on Amazon S3 Dashboard" src="https://files.readme.io/217fe0e-Search_for_export_files.png" />

* **Google Cloud**\
  Select *Storage* from the left panel of Google Cloud. Navigate to the *Bucket details* page and search with the `requestid`. All the exported files are displayed.

<Image align="center" alt={2862} border={true} caption="New Google Export Displays on Google Cloud" title="New Google Cloud export displays on Export page" src="https://files.readme.io/2dd4777-Screenshot_2020-04-06_at_8.23.50_PM.png" />

* **Microsoft Azure**\
  Log in to your Microsoft Azure account and select the *Storage account* under *Resources*. Click the *Blob service* link under the *Properties* tab and select the *Container* where you exported the data. (Optional) Click **Switch to Access Key** if you encounter any authorization error after selecting the *Container*.

<Image align="center" alt="New Export Displays on Microsoft Azure Dashboard" border={true} caption="New Export Displays on Microsoft Azure Dashboard" src="https://files.readme.io/7c9e1a4-New_Export_Displays_on_Microsoft_Azure_Dashboard.gif" width="90% " />

# Export Format

This section provides information about the file format and naming conventions for the files exported to your storage destination.

## File Name Format

* **File Name Format for Event Export**\
  The example below shows the file name format for event export:

  ```
  <export request id>-<timestamp of the export run>-<event name>-<yyyymmdd>-<file index>-<database-id>.json
  ```

  * *Export request ID*, *Timestamp of the export run*, *Event name*, *File index* (files are chunked to \~100 MB), *Database ID*, and file format.

* **File Name Format for User Profile Export**\
  The example below shows the file name format for user profile export:

  ```
  <account id>-<request id>-<timestamp of the export run>-<database-id>-<file format>.gz
  ```

  * *Account ID* (CleverTap project ID), *Request ID*, *Timestamp of the export run*, *Database ID*, and file format.

## File Data Format

Files are split by event names for event exports, and each file will have all event data for the given period for the event.

### JSON

The first line of the file contains the event name. After the first line, each line is JSON describing the timestamp, object id, and event properties.

```json
{
	"profile": {
		"identity": "dqsndckfk234"
	},
	"ts": 20171109000015,
	"eventProps": {
		"ct_connected_to_wifi": "false",
		"ct_bluetooth_version": "ble",
		"ct_bluetooth_enabled": "false",
		"ct_sdk_version": 30107,
		"ct_latitude": -6.1975594,
		"ct_longitude": 106.52913,
		"ct_os_version": "5.1.1",
		"ct_app_version": "2.30.1",
		"ct_network_carrier": "3",
		"ct_network_type": "4G"
	}
}
```

### CSV

CSV files are comma-delimited and have each event in separate rows.

<Image align="center" alt={2032} border={false} caption="Sample CSV File" title="Sample CSV File" src="https://files.readme.io/aa71f9f-Screenshot_2020-02-28_at_12.53.22_PM.png" />

### XML

XML has the timeStamp, eventName, followed by eventProperties.

```xml
<Event>
    <ts>20200220130735</ts>
    <eventName>Export Custom Event</eventName>
    <profile>
        <all_identities>exportProfile+81@clevertap.com</all_identities>
        <platform>Web</platform>
        <email>exportProfile+81@clevertap.com</email>
    </profile>
    <deviceInfo>
        <browser>Others</browser>
    </deviceInfo>
    <eventProps>
        <entry>
            <key>CT Source</key>
            <value>API</value>
        </entry>
        <entry>
            <key>Category</key>
            <value>Mens Watch</value>
        </entry>
        <entry>
            <key>Product name</key>
            <value>Casio Chronograph Watch</value>
        </entry>
        <entry>
            <key>Price</key>
            <value>59.99</value>
        </entry>
        <entry>
            <key>Currency</key>
            <value>USD</value>
        </entry>
    </eventProps>
</Event>
```

### Parquet

Parquet has a timestamp, eventName, and eventProperties for each event.

> 📘 **Parquet File Format**
>
> Parquet is an open-source file format for Hadoop. Parquet stores nested data structures in a flat columnar format. Currently, exports in Parquet format are compressed as **.parquet.gzip**. Contact the Customer Support Team if you wish to get the file as **.parquet**, i.e., without any additional compression.

# Prioritize User Identity for Exports

The export file includes an identity column with the user's Identity, Phone Number, or Email values. These values are set based on the identities configured in the CleverTap dashboard under the *Settings* > *User Identity* page. This feature lets you prioritize the identifier you want to export in the identity column.

Let us understand how the prioritization works based on the identities selected in the *User Identity* page:

* If you select only *Identity*, export includes the identity value. The export file's identity column is empty if it is unavailable.\
  ![](https://files.readme.io/aad1f81-image.png)
* If you select multiple identifiers, you must set the priorities on the *Export* page. For instance, you set Priority 1 to *Identity* and Priority 2 to *Email ID*. When exporting data, the export prioritizes the Identity value for the identity column. If it is absent, the Email ID is exported under the identity column of the export file. If both are missing, the column remains empty.\
  ![](https://files.readme.io/52ae818-UserIdentity.jpg)

> 📘 Key Points to Remember
>
> * If you change the identity later, the export works according to the set priority. To prioritize the modified identities, edit your export.
> * This feature applies only to the following export types: *All events* and *All user profiles*.
> * For the old running export, this configuration or prirotization is not applicable. You can add the prioritization by editing the running exports.

To prioritize user identity for exports:

1. Go to **Partners** > **Exports**.
2. Hover over the required AWS S3 export. Click the **Edit** button.
3. Under **Fallback priority order for identifiers**, set up the priority 1, 2, and 3 for the required identities from the drop-down list.

<Image align="center" alt={1008} border={true} caption="Edit Export Priority" title="Enter export details and click Export" src="https://files.readme.io/47d17d5-AWS3Priority.jpg" width="90% " />

# FAQs

This section consolidates FAQs that apply to the legacy creation flow.

### Do CleverTap data exports allow special characters?

Yes, CleverTap data exports allow the following special characters:

* Supports Unicode (UTF-8) character encoding.
* Replaces Whitespace, Tab, Slash, and null (\\0) with a hyphen.
* Replaces control characters with `?`.
* Supports emoji characters; some emojis (UTF-16) may not render properly.

### How does recurring export work?

On day one, the entire user profile data is sent. From day two onwards, only updates or additions are exported (for example, new profiles or updates to user properties/communication preferences). You can export data as frequently as every 4 hours and up to once every 24 hours.

### Can I run a one-time Profiles export if a recurring Profiles export is active?

Before running a one-time profile export, stop any scheduled recurring profile export.

### What formats are supported?

JSON, XML, CSV, and Parquet. Parquet is compressed as **.parquet.gzip** in the legacy flow.

### How are large exports chunked?

We chunk the data across multiple files for larger exports. File sizes are limited to \~100 MB to make them more consumable. The file index indicates the file number in the series.

### What other ways can I export data from CleverTap?

* **Export via API** (see API Overview).
* **Find People**: Download the profile data directly from the CleverTap dashboard through *Segments* → *Find People* → **View Details** → download under **Total users**.
* **Data Exports** to your storage destination (this legacy flow).
