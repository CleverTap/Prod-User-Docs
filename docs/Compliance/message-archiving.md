---
title: Message Archiving
excerpt: >-
  Learn how to archive outgoing messages in real time to your AWS S3, Azure Blob
  Storage, or GCP bucket using CleverTap’s Message Archiving feature.
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

CleverTap’s Message Archiving feature stores a copy of each outgoing message sent through Campaigns or Journeys, such as Push Notifications, Emails, SMS, or WhatsApp messages, directly to your AWS S3, Azure Blob Storage, or GCP bucket. Storing copies of outgoing messages from Campaigns and Journeys across multiple channels in real time provides evidence of compliance. It also allows access to archived compliance, audit, or customer support communication.

> 📘 Enable Message Archiving
>
> Message Archiving is a paid CleverTap add-on. Because archived messages are written directly to your cloud bucket, your cloud provider also charges you for storage, write requests, data retention, retrieval, and any cross-region data transfer. Check your cloud provider's official documentation for pricing details.<br />To enable it, contact your Customer Success Manager or [CleverTap Support.](https://help.clevertap.com/hc/en-us/requests/new)

Some of the key benefits of archiving your messages are:

- **Audit Readiness:** Maintain a complete record of all user communications to meet compliance requirements.
- **Real-Time Archiving:** Archive messages as they are sent, with minimal impact on delivery performance.
- **Low Maintenance:** Requires minimal setup and ongoing upkeep.

# Supported Channels

Currently, Message Archiving is available for the following channels:

- Email
- Push notifications
- SMS
- WhatsApp

# Introduction to Message Archiving

When the Message Archiving feature is enabled, CleverTap archives every outgoing message in real time to your specified storage destination (AWS S3, Azure Blob Storage, or GCP bucket). Messages are sent through campaigns or journeys, and the archiving process ensures all records are stored before delivery.

> 🚧 Message Delivery Lag
>
> Archiving occurs before delivery. This may introduce slight latency depending on the storage provider's rate limits and network performance.

# Archived File Structure

Each archived message is stored as a compressed JSON file using the `.lz4` format. The file path follows a consistent structure to ensure easy lookup and retrieval.

## File Path Structure

The archived messages are saved in your AWS S3 bucket, Azure Blob Storage, or GCP bucket using a specific key structure, helping organize and retrieve the files efficiently. The general structure of the file path is as follows:

```
sent_messages/<channel>/<yyyymm>/<campaign_id>/<user_id>/message_id.json.lz4

where:
<*> = folder
<yyyymm> = year, month // batchId(<yyyymmdd> year, month, day) from the message
<channel> = Push OR Sms OR Email or WhatsApp 
<user_id> = MD5 encoded data of Device Identity if exists, else, Customer Identity for Push, Mobile Number in CountryCode format for Sms & Whatsapp, EmailId for Email channel
message_id.json.lz4 is a lz4 compressed file representing one message. // support lz4 compression

```

An example file path may look like this:

```
sent_messages/WhatsApp/202409/1725435360/6e6d748a7cc752fbe4f72c777cc50a74/49482d489b871510eeff7db9a8ab443248ad1ea596e5108e02d16ab5b2ea47db.json.lz4
```

## Sample JSON Payloads

The archived files on the AWS contain a JSON payload representing the final message sent to the user. Below are examples of the JSON structures by channel.

