---
title: Alot Solutions
excerpt: RCS Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Alot Solutions is a Communications Platform as a Service (CPaaS) provider that enables businesses to engage customers across multiple channels. Its integration with CleverTap lets businesses send RCS campaigns directly from the CleverTap dashboard using Alot Solutions' RCS infrastructure, with delivery report (DLR) tracking for delivery status and visibility into campaign performance.

<Callout icon="📘" theme="info">
  #### Private Beta

  Generic RCS is an integration method that connects Alot Solutions to CleverTap. Generic RCS is available as part of the RCS Connect add-on and is currently in Private Beta for select CleverTap accounts. For early access to this feature, contact your Customer Success Manager or Account Manager.
</Callout>

Here are a few use cases where businesses can integrate Alot Solutions with CleverTap:

- Send RCS campaigns using approved templates.

* Trigger transactional and promotional messages based on CleverTap segments and user behavior.
* Track delivery status and inbound user messages using CleverTap callbacks.

<Callout icon="🚧" theme="warn">
  #### Support for Integrations

  This integration is managed and supported by Alot Solutions. For any questions or issues related to this integration, contact [Alot Solutions support](mailto:support@alotsolutions.com).
</Callout>

## Prerequisites

Before configuring Alot Solutions as your RCS provider in CleverTap, ensure the following are in place:

- The RCS Generic Campaigns feature is enabled on your CleverTap account.
- You have an active Alot Solutions account with RCS Services access.
- A provisioned, active RCS Agent in Alot Solutions.
- RCS-approved message templates in your Alot Solutions dashboard.
- An API key for your Alot Solutions account, available from your Alot Solutions point of contact.
- (Optional) An SMS Sender ID and SMS body parameters from Alot Solutions, for SMS fallback.
- (Optional) Distributed Ledger Technology (DLT) registration, including the Principal Entity ID and the approved template IDs, for SMS fallback when you send messages in India.

### RCS Agent Onboarding

An RCS Agent is a brand's verified business profile (the sender). Alot Solutions provisions the RCS Agent, and mobile carriers approve it. CleverTap uses the RCS Agent ID as the RCS Sender ID during provider setup to authorize and deliver RCS messages.

If you are new to Alot Solutions or have not completed RCS Agent onboarding, complete the onboarding in the Alot Solutions platform before you set up the provider in CleverTap.

The onboarding process includes the following steps:

- Registering the business with Alot Solutions as an RCS sender and creating the brand profile (name, logo, description, and website).
- Submitting brand and compliance details for carrier review and obtaining approval for RCS messaging.
- Completing the Alot Solutions verification checks, such as domain or business verification.
- Receiving the RCS Agent ID from Alot Solutions.

To find the RCS Agent ID, go to _Config_ > _RCS Agent_ in the Alot Solutions platform. You enter this value in the _RCS Sender ID_ field in CleverTap during provider setup.

## Set Up Generic RCS on CleverTap Dashboard

To configure the CleverTap dashboard, connect Alot Solutions as your RCS provider using the Generic RCS Provider option, as follows:

1. Go to _Settings > Channels > SMS_ in the CleverTap dashboard.
2. Select the _SMS Connect_ tab.
3. Click **+ Add Provider**.


<Image src="https://files.readme.io/0031f19943d70063956914d8a9a08c72f276f1681aac468e3502b5e4a243193d-Screenshot_2026-10-21_at_16.46.26.png" alt="SMS Connect tab present in the SMS Channel" align="center" caption="SMS Connect Tab in the SMS Channel" border={true} />


4. Under _Provider_, select _Generic RCS Provider_ from the dropdown and enter the Nickname for this provider setup.

<Callout icon="📘" theme="info">
  #### Whitelist IPs

  For additional security, whitelist the following IPs on your SMS settings: `13.124.142.16`, `52.79.51.100`.
</Callout>

