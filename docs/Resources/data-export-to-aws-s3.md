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
[block:callout]
{
  "type": "info",
  "body": "This capability is a part of the CleverTap corporate pack. Contact your sales account manager to have it activated for you",
  "title": "Note"
}
[/block]
# Initiating an export
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/485f839-export2.png",
        "export2.png",
        1410,
        481,
        "#dfe1e5"
      ],
      "border": true
    }
  ]
}
[/block]
- This feature can be configured to export data for all events or specific events that you select. 
- You also have the option to set up automatic recurring exports ranging from every 4 hours to every 24 hours.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e531521-export.png",
        "export.png",
        630,
        585,
        "#c2c3cd"
      ],
      "border": true
    }
  ]
}
[/block]
# Setup Steps

## Step 1 - Create an AWS S3 Bucket

Depending on your CleverTap account settings, we host your data in EU, US, SG or IN. 
Once you create an account in the same region as your CleverTap data hosting region, next step is to create your S3 bucket in that same region. For example, if your CleverTap account uses AWS EU(Ireland), then you will have to create a S3 bucket in the AWS EU(Ireland) region.

Login to your AWS account and then search for S3 in the AWS services box. Click on S3 in the search results. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f30c5a0-s3-1.png",
        "s3-1.png",
        891,
        566,
        "#eaecee"
      ],
      "border": true
    }
  ]
}
[/block]
Click on the + Create bucket button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/84ecd10-s3-2.png",
        "s3-2.png",
        521,
        274,
        "#bcc3c9"
      ],
      "border": true
    }
  ]
}
[/block]
Enter a Bucket name, region and other settings that you may need to configure
Complete your setup by selecting your logging, versioning, and encryption preferences. For this integration, you do not need to make any modifications to the default settings. However, you should check your internal organization's policies to see if you need to modify any of these settings. 

Then click Next.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0aeb412-s3-3.png",
        "s3-3.png",
        691,
        716,
        "#5d879a"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f59cf7a-s3-4.png",
        "s3-4.png",
        694,
        714,
        "#92b2c0"
      ],
      "border": true
    }
  ]
}
[/block]
On this page, you can keep default settings. Again, make sure to check your internal organization's policies to see if you need to modify any of these settings. 

Then click Next.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1af0fea-s3-5.png",
        "s3-5.png",
        684,
        714,
        "#5a8599"
      ],
      "border": true
    }
  ]
}
[/block]
Select Create bucket.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f57101b-s3-6.png",
        "s3-6.png",
        690,
        710,
        "#4a778b"
      ],
      "border": true
    }
  ]
}
[/block]
The bucket you just created should now show up in your S3 console. Note the name of your new bucket, which you will need to use in step 2.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/928170d-s3-7.png",
        "s3-7.png",
        1010,
        267,
        "#f5f7f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 2 - Create an API Key for Your S3 Bucket

In this step, we will create an AWS API key that has write access to the bucket we created in step 1. CleverTap will use this API key to export data to your S3 bucket.

