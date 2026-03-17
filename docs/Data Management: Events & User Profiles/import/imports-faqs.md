---
title: 'Imports: FAQs'
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This document answers common questions about importing user data into CleverTap through APIs or SFTP, covering sequencing, data preparation, and best practices to ensure data integrity during historical imports.

### What is Historical Data Import in CleverTap?

Historical Data Import allows you to bring user profiles and past events from older systems into CleverTap using the [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api), [Upload Events API](https://developer.clevertap.com/docs/upload-events-api), or [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp).

### Can I import historical data for both profiles and events using SFTP?

Yes. SFTP Import supports uploading, User Profile files, and Event files. Refer to [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp).

### Do I need to upload user profiles before events?

Yes. CleverTap requires that user profiles be uploaded first, followed by historical events.  
This ensures correct identity stitching during ingestion. Learn more: [Upload User Profiles](https://developer.clevertap.com/docs/upload-user-profiles-api)

### What information should be included in user profile uploads?

User profile uploads should include: Name, Age, Email ID, Phone number, Custom tags, Additional profile attributes

You can upload these using:

* [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api)
* [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp)

### How should I upload historical events?

Once profiles are uploaded, you can send historical events—such as purchases or lifecycle actions—using:

* [Upload Events API](https://developer.clevertap.com/docs/upload-events-api)
* [Events SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp)

### In what order should I upload historical event data?

Always upload events **chronologically**, beginning with the **oldest data first** and progressing to the most recent.  
This ensures proper sequencing and accurate behavioral timelines. Learn more: [Upload User Events](https://developer.clevertap.com/docs/upload-events-api)

### Can I test historical uploads before sending them to Production?

Yes. CleverTap recommends testing with a **sample dataset** in your **Test Account** first.  
Your Test Account can be reset, while Production cannot delete or modify imported data.

### How does CleverTap handle timestamps on historical events?

Events that contain timestamps will appear in the CleverTap Dashboard based on the provided event time.  
Import eligibility depends on your account’s **Data Retention Policy (DRP)**.

### How can I delete a connection that has running imports?

Go to _Import Connections_, select the connection, click **Delete**, and review the running imports. If there are any imports in ready, scheduled, paused, or running state, it stops all these active imports associated with the connection. Once done, click **Delete** and confirm.

### How can I whitelist IPs for CleverTap integration?

To ensure seamless communication between CleverTap and your systems, whitelist the required IP ranges. To access the list of IPs to whitelist for import integrations, refer to [CleverTap IP Ranges](https://developer.clevertap.com/docs/clevertap-ip-ranges).

### How can I upload my historical data to CleverTap, or is there any easy way to migrate my data from different tools to CleverTap?

You can upload historical data to CleverTap using either APIs or SFTP, depending on your data volume and technical setup.

For programmatic imports, use:

* [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api)
* [Upload Events API](https://developer.clevertap.com/docs/upload-events-api)

For bulk migrations, especially when importing large datasets from legacy systems or data warehouses, use:

* [SFTP Import](https://docs.clevertap.com/docs/imports-via-sftp)

For large-scale migrations, SFTP is generally recommended. For incremental or controlled imports, APIs provide more flexibility.

### What are the recommendations while uploading historical data to CleverTap?

To ensure accurate ingestion and reporting, follow these best practices:

* Upload user profiles before uploading events
* Maintain consistent User Identifiers across profiles and events
* Upload events in chronological order (oldest first)
* Validate a sample dataset in your Test Account before Production import
* Ensure timestamps are sent in Unix epoch format (seconds)
* Confirm that imported data falls within your account’s Data Retention Policy
* Break large datasets into smaller batches where applicable

Following these practices helps ensure proper identity stitching and accurate lifecycle computation.

### While uploading historical data, how do you handle the event timestamp?

When uploading historical events, include the original event occurrence time in the payload.

* The timestamp must be provided in Unix epoch format (seconds).
* Events appear in dashboards and analytics based on the provided event time.
* If no timestamp is provided, CleverTap records the event at ingestion time.

Ensure that timestamps are sent in seconds and not milliseconds to avoid reporting discrepancies.

Refer to [Upload Events API](https://developer.clevertap.com/docs/upload-events-api)

### What information can I send while pushing user information?

When uploading user profiles, you can send standard and custom profile properties, including:

* Identity (unique user identifier)
* Name
* Email ID
* Phone number
* Age
* Gender
* Date properties (in Unix epoch seconds)
* Custom attributes (string, numeric, boolean, or date properties)
* Tags

Ensure that property names are consistent across uploads to prevent profile fragmentation.

Refer to [Upload User Profiles API](https://developer.clevertap.com/docs/upload-user-profiles-api)

### For data like date of birth, which date format does CleverTap support?

Date properties must be sent in Unix epoch format (seconds).

CleverTap converts the timestamp internally into a date value for segmentation and reporting.

Ensure the timestamp represents seconds and not milliseconds.

Refer to [Upload User Profiles API](doc:upload-user-profiles)

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

A valid User Identifier is required for importing historical data.

### Limitations while importing data to CleverTap?

When importing historical data, consider the following:

* Data imported into Production cannot be deleted or rolled back
* Events outside your Data Retention Policy window may not be available for analysis
* Profiles must exist before events are uploaded
* Large datasets may need to be uploaded in batches
* Duplicate event handling must be managed externally
* Timestamps must be provided in Unix epoch format (seconds)

It is recommended to validate all imports in a Test Account before proceeding to Production.

<br />