5. [Set Up API by entering the Messaging Endpoint and Authentication details](doc:alot-solutions-rcs#set-up-api).
6. [Configure RCS Settings](doc:alot-solutions-rcs#rcs-config).
7. [Configure SMS Fallback](doc:alot-solutions-rcs#configure-sms-fallback).
8. Select _Mark as Default_ to set Alot Solutions as your primary RCS provider for all RCS messaging in CleverTap.
9. Click **Send Test** to verify the integration. Enter the following details:
   - **Country Code and Mobile Number:** Enter the recipient's country code and mobile number for the test.
   - **RCS Message:** Enter the message content to send via RCS.
10. Click **Save** after verifying that the integration was successful.

Once the provider is added, go to the _Provider Listing_ page for [Provider Operations](https://docs.clevertap.com/docs/rcs-setup#provider-operations).

## Set Up API

To set up the API, perform the following details:

1. Under _Messaging Endpoint_, enter the following details. The messaging endpoint is the API URL that Alot Solutions uses to receive RCS send requests from CleverTap.


   <Image src="https://files.readme.io/331df3cf8068cc533ee26821270d92023eeaeba44223557f11782405986a05e2-image.png" align="center" caption="Provider Configuration" border={true} />


   | Field             | Description                                          |
   | ----------------- | ---------------------------------------------------- |
   | **Request Type**  | `POST`                                               |
   | **HTTP Endpoint** | `https://alots.io/api/v1/rcs/clevertap_rcs_over_sms` |
2. Under _Headers_, add the following key-value pairs. Alot Solutions uses bearer token authentication passed as an HTTP header.


   <Image src="https://files.readme.io/dc2b122c3a3a091cffbd2fce71e638098c4414ef6e96287cd1eb1d6ba75329e3-Screenshot_2026-10-21_at_16.55.26.png" alt="Headers section in the Provider Configuration tab." align="center" caption="Headers section in the Provider Configuration tab" border={true} />


   | Key             | Value                                                                                          |
   | --------------- | ---------------------------------------------------------------------------------------------- |
   | `Authorization` | `Bearer <API_KEY>`<br /><br />Replace `<API_KEY>` with the API key provided by Alot Solutions. |
   | `Content-Type`  | `application/json`                                                                             |
3. (Optional) In the _Custom Concurrency_ field, enter the maximum number of parallel requests that CleverTap sends to the Alot Solutions API at any given time. Set this value based on the throughput limit that Alot Solutions recommends. If you leave the field blank, CleverTap applies its default concurrency settings. The maximum supported rate is 4,600 requests per second.
   <Callout icon="🚧" theme="warn">
     #### Higher Concurreny Limitations

     Setting a higher concurrency than Alot Solutions supports may result in rate limiting, message drops, or delayed delivery reports. Confirm the recommended limit with Alot Solutions before setting this value.
   </Callout>

## **Configure RCS Settings**

The _RCS Config_ section maps your Alot Solutions RCS Agent to CleverTap.

| Field           | Description                                                                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| RCS Sender ID   | Enter the RCS Agent ID from _Config > RCS Agent_ in the Alot Solutions platform. This is the verified business sender identity used to deliver RCS messages. |
| Callback Config | Contact your Alot Solutions point of contact to share the CleverTap callback URL and complete the callback configuration on the Alot Solutions platform.     |

## Configure SMS Fallback

SMS fallback ensures message delivery when RCS messages fail due to device incompatibility, lack of internet access, or carrier restrictions. If the recipient's device does not support RCS or is offline, CleverTap automatically sends the message as an SMS.

To enable SMS fallback, select SMS Configuration / Enable Fallback SMS and configure the following:


<Image src="https://files.readme.io/265fa0788352d92e493bb75f052c3eb45e12d66fc35eb790f69858ab9d26bb11-image.png" align="center" caption="Configure SMS Fallback" />


- **SMS Sender ID:** Required when SMS fallback is enabled.
- **SMS Body Parameters:** Add the key-value pairs required by your SMS fallback configuration.

<Callout icon="📘" theme="info">
  #### DLT Registration

  If you are sending messages in India, DLT (Distributed Ledger Technology) registration is mandatory. Configure the **Principal Entity ID** and approved template IDs
</Callout>

# Add Template

The Add Template feature lets you create, manage, and deploy RCS message templates for your campaigns. If Alot Solutions requires template approval, create the template in the Alot Solutions portal first, then create the same template in CleverTap under _Templates_. Use the exact same template name in both systems so submissions map correctly.

To access templates, go to _Settings > Channels > SMS > SMS Connect_, open your Alot Solutions provider, and select the **Template** tab. CleverTap supports three template formats:

- [Text](doc:rcs-message-templates#text)
- [Rich Card](doc:rcs-message-templates#rich-card-template)
- [Carousel Template](doc:rcs-message-templates#carousel)

## Create Campaign

For detailed instructions on creating an RCS campaign with FirstConnectt as your provider, refer to [Create SMS Campaign](doc:rcs-create-message).

## Create Journey

For detailed instructions on creating an RCS journey using FirstConnectt as your provider, refer to [Journeys.](doc:journeys)&#x20;
