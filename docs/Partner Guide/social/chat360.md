---
title: Chat360
excerpt: WhatsApp Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

<Anchor target="_blank" href="https://www.chat360.io/">Chat360</Anchor> is a conversational engagement platform that enables businesses to deliver personalized WhatsApp communications at scale. Integrating Chat360 with CleverTap allows you to use CleverTap’s customer data, segments, and behavioral events to trigger WhatsApp campaigns and automated journeys through Chat360.

With this integration, businesses can:

- Send WhatsApp campaigns using Meta-approved templates managed in Chat360.
- Trigger event-based and journey-driven WhatsApp messages using CleverTap data.
- Track delivery and engagement metrics across CleverTap and Chat360 dashboards.

> 🚧 Support for Integration
>
> Chat360 manages and continuously improves this integration. The CleverTap and Chat360 integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact [support@chat360.io](mailto:support@chat360.io) for support and resolution.

# Prerequisites for Integration

Check that you have the following:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- A Chat360 account with WhatsApp Business (WABA) access.
- A provisioned WhatsApp Business number from Chat360.
- WhatsApp message templates required for approval are available in the Chat360 dashboard.

# Integrate Chat360 with CleverTap

This integration involves the following four steps:

1. [Create Passcode on CleverTap Dashboard](doc:chat360#create-passcode-on-clevertap-dashboard)
2. [Configure CleverTap in Chat360](doc:chat360#configure-clevertap-in-chat360)
3. [Configure CleverTap Dashboard](doc:chat360#configure-clevertap-dashboard)
4. (Optional) [Set Up Callbacks in Chat360](doc:chat360#set-up-callbacks-in-chat360)

## Create Passcode on CleverTap Dashboard

CleverTap uses header-based authentication to authenticate requests to its REST API. Every CleverTap API call must include Account ID and Passcode as the request headers. To create a passcode, refer to [Create Account Passcode](https://developer.clevertap.com/docs/authentication#create-account-passcode).

## Configure CleverTap in Chat360

To connect CleverTap within the Chat360 platform, perform the following steps:

1. Go to _Integrations_ > _CleverTap_ in Chat360 Dashboard.
2. Enter the following details:

   - CleverTap Account ID
   - CleverTap Passcode
   - CleverTap Region (for example, IN, EU, or US)
3. Click **Connect** to authenticate the integration.

Once connected, Chat360 can access CleverTap segments and event data for triggering campaigns. For more details, refer to <Anchor target="_blank" href="https://docs.chat360.io/support/clevertap-integration">Integration with CleverTap on the Chat360 Platform</Anchor>.

## Configure CleverTap Dashboard

After connecting CleverTap to _Chat360_, configure _Chat360_ as a WhatsApp provider in CleverTap.

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_.
2. Click **+ Add Provider** and select _Generic (Other)_ from the Provider list.


<Image src="https://files.readme.io/885f26f7e2110aab22dd2bda2eba90bc4c3e187863d865a407301bc495da3a4d-image.png" alt="Provider Setup" align="center" width="65%" caption="WhatsApp Provider Setup" border={true} />


3. Enter the following details:

| Field                            | Details                                                                                                                                                                |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nickname**                     | Enter a name for your provider configuration, for example, `Chat360_WA`.                                                                                               |
| **Mobile Numbe**r                | Enter your WhatsApp Business number with the country code.                                                                                                             |
| **Request Type**                 | Select `POST`.                                                                                                                                                         |
| **HTTP Endpoint**                | Paste the _Chat360_ WhatsApp endpoint provided during onboarding.<br />Check that the URL is in HTTPS format, that is, your URL must begin with `https://`.            |
| **Delivery Report Callback URL** | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Chat360](doc:chat360#set-up-callbacks-in-chat360). |
| **Inbound Message Callback URL** | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Chat360](doc:chat360#set-up-callbacks-in-chat360). |

4. Add the Authorization headers provided by Chat360 during onboarding, as follows:


   <Image src="https://files.readme.io/0bdb0c80b88f1b3e9786dadf8dbc5219d4831ee6d9499066dc6aa6b73921b2bc-image.png" alt="Configure Headers" align="center" width="65% " caption="Configure Headers" border={true} />


   | Key              | Value         |
   | :--------------- | :------------ |
   | **x-client-id**  | `<clientId>`  |
   | **x-secret-key** | `<secretKey>` |

5. (Optional) Select _Mark this as default_ to set the service provider as the default for sending WhatsApp messages via Chat360.

6. (Optional) Select _Set auto-reply for users not tracked on CleverTap_ to automatically reply to users who message on WhatsApp but are not tracked on the CleverTap dashboard.

7. (Optional) Set the _Maximum Concurrent API requests_ between 30 and 1000. Consider your requirements and the provider limitations when defining this value.

8. Send a Test WhatsApp notification (refer to the following image):


<Image src="https://files.readme.io/c384922-sendtest.png" alt="Send a text message" align="center" caption="Send a Test Message on WhatsApp" border={true} />


## Set Up Callbacks in Chat360

Callbacks enable Chat360 to send delivery reports and inbound WhatsApp messages back to CleverTap. To set up callbacks in Chat360, perform the following steps:

1. In CleverTap, go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ > _Provider Nickname_.
2. Copy the following URLs:

   - _Delivery Report Callback URL_
   - _Inbound Message Callback URL_


<Image src="https://files.readme.io/37cbcadbac7369dfbb7e15bb36b4a4e8f851646666502ecf9c82cb2d4daa4992-8422e19929f1eaab1b982d4d8a98785454eb8da322dcb9d4894562d55ce3dc5b-image.png" alt="Callback URLs" align="center" width="65%" caption="CleverTap Callback URLs" border={true} />


3. Share these URLs with the Chat360 support team or configure them in the Chat360 dashboard under _CleverTap Integration Settings_.

Once configured, delivery status updates and inbound WhatsApp messages sync correctly between Chat360 and CleverTap. You can now broadcast WhatsApp messages directly from the CleverTap dashboard using Chat360.

# Add WhatsApp Message Templates

WhatsApp message templates are reusable, pre-approved messages you can send to users at scale, such as alerts, reminders, or promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

# Create Campaign

For detailed instructions on creating a WhatsApp campaign using Chat360 as the provider, refer to [Create WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

# Create Journey

For detailed instructions on creating a WhatsApp journey using Chat360 as the provider, refer to [Create WhatsApp Journey](doc:engagement-nodes-whatsapp).
