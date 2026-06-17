---
title: Heltar
excerpt: WhatsApp Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Heltar](https://www.heltar.com/) is a WhatsApp Business API (WABA) solution provider that helps businesses automate, personalize, and scale customer communication on WhatsApp. By integrating Heltar with CleverTap, businesses can trigger WhatsApp campaigns and transactional messages using CleverTap’s customer data, segmentation, and journey orchestration, while Heltar manages WhatsApp message delivery and compliance.

With this integration, businesses can:

- Send WhatsApp messages using Meta-approved templates provisioned through Heltar.
- Trigger event-based and segment-driven WhatsApp campaigns from CleverTap.
- Track message delivery and user engagement using CleverTap analytics and callbacks.

> 🚧 Support for Integration
>
> Heltar manages and continuously improves this integration. The CleverTap and Heltar integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact [contact@heltar.com](mailto:contact@heltar.com) for support and resolution.

# Prerequisites for Integration

Check that you have the following:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- An active Heltar account with WhatsApp Business API (WABA) access.
- A WhatsApp Business number is provisioned and active through Heltar.
- WhatsApp message templates required for approval are available in the Heltar dashboard.

# Integrate Heltar with CleverTap

This integration involves the following three key steps:

1. [Set Up Heltar Account](doc:heltar#set-up-heltar-account)
2. [Configure CleverTap Dashboard](doc:heltar#configure-clevertap-dashboard)
3. (Optional) [Set Up Callbacks in Heltar](doc:heltar#set-up-callbacks-in-heltar)

## Set Up Heltar Account

Heltar typically manages WhatsApp Business onboarding, API provisioning, and configuration during setup. During onboarding, the Heltar team shares the required endpoint details and authentication headers needed to configure CleverTap.

For assistance, contact [Heltar Support](tel:+918005756750).

## Configure CleverTap Dashboard

To configure Heltar as your WhatsApp provider in CleverTap, perform the following steps:

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ in the CleverTap dashboard.
2. Click **+ Add Provider** and select _Generic (Other)_ from the Provider list.


<Image src="https://files.readme.io/885f26f7e2110aab22dd2bda2eba90bc4c3e187863d865a407301bc495da3a4d-image.png" alt="Provider Setup" align="center" width="65%" caption="WhatsApp Provider Setup" border={true} />


3. Enter the following details:

| Field                            | Details                                                                                                                                                             |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nickname**                     | Enter the name for your provider configuration, for example, `Heltar_WA`.                                                                                           |
| **Mobile Number**                | Enter your WhatsApp Business number with the country code. (for example, +918889500122)                                                                             |
| **Request Type**                 | Select `POST`.                                                                                                                                                      |
| **HTTP Endpoint**                | Paste the WhatsApp endpoint provided by Heltar during onboarding.<br />Check that the URL is in HTTPS format, that is, your URL must begin with `https://`.         |
| **Delivery Report Callback URL** | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Heltar](doc:heltar#set-up-callbacks-in-heltar). |
| **Inbound Message Callback URL** | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Heltar](doc:heltar#set-up-callbacks-in-heltar). |

4. Under _Headers_, add the following:

| Key             | Value                    |
| --------------- | ------------------------ |
| `Authorization` | `Basic <Heltar API Key>` |
| `Content-Type`  | `application/json`       |

5. (Optional) Select _Mark this as default_ to make this service provider the default provider to send a WhatsApp message via Heltar.
6. (Optional) Select _Set auto-reply for users not tracked on CleverTap_ to automatically reply to users who message on WhatsApp but are not tracked on the CleverTap dashboard.
7. (Optional) Set the _Maximum Concurrent API requests_ between 30 and 1000. Consider your requirements and the provider's limitations when defining this value.
8. Send a Test WhatsApp notification (refer to the following image).


<Image src="https://files.readme.io/c384922-sendtest.png" alt="Send a text message" align="center" caption="Send a Test Message on WhatsApp" border={true} />


## Set Up Callbacks in Heltar

Callbacks ensure that message delivery reports and inbound WhatsApp messages are synced correctly between CleverTap and Heltar.

To set up callbacks, perform the following steps:

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ > _Provider Nickname_ from the CleverTap dashboard.
2. Copy the following URLs:

   - _Delivery Report Callback URL_
   - _Inbound Message Callback URL_
3. Share these callback URLs with the Heltar support team or configure them in the Heltar dashboard as instructed during onboarding.
4. Save the configuration.


<Image src="https://files.readme.io/4323dcdbb601b5b16c37a19543d005bebea459ff43bcd23a7334b0ce25c75472-8422e19929f1eaab1b982d4d8a98785454eb8da322dcb9d4894562d55ce3dc5b-image_1.png" alt="Callback URLs" align="center" width="65%" caption="CleverTap Callback URLs" border={true} />


Once configured, Heltar will forward delivery updates and inbound messages to CleverTap. You can now broadcast WhatsApp messages directly from the CleverTap dashboard using Heltar.

# Add WhatsApp Message Templates

WhatsApp message templates are reusable, pre-approved messages you can send to users at scale, such as alerts, reminders, or promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

# Create Campaign

For detailed instructions on creating a WhatsApp campaign using Heltar as the provider, refer to [Create WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

# Create Journey

For detailed instructions on creating a WhatsApp journey using Heltar as the provider, refer to [Create WhatsApp Journey](doc:engagement-nodes-whatsapp).