```json Push
// Android Firebase Cloud Messaging (FCM) push notification payload
{
    "to": "fcm:kahjszshdvbgfoqhkjahgsdfyp2nhri3oqsny26lpp26ylawiuhse84htexz", // platformId or pushToken.
    "payload": {
        "message": {
            "data": {
                "wzrk_pn": "true", // indicates a push notification.
                "wzrk_id": "1737624196_20250123", // unique identifier for the notification.
                "wzrk_pivot": "wzrk_default", // pivot point for message routing.
                "nt": "Exclusive Flash Sale - 50% Off!", // notification title.
                "nm": "Hurry! Limited-time offer just for you. Tap to claim your 50% discount before it expires!", // notification message body.
                "wzrk_ttl": "1737624843", // time-to-live (TTL) for the notification in epoch format.
                "wzrk_rnv": "true", // determines if the notification should be re-notified.
                "wzrk_push_amp": "false", // push amplification flag.
                "wzrk_dt": "FIREBASE", // delivery platform (for example, Firebase, APNS).
                "wzrk_pid": "1737624196", // push notification ID.
                "wzrk_cid": "", // campaign ID (if applicable).
                "wzrk_bc": "", // background color (if applicable).
                "wzrk_bi": "2", // badge icon reference (if applicable).
                "pr": "", // notification priority (if specified).
                "wzrk_acct_id": "YOUR_WZRK_ACCOUNT_ID", // account identifier.
                "wzrk_ck": "1400000001" // click tracking identifier.
            },
            "token": "kahjszshdvbgfoqhkjahgsdfyp2nhri3oqsny26lpp26ylawiuhse84htexz", // device token for push delivery.
            "messageConfig": {
                "ttlInSeconds": "600s", // notification time-to-live in seconds.
                "priority": "HIGH" // priority level for push delivery.
            }
        },
        "dryRun": false // indicates whether this message is a test notification.
    },
    "platform": "Android",
    "message_id": "6f44a05d42a1e1d282ef3bf8bb6591ccf04e49f9c5c33f2438db6275cdc410fd", // Unique hash per message.
    "version": 1, // Numerical version of the json structure.
    "sent_at": 1737624243036, // Message Archiving epoch in millis.
    "campaign_id": 1737624196, // Unique hash per message.
    "user_id": 45142258, // CleverTap internal Device Identity if exists, else, Customer Identity.
  "campaign_name": "Flat Offer Sale Campaign", // the campaign Name for current campaign, will always exist.
  "identity": // custom identifier
     [
      "mani@clevertap.com"
     ]
}

// iOS Apple Push Notification Service (APNS) push notification payload
{
    "to": "74bfe488e5b5e0139fc378ff9410ea4ce6a666d17603b49922a009a6383b56ee", // Device token for APNS push delivery.
    "payload": {
        "W$id": "1734938686_20241223", // Unique identifier for the notification.
        "wzrk_acct_id": "YOUR_WZRK_ACCOUNT_ID", // Account identifier.
        "W$rnv": true, // Determines if the notification should be re-notified.
        "W$dt": "APPLE", // Delivery platform (APNS for iOS).
        "aps": {
            "interruption-level": "active", // Defines the interruption level of the push.
            "relevance-score": 0.5, // Determines notification priority based on relevance.
            "alert": {
                "title": "Your Exclusive Discount Inside!", // Notification title.
                "body": "We've reserved a 50% OFF deal for you. Tap to unlock savings now!" // Notification body message.
            },
            "mutable-content": 1 // Allows content modification before displaying.
        },
        "W$pivot": "wzrk_default" // Pivot point for message routing.
    },
    "token": "74bfe488e5b5e0139fc378ff9410ea4ce6a666d17603b49922a009a6383b56ee", // Device token for push delivery.
    "collapseId": "1734938686", // Used for collapsing multiple similar notifications.
    "expiration": 1734939302, // Expiration time in epoch format.
    "platform": "iOS",
    "message_id": "245eb2b120c2768d30c42cb343832d579e8413ef1bce25cb4837e91d60630e5b", // Unique hash per message.
    "version": 1, // Numerical version of the JSON structure.
    "sent_at": 1734938702745, // Message archiving epoch in milliseconds.
    "campaign_id": 1734938686, // Unique hash per message.
    "user_id": 45142253, // CleverTap internal Device Identity if exists, else, Customer Identity.
  "campaign_name": "Flat Offer Sale Campaign", // The campaign Name for the current campaign, will always exist.
  "identity": // Custom identifier used to uniquely associate a message archive record with an account.
      [
       "mani@clevertap.com" 
      ]
}
```
```json Email
{
  "to": "mani@clevertap.com", // Recipient email
  "subject": "🚀 Exclusive Offer: 50% Off Just for You!", // Engaging subject line
  "from_name": "RepeatFrequently", // Proper sender name
  "from_address": "hello@orders.repeatfrequently.com", // Sender email
  "html_body": "<html><body><h1>Exclusive Deal Just for You!</h1><p>Get <strong>50% OFF</strong> on your next order. Hurry, limited-time offer!</p><br/><a href='https://www.yourlink.com'>Claim Your Offer</a><br/><img alt='' border='0' height='1' width='1' src='https://sk1.wizrocketmail.net/r?e=Kw1qHB8...'></body></html>", // Optimized HTML email
  "plainText_body": "Exclusive Deal Just for You! Get 50% OFF on your next order. Hurry, limited-time offer! Claim your offer: https://www.yourlink.com", // Matching plain text
  "amp_body": "<!doctype html><html ⚡4email><head><meta charset='utf-8'><script async src='https://cdn.ampproject.org/v0.js'></script><style amp4email-boilerplate>body{visibility:hidden}</style></head><body><h1>Exclusive Deal Just for You!</h1><p>Get <strong>50% OFF</strong> on your next order. Hurry, limited-time offer!</p><a href='https://www.yourlink.com'>Claim Your Offer</a></body></html>", // AMP email version
  "headers": "From: RepeatFrequently <hello@orders.repeatfrequently.com>,To: mani@clevertap.com,Subject: 🚀 Exclusive Offer: 50% Off Just for You!,MIME-Version: 1.0,Content-Type: multipart/alternative;",
  "message_id": "6c79694bee2f362fdbe14f7318e5706b26786b2008beca4490521e76c850f913", // Unique message identifier
  "version": 1, // JSON structure version
  "sent_at": 1713111244729, // Timestamp when the message was sent (epoch format)
  "campaign_id": 1653063304, // Unique campaign identifier
  "user_id": 17004116, // User identifier
  "campaign_name": "Flash Sale Email Campaign", // Updated campaign name
  "identity": // custom identifier
     [
      "+918112333333",
      "mani@clevertap.com",
      "Mani121"
     ]
}
```
```json SMS
{
  "to": "PhoneNumber", // ("15555555555")
  "body": "🚀 Exclusive Deal! Get 50% OFF on your next purchase. Use code: FLASH50. Hurry, offer ends soon! Tap here: www.yourlink.com", // SMS content
  "provider": "twilio", // SMS provider
  "message_id": "9f8c76ccdaf0895515f813af702670324d996296788652b50b3475d6fe6e719a", // Unique message identifier
  "version": 1, // JSON structure version
  "sent_at": 1712915161639, // Timestamp when the SMS was sent (epoch format)
  "campaign_id": 1712915111, // Unique campaign identifier
  "user_id": 17740451, // User identifier
  "campaign_name": "Flash Sale SMS Campaign", // Name of the SMS campaign
  "identity": // custom identifier
     [
      "+918468817470",
      "chhaya+arc@clevertap.com",
      "chhayaArc121"
     ]
}
```
```json WhatsApp
{
  "to": "PhoneNumber", // ("15555555555")
  "body": {
    "header": {
      "type": "location",
      "media": {
        "latitude": 25.25231501881499,
        "longitude": 86.98385572969912,
        "name": "DLH Park",
        "address": "7X2M+WFX, P&T Colony, Adampur, Bhagalpur, Bihar 812001, India"
      }
    },
    "body": {
      "type": "text",
      "text": "Hi John! Thank you for registering for GMAT. Please refer to the link for your Exam Center location in Bhagalpur.",
      "replacements": ["John", "Bhagalpur"]
    },
    "footer": null,
    "limited_time_offer": null,
    "buttons": []
  },
  "provider": "nexmo", // WhatsApp service provider (Vonage)
  "message_id": "b6e644a27196e6db63c552c8a3babb55f930dbc743bf5c35507621dee1c163cf", // Unique message identifier
  "version": 1, // JSON structure version
  "sent_at": 1712910207584, // Timestamp when the message was sent (epoch format)
  "campaign_id": 6153, // Unique campaign identifier
  "journey_id": 1255, // Journey ID if part of a sequence
  "user_id": 17633706, // User identifier
  "campaign_name": "My WhatsApp Message", // Name of the WhatsApp campaign
  "journey_name": "Check Journey", // Name of the journey
  "journey_node_id": 6, // Node identifier in the journey
  "identity": // custom identifier
    [
      "+918468817470",
      "chhaya+arc@clevertap.com",
      "chhayaArc121"
    ]
}
```

