---
title: Setup
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
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

1. Open your AWS console
2. In Amazon EventBridge > Amazon EventBridge Partners, click **Set up** under the CleverTap partner listing. It opens the *Set up event source* page.
3. Copy your AWS account information: Click **Copy** to copy your AWS account number to your clipboard.
4. Open your CleverTap dashboard
5. Navigate to your *Settings > Partners > Exports > AWS*

<Image title="EB config.png" alt={1180} className="border" border={true} src="https://files.readme.io/32bf8d8-EB_config.png" />

6. Paste the AWS account ID that you copied above in the **AWS Account ID** field.
7. In **AWS region** drop-down box, select the AWS region to receive events. 
8. Click **Save**. The event source name appears in AWS EventBridge. It may take a couple of minutes for the settings to be saved. 

## Part II: Associating event source to designated event bus in AWS console

To establish an event connection to Amazon EventBridge, your CleverTap event source needs to be associated with the event bus in Amazon EventBridge. The CleverTap event source created in Part I above appears in the **Amazon EventBridge > Partner events sources**. You can then select the event source name and associate it with an event bus.\
Once a connection is established, you can set your rules and targets for Amazon EventBridge to redirect events to an AWS service. For more details, see the [Amazon EventBridge documentation.](https://docs.aws.amazon.com/eventbridge/index.html) 

## How to send events to EventBridge

There are two ways events can be sent from CleverTap to EventBridge. 

* Via campaigns
* Via Journeys
