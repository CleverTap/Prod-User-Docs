---
title: Google Cloud Platform (GCP)
excerpt: Data Warehousing and Analytics Platform
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

The GCP Export feature enables you to bulk export your CleverTap event or profile data to a GCP bucket. You can export your CleverTap data to analyze it with Business Intelligence (BI) tools or store it in your data warehouse for future analysis.

> 📘 Feature Availability
>
> This capability is a part of the *Enterprise*, *Advanced*, and *Cutting Edge* plan. To activate this for your account, contact your Account Manager.

# Integrate GCP with CleverTap

The integration involves the following steps:

1. [Create a Service Account for your Project](doc:data-export-to-gcp#create-a-service-account-for-your-project).
2. [Create a Bucket](doc:data-export-to-gcp#create-a-bucket).
3. [Configure CleverTap Dashboard](doc:data-export-to-gcp#configure-clevertap-dashboard).

> 📘 Data Export
>
> Once you have set up both dashboards, you can configure export from the CleverTap dashboard. For more information, refer to the following: 
>
> * [Data Exports](doc:data-exports) for Legacy Profile and Event Export flow
> * [Profile Exports](doc:profile-exports) for Enhanced Profile Export flow

## Create a Service Account for your Project

To create a service account, perform the following steps:

1. Log in to your GCP account and select the project where you want to export your CleverTap data. Create a new project if you do not already have one.
2. From the left panel, select *IAM* and then navigate to *Admin* > *Service Accounts*. 
3. Create a new *Service Account* linked to the selected project and enter the Service account name and description, respectively.\
   This is the account that you will use to *authenticate* and *authorize* CleverTap to upload exports to your GCP project.

<Image title="Enter Service Account Details and click Create" alt={2880} align="center" border={true} src="https://files.readme.io/fb49ce9-Screenshot_2020-04-06_at_3.57.40_PM.png">
  Create a New Service Account
</Image>

2. Navigate to *Permissions* > *Storage Admin and continue*.

<Image title="Navigate to Storage Admin from Google Cloud" alt={2880} align="center" border={true} src="https://files.readme.io/b14f47c-Screenshot_2020-04-06_at_3.58.36_PM.png">
  Navigate to Storage Admin
</Image>

3. Click **+ Create Key** and select JSON for the Service account.\
   The JSON key downloads to your machine automatically. Save this key, as you will need to upload it to the CleverTap dashboard later.

<Image title="Create a key and select JSON format for Service Account" alt={2880} align="center" border={true} src="https://files.readme.io/e5bc98b-Screenshot_2020-04-06_at_4.04.32_PM.png">
  Create Key
</Image>

## Create a Bucket

Create a bucket to store the export files from CleverTap. To do so, perform the following steps:

1. From the left navigation, go to *Storage* and click **Create Bucket**.

<Image title="Navigate to Storage Browser from Google Cloud dashboard" alt={2280} align="center" border={true} src="https://files.readme.io/8d026fe-Screenshot_2020-04-06_at_4.12.33_PM.png">
  Navigate to Storage Browser from GCP Dashboard
</Image>

On clicking, *Create a bucket* page opens.

2. *Name your bucket* and fill in the other details as per your requirements.

<Image title="Enter your bucket details and create a bucket" alt={2880} align="center" border={true} src="https://files.readme.io/c696063-Screenshot_2020-04-06_at_4.14.53_PM.png">
  Enter your Bucket Details and Create a Bucket
</Image>

3. Click **Create**. Following is an image for a successfully created bucket:

<Image title="Bucket created successfully on Google Cloud" alt={2880} align="center" border={true} src="https://files.readme.io/fd5d73b-Screenshot_2020-04-06_at_4.16.03_PM.png">
  Bucket Created Successfully
</Image>

## Configure CleverTap Dashboard

Add the Service account credentials (created in [Step 1](doc:data-export-to-gcp#create-a-service-account-for-your-project) and bucket name to CleverTap. To configure the dashboard:

1. Go to *Settings* > *Partners* > *Integrations* from the CleverTap dashboard. 

<Image title="Navigating to Partner page from the CleverTap dashboard" alt={2848} align="center" width="90% " border={true} src="https://files.readme.io/1e53dc52cbe396c18b283d8ad85bf016c35dc817255901b3778e8c905cedaa70-Navigating_to_Partners_Page.png">
  Navigating to Partners
</Image>

2. Select the *Google Cloud* partner. The *Integrate analytics partner - Google Cloud* window opens on the right side of the screen.
3. Click **+ Google Cloud Bucket** to add a bucket. You can also add multiple buckets from this popup.
4. Enter the following details and click **Save Credentials**:

| Field               | Description                                                                                                                                                                       |
| :------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Bucket nickname     | Enter the nickname for your bucket.                                                                                                                                               |
| Service Account Key | Enter the contents of the downloaded Service Account Key JSON file (obtained in [Step 1](doc:data-export-to-gcp#create-a-service-account-for-your-project)) into the Service Key. |
| Bucket name         | Add the name of the bucket as given in the project.                                                                                                                               |

<Image title="Enter Google Cloud bucket details and click Integrate" alt={2358} align="center" width="60% " border={true} src="https://files.readme.io/1e6eb6a-SaveBucket.jpg">
  Enter Google Cloud Bucket Details
</Image>

> 🚧 Error When Saving Credential
>
> 1. Check if the bucket name is the same as in GCP. Bucket names need to be an exact match.
> 2. Generate the Service Account key again, copy and paste the new key into the *Service Account Key* field on the *Integrate analytics partner - Google Cloud* window.

<Image title="Service Account Key generated" alt={2540} align="center" border={true} src="https://files.readme.io/b4b5b46-Screenshot_2020-04-06_at_4.44.59_PM.png">
  Service Account Key
</Image>

# FAQs

### How to secure the data exports from CleverTap to GCP?

You can whitelist IPs to ensure that CleverTap has access to push data only to your GCP bucket. To get the list of IP whitelisting, refer to the [IP Whitelisting](doc:ip-whitelisting) documentation.

### How to resolve a `403: retentionPolicyNotMet` error during data export to GCP?

A `403: retentionPolicyNotMet` error can occur when exporting data to GCP. It could be because of a locked retention policy. To resolve this error: 

1. Open the **GCP Console**.
2. Go to **Menu** > **Cloud Storage** > **Buckets**.
3. Select the required bucket.
4. Go to the **Protection** tab.
5. Check the **Retention policy (for compliance)** section. If any policy is active, the **Edit**, **Delete**, and **Lock** icons are enabled.
6. Click the **Delete** icon to delete the retention policy. If the Delete icon is not enabled, the retention policy is locked on the bucket. In this case, you have no option but to change the bucket to which CleverTap uploads export data.

### Do CleverTap data exports allow special characters?

Yes, CleverTap data exports allow the following special characters:

* Supports Unicode (UTF-8)  character encoding. It facilitates the accurate representation of text in various languages and scripts. For example, Indian regional languages, Arabic, Korean, Russian, Japanese, Chinese, Spanish, Greek, Indonesian, etc.
* Replaces the following characters with a hyphen to avoid issues in output file generation: Whitespace, Tab, Slash, and null (\\0).
* Replaces control characters with ?. For more information, refer to [Control Character](https://en.wikipedia.org/wiki/Control_character). 
* Supports emoji characters; however, some emojis (UTF-16) may not render properly.

### What customer-related errors can stop exports, and how are customers notified when interruptions occur?

Export processes can stop due to customer-related errors. For example, invalid/expired credentials or a missing partner bucket. CleverTap sends emails to customers about the issue to ensure a timely resolution. 

Here is the customer-related error that can stop a GCP export: 

| Error Code | Error Message                                        | Cause and Resolution                                                                                                                                                                                                                           |
| :--------- | :--------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 403        | Credentials are incorrect, GCP account is forbidden. | Your Service Account Key has expired or is invalid. There could be various reasons why your key is incorrect. Recheck all the steps, and you can refer to [Integrate GCP with CleverTap](doc:data-export-to-gcp#integrate-gcp-with-clevertap). |

Exports are checked every hour for failures. If an error occurs, CleverTap sends three emails to the export creator within three days. Emails 1 and 2 include the error details and a link to resolve the issue. It warns that the export will stop if the problem is not resolved within three days. The third email notifies the creator that CleverTap has stopped the export.
