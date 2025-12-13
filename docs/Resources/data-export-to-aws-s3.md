---
title: Data Export to AWS S3
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

The AWS S3 Export feature enables you to bulk export your CleverTap event data to your AWS S3 bucket. You can use this for analysis in BI tools or for storage in your data warehouse for analysis in the future.

> 📘 Note
>
> This capability is a part of the CleverTap corporate pack. Contact your sales account manager to have it activated for you

# Initiating an export

<Image title="export2.png" alt={1410} className="border" border={true} src="https://files.readme.io/485f839-export2.png" />

* This feature can be configured to export data for all events or specific events that you select. 
* You also have the option to set up automatic recurring exports ranging from every 4 hours to every 24 hours.

<Image title="export.png" alt={630} className="border" border={true} src="https://files.readme.io/e531521-export.png" />

# Setup Steps

## Step 1 - Create an AWS S3 Bucket

Depending on your CleverTap account settings, we host your data in EU, US, SG or IN.\
Once you create an account in the same region as your CleverTap data hosting region, next step is to create your S3 bucket in that same region. For example, if your CleverTap account uses AWS EU(Ireland), then you will have to create a S3 bucket in the AWS EU(Ireland) region.

Login to your AWS account and then search for S3 in the AWS services box. Click on S3 in the search results. 

<Image title="s3-1.png" alt={891} className="border" border={true} src="https://files.readme.io/f30c5a0-s3-1.png" />

Click on the + Create bucket button.

<Image title="s3-2.png" alt={521} className="border" border={true} src="https://files.readme.io/84ecd10-s3-2.png" />

Enter a Bucket name, region and other settings that you may need to configure\
Complete your setup by selecting your logging, versioning, and encryption preferences. For this integration, you do not need to make any modifications to the default settings. However, you should check your internal organization's policies to see if you need to modify any of these settings. 

Then click Next.

<Image title="s3-3.png" alt={691} className="border" border={true} src="https://files.readme.io/0aeb412-s3-3.png" />

<Image title="s3-4.png" alt={694} className="border" border={true} src="https://files.readme.io/f59cf7a-s3-4.png" />

On this page, you can keep default settings. Again, make sure to check your internal organization's policies to see if you need to modify any of these settings. 

Then click Next.

<Image title="s3-5.png" alt={684} className="border" border={true} src="https://files.readme.io/1af0fea-s3-5.png" />

Select Create bucket.

<Image title="s3-6.png" alt={690} className="border" border={true} src="https://files.readme.io/f57101b-s3-6.png" />

The bucket you just created should now show up in your S3 console. Note the name of your new bucket, which you will need to use in step 2.

<Image title="s3-7.png" alt={1010} className="border" border={true} src="https://files.readme.io/928170d-s3-7.png" />

## Step 2 - Create an API Key for Your S3 Bucket

In this step, we will create an AWS API key that has write access to the bucket we created in step 1. CleverTap will use this API key to export data to your S3 bucket.

Click on your account name on the top right of the AWS console, and then click on Security Credentials.

<Image title="s3-8.png" alt={195} className="border" border={true} src="https://files.readme.io/43b4fc0-s3-8.png" />

Click on Users within the left-nav menu, and then click the Add user button.

<Image title="s3-11.png" alt={856} className="border" border={true} src="https://files.readme.io/ba3022e-s3-11.png" />

Enter a name for the new user and check the Programmatic access box. Then click Next.

<Image title="s3-12.png" alt={899} className="border" border={true} src="https://files.readme.io/4805d5b-s3-12.png" />

Then click Add user to group. Then click Create group.

<Image title="s3-13a.png" alt={1238} className="border" border={true} src="https://files.readme.io/ffe427d-s3-13a.png" />

Enter a Group name and then click on Create policy.

<Image title="s3-13b.png" alt={1116} className="border" border={true} src="https://files.readme.io/5624220-s3-13b.png" />

Click on the JSON tab.

