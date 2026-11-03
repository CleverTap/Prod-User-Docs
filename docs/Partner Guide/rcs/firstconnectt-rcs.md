---
title: FirstConnectt
excerpt: RCS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

FirstConnectt is a Communications Platform as a Service (CPaaS) provider that enables businesses to engage customers across multiple channels. Its integration with CleverTap lets businesses send Rich Communication Services (RCS) campaigns directly from the CleverTap dashboard using FirstConnectt's RCS infrastructure, with delivery report tracking for delivery status and visibility into campaign performance.

<Callout icon="📘" theme="info">
  #### Private Beta

  Generic RCS is an integration method that connects Alot Solutions to CleverTap. Generic RCS is available as part of the RCS Connect add-on and is currently in Private Beta for select CleverTap accounts. For early access to this feature, contact your Customer Success Manager or Account Manager.
</Callout>

Businesses can use FirstConnectt with CleverTap for the following use cases:

- Send RCS campaigns using approved templates.
- Trigger transactional and promotional messages based on CleverTap segments and user behavior.
- Track delivery status and inbound user messages using CleverTap callbacks.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and supported by FirstConnectt. For any questions or issues related to this integration, contact [FirstConnectt Support](mailto:care@firstconnectt.com).
</Callout>

# Prerequisites

Before you configure FirstConnectt as your RCS provider in CleverTap, ensure that you have the following:

- A CleverTap account with the RCS Generic Campaigns feature enabled.
- An active FirstConnectt account with RCS Services access.
- A provisioned, active RCS Agent in FirstConnectt. For more information, refer to RCS Agent Onboarding.
- RCS-approved message templates in your FirstConnectt dashboard.
- An API key for your FirstConnectt account, available from your FirstConnectt point of contact.
- (Optional) An SMS Sender ID and SMS body parameters from FirstConnectt, for SMS fallback.
- (Optional) Distributed Ledger Technology (DLT) registration, including the Principal Entity ID and the approved template IDs, for SMS fallback when you send messages in India.

# RCS Agent Onboarding

An RCS Agent is a brand's verified business profile (the sender). FirstConnectt provisions the RCS Agent, and mobile carriers approve it. CleverTap uses the RCS Agent ID as the RCS Sender ID during provider setup to authorize and deliver RCS messages.

If you are new to FirstConnectt or have not completed RCS Agent onboarding, complete the onboarding in the FirstConnectt platform before you set up the provider in CleverTap.

The onboarding process includes the following steps:

- Registering the business with FirstConnectt as an RCS sender and creating the brand profile (name, logo, description, and website).

* Submitting brand and compliance details for carrier review and obtaining approval for RCS messaging.
* Completing the FirstConnectt verification checks, such as domain or business verification.
* Receiving the RCS Agent ID from FirstConnectt. To find the RCS Agent ID, go to _Config_ > _RCS Agent_ in the FirstConnectt platform. You enter this value in the _RCS Sender ID_ field in CleverTap during provider setup.

# Set Up Generic RCS on CleverTap Dashboard

This section covers how to add FirstConnectt as an RCS provider on the CleverTap dashboard.

To add the provider, perform the following steps:

1. On the CleverTap dashboard, go to _Settings_ > _Channels_ > _SMS_, and then select the _SMS Connect_ tab.


   <Image src="https://files.readme.io/0031f19943d70063956914d8a9a08c72f276f1681aac468e3502b5e4a243193d-Screenshot_2026-10-21_at_16.46.26.png" alt="SMS Connect tab present in the SMS Channel" align="center" caption="Provider Configuration" border={true} />


2. Click **+ Add Provider**.

3. Under _Provider_, select _Generic RCS Provider_ from the dropdown and then enter the _Nickname_.
   <Callout icon="📘" theme="info">
     #### Whitelist IPs

     For additional security, whitelist the following IPs on your SMS settings: `13.124.142.16`, `52.79.51.100`.
   </Callout>

4. Set up API.

5. Configure RCS settings.

6. Configure SMS Fallback.

7. Select Mark as Default to set Alot Solutions as your primary RCS provider for all RCS messaging in CleverTap.

8. Click Send Test to verify the integration. Enter the following details:
   - Country Code and Mobile Number: Enter the recipient's country code and mobile number for the test.
   - RCS Message: Enter the message content to send via RCS.

9. Click Save after verifying that the integration was successful.

## Set Up API

This section covers how to enter the FirstConnectt messaging endpoint, authentication headers, and concurrency details in CleverTap.

To set up the API, perform the following steps:

