---
title: AWS S3
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

The data export feature enables you to bulk export your CleverTap event data to your AWS S3 bucket. You can use this for analysis in BI tools or storage in your data warehouse for analysis in the future.

> 📘 Feature Availability
>
> This capability is a part of the *Enterprise*, *Advanced*, and *Cutting Edge* plan. To activate this for your account, contact your Account Manager.

# Setup

The following are the two major steps involved in enabling this feature for your account:

1. [Create an AWS S3 Bucket](doc:data-export-to-aws-s3#create-an-aws-s3-bucket).
2. Configure Buckets details on the CleverTap Dashboard using one of the following methods:
   * [Using Access Key](doc:data-export-to-aws-s3#using-access-key)
   * [Using IAM Policy](doc:data-export-to-aws-s3#using-iam-policy)

> 📘 Data Export
>
> Once you have set up both dashboards, you can configure export from the CleverTap dashboard. For more information, refer to the following: 
>
> * [Data Exports](doc:data-exports) for Legacy Profile and Event Export flow
> * [Profile Exports](doc:profile-exports) for Enhanced Profile Export flow

## Create an AWS S3 Bucket

To create an AWS S3 bucket:

1. Log in to your AWS account, then search for *S3* in the AWS services box. 
2. Select *S3* from the search results. 

<Image title="Select S3 from AWS account" alt={891} align="center" border={true} src="https://files.readme.io/bb8d83c-Selecting_S3_from_the_list.png">
  Select S3 from AWS Account 
</Image>

   Upon clicking, the *Bucket* page is displayed.

3. Click **Create bucket**. On clicking, the *Create bucket* page displays:

<Image title="Click Create bucket from Buckets page" alt={2876} align="center" border={true} src="https://files.readme.io/111a267-Bucket_page.png">
  Click Create Bucket
</Image>

4. Enter a bucket name, region, logging, versioning, and encryption preferences. 

<Image title="Enter General Configuration for S3 bucket and click Create bucket" alt={1628} align="center" width="80%" border={true} src="https://files.readme.io/407acf4-Create_bucket_page.png">
  Configure S3 Bucket Settings and Click Create Bucket 
</Image>

> 📘 Recommendation for Setup
>
> For this integration, you need not modify the default settings; however, you must check your internal organization's policies to verify if you need to modify any of these settings.

Based on your CleverTap account settings, we host your data in Europe (EU), the United States (US), Singapore (SG), or India (IN). To identify the region of your account and the corresponding region that you must select when configuring the bucket settings, refer to the following table:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        CleverTap Dashboard URL
      </th>

      <th>
        Region
      </th>

      <th>
        AWS S3 Bucket Region
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        [https://eu1.dashboard.clevertap.com/login.html](https://eu1.dashboard.clevertap.com/login.html#/)
      </td>

      <td>
        EU
      </td>

      <td>
        EU (Ireland) eu-west-1
      </td>
    </tr>

    <tr>
      <td>
        [https://in1.dashboard.clevertap.com/login.html](https://in1.dashboard.clevertap.com/login.html#/)
      </td>

      <td>
        India
      </td>

      <td>
        Asia Pacific (Mumbai) ap-south-1
      </td>
    </tr>

    <tr>
      <td>
        [https://us1.dashboard.clevertap.com/login.html](https://us1.dashboard.clevertap.com/login.html#/)
      </td>

      <td>
        US
      </td>

      <td>
        US West (Oregon) us-west-2
      </td>
    </tr>

    <tr>
      <td>
        [https://sg1.dashboard.clevertap.com/login.html](https://sg1.dashboard.clevertap.com/login.html#/)
      </td>

      <td>
        Singapore
      </td>

      <td>
        Asia Pacific (Singapore)\
        ap-southeast-1
      </td>
    </tr>

    <tr>
      <td>
        [https://mec1.dashboard.clevertap.com/login.html](https://mec1.dashboard.clevertap.com/login.html)
      </td>

      <td>
        Middle East (UAE)
      </td>

      <td>
         Middle East (UAE) me-central-1
      </td>
    </tr>

    <tr>
      <td>
        [https://aps3.dashboard.clevertap.com/login.html](https://aps3.dashboard.clevertap.com/login.html)
      </td>

      <td>
        Indonesia
      </td>

      <td>
        Asia Pacific (Jakarta) ap-southeast-3
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Set Up AWS Bucket Region
>
> When setting up the AWS bucket region for your AWS account, ensure that the AWS bucket region matches your CleverTap account region. To identify the region of your CleverTap account, refer to the above table. 
>
> Also, you can set up the CleverTap account region only once during registration.

5. Click **Create bucket**. On successful bucket creation, the following message displays in the snack bar at the top:

<Image title="S3 Bucket created successfully message displays at the top" alt={2770} align="center" border={true} src="https://files.readme.io/681e832-Successful_bucket_creation.png">
  S3 Bucket Created Successfully
</Image>

The bucket you just created now appears in your S3 console. We recommend you note down the name of your new bucket, as you will need it for the next step.

## Configure S3 Bucket Details on CleverTap Dashboard

### Using IAM Policy

The following are the two major steps to configure S3 bucket details on the CleverTap dashboard using IAM Policy

i. [Copy IAM Policy from the CleverTap dashboard](doc:data-export-to-aws-s3#copy-iam-policy-from-the-clevertap-dashboard)

ii. [Add IAM Policy to S3 Bucket from AWS console](doc:data-export-to-aws-s3#add-iam-policy-to-s3-bucket-on-aws-console) 

#### Copy IAM Policy from the CleverTap Dashboard

To copy the IAM policy from the CleverTap dashboard:

1. Navigate to *Settings* > *Partners* and click **View Details** against Amazon S3. The *Integrate analytics partner - Amazon S3* window displays on the right side of the screen.

<Image title="Click View Details against Amazon S3 from Partner page" alt={1500} align="center" width="80%" border={true} src="https://files.readme.io/27118b6-Integrate_Analytics_Partner_-_AWS_S3.png">
  Click View Details against Amazon S3 from Partner Page
</Image>

2. Click **+ Amazon S3 Bucket** to create a new bucket.
3. Enter the *Bucket name*. 
4. Select *IAM (Identity and Access Management) Policy* option under *Configure with* section.

<Image title="Enter Bucket URL and select IAM Policy option" alt={1446} align="center" width="80%" border={true} src="https://files.readme.io/475094f-Select_IAM_Policy_option.png">
  Configure S3 Bucket with IAM Policy
</Image>

5. Click the ![](https://files.readme.io/2bd537e-Copy_icon.png) icon to copy the policy to the clipboard and keep this window open for saving these details later.

#### Add IAM Policy to S3 Bucket on AWS Console

To add IAM policy to the S3 bucket:

1. Select the bucket from the Bucket page of the AWS console.
2. Select the *Permissions* tab.
3. Click **Edit** under the *Bucket policy* section and enter the policy that you copied in Step *4* of [Copy IAM Policy from the CleverTap dashboard](doc:data-export-to-aws-s3#copy-iam-policy-from-the-clevertap-dashboard):

<Image title="Click Edit to edit S3 bucket policy" alt={2052} align="center" width="80%" border={true} src="https://files.readme.io/438b0da-Add_IAM_policy_to_S3_Bucket.png">
  Edit S3 Bucket Policy
</Image>

```json IAM Policy
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::062484260092:root"
            },
            "Action": "s3:PutObject*",
            "Resource": "arn:aws:s3:::bucket-name/*"
        },
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::062484260092:root"
            },
            "Action": "s3:PutObject*",
            "Resource": "arn:aws:s3:::bucket-name"
        }
    ]
}
```

> 🚧 IMPORTANT
>
> Ensure that you replace all the occurrences of `bucket-name` in the above JSON payload with your actual bucket name.

4. Click **Save Changes** to save the policy.
5. Go back to the same window opened in *Step 4* of [Copy IAM Policy From CleverTap Dashboard](doc:data-export-to-aws-s3#copy-iam-policy-from-the-clevertap-dashboard) and click **Save Credentials**.

The Amazon S3 bucket is now configured on both the AWS S3 console and the CleverTap dashboard. 

### Using Access Key

The following are the two major steps to configure S3 bucket details on the CleverTap dashboard using Access Key:

i. [Create an API Key for Your S3 Bucket](doc:data-export-to-aws-s3#create-an-api-key-for-your-s3-bucket).

ii. [Add Your S3 Bucket Details to CleverTap](doc:data-export-to-aws-s3#add-your-s3-bucket-details-to-clevertap).

#### Create an API Key for Your S3 Bucket

This section demonstrates the creation of an AWS API key with write access to the bucket we created in the above step. CleverTap uses this API key to export data to your S3 bucket.

1. Click on your account name on the top right of the AWS console.
2. Select *Security credentials*.

<Image title="Select Security credentials option" alt={388} align="center" width="smart" border={true} src="https://files.readme.io/152163f-Security_credentials.png">
  Select Security credentials
</Image>

3. Select *Users* from the left navigation and click **Add user**.

<Image title="Click Add users from the User page" alt={2878} align="center" border={true} src="https://files.readme.io/8b81e57-Click_Add_users.png">
  Add Users
</Image>

On clicking, the *Add user* page displays.

4. Enter the *User name* and select the *Programmatic access* checkbox.
5. Click **Next:Permissions**.

<Image title="Enter the User name, select AWS credential type and click Next: Permissions" alt={2878} align="center" border={true} src="https://files.readme.io/7840a59-Add_user.png">
  Select AWS Access Type and Click Next: Permissions
</Image>

On clicking, *Set permissions* page displays.

6. Click **Create group** under *Add user to group* tab.

<Image title="Click Create group under Add user to group tab" alt={2872} align="center" border={true} src="https://files.readme.io/592634b-Create_group.png">
  Add User to Group
</Image>

On clicking, *Create group* page displays.

<Image title="Assign policy to group" alt={2482} align="center" border={true} src="https://files.readme.io/5cfd145-Create_group_page.png">
  Assign Policy to Group
</Image>

7. Click **Create policy**. On clicking, *Create policy* page opens in a new tab.
8. Select the **JSON** tab and then paste the JSON code given below in the box. 
9. Replace `clevertap-example` in the JSON code with the name of the S3 bucket you created in the above step.\
   The permissions defined in this policy allow CleverTap to get information about your bucket and upload files to it.

> 📘 AWS API Access Policies
>
> *IP Whitelisting* is not supported with S3 exports. For more information about AWS API access policies, refer to [this post](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_s3_rw-bucket-console.html) from the AWS blog.

<Image title="Bucket policy in JSON format" alt={2874} align="center" border={true} src="https://files.readme.io/bc21bb7-Replace_JSON_code.png">
  Bucket Policy in JSON Format
</Image>

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
                "arn:aws:s3:::clevertap-example"
            ]
        },
        {
            "Effect": "Allow",
            "Action": [
                "s3:PutObject"
            ],
            "Resource": [
                "arn:aws:s3:::clevertap-example/*"
            ]
        }
    ]
}
```

10. Click **Next: Tags**  and then click **Next: Review**. On clicking, the *Create policy* page opens.
11. Enter the policy *Name* and click **Create policy**.

<Image title="Enter policy name and click Create policy" alt={2648} align="center" border={true} src="https://files.readme.io/f81305a-Create_policy.png">
  Enter Policy Name and Click Create policy
</Image>

On successful policy creation, the following message displays in the snack bar at the top:

<Image title="Policy created successfully message displays at the top" alt={2870} align="center" border={true} src="https://files.readme.io/cc7b89a-Policy_created_successfully.png">
  Bucket  Policy Created Successfully
</Image>

12. Go back to the *Create group* page (opened in *Step 6*), search for the policy you just created, and assign it to the new group by selecting the checkbox.
13. Click **Create group**. On clicking, the *Add user* page displays.

<Image title="SSelect Policy and Click Create Group" alt={2486} align="center" border={true} src="https://files.readme.io/c28e813-Search_policy.png">
  Select Policy and Click Create Group
</Image>

14. Click **Next: Tags** and then click **Next: Review**.

<Image title="Click Next: Tags.png" alt={2012} align="center" border={true} src="https://files.readme.io/15f1ead-Click_Next_Tags.png">
  Click Next: Tags
</Image>

15. Click **Create user**. 

<Image title="Click Create user" alt={1980} align="center" border={true} src="https://files.readme.io/d88007d-Create_user.png">
  Click Create user
</Image>

On successful user creation, the following page displays. You will see your *Access key ID* and the *Secret access key*. 

<Image title="Copy or download Access key ID and Secret access key" alt={2878} align="center" border={true} src="https://files.readme.io/d3b1def-Access_key_and_secret_access_key.png">
  Copy or Download User Security Credentials
</Image>

These credentials allow CleverTap to upload files to your S3 bucket. We recommend you note down these values as you will require them for the next step. Otherwise, you can also click **Download .csv** to save these details for future use.

#### Add Your S3 Bucket Details to CleverTap

To add your S3 bucket details to Clevertap, perform the following steps:

1. Go to *Settings* > *Partners* and click **View Details** against Amazon S3. The *Integrate analytics partner - Amazon S3* window displays on the right side of the screen.

<Image title="Integrate Analytics Partner - AWS S3.png" alt={1500} align="center" border={true} src="https://files.readme.io/6ab03f2-Integrate_Analytics_Partner_-_AWS_S3.png">
  Click View Details against Amazon S3 from Partners Page
</Image>

2. Click **+ Amazon S3 Bucket** to create a new bucket. The *Integrate Amazon S3 Bucket* window opens on the right side of the screen. 
3. Enter the *Bucket nickname* and *Bucket URL*. 
4. Select the *User details* option under *Configure with* section.
5. Enter your *Access key ID* and the *Secret access key* obtained earlier and click **Save Credentials**.

<Image title="Select User details and enter the user security credentials" alt={1494} align="center" border={true} src="https://files.readme.io/5f44e48-Select_User_details_option.png">
  Enter User Security Credentials and Click Save Credentials 
</Image>

# FAQs

### What permission is required for CleverTap to export data to your AWS S3 bucket?

A. CleverTap needs write permission to be able to export data to your AWS S3 bucket, as shown in the following figure:

<Image title="IAM Policy to provide CleverTap with write access" alt={1446} align="center" width="80%" border={true} src="https://files.readme.io/7bed273-Select_IAM_Policy_option.png">
  IAM Policy to Provide CleverTap with Write Access
</Image>

### What should I do if I already have an existing IAM policy for the AWS S3 bucket?

Ensure that you modify the current IAM policy to provide CleverTap with write access to export data to your AWS S3 bucket.
