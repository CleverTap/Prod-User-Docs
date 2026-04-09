---
title: 'Imports: FAQs'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<br />

# Overview

This document answers common questions about importing user data into CleverTap through SFTP or data warehouses, covering sequencing, data preparation, and best practices to ensure data integrity during historical imports.

### What are the different ways to import historical data into CleverTap?

You can upload historical data to CleverTap using any of the following methods, depending on your data volume, frequency, and technical setup:

* **SFTP Import**: Best for recurring bulk uploads of both user profiles and events. Supports CSV format with manifest file mapping. For more information, refer to [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp).
* **Data Warehouse Import**: Best for importing directly from cloud warehouses like Snowflake, BigQuery, Amazon Redshift, Databricks, and Microsoft Fabric. Supports scheduled and one-time imports. For more information, refer to [Data Warehouse Import](https://docs.clevertap.com/docs/data-warehouse-import).
* **CSV Upload**: Best for quick, one-time profile uploads via the dashboard (profiles only, up to 1 GB per file). For more information, refer to [CSV Upload](https://docs.clevertap.com/docs/csv-upload).
* **Upload User Profiles API / Upload Events API**: Best for programmatic, real-time or near-real-time data ingestion. For more information, refer to [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api) and [Upload Events API](https://developer.clevertap.com/docs/upload-events-api).

### Do I need to upload user profiles before events?

Yes, it is strongly recommended to upload user profiles before events. This ensures that:

* CleverTap can correctly stitch events to the right user profiles during ingestion via identity resolution.
* Events uploaded without a matching profile may result in incomplete or anonymous user records, affecting segmentation and campaign targeting accuracy.
* Lifecycle metrics (for example, First Event, Last Event) are computed accurately.

For more information, refer to [Upload User Profiles](https://developer.clevertap.com/docs/upload-user-profiles-api) and [How Profiles Merge](https://docs.clevertap.com/docs/how-profiles-merge).

### What information should I include in user profile uploads?

To enable effective personalisation and targeting, include as much user information as possible. At a minimum, every profile upload must include a valid User Identifier (Identity). Recommended fields include:

* **Mandatory**: Identity (unique user ID such as internal DB ID, CRM ID, UUID, or any unique string).
* **System User Properties**: Name, Age, Email ID, Phone number (in `+[country code][number]` format). For more information, refer to [System User Properties](https://docs.clevertap.com/docs/user-profiles#system-user-properties).
* **Custom Profile Attributes**: Any business-specific properties (for example, membership tier, preferred language).
* **Nested Objects**: User properties with nested structures for complex data. For more information, refer to [Nested Objects in User Properties](https://docs.clevertap.com/docs/nested-objects-in-user-properties).
* **Communication Preferences**: Opt-in/opt-out status for channels such as Email, SMS, WhatsApp, and Push.

Ensure all date properties use Unix epoch format (seconds). For more information, refer to [Schema](https://docs.clevertap.com/docs/schema) for supported data types.

### Can I test historical tested before sending them to production?

Yes, CleverTap strongly recommends testing with a sample dataset in your test account before importing into production.

The following are the key points to remember before sending them to production:

* Your test account can be reset; production cannot delete or modify imported data.
* The test account has a default 1-month Data Retention Policy (DRP), so ensure your sample data falls within this window.
* Validate correct identity stitching, event-to-profile mapping, timestamp accuracy, data type consistency, and field mapping in the manifest file during testing.
* For API-based imports, use the **dryRun** parameter (_?dryRun=1_) to validate payloads without ingesting data.

### How does CleverTap handle timestamps on historical events?

When uploading historical events, include the original event occurrence time in the payload:

* For API, timestamps must be in Unix epoch format (seconds).
* For SFTP and Data Warehouse imports, CleverTap supports multiple date-time formats, as configured in the manifest file or during mapping (e.g., dd/MM/yyyy HH:mm:ss, yyyy-MM-dd, epoch). For more information, refer to [SFTP Import – Date Time Formats](https://docs.clevertap.com/docs/imports-via-sftp#supported-date-time-format) and [Data Warehouse imports - Date Time](https://docs.clevertap.com/docs/map-data-for-import#supported-date-format)
* Events appear in dashboards and analytics based on the provided event time, not ingestion time.
* If no timestamp is provided, CleverTap records the event at ingestion time, potentially leading to inaccurate historical reporting.
* Import eligibility depends on your account’s [Data Retention Policy (DRP)](https://docs.clevertap.com/docs/schema#set-data-retention-policy). Events outside the DRP window may not be available for analysis.
* For the Test Account, the default DRP is 1 month.

<Callout icon="📘" theme="info">
  #### Note

  All timestamps are treated as UTC (Coordinated Universal Time) unless otherwise specified in the manifest configuration.
</Callout>

### How can I delete a Data Warehouse connection that has a running import?

To delete a Data Warehouse connection with active imports:

* Navigate to _Settings_ > _Partners_ > _Import_ > _Import Connections_.
* Select the connection you want to delete and click **Delete**.
* Review any active imports. If imports are in _Ready_, _Scheduled_, _Paused_, or _Running_ states, you must stop all of them before proceeding.
* Once all imports are stopped, click **Delete** again and confirm your action.

### How can I whitelist IPs for CleverTap integration?

To ensure seamless communication between CleverTap and your data warehouses, whitelist the following required IP ranges based on your CleverTap dashboard region:

<Table>
  <thead>
    <tr>
      <th>
        Region
      </th>

      <th>
        IP Range(s)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Europe (`eu1`)
      </td>

      <td>
        `34.250.139.131`  
        `34.249.27.35`  
        `34.240.158.5`  
        `3.254.126.216`
      </td>
    </tr>

    <tr>
      <td>
        India (`in1`)
      </td>

      <td>
        `35.154.242.39`  
        `13.126.204.11`  
        `65.1.219.106`  
        `13.126.239.79`
      </td>
    </tr>

    <tr>
      <td>
        Singapore (`sg1`)
      </td>

      <td>
        `3.1.111.122`  
        `52.221.166.167`  
        `13.213.186.178`  
        `18.141.242.16`
      </td>
    </tr>

    <tr>
      <td>
        United States (`us1`)
      </td>

      <td>
        `44.233.27.236`  
        `44.232.188.247`  
        `44.245.25.40`  
        `54.184.78.137`
      </td>
    </tr>

    <tr>
      <td>
        Indonesia (`aps3`)
      </td>

      <td>
        `43.218.28.119`  
        `43.218.2.244`  
        `16.79.157.29`  
        `108.137.137.104`
      </td>
    </tr>

    <tr>
      <td>
        UAE (`mec1`)
      </td>

      <td>
        `3.28.217.95`  
        `3.28.209.115`  
        `3.28.232.78`  
        `158.252.128.120`
      </td>
    </tr>
  </tbody>
</Table>

### What are the recommendations while uploading historical data to CleverTap?

To ensure accurate ingestion and reporting, follow these best practices:

* Upload user profiles before uploading events
* Maintain consistent User Identifiers across profiles and events
* Upload events in chronological order (oldest first)
* Validate a sample dataset in your test account before production import
* Ensure timestamps are sent in Unix epoch format (seconds)
* Confirm that imported data falls within your account’s Data Retention Policy
* Break large datasets into smaller batches where applicable
* Ensure column headers are present in all CSV files (mandatory for SFTP import).
* Use consistent data types for the same property across all uploads (for example, do not mix string and numeric values for the same attribute).
* Avoid using special or reserved values as Identity (e.g., _null_, _undefined_, _none_, blank strings, or _test_). For more information, refer to [CSV Upload – FAQs](https://docs.clevertap.com/docs/csv-upload#faq)
* For SFTP imports, every data file must be accompanied by a manifest file. For more information, refer to [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp)

Following these practices helps ensure proper identity stitching and accurate lifecycle computation.

### For data like date of birth, which date format does CleverTap support?

The supported date format depends on the import method:

* **API:** Date properties must be sent in Unix epoch format (seconds). CleverTap converts the timestamp internally into a date value for segmentation and reporting.
* **SFTP imports and Data Warehouse imports:** Multiple date-time formats are supported as configured in the manifest file (for example, `dd/MM/yyyy`, `yyyy-MM-dd'T'HH:mm:ss`, `epoch`) or while configuring mapping. If the timestamp is missing from a date-time field, CleverTap adds a default timestamp of 00:00:01.
* **CSV Upload (Dashboard):** Supports the `$D_ prefix` notation for epoch timestamps (for example, `$D_1695801332`). The data type must be set to alphanumeric in the mapping. CSV upload also supports other data types based on the mapping.

For more information, refer to [SFTP Import – Date Time Formats](https://docs.clevertap.com/docs/imports-via-sftp#supported-date-time-format), [Data Warehouse imports - Date Time](https://docs.clevertap.com/docs/map-data-for-import#supported-date-format), and [CSV Upload](https://docs.clevertap.com/docs/csv-upload)

### How can I define my User Identifier in CleverTap?

The User Identifier (Identity) is a unique value used to distinguish one user profile from another.

You can define Identity using:

* Internal database user ID
* CRM ID
* UUID
* Any unique string value

The Identity value must:

* Be unique per user
* Remain consistent across profile and event uploads
* Not be reassigned to a different user
* Identity value must be less than 1024 characters.
* In addition to Identity, CleverTap also supports _objectId [CleverTapID]_ (a system-assigned identifier). At least one must be present.
* For SFTP imports, the _objectId_ column header is mandatory.
* For the CSV Upload (Dashboard), the _identity (lowercase i)_ column is mandatory.

For more information, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [How Profiles Merge](https://docs.clevertap.com/docs/how-profiles-merge).

### What are the limitations while importing data to CleverTap?

When importing historical data, consider the following:

* Data imported into production cannot be rolled back
* Events outside your Data Retention Policy window will not be available for analysis
* Duplicate event handling must be managed externally
* _Timestamps_ must be provided in Unix epoch format (seconds)
* SFTP supports files up to 5 GB per file. CSV Upload supports files up to 1 GB per file. Encrypted files (PGP) must be under 1 GB; split larger files before uploading.
* SFTP import and Data Warehouse import currently do not support importing the items array for the Charged event.
* Event names in CleverTap are case-sensitive (for example, _Product Viewed_ and _product viewed_ are treated as separate events).
* Upload APIs have a limit of 1,000 objects per 4 MB per request, with approximately 30 requests per second throttle.
* All files must be in CSV format and accompanied by a manifest file.
* Map and Array data types are currently not supported in dashboard CSV uploads and Data Warehouse Imports.
* It is recommended to validate all imports in a test account before proceeding to production.

### Which file formats does import support?

The supported file format depends on the import method:

* **SFTP Import:** CSV format only. Each CSV file must be accompanied by a manifest file (JSON) that maps your columns to CleverTap properties. For more information, refer to [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp)
* **SFTP with Encryption (PGP):** CSV.ASC File format. Encrypted files must be under 1 GB. For more information, refer to [File Upload Encryption](https://docs.clevertap.com/docs/file-upload-encryption)
* **Data Warehouse Import:** Data is read directly from your warehouse tables/views (Snowflake, BigQuery, Redshift, Databricks, Microsoft Fabric). No file format conversion needed. For more information, refer to [Data Warehouse Import](https://docs.clevertap.com/docs/data-warehouse-import)
* **CSV Upload (Dashboard):** CSV format only, for user profiles. For more information, refer to [CSV Upload](https://docs.clevertap.com/docs/csv-upload)
* **APIs:** JSON format. For more information, refer to [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api) and [Upload Events API](https://developer.clevertap.com/docs/upload-events-api)

### What is a manifest file, and is it mandatory for SFTP imports?

Yes. A manifest file is mandatory for every SFTP import. It is a JSON file that maps the columns in your CSV file to CleverTap properties. The format is _anyfilename.manifest_.

The following are the key points to remember:

* Every manifest file must have a unique name.
* Data file processing starts only after the corresponding manifest file is uploaded.
* The manifest file specifies the data type, CleverTap property name, and date format (if applicable) for each column.
* Uploading a CSV without its manifest file will result in an error.

For sample manifest files, refer to [SFTP Import – Sample Manifest Files](https://docs.clevertap.com/docs/imports-via-sftp#sample-manifest-file-for-upload).

### How can the status of my imports be monitored?

CleverTap provides multiple ways to track import status:

* **SFTP:** Go to _Settings_ > _Import_ > _Activity Log_ to view uploaded files and their status. You will also receive email notifications at key milestones such as _file pickup, processing, success, or failure_. You can also configure webhooks for notifications.
* **Data Warehouse:** Go to _Settings_ > _Partners_ > _Import_ > _Import Connections_ to view import run history and stats. For more information, refer to [Import Listing and Stats](https://docs.clevertap.com/docs/import-listing-and-stats#stats). You will also receive email and CleverTap Dashboard notifications at key milestones such as _Import Start, Import Completed with success, or Import Completed with failure_.
* **CSV Upload:** Go to _Settings_ > _Engage_ > _CSV Uploads_. The status for CSV upload is shown as _Completed, Processing, Rejected_, and _Start Mapping_. You will also receive email notifications at key milestones such as file processing, success, or failure.

When an import fails, you receive a failure email with a CSV attachment containing details of the failed records and error reasons for SFTP and CSV upload.

### How do I troubleshoot failed imports?

When an import fails, perform the following steps:

* **Check email notifications:** Failed imports trigger an email with a CSV attachment listing the failed records and error descriptions in the last column for SFTP and CSV upload. For Data Warehouse import, an email with the failed count and a link to the _Stats_ page gets triggered. You can also go to _Settings_ > _Partners_ > _Import_ > _Import Connections_ to view detailed import stats. For more information, refer to [Import Listing and Stats](https://docs.clevertap.com/docs/import-listing-and-stats#stats).
* **Review the Activity Log:** For SFTP, go to _Settings > Import > Activity Log_. For the Data Warehouse, check the Import Run Details under Import Connections.
* **Common errors include:** missing or invalid Identity/objectId, incorrect data types, malformed manifest file, timestamps outside the DRP window, file format issues, and column header mismatches. For the data warehouse, check permissions/access.
* **Error Stream:** Use the [Error Stream feature](https://docs.clevertap.com/docs/error-stream) (accessible from the main menu) to view ingestion errors over a specified time period.
* **Validate first:** Always test a sample dataset in your test account before running a full production import.

### Can I schedule recurring imports from a Data Warehouse?

Yes. CleverTap supports both one-time and recurring scheduled imports from your data warehouse. You can configure the import frequency (for example, daily, weekly, or custom intervals) during the scheduling step. For more information, refer to [Schedule Import](https://docs.clevertap.com/docs/schedule-import).

For SFTP, you can also automate recurring imports by writing a script that connects to CleverTap SFTP and transfers data at defined intervals.

### Can I import encrypted files to CleverTap?

Yes. CleverTap supports PGP encryption for secure SFTP file uploads. With File Upload Encryption, your data files are encrypted before transfer and decrypted securely within CleverTap’s environment.

The following key points to remember:

* Supports CSV.ASC file formats.
* Encrypted files must be under 1 GB. Split larger files before uploading.
* You can generate PGP key pairs either self-generated or via CleverTap.
* Each encrypted file must be accompanied by a manifest file that includes the Key ID.

For more information, refer to [File Upload Encryption](https://docs.clevertap.com/docs/file-upload-encryption).

### How does CleverTap handle duplicate events during import?

CleverTap does not perform automatic deduplication for imported events. If the same event with the same timestamp and properties is uploaded multiple times, it will be recorded as separate event entries. You must manage duplicate detection and handling externally before importing.

For user profiles, if an existing profile with the same Identity is uploaded again, the old profile is updated with the new values (upsert behavior).

### What happens if I upload events for users that do not exist in CleverTap?

If events are uploaded for users whose profiles do not yet exist in CleverTap, the system creates an anonymous user or one with the provided identity. This can lead to fragmented user data and inaccurate lifecycle computation. To avoid this, always upload user profiles before uploading events.

For more information on identity resolution and profile merging, refer to [How Profiles Merge](https://docs.clevertap.com/docs/how-profiles-merge).

### Can I import event data via CSV upload?

No. Currently, the CSV Upload feature (_Settings_ > _Engage_ > _CSV Uploads_) supports user profiles only. To import events, use SFTP Import, Data Warehouse Import, or the Upload Events API.

### What happens if I upload data with an incorrect data type for an attribute?

CleverTap validates data types during ingestion. If a value does not match the expected data type for a property (as defined in the schema or manifest file), the record may fail and appear in the error report.

To avoid this failure:

* Ensure numeric fields contain numbers, date fields contain valid dates, and string fields do not exceed the character limit.
* Use the manifest file (for SFTP) or column mapping (for CSV Upload and Data Warehouse Import) to explicitly define data types for each field.
* Review your property definitions under [Schema](https://docs.clevertap.com/docs/schema) to confirm expected data types before importing.

### What character encoding should my import files use?

All CSV files uploaded to CleverTap via SFTP, CSV Upload, or encrypted file upload must use UTF-8 encoding. Files saved in other encodings, such as Latin-1 or Windows-1252, may cause data corruption, especially with non-English characters.

<Callout icon="📘" theme="info">
  #### Best Practice

  When saving CSV files from Excel, select `CSV UTF-8 (Comma delimited)` as the file format.
</Callout>

### What are the rate limits or batch size restrictions for API-based imports?

Yes. When using the Upload User Profiles API or Upload Events API:

* Maximum of 1,000 objects per request with a 4 MB payload limit.
* Use the **dryRun** parameter (`?dryRun=1`) to validate payloads without ingesting data.

For SFTP imports, files up to 5 GB are supported. For CSV upload via the dashboard, the maximum file size is 1 GB.

### How do I troubleshoot a Data Warehouse import connection failure?

If your Data Warehouse connection or test connection fails, check the following:

* **IP Whitelisting:** Ensure [CleverTap’s IP ranges](doc:import-faqs#how-can-i-whitelist-ips-for-clevertap-integration) are allowlisted in your warehouse’s firewall/network rules.
* **Credentials:** Verify that the service account, username, password, or key file used in the connection setup has the correct read permissions on the source table/view.
* **Table/View access:** Confirm that the table or view referenced in your import configuration exists and is accessible by the configured service account.
* **Network/VPN:** If your warehouse is behind a VPN or private network, ensure the necessary routing is in place.

For detailed setup instructions for each warehouse, refer to [Set Up Import](https://docs.clevertap.com/docs/create-import).

### Are there any naming conventions or limits for custom attributes?

Yes. When importing data with custom user properties or event properties, ensure the following points are taken into consideration:

* Property names should be descriptive and consistent across all import methods (API, SFTP, Data Warehouse).
* Avoid using reserved system property names as custom property names.
* Once a property name and data type are set in CleverTap, they cannot be changed. Plan your schema carefully before the first import.
* Event names are case-sensitive.

For best practices on naming conventions of user and event properties, refer to [Schema](https://docs.clevertap.com/docs/schema).

<br />