1. Under _Messaging Endpoint_, enter the following details. The messaging endpoint is the API URL that FirstConnectt uses to receive RCS send requests from CleverTap.


   <Image src="https://files.readme.io/b9b15cccec2cacb814735010cf47417a03a225e48dfa374baf4eedaa9edfebc2-image.png" align="center" caption="Set Up API" border={true} />


   | Field           | Value                                                      |
   | --------------- | ---------------------------------------------------------- |
   | _Request Type_  | `POST`                                                     |
   | _HTTP Endpoint_ | `https://connecttone.io/api/v1/rcs/clevertap_rcs_over_sms` |
2. Under _Headers_, add the following key-value pairs. FirstConnectt uses bearer token authentication passed as an HTTP header.


   <Image src="https://files.readme.io/4fa8cd34ae894cab9e8fb5e210635e389b1842e1171b16290df1cb4653488128-image.png" align="center" caption="Provider Configuration - Headers Section" border={true} />


   | Key             | Value                                                                                         |
   | --------------- | --------------------------------------------------------------------------------------------- |
   | `Authorization` | `Bearer <API_KEY>`<br /><br />Replace `<API_KEY>` with the API key provided by FirstConnectt. |
   | `Content-Type`  | `application/json`                                                                            |
3. (Optional) In the _Custom Concurrency_ field, enter the maximum number of parallel requests that CleverTap sends to the FirstConnectt API at any given time. Set this value based on the throughput limit that FirstConnectt recommends. If you leave the field blank, CleverTap applies its default concurrency settings. The maximum supported rate is 4,600 requests per second.
   <Callout icon="🚧" theme="warn">
     #### Higher Concurrency Limitations

     Setting a higher concurrency than FirstConnectt supports may result in rate limiting, message drops, or delayed delivery reports. Confirm the recommended limit with FirstConnectt before setting this value.
   </Callout>

## Configure RCS Settings

The RCS Config section maps your FirstConnectt RCS Agent to CleverTap.

| Field           | Description                                                                                                                                                 |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RCS Sender ID   | Enter the RCS Agent ID from _Config > RCS Agent_ in the FirstConnectt platform. This is the verified business sender identity used to deliver RCS messages. |
| Callback Config | Contact your FirstConnectt point of contact to share the CleverTap callback URL and complete the callback configuration on the FirstConnectt platform.      |

<Callout icon="📘" theme="info">
  #### Callback URL Generation

  The Delivery Report Callback URL is generated automatically by CleverTap once the provider is saved. Copy it from the _Provider Setup_ page and share it with FirstConnectt support.
</Callout>

## Configure SMS Fallback

SMS fallback helps deliver the message when RCS delivery fails because of device incompatibility, lack of internet access, or carrier restrictions. If the recipient's device does not support RCS or is offline, CleverTap automatically sends the message as an SMS.&#x20;

If you send messages in India, DLT registration is mandatory under the Telecom Regulatory Authority of India (TRAI) regulations.

To enable SMS fallback, configure the following:


<Image src="https://files.readme.io/37a68035fb11890717571c9af96a90f3a56467015f0f09b7c161cd2049b8458f-Screenshot_2026-10-21_at_16.59.50.png" align="center" caption="Configure SMS Fallback" border={true} />


- **SMS Sender ID:** Required when SMS fallback is enabled.
- **SMS Body Parameters:** Add the key-value pairs required by your SMS fallback configuration.

<Callout icon="📘" theme="info">
  #### DLT Registration

  If you are sending messages in India, DLT (Distributed Ledger Technology) registration is mandatory. Configure the **Principal Entity ID** and approved template IDs as per TRAI regulations.
</Callout>

# Add Template

The Add Template feature lets you create, manage, and deploy RCS message templates for your campaigns. If FirstConnectt requires template approval, create the template in the FirstConnectt portal first, then create the same template in CleverTap under _Templates_. Use the exact same template name in both systems so submissions map correctly.

To access templates, go to _Settings > Channels > SMS > SMS Connect_, open your FirstConnectt provider, and select the _Template_ tab. CleverTap supports the following three template formats:

- [Text](doc:rcs-message-templates#text)
- [Rich Card](doc:rcs-message-templates#rich-card-template)
- [Carousel Template](doc:rcs-message-templates#carousel)

## Create Campaign

For detailed instructions on creating an RCS campaign with FirstConnectt as your provider, refer to [Create SMS Campaign](doc:rcs-create-message).

## Create Journey

For detailed instructions on creating an RCS journey using FirstConnectt as your provider, refer to [Journeys.](doc:journeys)&#x20;

<br />
