---
title: Alot Solutions
excerpt: >-
  Understand how to integrate Alot Solutions with CleverTap for WhatsApp
  communication
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Alot Solutions is a CPaaS provider that enables businesses to engage customers across multiple channels. Its integration with CleverTap lets businesses send WhatsApp campaigns directly from the CleverTap dashboard using Alot Solutions' WhatsApp Business API infrastructure, with DLR tracking for delivery status and campaign performance visibility.

Here are a few ways businesses use Alot Solutions with CleverTap:

- **Approved Templates**: Send WhatsApp campaigns using Meta-approved templates.
- **Triggers**: Trigger transactional and promotional messages based on CleverTap segments and user behavior.
- **Delivery Tracking**: Track delivery status and inbound user messages using CleverTap callbacks.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and supported by FirstConnectt. For any questions or issues related to this integration, contact [Alot Solutions support](mailto:support@alotsolutions.com).
</Callout>

This document covers the following:

- [Prerequisites for Integration](#prerequisites-for-integration)
- [Configure CleverTap Dashboard](#configure-clevertap-dashboard)
- [Set Up CleverTap Callbacks in Alot Solutions](#set-up-clevertap-callbacks-in-alot-solutions)
- [Add WhatsApp Message Templates](#add-whatsapp-message-templates)
- [Create a Campaign](#create-a-campaign)
- [Create a Journey](#create-a-journey)

## Prerequisites for Integration

Before configuring Alot Solutions as your WhatsApp provider in CleverTap, ensure the following are in place:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- You have an active Alot Solutions account with access to the WhatsApp Business API (WABA).
- A WhatsApp Business number is provisioned and active in Alot Solutions.
- Meta-approved WhatsApp message templates are available in your Alot Solutions dashboard.

<Callout icon="📘" theme="info">
  #### Note

  If you are new to Alot Solutions or have not yet completed WhatsApp onboarding, reach out to [Alot Solutions support](mailto:support@alotsolutions.com).
</Callout>

## Configure CleverTap Dashboard

To configure the CleverTap dashboard, connect Alot Solutions as your WhatsApp provider using the Generic WhatsApp provider option.

1. Go to _Settings > Channels > WhatsApp_ in the CleverTap dashboard.
2. Select the **WhatsApp Connect** tab.
3. Click **+ Provider Configuration**. The _Provider Configuration_ form opens.
4. Under _Provider_, select **Generic (Other)** from the dropdown.
5. Enter the following details:

| Field                        | Details                                                                                                                                                                                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname                     | Enter a unique name for this provider. For example: `Alot Solutions`.                                                                                                                                                                                       |
| Inbound Message Callback URL | This URL is generated automatically by CleverTap. Copy it and share it with Alot Solutions to receive inbound WhatsApp messages. For setup instructions, see [Set Up CleverTap Callbacks in Alot Solutions](#set-up-clevertap-callbacks-in-alot-solutions). |
| Delivery Report Callback URL | This URL is generated automatically by CleverTap. Copy it and share it with Alot Solutions to receive delivery status updates. For setup instructions, see [Set Up CleverTap Callbacks in Alot Solutions](#set-up-clevertap-callbacks-in-alot-solutions).   |
| Mobile Number                | Enter your WhatsApp Business number with the country code. For example: `+91888XXXXXX`.                                                                                                                                                                     |
| Request Type                 | Select **POST**.                                                                                                                                                                                                                                            |
| HTTP Endpoint                | Enter the WhatsApp API endpoint provided by Alot Solutions during onboarding. The URL must begin with `https://alots.io/api/v1/meta/clevertap`.                                                                                                             |


<Image src="https://files.readme.io/68e61dba1648db285746535c50f804e1f9ccaff113f3ec1341b6331b3d2946fc-Screenshot_2026-10-12_at_17.06.26.png" align="center" caption="Provider Configuration section for SMS Channel" border={true} />


6. Under _Headers_, add the following key-value pairs using the credentials shared by Alot Solutions during onboarding:

| Key             | Value              |
| --------------- | ------------------ |
| `Authorization` | `Bearer <API_KEY>` |
| `Content-Type`  | `application/json` |

Replace `<API_KEY>` with the API key provided by Alot Solutions.


<Image src="https://files.readme.io/49e7aca7933cdd6a96aa373e3b800abb4140688169d12a0f1cea68d6f07e9537-Screenshot_2026-10-08_at_15.14.21.png" align="center" caption="Key-value pair section for WhatsApp Channel" border={true} />


7. Select the following optional settings as required:
   - **Set auto-reply for users not tracked on CleverTap**: Automatically replies to users who send a WhatsApp message but are not tracked in the CleverTap dashboard.
   - **Mark this as a default**: Makes Alot Solutions the default provider for all WhatsApp messages.

8. (Optional) Set _Maximum Concurrent API Requests_ to a value between 30 and 1,000, based on your requirements and Alot Solutions' throughput limits.

9. Click **Send Test WhatsApp** to verify the configuration, then click **Save**.


<Image src="https://files.readme.io/9d500c91c46beb999a650b0e0c3bf680eafb01b96722126bc81d7a6e67f2f5cb-Screenshot_2026-10-08_at_15.18.10.png" align="center" caption="Test WhatsApp Option" border={true} />


## Set Up CleverTap Callbacks in Alot Solutions

Setting up callbacks lets Alot Solutions send delivery reports and inbound WhatsApp messages back to CleverTap for accurate reporting and two-way messaging.

1. In CleverTap, go to _Settings > Channels > WhatsApp > WhatsApp Connect_.
2. Open your Alot Solutions provider by clicking its nickname.
3. From the _Provider Configuration_ form, copy the following auto-generated URLs:
   - _Inbound Message Callback URL_
   - _Delivery Report Callback URL_


<Image src="https://files.readme.io/68e61dba1648db285746535c50f804e1f9ccaff113f3ec1341b6331b3d2946fc-Screenshot_2026-10-12_at_17.06.26.png" align="center" caption="Provider Configuration section for SMS Channel" border={true} />


<Callout icon="🚧" theme="warn">
  #### Warning

  Copy each callback URL exactly as it appears in the CleverTap dashboard. An incorrect URL will prevent delivery reports and inbound messages from reaching CleverTap.
</Callout>

4. Log in to your Alot Solutions dashboard and go to _Config > WABA Onboarding > Webhook URL_.
5. Paste the callback URLs, select **CleverTap** as the integration type, and complete the configuration.
6. Click **Save** to apply the changes.

## Add WhatsApp Message Templates

WhatsApp message templates are reusable, Meta-approved messages you can send at scale for alerts, reminders, and promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](https://docs.clevertap.com/docs/whatsapp-message-templates).

## Create a Campaign

For detailed instructions on creating a WhatsApp campaign using Alot Solutions as your provider, refer to [Create WhatsApp Campaign](https://docs.clevertap.com/docs/create-message-whatsapp).

## Create a Journey

For detailed instructions on creating a WhatsApp journey using Alot Solutions as your provider, refer to [Create WhatsApp Journey](https://docs.clevertap.com/docs/whatsapp-flows).