## Browse Archived Message From AWS S3 Bucket

The following image shows the steps to browse the archived messages on the AWS S3 bucket:


<Image src="https://files.readme.io/6dbc6e767772b915a0d9db56f9a4484df2c91b36c829f06d6f781d2ad4721e99-AWS_Slow.gif" alt="Sample Message Archive" align="center" border={true} />


# Set Up Message Archiving

## Prerequisites

Before setting up Message Archiving, check that you have the following:

- An active CleverTap account.
- An AWS S3 bucket, Azure Blob Storage, or GCP bucket in the same region as your CleverTap account region.

## Steps to Set Up Message Archiving

To set up message archiving, perform the following steps:

1. **Configure AWS S3 bucket, Azure Blob Storage, or GCP bucket on CleverTap dashboard**: Provide the necessary details for your AWS S3 bucket, including the bucket name and region. For more information, refer to [Configure AWS S3 Bucket on CleverTap Dashboard](doc:data-export-to-aws-s3#configure-s3-bucket-details-on-clevertap-dashboard), [Configure Azure Blob Storage](doc:microsoft-azure) or [Configure GCP Bucket on CleverTap Dashboard.](doc:data-export-to-gcp#configure-clevertap-dashboard) Note that for setting up message archiving with AWS S3, configure the bucket with an appropriate IAM policy. For more information, refer to [Add IAM Policy to S3 Bucket](doc:data-export-to-aws-s3#add-iam-policy-to-s3-bucket-on-aws-console).
2. **Configure Data Retention Policy**: You must set up the data retention policy for your AWS S3 bucket according to your organizational needs directly in the AWS S3 console.

For more information and detailed configuration steps, refer to [Data Export to AWS S3](doc:data-export-to-aws-s3#create-an-aws-s3-bucket), [Data Export to Azure](doc:microsoft-azure#create-a-new-data-export), or [Data Export to GCP](doc:data-export-to-gcp#create-a-new-data-export).

# Security and Data Protection

Clevertap is committed to safeguarding your data. We ensure the protection of your data by implementing the following measures:

- **Data in Transit:** All data is transmitted using the HTTPS protocol, ensuring secure data transfer between CleverTap and your AWS S3 bucket, Azure Storage Blob, or GCP bucket.
- **Data at Rest:** The security of data at rest within the AWS S3 bucket, Azure Storage Blob, or GCP bucket is the customer's responsibility. This includes ensuring that proper encryption and access controls are in place.

# FAQs

Explore concise troubleshooting tips and FAQs for Messaging Archival in this section.

The following information provides helpful troubleshooting tips and common questions about Message Archiving.

#### **Q: Is there a user interface for Message Archiving?**

A: No, the Message Archiving feature operates without a user interface. Once enabled, it seamlessly archives messages to your AWS S3 bucket, Azure Storage Blob, or GCP bucket. We will provide a user interface in the future.

#### **Q: How long is the data stored?**

A: You define the data retention policy within your AWS S3 bucket, Azure Storage Blob, or GCP bucket settings.

#### **Q: Who bears the cost of storage?**

A: The customer bears all storage and data transfer costs associated with their AWS S3 bucket, Azure Storage Blob, or GCP bucket.

#### **Q: Does archiving happen in real-time?**

A: Yes, message archiving occurs in real-time, ensuring that all communications are promptly saved.

#### **Q: What happens if my AWS credentials are invalid?**

A: If your AWS credentials become invalid, CleverTap cannot archive messages to your AWS S3 bucket or Azure Storage Blob, and no further campaign messages will be sent to your users. This is to ensure that every message that is sent out is archived first.

#### **Q: How are retries handled?**

A: If the bucket is unreachable, we will retry up to three times for AWS errors (such as AccessDenied).  CleverTap handles the AWS S3 rate limit errors.

#### **Q: What happens if archiving fails ?**

If the archiving fails after multiple retries, messages are marked as  _Failed to Archive Message_.


<Image src="https://files.readme.io/4b8eca3f061741697bca2f07b0307f88efd5ee2f3b5600a1f70bbe72865356d1-image.png" alt="Failed to archive message" align="center" border={true} />


#### **Q: Why does my archive**`sent at`**&#x20;timestamp differs slightly from the actual send time?**

A: The message is archived just before it is sent to the end user, due to which slight delays can occur. This may lead to minor differences in timestamps.

#### **Q: How does CleverTap send archived data to customers?**

A: CleverTap sends data in a compressed form to the customer's chosen location, such as the AWS S3 bucket, Azure Storage Blob, or GCP bucket. You can view the JSON format for each channel from [Sample Message Archiving JSON payloads](doc:messaging-archiving#sample-json-payloads).

#### **Q: What file format does CleverTap use for the message archive?**

A: The archived messages are stored as LZ4 compressed JSON files.

#### **Q: How does CleverTap charge for data transfer to another AWS region or outside AWS (Azure/GCP)?**

A: The cost is determined per the cloud provider's data transfer charges if a customer transfers data to another AWS region. Transfers outside AWS (Azure/GCP) are classified as data-out-to-internet and are charged based on the cloud provider's pricing model, which may include a base cost and tiered pricing.

#### **Q: How does CleverTap handle message archiving for AMP emails?**

A: CleverTap archives every sent message, ensuring a comprehensive record of communication.

#### **Q: Does CleverTap store attachments in archived messages?**

A: CleverTap optimizes storage by archiving key details of Email and WhatsApp campaigns.

#### **Q: How does CleverTap handle sensitive data in archived messages?**

A: Archived messages may include CleverTap IDs (CTID) and the customer’s unique user ID. Customers can configure their campaigns based on their data privacy policies.

#### **Q: How can customers access archived messages?**

A: CleverTap ensures customers fully control their archived messages by delivering the messages to their preferred storage location. Customers can retrieve and manage their data according to their specific compliance and security policies.
