---
title: Access Key
excerpt: >-
  Understand how to configure Amazon S3 in CleverTap using Access Key
  authentication.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Access Key authentication grants CleverTap access to your Amazon S3 bucket through the access key ID and secret access key of an AWS IAM user. This method applies to both import and export connections.

<Callout icon="📘" theme="info">
  ### Note

  AWS recommends short-lived credentials over long-term access keys. If your security policy allows it, use the [IAM Role](doc:iam-role) method instead. The IAM Role method requires no credentials in CleverTap and fewer steps on AWS. For a comparison of all three methods, refer to [Choose Configuration Method](doc:aws-s3-configuration#choose-configuration-method).
</Callout>

The configuration involves creating an IAM policy and an IAM user, generating an access key, and entering the key in CleverTap.

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Set Up Amazon S3 for Integration](#set-up-amazon-s3-for-integration)
- [Configure Amazon S3 in CleverTap](#configure-amazon-s3-in-clevertap)
- [Verify Integration](#verify-integration)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

<Accordion title="Quick Start Guide for Existing Users">
  An existing IAM user for CleverTap shortens the setup to three steps.

  1. Verify the permissions of your IAM user. For more information, refer to [Verify IAM User Permissions](#verify-iam-user-permissions).
  2. Retrieve or rotate the access key. For more information, refer to [Retrieve or Rotate Access Key](#retrieve-or-rotate-access-key).
  3. Enter the access key credentials in CleverTap. For more information, refer to [Configure Amazon S3 in CleverTap](#configure-amazon-s3-in-clevertap).
</Accordion>

## Prerequisites for Integration

Before you configure Access Key authentication, ensure that the AWS bucket, the CleverTap bucket details, and the required AWS access are available.

- An Amazon S3 bucket created on AWS. For more information, refer to [Create S3 Bucket on AWS](doc:aws-s3-configuration#create-s3-bucket-on-aws).
- Bucket details entered on the CleverTap dashboard with **Access Key** selected as the _Configure with_ method. For more information, refer to [Add Bucket on CleverTap Dashboard](doc:aws-s3-configuration#add-bucket-on-clevertap-dashboard).
- One of the following, depending on whether you use a new or an existing IAM user:
  - **New IAM user**: AWS console access with permissions to create IAM policies, IAM users, and access keys
  - **Existing IAM user**: The access key ID and secret access key of an IAM user that has the required S3 permissions. If you did not store the secret access key, generate a new one. For more information, refer to [Use Existing AWS Credentials](#use-existing-aws-credentials).

## Set Up Amazon S3 for Integration

Setting up Amazon S3 for Access Key authentication requires an IAM policy, an IAM user with that policy attached, and an access key for the user. If you already have an IAM user for CleverTap, skip to [Use Existing AWS Credentials](#use-existing-aws-credentials).

### Create IAM Policy

The IAM policy defines the S3 permissions that CleverTap needs on your bucket. For more information about AWS IAM, refer to [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html).

1. Log in to your AWS console and go to _Identity and Access Management (IAM)_.


   <Image src="https://files.readme.io/2c165970a777e4be2da7dc80ecbbc0fbab918116d051b91105a50b127242df03-IAM.png" align="center" caption="IAM" border={true} />


2. Select **Policies** from the left navigation and click **Create policy**.


   <Image src="https://files.readme.io/b499b19c10f08d62c4bcff40e250316b03fe7a1d6b0bd285435e3df459519b10-policies.png" align="center" caption="Create Policy - AWS S3" border={true} />


3. Select the **JSON** tab.

4. Select the tab that matches your connection type, and paste the policy into the editor.

   <Tabs>
     <Tab title="Import">
       ```json
       {
           "Version": "2012-10-17",
           "Statement": [
               {
                   "Effect": "Allow",
                   "Action": [
                       "s3:GetObject",
                       "s3:ListBucket"
                   ],
                   "Resource": [
                       "arn:aws:s3:::bucket-name",
                       "arn:aws:s3:::bucket-name/*"
                   ]
               }
           ]
       }
       ```
     </Tab>

     <Tab title="Export">
       ```json
       {
           "Version": "2012-10-17",
           "Statement": [
               {
                   "Effect": "Allow",
                   "Action": [
                       "s3:ListBucket"
                   ],
                   "Resource": [
                       "arn:aws:s3:::bucket-name"
                   ]
               },
               {
                   "Effect": "Allow",
                   "Action": [
                       "s3:PutObject"
                   ],
                   "Resource": [
                       "arn:aws:s3:::bucket-name/*"
                   ]
               }
           ]
       }
       ```
     </Tab>
   </Tabs>

5. Replace every occurrence of `bucket-name` in the policy with the name of your S3 bucket, including the occurrence that ends in `/*`.

6. Click **Next**.


   <Image src="https://files.readme.io/7645db1db4a18cd0b8f20def69854a4c42c5c8df663099fb2ac5193626b44b1f-specify_permission.png" align="center" caption="Policy Editor - AWS S3" border={true} />


7. Enter a name for your policy under _Policy name_ and click **Create policy**.

### Create IAM User and Attach Policy

The IAM user holds the policy and provides the credentials that CleverTap uses to access your bucket.

1. Select **Users** from the left navigation and click **Create user**.


   <Image src="https://files.readme.io/b9791cf6474ad4e9d95e65d6bc67351598e68be66bdcc4fe834373fc9bbc6ed3-IAM_Users.png" align="center" caption="Create User" border={true} />


2. Enter a value for _User name_ and click **Next**. Leave the _Provide user access to the AWS Management Console_ checkbox cleared because CleverTap requires only programmatic access.


   <Image src="https://files.readme.io/25f2e870defe093546f77743678425d50c13a046ed8781d8a3384876c7735780-User_details.png" align="center" caption="Add User Name - AWS S3" border={true} />


3. Under _Permissions options_, select **Attach policies directly**. This option attaches the policy to the user itself, so the permissions apply to this user without a user group.

4. Search for the policy you created in [Create IAM Policy](#create-iam-policy), select the policy, and click **Next**.


   <Image src="https://files.readme.io/6658e55cf63528f0bdf2bafb6b397fbe7656e72d6c330674728e970724d00163-set_permissions.png" align="center" caption="Attach Policies Directly - AWS S3" border={true} />


5. Click **Create user**.


   <Image src="https://files.readme.io/2f4af6ae5986c5dc63ba0f8e47bb1402231dbe23bdd9943fd5b58237cc824d9f-CREATE_USER.png" align="center" caption="Create User" border={true} />


### Generate Access Key

The access key consists of an access key ID and a secret access key that CleverTap uses to authenticate with AWS.

1. Open the user that you created from the _Users_ list and go to the **Security credentials** tab.

2. Under _Access keys_, click **Create access key**.


   <Image src="https://files.readme.io/8b9962a6b0f6d73e8f56e305b4ab1228aadaa71cc5572641b297134c7a8677be-create_access_key.png" align="center" caption="Create Access Key" border={true} />


3. Under _Use case_, select **Third-party service**. Under _Confirmation_, select **I understand the above recommendation and want to proceed to create an access key** and click **Next**.


   <Image src="https://files.readme.io/556144f8689c588c52db2d995d9f7d492db76abdc55cee8f5fac6d2561c9b83d-third_party_services.png" align="center" caption="Third-Party Service" border={true} />


4. (Optional) Enter a description for the access key under _Description tag value_, for example, `CleverTap S3 export`.

5. Click **Create access key**.


   <Image src="https://files.readme.io/7d6c6af07f0bd0796ed7c5526462518ab8a022db340cd1dee398fef0cfbea14b-set_description_tag.png" align="center" caption="Create Access Key" border={true} />


6. Copy the _Access key_ and _Secret access key_ values. You enter these values when you [configure the connection](#configure-amazon-s3-in-clevertap) in CleverTap.

<Callout icon="🚧" theme="warn">
  ### Important

  The secret access key appears only on this screen, and you cannot retrieve it later. Store the key securely before you leave the page. If you lose the key, create a new access key.
</Callout>

### Use Existing AWS Credentials

An existing IAM user for CleverTap requires verified permissions and a stored access key before you configure the connection.

#### Verify IAM User Permissions

The IAM user needs, at minimum, the permissions in the policy for your connection type for CleverTap to access your S3 bucket.

1. Log in to your AWS console, go to _Identity and Access Management (IAM)_, and select **Users** from the left navigation.

2. Open the IAM user that CleverTap uses and select the **Permissions** tab.

3. Confirm that an attached policy grants at least the actions in the [policy for your connection type](#create-iam-policy), with `bucket-name` replaced by the name of your S3 bucket. If the user lacks such a policy, [create the policy](#create-iam-policy) and attach it to the user.

#### Retrieve or Rotate Access Key

You can retrieve the access key ID of an existing key, or you can create a new key if you did not store the secret access key.

1. Go to the **Security credentials** tab of the IAM user and scroll to _Access keys_.

2. If an active access key exists and you stored its secret access key, note the _Access key ID_ and continue to [Configure Amazon S3 in CleverTap](#configure-amazon-s3-in-clevertap).

3. If you did not store the secret access key, click **Create access key**, and then complete steps 3 to 6 in [Generate Access Key](#generate-access-key).

<Callout icon="🚧" theme="warn">
  ### Note

  An IAM user can have at most two access keys. Deactivate or delete keys that you no longer use.
</Callout>

## Configure Amazon S3 in CleverTap

The CleverTap dashboard accepts the access key credentials that you created or retrieved on AWS.

1. Return to the CleverTap dashboard and open your Amazon S3 connection:
   - For import, go to _Settings > Partners > Import Center_ and select your Amazon S3 connection.
   - For export, go to _Settings > Partners > Export Center_ and select your Amazon S3 connection.

2. Under _Configure with_, select **Access Key**.

3. Enter the _Access Key_ and _Secret Key_ values that you copied from AWS.


   <Image src="https://files.readme.io/c4846538ba9ffe95a2deeab6a2191c344f937a1510a7d5c5610d0316f0117138-Bucket_details.png" align="center" caption="Paste Access Key and Secret Key" border={true} />


## Verify Integration

CleverTap verifies the connection when you test or save it, and the verification method depends on the connection type.

- **Import**: Click **Test Connection**. When the test succeeds, click **Save**.
- **Export**: Click **Save**. CleverTap uploads a test file to the bucket and region that you specified, and it saves the connection only if the upload succeeds.

After the connection saves successfully, you have configured the Amazon S3 bucket on both the AWS console and the CleverTap dashboard.

### Review Security Configuration

The following checks confirm that the connection follows least-privilege practices before you use it in production.

- Confirm that the IAM policy contains only the actions that the connection type requires (read for import, write for export).
- Confirm that the `Resource` values reference the correct bucket, with `/*` for object-level actions.
- Confirm that the IAM user has no console access and no permissions beyond this policy.
- Confirm that your organization's secrets manager stores the secret access key.
- Confirm that **Test Connection** (import) or **Save** (export) succeeded on the CleverTap dashboard.

## FAQs

### Why does Save fail with an access-denied error for an export connection?

The IAM policy grants read access (`s3:GetObject`) but not write access (`s3:PutObject`). Attach the export policy from [Create IAM Policy](#create-iam-policy) to the IAM user.

### Why does Test Connection fail with an access-denied error for an import connection?

The IAM policy grants write access but not read access, or the policy omits `s3:ListBucket` on the bucket ARN. Attach the import policy from [Create IAM Policy](#create-iam-policy). Note that `s3:ListBucket` applies to the bucket ARN `arn:aws:s3:::bucket-name`, without the `/*` suffix.

### Why does the connection fail immediately with an invalid-credentials error?

You mistyped the secret access key, or someone deactivated or deleted the key in IAM. Create a new access key and update the connection with the new credentials.

### Why is Next disabled when I create an access key?

The confirmation checkbox on the _Access key best practices & alternatives_ screen is not selected. Select **I understand the above recommendation and want to proceed to create an access key** to enable **Next**.

### Why does policy validation fail in the JSON editor?

You did not replace `bucket-name`, or you replaced only one occurrence. Replace every occurrence of `bucket-name`, including the occurrence that ends in `/*`.

## Next Steps

After you configure the connection, you can create imports and exports that use it.

- Create an import that reads from this connection. For more information, refer to [Create Import](doc:create-file-based-import), [Map Data for Import](doc:map-data-for-file-based-import), [Schedule Import](doc:schedule-file-based-import), and [Import Listing and Stats](doc:import-listing-and-stats-for-file-based-import).
- Create an export that writes to this connection. For more information, refer to [Cloud Storage](doc:cloud-storage), [Event Exports](doc:event-exports), or [Profile Exports](doc:profile-exports).