Click on your account name on the top right of the AWS console, and then click on Security Credentials.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/43b4fc0-s3-8.png",
        "s3-8.png",
        195,
        230,
        "#d6d8d9"
      ],
      "border": true
    }
  ]
}
[/block]
Click on Users within the left-nav menu, and then click the Add user button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba3022e-s3-11.png",
        "s3-11.png",
        856,
        436,
        "#e4e5e7"
      ],
      "border": true
    }
  ]
}
[/block]
Enter a name for the new user and check the Programmatic access box. Then click Next.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4805d5b-s3-12.png",
        "s3-12.png",
        899,
        628,
        "#edeeef"
      ],
      "border": true
    }
  ]
}
[/block]
Then click Add user to group. Then click Create group.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffe427d-s3-13a.png",
        "s3-13a.png",
        1238,
        516,
        "#f2f7fa"
      ],
      "border": true
    }
  ]
}
[/block]
Enter a Group name and then click on Create policy.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5624220-s3-13b.png",
        "s3-13b.png",
        1116,
        547,
        "#eff0f1"
      ],
      "border": true
    }
  ]
}
[/block]
Click on the JSON tab.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81bbc55-s3-13c.png",
        "s3-13c.png",
        938,
        592,
        "#ebeced"
      ]
    }
  ]
}
[/block]
Paste the JSON below in the box. Replace "clevertap-example" with the name of the S3 bucket you created in step 1. The permissions defined in this policy will allow CleverTap to get information about your bucket and upload files to it. 
[block:callout]
{
  "type": "success",
  "body": "For more information about AWS API access policies, please review [this post](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_s3_rw-bucket-console.html) from the AWS Blog."
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{\n    \"Version\": \"2012-10-17\",\n    \"Statement\": [\n        {\n            \"Effect\": \"Allow\",\n            \"Action\": [\n                \"s3:ListBucket\"\n            ],\n            \"Resource\": [\n                \"arn:aws:s3:::clevertap-example\"\n            ]\n        },\n        {\n            \"Effect\": \"Allow\",\n            \"Action\": [\n                \"s3:PutObject\"\n            ],\n            \"Resource\": [\n                \"arn:aws:s3:::clevertap-example/*\"\n            ]\n        }\n    ]\n}",
      "language": "json"
    }
  ]
}
[/block]
Click the Review policy button. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09bcba9-s3-policy-1.png",
        "s3-policy-1.png",
        1206,
        723,
        "#fafafb"
      ],
      "border": true
    }
  ]
}
[/block]
Enter a name. Then click Create policy.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dda70d4-s3-policy-2.png",
        "s3-policy-2.png",
        1109,
        722,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]
Go back to the Group page. Search for the policy you just created, assign it to the new group by checking the box next to it, and then click Create group.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07297ba-s3-policy-3.png",
        "s3-policy-3.png",
        999,
        593,
        "#eff0f2"
      ],
      "border": true
    }
  ]
}
[/block]
Now add the User to the group. Click the Next Review button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/95dbeec-s3-13h.png",
        "s3-13h.png",
        1255,
        649,
        "#f8faf9"
      ],
      "border": true
    }
  ]
}
[/block]
Then click Create user. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2516f4c-s3-13i.png",
        "s3-13i.png",
        1232,
        491,
        "#f8f9f9"
      ],
      "border": true
    }
  ]
}
[/block]
On the next page, you will be shown your Access key ID and the Secret access key. These credentials will allow CleverTap to upload files to your S3 bucket. Note these values, which you will use in step 3.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/71c1e9e-s3-13j.png",
        "s3-13j.png",
        1235,
        207,
        "#f8f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 3 - Add Your S3 Bucket Details to CleverTap

Login to your CleverTap account, and go to [this page](https://eu1.dashboard.clevertap.com/AAA-BBB-CCC/my-exports.html). Click on the Settings button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ef722f0-settings1.png",
        "settings1.png",
        1410,
        481,
        "#dfe0e4"
      ],
      "border": true
    }
  ]
}
[/block]
Enter your bucket name from step 1. Enter your Access key ID and the Secret access key from Step 2.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/33df145-s3-setting.png",
        "s3-setting.png",
        1099,
        776,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 4 - Create a New Data Export

Click on the Partner Data -> Exports -> Activity Log -> Create Export 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5ce7991-Activity_Log.png",
        "Activity Log.png",
        1440,
        752,
        "#f5f7f7"
      ]
    }
  ]
}
[/block]

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

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e9c77b8-ezgif.com-video-to-gif_1.gif",
        "ezgif.com-video-to-gif (1).gif",
        600,
        288,
        "#f3f3f5"
      ],
      "border": true
    }
  ]
}
[/block]

