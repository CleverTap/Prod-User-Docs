---
title: Google Cloud Platform (GCP)
excerpt: >-
  Understand how to integrate CleverTap dashboard to Google Cloud Platform
  (GCP).
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Google Cloud Storage (GCS) integration connects CleverTap to a bucket that you own, so you can move user and event data in both directions. With the integration, you can:

- Import user profiles and events from CSV or Parquet files stored in your GCS bucket.
- Export profile and event data to your GCS bucket for analysis in BI tools or storage in a data warehouse.

<Callout icon="📘" theme="info">
  ### Note

  CleverTap supports IP whitelisting for Google Cloud Storage connections. CleverTap connects from fixed IP ranges, and the ranges for import and export differ. For the ranges to allow, refer to the [FAQs](#faqs).
</Callout>

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Set Up Google Cloud Storage for Integration](#set-up-google-cloud-storage-for-integration)
- [Configure Google Cloud Storage in CleverTap](#configure-google-cloud-storage-in-clevertap)
- [Verify Integration](#verify-integration)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

<Accordion title="Quick Start Guide for Existing Users">
  If you previously configured a Google Cloud service account and bucket and you know the CleverTap dashboard, the setup requires the following details and steps.

  Have the following details ready:

  - The GCS bucket name, which you enter as _Folder_ on the CleverTap dashboard
  - (Import only, optional) The subfolder path within the bucket
  - The Service Account Key (JSON) of a service account that has the required role on the bucket:
    - Import: **Storage Object Viewer** (`roles/storage.objectViewer`)
    - Export: **Storage Legacy Bucket Writer** (`roles/storage.legacyBucketWriter`), or a custom role with `storage.buckets.get`, `storage.objects.create`, and `storage.objects.list`

  Then configure the connection:

  1. Go to _Settings > Partners_ and select **Google Cloud** on the **Integrations** tab.
  2. Select the **Import Connections** or **Export Connections** tab, and then click **Add Google Cloud Bucket**.
  3. Enter the _Connection name_ and the _Folder_ (your bucket name). For an import connection, optionally enter a _Subfolder_.
  4. Under _Google Service Account Key_, select **Upload JSON file** and upload your downloaded key, or select **Custom key** and paste the key contents.
  5. For import, click **Test Connection** and then **Save**. For export, click **Save**.

  After you save the connection, continue with [Next Steps](#next-steps).
</Accordion>

## Prerequisites for Integration

Before you set up the integration, ensure that the required Google Cloud permissions, CleverTap access, and bucket name are available.

- An active Google Cloud account with a project, and permissions in that project to create service accounts and keys, create buckets, and grant IAM roles on buckets. The **Service Account Admin**, **Service Account Key Admin**, and **Storage Admin** roles on the project together cover these actions. If you plan to create a custom role for export, you also need **Role Administrator** (`roles/iam.roleAdmin`) on the project.
- Permission to create service account keys. Google Cloud organizations created on or after May 3, 2024 enforce the _Disable service account key creation_ organization policy (`constraints/iam.managed.disableServiceAccountKeyCreation`) by default. If your organization enforces this policy, an Organization Policy Administrator must exempt your project before you can create the key in [Create Service Account Key](#create-service-account-key). For more information, refer to Google Cloud's [Manage Google Cloud security baseline constraints](https://cloud.google.com/resource-manager/docs/secure-by-default-organizations) documentation.
- A CleverTap account with the Google Cloud partner enabled. To enable the feature for your account, contact your CleverTap account manager.
- A globally unique bucket name that follows the bucket naming rules in [Create Bucket](#create-bucket)
- The CleverTap IP ranges to allow, if your organization restricts access to Cloud Storage by source IP. For more information, refer to the [FAQs](#faqs).

### Review Authentication Method

CleverTap authenticates to Google Cloud Storage with a Service Account Key, the only supported method for both import and export connections, and CleverTap does not support Workload Identity Federation.

| Method                  | Import | Export | What you create on Google Cloud                                                                             | Credentials stored in CleverTap | Role to grant on the bucket                                                                                                                                                                                          |
| ----------------------- | ------ | ------ | ----------------------------------------------------------------------------------------------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Service Account Key** | Yes    | Yes    | A service account, an IAM role grant on the bucket for that service account, and a JSON key for the account | Service Account Key (JSON)      | Import: **Storage Object Viewer**<br />Export: **Storage Legacy Bucket Writer**, or a custom role. For more information, refer to [Grant Service Account Access to Bucket](#grant-service-account-access-to-bucket). |

## Set Up Google Cloud Storage for Integration

Setting up Google Cloud Storage for the integration involves creating a service account and a bucket, granting the service account access to the bucket, and creating a Service Account Key. If you already have a service account and bucket, skip to [Grant Service Account Access to Bucket](#grant-service-account-access-to-bucket).

### Create Service Account

The service account is the identity that CleverTap uses to read files from or write files to your bucket.

1. Log in to the Google Cloud console and select the project for your bucket. If you do not have a project, create a new one.

2. From the navigation menu, select _IAM & Admin > Service Accounts_.

3. Click **Create service account**.


   <Image src="https://files.readme.io/fb49ce9-Screenshot_2020-04-06_at_3.57.40_PM.png" align="center" caption="Create Service Account" border={true} />


4. Under _Service account details_, enter a _Service account name_ (for example, `clevertap-storage`) and a description. The console generates the _Service account ID_ from the name.

5. Click **Create and continue**.

6. (Optional) Under _Grant this service account access to project_, leave the role empty. You grant the role on the bucket in [Grant Service Account Access to Bucket](#grant-service-account-access-to-bucket), which limits CleverTap to that one bucket. If your organization requires project-level grants instead, select the role here, using the table in that section.

7. Click **Continue**, leave _Grant users access to this service account_ empty, and click **Done**.

8. Note the service account email, which uses the following format. You need the email to grant access to the bucket.

   ```text
   <service-account-id>@<project-id>.iam.gserviceaccount.com
   ```

For more information, refer to Google Cloud's [Create service accounts](https://cloud.google.com/iam/docs/service-accounts-create) documentation.

### Create Bucket

A general-purpose bucket stores the files that CleverTap reads or writes.

1. From the navigation menu, select _Cloud Storage > Buckets_.

2. Click **Create**.


   <Image src="https://files.readme.io/8d026fe-Screenshot_2020-04-06_at_4.12.33_PM.png" align="center" caption="Create Bucket" border={true} />


3. Under _Name your bucket_, enter the bucket name that you specify under _Folder_ on the CleverTap dashboard, and click **Continue**.

   <Callout icon="📘" theme="info">
     ### Note

     Bucket names must be 3 to 63 characters, contain only lowercase letters, numbers, dashes (-), underscores (\_), and dots (.), and begin and end with a letter or number. Bucket names must be unique across all Google Cloud projects globally. For more information, refer to Google Cloud's [bucket naming guidelines](https://cloud.google.com/storage/docs/buckets#naming).
   </Callout>


   <Image src="https://files.readme.io/c696063-Screenshot_2020-04-06_at_4.14.53_PM.png" align="center" caption="Name Your Bucket" border={true} />


4. Under _Choose where to store your data_, select any location type and location, and click **Continue**. CleverTap does not require a specific bucket location.

5. Under _Choose a storage class for your data_, keep **Standard** and click **Continue**. Import connections read files on every import run, and colder storage classes add retrieval costs and latency.

6. Under _Choose how to control access to objects_, keep **Enforce public access prevention on this bucket** selected, keep **Uniform** access control, and click **Continue**. CleverTap does not use object ACLs.

7. Under _Choose how to protect object data_, keep the default soft delete policy and keep object versioning and retention policy off. Under _Data encryption_, keep **Google-managed encryption key**. If your organization requires a customer-managed encryption key, refer to the [FAQs](#faqs) before you select it.

8. Click **Create**.

9. Note the bucket name. You enter it during the CleverTap configuration.

For more information, refer to Google Cloud's [Create a bucket](https://cloud.google.com/storage/docs/creating-buckets) documentation.

<Callout icon="🚧" theme="warn">
  ### Caution

  Do not enable a _Retention policy_ on a bucket that you use for export. CleverTap writes export files in chunks, and a retention policy causes uploads to fail with `403: retentionPolicyNotMet`. You cannot remove a locked retention policy, so you must create a new bucket. For more information, refer to Google Cloud's [Use and lock retention policies](https://cloud.google.com/storage/docs/using-bucket-lock) documentation.
</Callout>

### Create Folder for Import

For an import connection, you can optionally create a folder so that CleverTap reads only from a specific path within the bucket.

<Callout icon="📘" theme="info">
  ### Note

  For an export connection, you set the folder path when you create the export job, and Cloud Storage creates the path when CleverTap writes the first file, so you do not need to create a folder in advance.
</Callout>

1. Select your bucket from the _Buckets_ list.

2. Click **Create folder**.

3. Enter a folder name and click **Create**.

4. Note the folder name. You enter it in the _Subfolder_ field on the CleverTap dashboard.

For more information, refer to Google Cloud's [Folders overview](https://docs.cloud.google.com/storage/docs/objects#namespace) documentation.

### Grant Service Account Access to Bucket

Granting the service account a role on the bucket lets CleverTap read files (import) or write files (export), and it limits CleverTap's access to that one bucket.

CleverTap uses the following Cloud Storage permissions:

| Permission               | Import     | Export      |
| ------------------------ | ---------- | ----------- |
| `storage.objects.list`   | Required   | Recommended |
| `storage.objects.get`    | Required   | Not needed  |
| `storage.objects.create` | Not needed | Required    |
| `storage.buckets.get`    | Not needed | Required    |

Grant the role that matches your connection type:

| Connection type              | Role to grant on the bucket                                                                             | Permissions included                                                                              | Notes                                                                                                                                                                                                                                       |
| ---------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Import**                   | **Storage Object Viewer** (`roles/storage.objectViewer`)                                                | `storage.objects.get`, `storage.objects.list`                                                     | Includes exactly the permissions that import requires.                                                                                                                                                                                      |
| **Export** (recommended)     | **Storage Legacy Bucket Writer** (`roles/storage.legacyBucketWriter`)                                   | `storage.buckets.get`, `storage.objects.list`, `storage.objects.create`, `storage.objects.delete` | The smallest predefined role that includes both `storage.buckets.get` and `storage.objects.create`. It also includes `storage.objects.delete`, which CleverTap does not use. You can grant legacy roles only on a bucket, not on a project. |
| **Export** (least privilege) | A custom role that contains `storage.buckets.get`, `storage.objects.create`, and `storage.objects.list` | Only the listed permissions                                                                       | Use this role when your security policy does not permit the extra `storage.objects.delete` permission. For more information, refer to [Create Custom Role for Export](#create-custom-role-for-export).                                      |

<Callout icon="🚧" theme="warn">
  ### Important

  - **Storage Object Creator** is not sufficient for export. It does not include `storage.buckets.get`, so the export connection fails with a 403 error when you click **Save**.
  - Do not grant **Storage Admin** to the service account. The role includes `storage.buckets.*` and `storage.objects.*`, and when you grant it at the project level, it lets the key holder delete or change the IAM policy on every bucket in the project. CleverTap never requires it.
</Callout>

1. From the navigation menu, select _Cloud Storage > Buckets_ and select your bucket.

2. Select the **Permissions** tab.

3. Click **Grant access**.

4. Under _Add principals_, paste the service account email that you noted in [Create Service Account](#create-service-account).

5. Under _Assign roles_, select **Storage Object Viewer** for an import connection, or **Storage Legacy Bucket Writer** (or your custom role) for an export connection. If you use the same bucket for both import and export, add both roles.

6. Click **Save**.


   <Image src="https://files.readme.io/dae6adc67f34ec6ff7699e0d1eb139796138ec38080a006582776d7f0f0e723e-Screenshot_2026-10-06_at_8.24.18_PM.png" align="center" caption="Grant Access" border={true} />


For more information, refer to Google Cloud's [Set and manage IAM policies on buckets](https://cloud.google.com/storage/docs/access-control/using-iam-permissions) and [IAM roles for Cloud Storage](https://cloud.google.com/storage/docs/access-control/iam-roles) documentation.

### Create Custom Role for Export

A custom role gives the service account only the permissions that CleverTap uses for export, which matters when your security policy does not permit the `storage.objects.delete` permission in **Storage Legacy Bucket Writer**. Creating a custom role requires the **Role Administrator** (`roles/iam.roleAdmin`) role on the project.

1. From the navigation menu, select _IAM & Admin > Roles_.

2. Select your project from the dropdown at the top of the page.

3. Click **Create custom role**.

4. Enter a _Title_ (for example, `CleverTap Export Writer`), a _Description_, and an _ID_. Keep the _Role launch stage_ as **General Availability**.

5. Click **Add permissions**.

6. In the _Filter_ box, enter each of the following permissions, select the permission, and click **Add**:
   - `storage.buckets.get`
   - `storage.objects.create`
   - `storage.objects.list`

7. Click **Create**.

The custom role now appears under _Assign roles_ when you grant access on the bucket. For more information, refer to Google Cloud's [Create and manage custom roles](https://cloud.google.com/iam/docs/creating-custom-roles) documentation.

### Create Service Account Key

The Service Account Key is the credential that you provide to CleverTap.

1. From the navigation menu, select _IAM & Admin > Service Accounts_.

2. Click the email address of the service account that you created.

3. Select the **Keys** tab.

4. Click **Add key** and select **Create new key**.

5. Under _Key type_, keep **JSON** and click **Create**. The JSON key file downloads to your machine automatically.


   <Image src="https://files.readme.io/e5bc98b-Screenshot_2020-04-06_at_4.04.32_PM.png" align="center" caption="Create Service Account Key" border={true} />


For more information, refer to Google Cloud's [Create and delete service account keys](https://cloud.google.com/iam/docs/keys-create-delete) documentation.

<Callout icon="📘" theme="info">
  ### Security Best Practice

  Save the downloaded JSON key securely, because Google Cloud does not let you download it again. If you believe the key has leaked, delete it from the _Keys_ tab, create a new one, and update the connection on the CleverTap dashboard.
</Callout>

<Callout icon="🚧" theme="warn">
  ### Key Creation Disabled

  If **Create new key** is unavailable or Google Cloud shows "Service account key creation is disabled," your organization enforces the `iam.managed.disableServiceAccountKeyCreation` policy. Ask an Organization Policy Administrator to add an exception for your project under _IAM & Admin > Organization Policies > Disable service account key creation_, and then repeat these steps. For more information, refer to the _Allow service account key creation_ section of Google Cloud's [Create and delete service account keys](https://cloud.google.com/iam/docs/keys-create-delete) documentation.
</Callout>

## Configure Google Cloud Storage in CleverTap

The CleverTap dashboard needs the bucket details and the Service Account Key to complete the connection.

### Add Bucket on CleverTap Dashboard

Adding the bucket registers the bucket name, the optional subfolder, and the Service Account Key for the connection.

1. On the CleverTap dashboard, go to _Settings > Partners_ and select **Google Cloud** on the **Integrations** tab.

2. Select the connection type:
   - For import, select the **Import Connections** tab.
   - For export, select the **Export Connections** tab.

3. Click **Add Google Cloud Bucket**.

4. Under _Bucket Details_, enter the details in the following table:

   | Field                        | Import | Export | Description                                                                                                                                                                                                                                        |
   | ---------------------------- | ------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | _Connection name_            | Yes    | Yes    | A unique name that identifies this connection in CleverTap, for example, `events-prod-gcp`.                                                                                                                                                        |
   | _Folder_                     | Yes    | Yes    | Required. The name of the GCS bucket. The name must match your bucket name in Google Cloud exactly, for example, `product_integration`.                                                                                                            |
   | _Subfolder_                  | Yes    | No     | Optional. A path within the bucket if your import files are in a subdirectory, for example, `file_based`. CleverTap reads only from this path. For export, you set the folder path when you create the export job.                                 |
   | _Preview_                    | Yes    | Yes    | Displays the resulting path that CleverTap uses: `gs://<folder>/<subfolder>` for import and `gs://<folder>` for export. Verify the path before you proceed.                                                                                        |
   | _Google Service Account Key_ | Yes    | Yes    | Required. Select **Upload JSON file** to upload your downloaded Service Account Key file (1 MB maximum, JSON only), or select **Custom key** to paste the key contents instead. Paste the complete file, including the opening and closing braces. |

   <Callout icon="📘" theme="info">
     ### Field Mapping

     The CleverTap dashboard does not have a separate field labeled "Bucket name." The _Folder_ field identifies your bucket, so enter your bucket name there, for example, `product_integration`. For import connections, use _Subfolder_ only if CleverTap should read from a directory nested inside that bucket.
   </Callout>


   <Image src="https://files.readme.io/a424fa5d1774394ddf4b87a6be53863010a8f16f22c1cc906f59109e420e1692-Screenshot_2026-10-08_at_3.51.04_PM.png" align="center" caption="Google Cloud Bucket Details" border={true} />


## Verify Integration

CleverTap verifies the connection when you test or save it, and the verification method depends on the connection type.

- **Import**: Click **Test Connection**. CleverTap lists the bucket, and the subfolder if you entered one, using the Service Account Key. When the test succeeds, click **Save**.
- **Export**: Click **Save**. CleverTap uploads a test file to the bucket that you specified, and it saves the connection only if the upload succeeds.

If the test or save fails, refer to the [FAQs](#faqs).

## FAQs

### What permissions does CleverTap need?

For import, CleverTap needs read access on the bucket: `storage.objects.get` and `storage.objects.list`, both of which **Storage Object Viewer** includes. For export, CleverTap needs `storage.objects.create` and `storage.buckets.get` on the bucket, and `storage.objects.list` is recommended. **Storage Legacy Bucket Writer** includes all three, or you can create a custom role with exactly those permissions. CleverTap never requires **Storage Admin**.

### Can I use one connection for both import and export?

No. You configure import and export connections separately under _Import Connections_ and _Export Connections_. You can point both connections at the same bucket, and you grant the service account both roles on that bucket.

### Does the bucket have to be in a specific location?

No. Any Google Cloud location type and location works.

### How can I limit which files CleverTap reads from my bucket?

Use the _Subfolder_ field on the import connection to point CleverTap to a specific directory within your bucket. CleverTap reads only from that path. For stricter isolation, create a dedicated bucket for CleverTap and grant the service account a role on that bucket only.

### How do I whitelist CleverTap's IP addresses for my bucket?

CleverTap connects to Google Cloud Storage from fixed IP ranges. If your organization restricts access to Cloud Storage by source IP, for example, through a VPC Service Controls access level, allow the ranges for the connection type that you use. The import and export ranges differ:

- **Export**: Refer to [CleverTap IP Ranges](https://developer.clevertap.com/docs/clevertap-ip-ranges#ip-ranges).
- **Import**: Refer to [How can I whitelist IPs for CleverTap integration?](https://docs.clevertap.com/docs/import-faqs#how-can-i-whitelist-ips-for-clevertap-integration) in the Import FAQs.

IP whitelisting does not replace the IAM role grant. The service account still needs the role described in [Grant Service Account Access to Bucket](#grant-service-account-access-to-bucket).

### What happens if I delete or rotate my Service Account Key in Google Cloud?

Imports and exports that use the connection fail. For export, CleverTap also emails the export creator with the error "Credentials are incorrect, GCP account is forbidden" (403). Create a new JSON key in Google Cloud, go to _Settings > Partners > Google Cloud_, and edit the connection on the relevant tab. Upload the new JSON file or paste the new key under **Custom key**. For import, click **Test Connection** and then **Save**. For export, click **Save**. Confirm that the service account still has the role on the bucket.

### How does CleverTap notify me when an export stops?

CleverTap checks exports for failures every hour. If an error occurs, CleverTap sends three emails to the export creator within three days. The first two emails include the error details and a link to fix the problem, and they warn that the export stops if you do not fix the problem within three days. The third email notifies the export creator that CleverTap stopped the export.

### Why does Google Cloud show "Service account key creation is disabled"?

Your organization enforces the `iam.managed.disableServiceAccountKeyCreation` policy, which is the default for organizations created on or after May 3, 2024. Ask an Organization Policy Administrator to exempt the project, and then create the key again. For more information, refer to [Create Service Account Key](#create-service-account-key).

### Why does Google Cloud show "The requested bucket name is not available"?

GCS bucket names are unique across all Google Cloud projects, so another project already uses the name. Choose another name, for example, by appending your company name or project ID. Then enter the final name in the _Folder_ field on the CleverTap dashboard.

### Why does Test Connection fail for an import connection?

The _Folder_ does not match the bucket name, the _Subfolder_ does not exist, the service account lacks `storage.objects.list` or `storage.objects.get`, or the key is incomplete or someone deleted it. Confirm that _Folder_ matches the bucket name exactly (the match is case-sensitive), confirm that the subfolder exists, confirm that the service account has **Storage Object Viewer** on the bucket, and confirm that the uploaded JSON is under 1 MB and still appears on the _Keys_ tab.

### Why does Save fail with a 403 error for an export connection when the service account has Storage Object Creator?

**Storage Object Creator** does not include `storage.buckets.get`, which CleverTap requires to verify the bucket before it uploads. Replace the role with **Storage Legacy Bucket Writer**, or grant a custom role that includes `storage.buckets.get`, `storage.objects.create`, and `storage.objects.list`. For more information, refer to [Grant Service Account Access to Bucket](#grant-service-account-access-to-bucket).

### Why does Save fail for an export connection when CleverTap cannot upload the test file?

The _Folder_ does not match the bucket name, the service account lacks `storage.objects.create` or `storage.buckets.get`, the bucket has a retention policy, or your organization blocks the export IP ranges of CleverTap. Confirm that _Folder_ matches exactly, confirm the role on the bucket, check the _Protection_ tab of the bucket for a retention policy, and confirm that your organization allows the export IP ranges if it restricts access by IP. For more information, refer to [How do I whitelist CleverTap's IP addresses for my bucket?](#how-do-i-whitelist-clevertaps-ip-addresses-for-my-bucket).

### Why does an export fail with 403: retentionPolicyNotMet?

A retention policy is active on the bucket, so CleverTap cannot write or replace files. To remove the policy:

1. Open the Google Cloud console and go to _Cloud Storage > Buckets_.
2. Select the bucket.
3. Go to the **Protection** tab.
4. In the _Retention policy (for compliance)_ section, click the **Delete** icon.

If the **Delete** icon is disabled, someone locked the policy, and you cannot remove it. In that case, create a new bucket without a retention policy and update the connection.

### Why does an import run but read no files?

The _Subfolder_ points to a path that contains no CSV or Parquet files, the files are in a different folder, or your organization blocks the import IP ranges of CleverTap. Verify that the path under _Preview_ matches the location where your pipeline writes the files. If your organization restricts access by IP, confirm that it allows the import IP ranges. For more information, refer to [How do I whitelist CleverTap's IP addresses for my bucket?](#how-do-i-whitelist-clevertaps-ip-addresses-for-my-bucket).

## Next Steps

After you configure the connection, you can create imports and exports that use it.

- Create an import that reads from this connection. For more information, refer to [Create Import](doc:create-file-based-import), [Map Data for Import](doc:map-data-for-file-based-import), and [Schedule Import](doc:schedule-file-based-import).
- Create an export that writes to this connection. For more information, refer to [Events Exports](doc:event-exports) or [Profile Exports](doc:profile-exports).
