---
title: Amazon EventBridge
excerpt: ''
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

CleverTap now enables you to send events to the [Amazon EventBridge](https://aws.amazon.com/eventbridge/) ecosystem. Events can flow from CleverTap via Amazon EventBridge to various other services such as AWS Lambda, Amazon SNS, Amazon SQS, Redshift, Firehose and Amazon Kinesis streams.

Once integrated with Amazon EventBridge, you can send the CleverTap events into any service in your AWS account.

# Pre-requisites

* On AWS
  * AWS account ID
  * AWS region to be associated to
* On CleverTap
  * AWS Account credentials
  * Data stream setup

# Integrate EventBridge with CleverTap

This process involves the following three steps:

1. [Find Amazon EventBridge Event Source Details](doc:amazon-eventbridge#find-amazon-eventbridge-event-source-details).
2. [Configure CleverTap Event Source](doc:amazon-eventbridge#configure-clevertap-event-source).
3. [Associate Event Source with Designated Event Bus in AWS Console](doc:amazon-eventbridge#associate-event-source-with-designated-event-bus-in-aws-console).

## Find Amazon EventBridge Event Source Details

To find the event source details:

1. Navigate to Amazon EventBridge Partners from the Amazon EventBridge dashboard.
2. Click **Set up** under the CleverTap partner listing. The *Set up event source* page opens.
3. Click **Copy** to copy your AWS account number to your clipboard and save it. You will require these details for configuring the CleverTap dashboard.

## Configure CleverTap Event Source

To configure CleverTap Event Source:

1. Log in to your CleverTap account and navigate to the *Settings* > *Partners* page.

<Image title="Navigate to Partners page from the CleverTap dashboard" alt={2854} align="center" border={true} src="https://files.readme.io/2685d0f-Navigate_to_Partners_page.png">
  Navigating to Partners Page
</Image>

2. Hover on the *Amazon EventBridge* icon and click **Integrate**. The *Integrate raw data partner - Amazon EventBridge* popup opens on the right side of the screen.

<Image title="Hover on Amazon EventBridge icon and click Integrate" alt={2400} align="center" border={true} src="https://files.readme.io/a1bb7e6-Click_Integrate.png">
  Integrate Amazon EventBridge
</Image>

3. Enter the following Amazon service details and click **Integrate**:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <p>Field</p>
      </th>

      <th>
        <p>Description</p>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <p>Partner Nickname</p>
      </td>

      <td>
        <p>Enter the <em>Nickname</em> for your integration.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>AWS Account ID</p>
      </td>

      <td>
        <ul><li>Enter the AWS account number obtained in <em>Step 3</em> of <a href="doc:amazon-eventbridge#find-amazon-eventbridge-event-source-details">Find Amazon EventBridge Event Source Details</a>.</li><li>This user property is used as an identifier when sending event data to Amazon EventBridge.</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        Region
      </td>

      <td>
        The AWS account region. The events are sent to the selected region.
      </td>
    </tr>
  </tbody>
</Table>

<Image title="Enter Amazon EventBridge Project Details and click Integrate" alt={2394} align="center" border={true} src="https://files.readme.io/d374259-Integrate_raw_data_partner_-_Amazon_EventBridge.png">
  Enter Amazon EventBridge Project Details to Integrate
</Image>

After successful integration, the *Integrated* tag displays against *Amazon EventBridge* on the *Partners List* page.

<Image title="Integrated tag denotes that the Amazon Eventbridge integration is successful" alt={2852} align="center" border={true} src="https://files.readme.io/32b704a-Integrated_tag.png">
  Amazon EventBridge Integration Successful
</Image>

## Associate Event Source with Designated Event Bus in AWS Console

To establish an event connection to Amazon EventBridge, your CleverTap event source must be associated with the event bus in Amazon EventBridge. You can now see the CleverTap event source, created in *Step 3* of [Configure CleverTap Event Source](doc:amazon-eventbridge#configure-clevertap-event-source), under the *Partner* events sources on the Amazon EventBridge dashboard. To associate the event source with the designated event bus in the AWS console:

1. Select the event source name and associate it with an event bus. 
2. After establishing the connection, set your rules and targets for Amazon EventBridge to redirect events to an AWS service. For more information, refer to the [Amazon EventBridge documentation](https://docs.aws.amazon.com/eventbridge/index.html).

# Send Events to EventBridge

There are two ways events can be sent from CleverTap to EventBridge. 

* Via campaigns
* Via Journeys

### Sending via Campaigns

* Navigate to Campaigns from the CleverTap dashboard and click on ‘**+ Campaign**’. 
* Select **Amazon EventBridge** from the channels list. 

<Image title="Select Amazon EventBridge from the channels dropdown" alt={854} align="center" border={true} src="https://files.readme.io/8abeb70-EB_Campaign.png">
  Select Amazon EventBridge from the Channels List
</Image>

* Select the appropriate option on '**Type'**, '**When**' pages
* Select the events to be sent to Amazon EventBridge on the '**Who**' page. 
* Once you reach the '**What'** page, you will be able to choose what to send to Amazon EventBridge

<Image title="Define Amazon EventBridge Message Content" alt={1113} align="center" border={true} src="https://files.readme.io/7ec2ed0-EB_Campaign_What.png">
  Define Amazon EventBridge Message Content
</Image>

* If the EventBridge connection is not set up, you will not be able to proceed. The ‘**Modify settings**’ link will navigate you to the configuration section for Amazon EventBridge.
* You can also choose the details to send in the payload - Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens
* Click **‘Continue’** to proceed to the **'Setup'** page, and then to the **'Overview'**&#x70;age and then schedule the campaign

### Sending via Journeys

* When you are creating a journey, you can drag a ‘**Partner**’ node from engage node section

<Image title="Drag and drop Amazon EventBridge engagement node" alt={1216} align="center" border={true} src="https://files.readme.io/4667f6c-EB_Journey_node.png">
  Drag and Drop Amazon EventBridge Engagement Node
</Image>

* On the '**Channel Type'** page, click on ‘**Amazon EventBridge**’ to proceed. 

<Image title="Define Amazon EventBridge Message Content" alt={1119} align="center" border={true} src="https://files.readme.io/f3f134d-EB_Journey_what.png">
  Define Amazon EventBridge Message Content
</Image>

* Once you reach the '**What**' page, you will be able to choose what to send to Amazon EventBridge

<Image title="Click Save and Close after Defining the Message Content" alt={1119} align="center" border={true} src="https://files.readme.io/b5ce183-EB_Journey_what.png">
  Click Save and Close after Defining the Message Content
</Image>

* If the EventBridge connection is not set up, you will not be able to proceed. The ‘**Modify settings**’ link will navigate you to the configuration section for Amazon EventBridge.
* You can also choose the details to send in the payload - Email, Identity & CleverTap ID, User profile attributes, GCM / APNS tokens
* Click **‘Save and close’** to save the node
