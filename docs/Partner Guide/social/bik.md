---
title: BIK
excerpt: WhatsApp Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[BIK](https://bik.ai/) is a conversational commerce and WhatsApp engagement platform that enables businesses to interact with customers using the WhatsApp Business API. Integrating BIK with CleverTap allows you to send WhatsApp campaigns directly from the CleverTap dashboard while leveraging BIK’s WhatsApp infrastructure.

With this integration, businesses can:

- Send WhatsApp campaigns using Meta-approved templates.
- Trigger transactional and promotional messages based on CleverTap segments and user behavior.
- Track delivery status and inbound user messages using CleverTap callbacks.

> 🚧 Support for Integration
>
> BIK manages and continuously improves this integration. The CleverTap and BIK integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact [support@bik.ai](mailto:support@bik.ai) for support and resolution.

# Prerequisites for Integration

Check that you have the following:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- You have an active BIK account with WhatsApp Business API (WABA) access.
- A WhatsApp Business number has been provisioned and is active in BIK.
- Meta-approved WhatsApp message templates in the BIK dashboard.

> 📘 BIK Onboarding and WhatsApp Setup
>
> This is applicable only if you are new to BIK or have not yet completed WhatsApp onboarding, refer to the following guides:
>
> - [BIK Platform Onboarding Guide](https://help.bik.ai/en/articles/8206255-getting-started-with-bik)
> - [WhatsApp Business Onboarding with BIK](https://help.bik.ai/en/articles/9881919-using-bik-as-whatsapp-provider-on-clevertap)
>
> These steps are required only to provision your WhatsApp Business number in BIK. Once completed, you can proceed with the CleverTap integration.

# Integrate BIK with CleverTap

This integration involves the following three key steps:

1. [Configure CleverTap Dashboard](doc:bik#configure-clevertap-dashboard)
2. (Optional) [Set Up CleverTap Callbacks in BIK](doc:bik#set-up-clevertap-callbacks-in-bik)

## Configure CleverTap Dashboard

To configure BIK as your WhatsApp provider in CleverTap:

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ on the CleverTap dashboard.
2. Click **+ Add Provider** and select _Generic (Other)_ from the Provider list.


<Image src="https://files.readme.io/885f26f7e2110aab22dd2bda2eba90bc4c3e187863d865a407301bc495da3a4d-image.png" alt="Provider Setup" align="center" width="65%" caption="WhatsApp Provider Setup" border={true} />


3. Enter the following details:

| Field                        | Details                                                                                                                                                                         |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname                     | Enter a name such as `BIK_WA`.                                                                                                                                                  |
| Mobile Number                | Enter your WhatsApp Business number with the country code. For example, +918889500122.                                                                                          |
| Request Type                 | Select `POST`.                                                                                                                                                                  |
| HTTP Endpoint                | Paste the WhatsApp endpoint provided by BIK during onboarding.<br />Check that the URL is in HTTPS format, that is, your URL must begin with `https://`.                        |
| Delivery Report Callback URL | This URL is generated automatically in the CleverTap dashboard. For more information, refer to  [Set Up CleverTap Callbacks in BIK](doc:bik#set-up-clevertap-callbacks-in-bik). |
| Inbound Message Callback URL | This URL is generated automatically in the CleverTap dashboard. For more information, refer to  [Set Up CleverTap Callbacks in BIK](doc:bik#set-up-clevertap-callbacks-in-bik). |

4. Under _Headers_, add the authorization headers shared by BIK during onboarding, as follows:

   | Key           | Value                 |
   | :------------ | :-------------------- |
   | Authorization | `Basic [BIK API Key]` |
   | Content-Type  | `application/json`    |

5. (Optional) Select _Mark this as default_ to make this service provider the default provider to send a WhatsApp message via BIK.

6. (Optional) Select _Set auto-reply for users not tracked on CleverTap_ to automatically reply to users who message on WhatsApp but are not tracked on the CleverTap dashboard.

7. (Optional) Set the _Maximum Concurrent API requests_ between 30 and 1000. Consider your requirements and the provider's limitations when defining this value.

8. Send a Test WhatsApp notification (refer to the following image).


<Image src="https://files.readme.io/c384922-sendtest.png" alt="Send a text message" align="center" caption="Send a Test Message on WhatsApp" border={true} />


## Set Up CleverTap Callbacks in BIK

Callbacks allow BIK to send delivery reports and inbound WhatsApp messages back to CleverTap. To set up callbacks in the BIK dashboard, perform the following steps:

1. In CleverTap, go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ > _Provider Nickname_.

2. Copy the following URLs:

   - **Delivery Report Callback URL**
   - **Inbound Message Callback URL**


   <Image src="https://files.readme.io/8422e19929f1eaab1b982d4d8a98785454eb8da322dcb9d4894562d55ce3dc5b-image.png" alt="Callback URLs" align="center" width="65%" caption="CleverTap Callback URLs" border={true} />


3. Log in to your **BIK Dashboard** and go to the CleverTap integration configuration section.

4. Paste both callback URLs and save the configuration.

Once configured, message delivery updates and inbound WhatsApp messages sync correctly between CleverTap and BIK. You can now broadcast WhatsApp messages directly from the CleverTap dashboard using BIK.

# Add WhatsApp Message Templates

WhatsApp message templates are reusable, pre-approved messages you can send to users at scale, such as alerts, reminders, or promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

# Create Campaign

For detailed instructions on creating a WhatsApp campaign using BIK as the provider, refer to [Create WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

# Create Journey

For detailed instructions on creating a WhatsApp journey using BIK as the provider, refer to [Create WhatsApp Journey](doc:engagement-nodes-whatsapp).
