---
title: Amazon EventBridge
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

CleverTap now enables you to send events to the [Amazon EventBridge](https://aws.amazon.com/eventbridge/) ecosystem. Events can flow from CleverTap via Amazon EventBridge to various other services such as AWS Lambda, Amazon SNS, Amazon SQS, Redshift, Firehose and Amazon Kinesis streams.

Once integrated with Amazon EventBridge, you can send the CleverTap events into any service in your AWS account.

# Pre-requisites

* On AWS
  * AWS account ID
  * AWS region to be associated to
* On CleverTap
 * AWS Account credentials
 * Data stream setup

# How to establish the integration

Establishing AWS integration is a 2 step process

## Part I: Configuring CleverTap event source 
* Open your AWS console
* In Amazon EventBridge > Amazon EventBridge Partners, click **Set up** under the CleverTap partner listing. It opens the **Set up event source** page.
* Copy your AWS account information: Click **Copy** to copy your AWS account number to your clipboard.
* Open your CleverTap dashboard
* Go to your **Settings > Partner data exports > AWS Integrations**
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/32bf8d8-EB_config.png",
        "EB config.png",
        1180,
        392,
        "#fcfcfd"
      ],
      "border": true
    }
  ]
}
[/block]
* Paste the AWS account ID that you copied in above in the **AWS Account ID** field.
* In **AWS region** drop-down box, select the AWS region to receive events. 
* Click **Save**. The event source name appears in AWS EventBridge. It may take a couple of minutes for the settings to be saved. 

## Part II: Associating event source to designated event bus in AWS console

To establish an event connection to Amazon EventBridge, your CleverTap event source needs to be associated to the event bus in Amazon EventBridge. The CleverTap event source created in Part I above appears in the **Amazon EventBridge > Partner events sources**. You can then select the event source name and associate it with an event bus.
Once a connection is established, you can set your rules and targets for Amazon EventBridge to redirect events to an AWS service. For more details, see the [Amazon EventBridge documentation.](https://docs.aws.amazon.com/eventbridge/index.html) 

## How to send events to EventBridge

There are two ways events can be sent from CleverTap to EventBridge. 
* Via campaigns
* Via Journeys

### Sending via Campaigns
* Go to campaigns listing page and click on ‘**+ Campaign**’ green button on the top right corner. 
* Once you reach the channels page, click on ‘**Amazon EventBridge**’ to proceed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8abeb70-EB_Campaign.png",
        "EB Campaign.png",
        854,
        804,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
* Select the appropriate option on '**Type'**, '**When**' pages
* Select the events to be sent to Amazon EventBridge on the '**Who**' page. 
* Once you reach the '**What'** page, you will be able to choose what to send to Amazon EventBridge
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ec2ed0-EB_Campaign_What.png",
        "EB Campaign What.png",
        1113,
        686,
        "#f9fafc"
      ],
      "border": true
    }
  ]
}
[/block]
* If the EventBridge connection is not setup, you will not be able to proceed. The ‘**Modify settings**’ link will navigate you to configuration section for Amazon EventBridge.
* You can also choose the details to send in the payload - Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens
* Click **‘Continue’** to proceed to the **'Setup'** page, and then to the** 'Overview' **page and then schedule the campaign

### Sending via Journeys

* When you are creating a journey, you can drag a ‘**Partner**’ node from engage node section
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4667f6c-EB_Journey_node.png",
        "EB Journey node.png",
        1216,
        761,
        "#f5f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
* On the '**Channel Type'** page, click on ‘**Amazon EventBridge**’ to proceed. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f3f134d-EB_Journey_what.png",
        "EB Journey what.png",
        1119,
        687,
        "#f9fafc"
      ],
      "border": true
    }
  ]
}
[/block]
* Once you reach the '**What**' page, you will be able to choose what to send to Amazon EventBridge
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b5ce183-EB_Journey_what.png",
        "EB Journey what.png",
        1119,
        687,
        "#f9fafc"
      ],
      "border": true
    }
  ]
}
[/block]
* If the EventBridge connection is not setup, you will not be able to proceed. The ‘**Modify settings**’ link will navigate you to configuration section for Amazon EventBridge.
* You can also choose the details to send in the payload - Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens
* Click **‘Save and close’** to save the node