![938](https://files.readme.io/81bbc55-s3-13c.png "s3-13c.png")

Paste the JSON below in the box. Replace "clevertap-example" with the name of the S3 bucket you created in step 1. The permissions defined in this policy will allow CleverTap to get information about your bucket and upload files to it. 

> 👍 For more information about AWS API access policies, please review [this post](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_s3_rw-bucket-console.html) from the AWS Blog.

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

Click the Review policy button. 

<Image title="s3-policy-1.png" alt={1206} className="border" border={true} src="https://files.readme.io/09bcba9-s3-policy-1.png" />

Enter a name. Then click Create policy.

<Image title="s3-policy-2.png" alt={1109} className="border" border={true} src="https://files.readme.io/dda70d4-s3-policy-2.png" />

Go back to the Group page. Search for the policy you just created, assign it to the new group by checking the box next to it, and then click Create group.

<Image title="s3-policy-3.png" alt={999} className="border" border={true} src="https://files.readme.io/07297ba-s3-policy-3.png" />

Now add the User to the group. Click the Next Review button.

<Image title="s3-13h.png" alt={1255} className="border" border={true} src="https://files.readme.io/95dbeec-s3-13h.png" />

Then click Create user. 

<Image title="s3-13i.png" alt={1232} className="border" border={true} src="https://files.readme.io/2516f4c-s3-13i.png" />

On the next page, you will be shown your Access key ID and the Secret access key. These credentials will allow CleverTap to upload files to your S3 bucket. Note these values, which you will use in step 3.

<Image title="s3-13j.png" alt={1235} className="border" border={true} src="https://files.readme.io/71c1e9e-s3-13j.png" />

## Step 3 - Add Your S3 Bucket Details to CleverTap

Login to your CleverTap account, and go to [this page](https://eu1.dashboard.clevertap.com/AAA-BBB-CCC/my-exports.html). Click on the Settings button.

<Image title="settings1.png" alt={1410} className="border" border={true} src="https://files.readme.io/ef722f0-settings1.png" />

Enter your bucket name from step 1. Enter your Access key ID and the Secret access key from Step 2.

<Image title="s3-setting.png" alt={1099} className="border" border={true} src="https://files.readme.io/33df145-s3-setting.png" />

## Step 4 - Create a New Data Export

Click on the Partner Data -> Exports -> Activity Log -> Create Export 

![1440](https://files.readme.io/5ce7991-Activity_Log.png "Activity Log.png")

When creating export there are various settings that need to be defined 

### Choose export Partner

* AWS for exporting Data to AWS

### Choose export Type

* All user events - Will export data for all events that have been defined which includes System and Custom events 
* Select Events - Will export specific events that you want to export 
* All user profiles - Will export all you user profile data

### Choose export Frequency

* One time - Single Export for the export type selected . You can export data up the last 45 days 
* Recurring - Setup a recurring export which will export all the new events/user profiles captured in the last window. You can export as frequently as every 4 hours and upto once every 24 hours 

### Choose export Format

* JSON
* XML
* CSV
* Parquet

If there is a scheduled recurring profile export, you must stop it to run a one time profile export.

<Image title="ezgif.com-video-to-gif (1).gif" alt={600} className="border" border={true} src="https://files.readme.io/e9c77b8-ezgif.com-video-to-gif_1.gif" />

CleverTap will now process the export. You can refresh the Activity Log page to see the current status of the export. Once the export is completed, the status for that export will say done.\
For Recurring Exports the status will be in Pending .

![1440](https://files.readme.io/fbd1ebc-Activity_Log.png "Activity Log.png")

To confirm your event data was successfully exported, login to your AWS account and go to the S3 console. You should see some files uploaded to your S3 bucket as shown in the screenshot below.\
You can copy the Request ID from the activity log and search with that in S3 , you should see you respective file there 

<Image title="s3-data.png" alt={594} className="border" border={true} src="https://files.readme.io/4127993-s3-data.png" />

# Export Format

## File Name Format

The example below shows the file name format for data exports.

* The export request id is generated when you create a request in the CleverTap dashboard.
* The timestamp is when the export was run.
* The event name is event type that is included in the file.
* For larger exports, we chunk the data across multiple files. The file index notes what file number in the file series it is. We have limited file sizes to 100 MB chunks to make them more consumable.

```text
<export request id>-<timestamp of the export run>-<event name>-<yyyymmdd>-<file index>-<database-id>.json
```

## File Data Format

* Files will be split by Event Names for Event Exports , each file will all event data for the given period for the Event 

## JSON

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

## CSV

CSV files will be comma delimited and will have each events in separate rows .

![2032](https://files.readme.io/aa71f9f-Screenshot_2020-02-28_at_12.53.22_PM.png "Screenshot 2020-02-28 at 12.53.22 PM.png")

## XML

Will have the timeStamp , eventName followed by  eventProperties

```typescript
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

## Parquet

Will have timestamp ,eventName and eventProperties for each event 

> 📘 Parquet File Format
>
> Parquet, an open source file format for Hadoop. Parquet stores nested data structures in a flat columnar format.
