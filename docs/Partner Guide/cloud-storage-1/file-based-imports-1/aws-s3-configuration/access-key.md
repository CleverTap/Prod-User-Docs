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

This document covers how to configure your Amazon S3 connection in CleverTap using Access Key authentication. This method uses an Access Key ID and Secret Access Key of an AWS IAM user to grant CleverTap access to your bucket. It applies to both import and export connections.

Before you begin, complete Create an _S3 Bucket on AWS_ and _Add the Bucket_ on the CleverTap Dashboard in [Amazon S3](doc:amazon-s3), and select Access Key under Configure with.

<Callout icon="📘" theme="info">
  ### **Note**

  AWS recommends short-lived credentials over long-term access keys. If your security policy allows it, use the IAM Role method instead; it requires no credentials in CleverTap and fewer steps on AWS.
</Callout>

The configuration involves the following major steps:

1. Create an IAM User and Attach the Policy
2. Generate an Access Key
3. Configure the Connection on CleverTap

If you already have an IAM user for CleverTap, skip to [Use Existing AWS Credentials](#use-existing-aws-credentials).

## Prerequisites

Ensure the following are in place before proceeding:

- An S3 bucket has already been created on AWS. Refer to Create an S3 Bucket on AWS.

- The bucket details entered on the CleverTap dashboard with Access Key selected. Refer to Add the Bucket on the CleverTap Dashboard.

- AWS console access with permissions to create IAM policies, IAM users, and access keys.

# Configure with Access Key

Setting up Amazon S3 for Access Key authentication requires an IAM policy, an IAM user with that policy attached, and an access key for the user. If you already have an IAM user for CleverTap, skip to [Use Existing AWS Credentials](#use-existing-aws-credentials).

**Create an IAM Policy**

The IAM policy defines the S3 permissions that CleverTap needs on your bucket. For more information about AWS IAM, refer to [Creating IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html).

1. Log in to your AWS console and go to _Identity and Access Management (IAM)_.


   <Image src="https://files.readme.io/2c165970a777e4be2da7dc80ecbbc0fbab918116d051b91105a50b127242df03-IAM.png" align="center" caption="IAM" border={true} />


2. Select **Policies** from the left navigation and click **Create policy**.


   <Image src="https://files.readme.io/b499b19c10f08d62c4bcff40e250316b03fe7a1d6b0bd285435e3df459519b10-policies.png" align="center" caption="Create policy - AWS S3" border={true} />


3. Select the _JSON_ tab and paste the policy for your use case into the editor.&#x20;

4. Replace `bucket-name` with the name of your S3 bucket.<br />
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

5. Click **Next**.


   <Image src="https://files.readme.io/7645db1db4a18cd0b8f20def69854a4c42c5c8df663099fb2ac5193626b44b1f-specify_permission.png" align="center" caption="Policy Editor - AWS S3" border={true} />


6. Enter a name for your policy under _Policy name_ and click **Create policy**.

#### Create an IAM User and Attach the Policy

This section covers creating an IAM user for CleverTap and attaching the policy you created.

To create the user, perform the following steps:

1. Select IAM users from the left navigation and click Create user.


   <Image src="https://files.readme.io/b9791cf6474ad4e9d95e65d6bc67351598e68be66bdcc4fe834373fc9bbc6ed3-IAM_Users.png" align="center" caption="Create User" border={true} />


2. Enter a value for _User name_ and click **Next**. Leave Provide user access to the AWS Management Console cleared; CleverTap only needs programmatic access.


   <Image src="https://files.readme.io/25f2e870defe093546f77743678425d50c13a046ed8781d8a3384876c7735780-User_details.png" align="center" caption="Add User Name - AWS S3" border={true} />


3. Search for the policy you created in [Create an IAM Policy](#create-a-IAM-policy), select it, and click **Next**.


   <Image src="https://files.readme.io/6658e55cf63528f0bdf2bafb6b397fbe7656e72d6c330674728e970724d00163-set_permissions.png" align="center" caption="Attach Policies Directly - AWS S3" border={true} />


4. Click **Create user**.


   <Image src="https://files.readme.io/2f4af6ae5986c5dc63ba0f8e47bb1402231dbe23bdd9943fd5b58237cc824d9f-CREATE_USER.png" align="center" caption="Create User" border={true} />


#### Generate Access Key

This section covers generating an access key that CleverTap uses to authenticate.

1. Open the user you just created in the _Users_ list, and go to the _Security credentials_ tab.
2. Under _Access keys_, click **Create access key**.


<Image src="https://files.readme.io/8b9962a6b0f6d73e8f56e305b4ab1228aadaa71cc5572641b297134c7a8677be-create_access_key.png" align="center" caption="Create Access Key" border={true} />


2. Under Use Case, select **Third-party service.&#x20;**&#x55;nder Confirmation, select I understand the above recommendation and want to proceed to create an access key, and then click Next.


   <Image src="https://files.readme.io/556144f8689c588c52db2d995d9f7d492db76abdc55cee8f5fac6d2561c9b83d-third_party_services.png" align="center" caption="Third-Party Service" border={true} />


3. (Optional) Enter a Description tag value, for example, `CleverTap S3 export`.&#x20;

4. Click **Create access key**.


   <Image src="https://files.readme.io/7d6c6af07f0bd0796ed7c5526462518ab8a022db340cd1dee398fef0cfbea14b-set_description_tag.png" align="center" caption="Create Access Key" border={true} />


5. Copy the _Access Key_ and _Secret Access Key_ values. You will need these to [configure the connection](#configure-the-connection) on CleverTap.

<Callout icon="🚧" theme="warn">
  ### Important

  The **Secret Access Key** is shown only on this screen and cannot be retrieved later. Store it securely before you leave the page. If you lose it, create a new access key.
</Callout>

### Use Existing AWS Credentials

If you already have an IAM user for CleverTap, verify its permissions and retrieve or rotate its access key.

#### Verify IAM User Permissions

This section covers finding an existing access key or generating a new one if you haven't stored the Secret Access Key.

2. Open the IAM user that CleverTap uses and select the **Permissions** tab.

To ensure CleverTap can access your S3 bucket, verify that the IAM user has at minimum the following permissions.

1. Open the user from the Users list and select the Permissions tab.
2. Confirm that an attached policy grants at least the actions listed below. If not, [create the policy](#create-a-IAM-policy) and attach it. Replace `bucket-name` with your actual bucket name.

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

#### Retrieve or rotate the access key

1. Select the Security credentials tab and scroll to Access keys.
2. If an active access key exists and you have its Secret Access Key stored, note the Access Key ID and continue to Configure the Connection on CleverTap.
3. If you did not store the Secret Access Key, click **Create access key**, then follow [Generate an Access Key](doc:generate-an-access-key#generate-an-access-key) from step 3.

<Callout icon="⚠️" theme="warn">
  ### Note

  An IAM user can have at most two access keys. Deactivate or delete keys that are no longer used.
</Callout>

## Configure the Connection on CleverTap

Once your AWS credentials are in place, return to the CleverTap dashboard to complete the connection.

1. Return to the CleverTap dashboard. For import, navigate to _Settings_ > _Partners_ > _Import centre_ and select Amazon S3 connection. For export, go to _Settings_ > _Partners_ > Export centre, select **Amazon S3 connection.**

2. Go to the **Security credentials** tab of the IAM user and scroll to _Access keys_.

3. If an active access key exists and you stored its secret access key, note the _Access key ID_ and continue to [Configure Amazon S3 in CleverTap](#configure-amazon-s3-in-clevertap).


   <Image src="https://files.readme.io/c4846538ba9ffe95a2deeab6a2191c344f937a1510a7d5c5610d0316f0117138-Bucket_details.png" border={true} />


4. Verify and save:
   - For import, click Test Connection. When the test succeeds, click Save.
   - For export, click Save.

<Callout icon="🚧" theme="warn">
  ### Note

  For export, when you click **Save**, CleverTap uploads a test file to the specified bucket and region to verify the configuration. The configuration is saved only if the test file upload succeeds.
</Callout>

The Amazon S3 bucket is now configured on both the AWS console and the CleverTap dashboard.

## Troubleshooting

| Issue                                                                         | Cause                                                                                      | Resolution                                                                                                                       |
| ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| Export **Save** fails with an access-denied error                             | The IAM policy grants read (`s3:GetObject`) but not write (`s3:PutObject`).                | Attach the export policy from _Create an IAM Policy_.                                                                            |
| Import **Test Connection** fails with an access-denied error                  | The IAM policy grants write but not read, or `s3:ListBucket` is missing on the bucket ARN. | Attach the import policy from _Create an IAM Policy_. Note that `s3:ListBucket` applies to `arn:aws:s3:::bucket-name` (no `/*`). |
| Connection fails immediately with an invalid-credentials error                | The Secret Access Key was mistyped, or the key was deactivated or deleted in IAM.          | Create a new access key and update the connection.                                                                               |
| **Next** is disabled on the _Access key best practices & alternatives_ screen | The confirmation checkbox is not selected.                                                 | Select **I understand the above recommendation and want to proceed to create an access key**.                                    |
| Policy validation fails in the JSON editor                                    | `bucket-name` was not replaced, or only one occurrence was replaced.                       | Replace every occurrence of `bucket-name,` including the one ending in `/*`.                                                     |

# Verification Checklist

Confirm the following before using the connection in production:

- The IAM policy contains only the actions required for the connection type (read for import, write for export).
- The policy's `Resource` values reference the correct bucket, with `/*` for object-level actions.
- The IAM user has no console access and no permissions beyond this policy.
- The Secret Access Key is stored in your organization's secrets manager.
- **Test Connection (import)** or **Save (export)** succeeded on the CleverTap dashboard.
