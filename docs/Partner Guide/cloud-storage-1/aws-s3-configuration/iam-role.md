---
title: IAM Role
excerpt: Understand how to configure Amazon S3 in CleverTap using an IAM Role.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The IAM Role method grants CleverTap access to your Amazon S3 bucket through a bucket policy that the CleverTap dashboard generates, so you do not need an IAM user or access key. With this method, CleverTap authenticates with its own AWS identity, and you grant that identity access to your bucket by applying the generated policy. CleverTap stores no credentials, and the method applies to both import and export connections.

The generated policy differs by connection type:

- **Import**: Grants CleverTap's IAM role `s3:GetObject` and `s3:ListBucket` on your bucket (read access).
- **Export**: Grants CleverTap's AWS account `s3:PutObject*` on your bucket path (write access).

<Callout icon="🚧" theme="warn">
  ### Important

  CleverTap's AWS account ID differs by CleverTap region. Always copy the policy from your own dashboard, and do not reuse a policy from documentation, another project, or another region.
</Callout>

The configuration involves copying the generated policy, applying the policy to your S3 bucket, and saving the connection in CleverTap. For a comparison of all three methods, refer to [Choose Configuration Method](doc:aws-s3-configuration#choose-configuration-method).

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Set Up Amazon S3 for Integration](#set-up-amazon-s3-for-integration)
- [Verify Integration](#verify-integration)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

## Prerequisites for Integration

Before you configure the IAM Role method, ensure that the AWS bucket, the CleverTap bucket details, and the required AWS permissions are available.

- An Amazon S3 bucket created on AWS. For more information, refer to [Create S3 Bucket on AWS](doc:aws-s3-configuration#create-s3-bucket-on-aws).
- Bucket details entered on the CleverTap dashboard with the correct _Folder_ value and **IAM Role** selected as the _Configure with_ method. CleverTap inserts the _Folder_ value into the generated policy. For more information, refer to [Add Bucket on CleverTap Dashboard](doc:aws-s3-configuration#add-bucket-on-clevertap-dashboard) and [Enter Folder Name](doc:aws-s3-configuration#enter-folder-name).
- AWS console access with permission to edit the bucket policy (`s3:PutBucketPolicy`) on the bucket

## Set Up Amazon S3 for Integration

Setting up Amazon S3 for the IAM Role method requires copying the policy that CleverTap generates and applying the policy as the bucket policy of your S3 bucket.

### Copy IAM Policy from CleverTap Dashboard

CleverTap pre-fills the policy with its AWS principal and the bucket name that you entered under _Folder_.

1. On the _Connect to Amazon S3 for import_ or _Connect to Amazon S3 for export_ page, confirm that _Folder_ contains your exact bucket name. The policy regenerates when you change _Folder_.

2. Under _Configure with_, select **IAM Role**.

3. Click the copy icon to copy the generated IAM policy.


   <Image src="https://files.readme.io/c5c322599a4c8ca50b1af6ce46447d9a022be687ca1bcbc2cb0e9a5f9cfc78fb-IAM_Policy.png" align="center" caption="IAM Policy" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  The CleverTap dashboard labels this policy an IAM policy, but on AWS you apply it as the bucket policy of your S3 bucket (a resource-based policy), not as an IAM identity policy. Keep this page open, and return to it to save the connection.
</Callout>

### Apply IAM Policy to S3 Bucket on AWS

Applying the policy as a bucket policy on AWS grants CleverTap access to your bucket. For more information about AWS bucket policies, refer to [Adding a bucket policy using the Amazon S3 console](https://docs.aws.amazon.com/AmazonS3/latest/userguide/add-bucket-policy.html).

1. Log in to your AWS console and go to **S3**.

2. Select your bucket from the _Buckets_ page.


   <Image src="https://files.readme.io/1f50b88f2ed9f96ffbb29ba9cbb156ae35f9ab2a5dc7af1fa14e173b5add03a7-select_bucket.png" align="center" caption="Select Bucket - AWS S3" border={true} />


3. Go to the **Permissions** tab and click **Edit** under _Bucket policy_.


   <Image src="https://files.readme.io/d91969dac48b7dcdb004da8885d9571f8177955d68b74f9f45b3773b2d8aac02-buket_policy.png" align="center" caption="Permissions and Bucket Policy - AWS S3" border={true} />


4. Add the CleverTap policy to the bucket policy:
   - If the bucket has no bucket policy, paste the policy that you copied from CleverTap.
   - If the bucket has a bucket policy, add the statements from the CleverTap policy to the existing `Statement` array.

5. Click **Save changes**.


   <Image src="https://files.readme.io/a8e949397872f4f74e2ba4b814f110191d59518694b7e21bca84e9aee113f7ca-edit_bucket_policy.png" align="center" caption="Paste IAM Policy and Save Changes" border={true} />


<Callout icon="🚧" theme="warn">
  ### Important

  Do not replace an existing bucket policy with the CleverTap policy. Replacing the policy removes permissions on which other systems depend.
</Callout>

## Verify Integration

CleverTap verifies the connection when you test or save it after you save the bucket policy on AWS.

1. Confirm that you saved the bucket policy on AWS, and then return to the Amazon S3 connection page that you left open on the CleverTap dashboard.

2. Verify and save the connection:
   - **Import**: Click **Test Connection**. When the test succeeds, click **Save**.
   - **Export**: Click **Save**. CleverTap uploads a test file to the bucket and region that you specified, and it saves the connection only if the upload succeeds.

After the connection saves successfully, you have configured the Amazon S3 bucket on both the AWS console and the CleverTap dashboard.

### Review Security Configuration

The following checks confirm that the bucket policy and the CleverTap connection match before you use the connection in production.

- Confirm that _Folder_ on the CleverTap dashboard matches the AWS bucket name exactly.
- Confirm that the bucket policy on AWS contains the CleverTap statements and all pre-existing statements.
- Confirm that the principal in the bucket policy matches the principal on your CleverTap dashboard.
- Confirm that **Test Connection** (import) or **Save** (export) succeeded on the CleverTap dashboard.

## FAQs

### Why does AWS reject the bucket policy with an "Invalid principal" error?

You copied the policy from another source, or you edited the principal account ID. Copy the policy again from your CleverTap dashboard without modification.

### Why does AWS reject the bucket policy with a resource error?

The bucket name in the policy does not match the bucket that you are editing. Correct _Folder_ on the CleverTap dashboard, copy the regenerated policy, and paste the policy again.

### Why do existing integrations lose access after I save the policy?

You replaced the existing bucket policy instead of extending it. Restore the previous statements, and add the CleverTap statements to the `Statement` array.

### Why does Save or Test Connection fail on CleverTap even though I saved the policy?

The _Region_ value on CleverTap differs from the region of the bucket, or the policy contains a wildcard principal while you enable _Block all public access_. The CleverTap policy uses a specific principal and works with _Block all public access_, so confirm the _Region_ value on CleverTap first.

## Next Steps

After you configure the connection, you can create imports and exports that use it.

- Create an import that reads from this connection. For more information, refer to [Create Import](doc:create-file-based-import), [Map Data for Import](doc:map-data-for-file-based-import), [Schedule Import](doc:schedule-file-based-import), and [Import Listing and Stats](doc:import-listing-and-stats-for-file-based-import).
- Create an export that writes to this connection. For more information, refer to [Cloud Storage](doc:cloud-storage), [Event Exports](doc:event-exports), or [Profile Exports](doc:profile-exports).
