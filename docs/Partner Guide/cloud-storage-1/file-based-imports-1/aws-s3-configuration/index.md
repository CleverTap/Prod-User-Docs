---
title: Amazon S3
excerpt: Understand how to connect your S3 bucket into CleverTap
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Amazon S3 integration connects CleverTap to a bucket that you own, so you can move user and event data in both directions. With the integration, you can:

- Import user profiles and events from files stored in your S3 bucket.
- Export profile and event data to your S3 bucket for analysis in BI tools or storage in a data warehouse.
- Encrypt exported data with your own AWS KMS key (SSE-KMS).

<Callout icon="📘" theme="info">
  ### Note

  - IAM Policy with SSE-KMS Encryption is available only for export connections. The import connection screen shows only Access Key and IAM Role.
  - CleverTap does not support IP whitelisting for S3 connections.
</Callout>

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Set Up Amazon S3 for Integration](#set-up-amazon-s3-for-integration)
- [Configure Amazon S3 in CleverTap](#configure-amazon-s3-in-clevertap)
- [Verify Integration](#verify-integration)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

## Prerequisites for Integration

Before you set up the integration, ensure that the required AWS permissions, CleverTap access, and bucket name are available.

- An active AWS account with permissions to create S3 buckets, plus permissions to create IAM policies and IAM users (Access Key) or KMS keys (SSE-KMS), depending on your method
- A CleverTap account with the Amazon S3 partner enabled
- A globally unique bucket name that follows the bucket naming rules in [Create S3 Bucket on AWS](#create-s3-bucket-on-aws)

### Choose Configuration Method

CleverTap supports three methods for granting access to your S3 bucket, and the method that you choose determines the AWS resources that you create.

| Method                                 | Import | Export | What you create on AWS                                                                                                    | Credentials stored in CleverTap | Recommended for                                                  |
| -------------------------------------- | ------ | ------ | ------------------------------------------------------------------------------------------------------------------------- | ------------------------------- | ---------------------------------------------------------------- |
| **IAM Role**                           | Yes    | Yes    | A CleverTap-generated bucket policy that grants CleverTap's AWS principal access to your bucket                           | None                            | Customers who prefer no long-term credentials to store or rotate |
| **Access Key**                         | Yes    | Yes    | An IAM policy, an IAM user, and an access key                                                                             | Access Key and Secret Key       | Customers whose security policy requires a dedicated IAM user    |
| **IAM Policy with SSE-KMS Encryption** | No     | Yes    | A customer-managed KMS key, a KMS key policy statement, an S3 bucket with SSE-KMS default encryption, and a bucket policy | KMS Key ARN                     | Customers who must encrypt exported data with their own KMS key  |

## Set Up Amazon S3 for Integration

Setting up Amazon S3 for the integration starts with a general-purpose S3 bucket in your AWS account. If you use IAM Policy with SSE-KMS Encryption, create the KMS key before step 9, because that step requires the key ARN. For more information, refer to [Create KMS Key on AWS](doc:iam-policy-with-sse-kms-encryption#create-kms-key-on-aws).

### Create S3 Bucket on AWS

The following steps create a general-purpose S3 bucket with the default settings that the integration uses.

1. Log in to your AWS console and search for _S3_ in the search bar.

2. Select **S3** from the search results.


   <Image src="https://files.readme.io/3cf847f09fe036c23254c9fbb05263e4bef75fe9b2213228231fb59a29103388-bucket_on_aws.png" align="center" caption="Create S3 Bucket" border={true} />


3. Click **Create bucket**.

4. Under _General configuration_, confirm that the _AWS Region_ matches the region that you select on the CleverTap dashboard. AWS preselects the region based on your current console region.


   <Image src="https://files.readme.io/da8eaa27c10edb81c723875682279f624ce530e54b0f804cabcc0434b698f17f-region_s3.png" align="center" caption="Create Bucket and Select Region" border={true} />


5. Under _Bucket name_, enter the bucket name that you specify under _Folder_ on the CleverTap dashboard.

   <Callout icon="📘" theme="info">
     ### Note

     Bucket names must be 3 to 63 characters, begin and end with a letter or number, and contain only lowercase letters, numbers, periods (.), and hyphens (-). Bucket names must be unique within the global namespace.
   </Callout>


   <Image src="https://files.readme.io/2d3c20f4a84d5e80927a9e2be9bf8106317576874d772af4c15fba4c2d604d92-Create_bucket.png" align="center" caption="General Configuration - AWS S3" border={true} />


6. Under _Object Ownership_, keep the default selection of **ACLs disabled (recommended)**.


   <Image src="https://files.readme.io/dad91a1c1a1aea80237205a3c0c66dfcb041ba60f14860b5899b8bc9694ed52b-object_ownership_-_s3.png" align="center" caption="Object Ownership - AWS S3" border={true} />


7. Under _Block Public Access settings for this bucket_, keep **Block all public access** selected.


   <Image src="https://files.readme.io/6a6247ce03f9731e2d39a306e415bbf30e0c04c7f43f0f1b499bf6d98cd84263-Block_public_access.png" align="center" caption="Block All Public Access - AWS S3" border={true} />


8. Under _Bucket Versioning_, keep the default selection of **Disable**.


   <Image src="https://files.readme.io/b28382cda36ab26b92c2b4e09fe1be0a4dc74cf7177703961562373506cd7aab-Bucket_versioning.png" align="center" caption="Bucket Versioning - AWS S3" border={true} />


9. Under _Default encryption_, select the encryption type that matches your configuration method:

   - **Access Key** or **IAM Role**: Keep the default selection of **Server-side encryption with Amazon S3 managed keys (SSE-S3)**.
   - **IAM Policy with SSE-KMS Encryption**: Select **Server-side encryption with AWS Key Management Service keys (SSE-KMS)**, select **Enter AWS KMS key ARN**, paste the KMS key ARN that you copied in [Create KMS Key on AWS](doc:iam-policy-with-sse-kms-encryption#create-kms-key-on-aws), and keep _Bucket Key_ set to **Enable**.


   <Image src="https://files.readme.io/ce5516130a658c7e6120b20e89b76cff0b3545f3542c1907cbdc6c3653e9c7e0-DEFAULT_ENCRYPTION.png" align="center" caption="Default Encryption" border={true} />


   <Callout icon="📘" theme="info">
     ### Note

     The integration works with the default settings. Check your organization's internal policies to determine whether any setting requires a change.
   </Callout>

10. Click **Create bucket**.

## Configure Amazon S3 in CleverTap

CleverTap uses the bucket details that you enter on the dashboard, in particular the _Folder_ value, to generate the policies for the IAM Role and SSE-KMS methods. Complete this section before the AWS policy steps.

### Add Bucket on CleverTap Dashboard

Adding the bucket registers the bucket name, region, and configuration method for the connection.

1. On the CleverTap dashboard, go to _Settings > Partners_ and select **Amazon S3** on the **Integrations** tab.


   <Image src="https://files.readme.io/b3f0ce305a6b5d740249c3d994f1d7f529c118e55c24171451edbe285df544c1-S3_Integration.png" align="center" caption="Select S3 Integration" border={true} />


2. Select the connection type:
   - For import, select the **Import Connections** tab.
   - For export, select the **Export Connections** tab.

3. Click **Add Amazon S3 Bucket**.


   <Image src="https://files.readme.io/8a603048aa4f23718a02d8ed7a96cd8d193be866355af72b557bf9462641b39d-add_amazon_s3_bucket.png" alt="The Connect to Amazon S3 for import or Connect to Amazon S3 for export page displays" align="center" caption="Add Amazon S3 Bucket" border={true} />



   <Image src="https://files.readme.io/55f170b5faa1381627916560866e752bf86c0a6412901154da3b88b422d19442-Bucket_details.png" align="center" caption="Bucket Details" border={true} />


4. Enter a value for _Bucket Nickname_.

5. Under _Bucket Information_, select the AWS _Region_ where you host your S3 bucket. The region must match the region of the bucket that you created on AWS. You can select any AWS region regardless of where CleverTap hosts your account, but for optimal performance, CleverTap recommends the region that corresponds to your CleverTap account.

6. Enter the bucket name under _Folder_. For more information, refer to [Enter Folder Name](#enter-folder-name).

7. (Optional, import only) Enter the path of the subfolder that contains your import files under _Subfolder_.

8. Under _Configure with_, select the method that you chose, and then complete the AWS steps in [Complete Configuration for Your Method](#complete-configuration-for-your-method).

<Callout icon="🚧" theme="warn">
  ### Caution

  Do not click **Save** or **Test Connection** yet. Both actions contact your bucket and fail until the AWS-side permissions are in place. Keep this page open, and return to it after you complete the method-specific steps. Clicking **Discard** shows a _Discard edits?_ confirmation and removes everything that you entered.
</Callout>

### Enter Folder Name

The _Folder_ field specifies the name of the S3 bucket on AWS from which CleverTap reads and to which CleverTap writes. The value that you enter must exactly match the bucket name on AWS. After you save the connection, the _Preview_ field displays the full S3 path in the following format, which you can use to verify the bucket URL:

```text
https://s3.<region>.amazonaws.com/<folder>
```

### Complete Configuration for Your Method

Each configuration method has its own document, and each document returns you to the CleverTap page that you left open.

- **Access Key**: Refer to [Access Key](doc:access-key).
- **IAM Role**: Refer to [IAM Role](doc:iam-role).
- **IAM Policy with SSE-KMS Encryption**: Refer to [IAM Policy with SSE-KMS Encryption](doc:iam-policy-with-sse-kms-encryption).

## Verify Integration

CleverTap verifies the connection when you test or save it, and the verification method depends on the connection type.

- **Import**: Click **Test Connection**. CleverTap attempts to list the bucket, and the subfolder if you entered one, with the configured method. When the test succeeds, click **Save**.
- **Export**: Click **Save**. CleverTap uploads a test file to the bucket and region that you specified, and it saves the connection only if the upload succeeds.

If the test or save fails, refer to [FAQs](#faqs).

## FAQs

### What permissions does CleverTap need?

For import, CleverTap needs read access (`s3:GetObject`, `s3:ListBucket`) on the bucket. For export, CleverTap needs write access (`s3:PutObject*`) on the bucket path. The IAM Role and SSE-KMS methods generate the exact policy for you.

### Does the bucket have to be in the same region as my CleverTap account?

No. You can use a bucket in any AWS region. For optimal performance, CleverTap recommends the region that corresponds to your CleverTap account.

### Can I use one connection for both import and export?

No. You configure import and export connections separately under _Import Connections_ and _Export Connections_. You can point both connections at the same bucket.

### Why does AWS show "The specified bucket name is not available" when I create the bucket?

S3 bucket names are unique across all AWS accounts, so another account already uses the name. Choose another name, for example, by appending your company name or AWS account ID. Then update _Folder_ on the CleverTap dashboard to the final name.

### Why does Save fail for an export connection?

CleverTap cannot upload the test file when the bucket name or region on the CleverTap dashboard does not match AWS, or when you have not saved the AWS-side policy. Confirm that _Folder_ matches the bucket name exactly (the match is case-sensitive), confirm the region, and confirm that you saved the bucket policy or IAM policy on AWS before you click **Save**.

### Why does Test Connection fail for an import connection?

The policy grants write access but not read access, or the _Subfolder_ path does not exist. Confirm that the policy grants `s3:GetObject` and `s3:ListBucket`, and confirm that the subfolder exists in the bucket.

### Why does the generated policy contain a bucket name that is not mine?

The _Folder_ field was empty or incorrect when CleverTap generated the policy. Correct _Folder_ on the CleverTap dashboard, and CleverTap regenerates the policy. Then copy the policy again.

### Why can't I decrypt exported files?

The bucket uses SSE-KMS, but the IAM principal that reads the files has no `kms:Decrypt` permission on the key. Grant `kms:Decrypt` on the key to that principal. This permission is separate from CleverTap's access.

## Next Steps

After you add the bucket, you can create imports and exports that use the connection.

- Create an import that reads from this connection. For more information, refer to [Create Import](doc:create-file-based-import), [Map Data for Import](doc:map-data-for-file-based-import), [Schedule Import](doc:schedule-file-based-import), and [Import Listing and Stats](doc:import-listing-and-stats-for-file-based-import).
- Create an export that writes to this connection. For more information, refer to [Cloud Storage](doc:cloud-storage), [Event Exports](doc:event-exports), or [Profile Exports](doc:profile-exports).