[block:embed]
{}
[/block]
CleverTap will now process the export. You can refresh the Activity Log page to see the current status of the export. Once the export is completed, the status for that export will say done.
For Recurring Exports the status will be in Pending .
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fbd1ebc-Activity_Log.png",
        "Activity Log.png",
        1440,
        693,
        "#f5f7f7"
      ]
    }
  ]
}
[/block]
To confirm your event data was successfully exported, login to your AWS account and go to the S3 console. You should see some files uploaded to your S3 bucket as shown in the screenshot below.
You can copy the Request ID from the activity log and search with that in S3 , you should see you respective file there 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4127993-s3-data.png",
        "s3-data.png",
        594,
        474,
        "#e5ebee"
      ],
      "border": true
    }
  ]
}
[/block]
# Export Format


## File Name Format 

The example below shows the file name format for data exports.
  * The export request id is generated when you create a request in the CleverTap dashboard.
  * The timestamp is when the export was run.
  * The event name is event type that is included in the file.
  * For larger exports, we chunk the data across multiple files. The file index notes what file number in the file series it is. We have limited file sizes to 100 MB chunks to make them more consumable.
[block:code]
{
  "codes": [
    {
      "code": "<export request id>-<timestamp of the export run>-<event name>-<yyyymmdd>-<file index>-<database-id>.json",
      "language": "text"
    }
  ]
}
[/block]
## File Data Format
* Files will be split by Event Names for Event Exports , each file will all event data for the given period for the Event 

## JSON

The first line of the file contains the event name. After the first line, each line is JSON describing the timestamp, object id, and event properties.
[block:code]
{
  "codes": [
    {
      "code": "{\n\t\"profile\": {\n\t\t\"identity\": \"dqsndckfk234\"\n\t},\n\t\"ts\": 20171109000015,\n\t\"eventProps\": {\n\t\t\"ct_connected_to_wifi\": \"false\",\n\t\t\"ct_bluetooth_version\": \"ble\",\n\t\t\"ct_bluetooth_enabled\": \"false\",\n\t\t\"ct_sdk_version\": 30107,\n\t\t\"ct_latitude\": -6.1975594,\n\t\t\"ct_longitude\": 106.52913,\n\t\t\"ct_os_version\": \"5.1.1\",\n\t\t\"ct_app_version\": \"2.30.1\",\n\t\t\"ct_network_carrier\": \"3\",\n\t\t\"ct_network_type\": \"4G\"\n\t}\n}",
      "language": "json"
    }
  ]
}
[/block]
## CSV
CSV files will be comma delimited and will have each events in separate rows .


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aa71f9f-Screenshot_2020-02-28_at_12.53.22_PM.png",
        "Screenshot 2020-02-28 at 12.53.22 PM.png",
        2032,
        798,
        "#eeefef"
      ]
    }
  ]
}
[/block]
## XML
Will have the timeStamp , eventName followed by  eventProperties

[block:code]
{
  "codes": [
    {
      "code": "<Event>\n    <ts>20200220130735</ts>\n    <eventName>Export Custom Event</eventName>\n    <profile>\n        <all_identities>exportProfile+81@clevertap.com</all_identities>\n        <platform>Web</platform>\n        <email>exportProfile+81@clevertap.com</email>\n    </profile>\n    <deviceInfo>\n        <browser>Others</browser>\n    </deviceInfo>\n    <eventProps>\n        <entry>\n            <key>CT Source</key>\n            <value>API</value>\n        </entry>\n        <entry>\n            <key>Category</key>\n            <value>Mens Watch</value>\n        </entry>\n        <entry>\n            <key>Product name</key>\n            <value>Casio Chronograph Watch</value>\n        </entry>\n        <entry>\n            <key>Price</key>\n            <value>59.99</value>\n        </entry>\n        <entry>\n            <key>Currency</key>\n            <value>USD</value>\n        </entry>\n    </eventProps>\n</Event>",
      "language": "typescript"
    }
  ]
}
[/block]
## Parquet
Will have timestamp ,eventName and eventProperties for each event 
[block:callout]
{
  "type": "info",
  "body": "Parquet, an open source file format for Hadoop. Parquet stores nested data structures in a flat columnar format.",
  "title": "Parquet File Format"
}
[/block]