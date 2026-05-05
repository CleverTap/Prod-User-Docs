---
title: Limechat Chatbot Configuration
excerpt: Learn how to integrate Limechat with CleverTap for WhatsApp Chatbot.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

[Limechat](https://www.limechat.ai/) Chatbot integration with CleverTap's WhatsApp Direct allows you to automate responses to incoming WhatsApp messages.

This process involves the following steps:

1. [Add a Chatbot Configuration](#add-a-chatbot-configuration)
2. [Configure the Proxy Endpoints and Token](#proxy-endpoints-and-token)
3. [Manage Chatbot Configurations](#manage-chatbot-configurations)

## Prerequisites

Before setting up a Limechat chatbot configuration, ensure the following are in place:

* An active Limechat account with a configured bot.
* WhatsApp Direct is set up in your CleverTap project with at least one verified mobile number. For more information, refer to [WhatsApp Direct Add-on](https://docs.clevertap.com/docs/whatsapp-direct-add-on).

## Add a Chatbot Configuration

To connect Limechat to your WhatsApp Direct number:

1. From the CleverTap dashboard, navigate to _Settings > Channels > WhatsApp > WhatsApp Direct_.
2. Select your WABA account and click the _Chatbots_ tab.
3. Click **Add Chatbot configuration**.
4. Fill in the fields described in [Chatbot Configuration Fields](#chatbot-configuration-fields).
5. Click **Save**.

After saving, CleverTap generates a _token_ and displays the _Proxy Endpoints_ for this chatbot. Copy these values and paste them into your Limechat dashboard to complete the integration. For more information, refer to [Proxy Endpoints and Token](#proxy-endpoints-and-token).

### Chatbot Configuration Fields

The following fields are available in the _Add Chatbot configuration_ form:

| Field            | Required | Description                                                                                                                                                                                                                                                              |
| ---------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _Name_           | Yes      | A display name for this chatbot configuration. Used to identify it in the _Chatbots_ list.                                                                                                                                                                               |
| _Mobile Number_  | Yes      | The WhatsApp Direct number that this chatbot will handle. Select from the numbers linked to your WABA account.                                                                                                                                                           |
| _Callback URL_   | Yes      | The webhook URL provided by Limechat. CleverTap forwards incoming WhatsApp messages to this URL. Obtain this URL from your Limechat dashboard. The URL must begin with `https://`.                                                                                       |
| _Authentication_ | No       | The authentication method used when CleverTap calls the Limechat callback URL. Select one of the following options: _No Authentication_, _Basic Authentication_, or _OAuth 2.0_. For details on each option, refer to [Authentication Options](#authentication-options). |
| _Key-Value Pair_ | No       | Additional custom metadata to include in each callback request sent to Limechat. Click **+ Key-Value Pair** to add one or more entries. These are passed as part of the request payload and can be used by Limechat to route or contextualize messages.                  |

### Authentication Options

CleverTap supports the following authentication methods to secure the callback requests sent to Limechat. Select the method that matches your Limechat endpoint configuration:

* _No Authentication_: No credentials are required.
* _Basic Authentication_: Uses a Base64-encoded username and password. For more information, refer to [Basic Authentication](https://developer.clevertap.com/docs/authentication#basic-authentication).
* _OAuth 2.0_: Uses a bearer token fetched from your OAuth provider. For more information, refer to [OAuth 2.0](https://developer.clevertap.com/docs/authentication#oauth-20).

## Proxy Endpoints and Token

After saving the chatbot configuration, CleverTap displays the _Proxy Endpoints_ section. These are CleverTap-hosted endpoints that Limechat uses to send messages back to your WhatsApp users through CleverTap. Copy and paste these endpoint URLs and the generated token into your Limechat dashboard to complete the two-way connection:

| Endpoint                  | Description                                                                                                                                                      | URL                                                                            |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| _Get All Templates_       | Retrieves all approved [WhatsApp message templates](https://docs.clevertap.com/docs/whatsapp-message-templates) in your CleverTap account.                       | `https://<region>-dashboard.clevertap.com/v1/whatsapp/messages`                |
| _Send Message_            | Sends a WhatsApp message to a user via CleverTap.                                                                                                                | `https://<region>-dashboard.clevertap.com/v1/whatsapp/messages`                |
| _Create Template_         | Creates a new [WhatsApp message template](https://docs.clevertap.com/docs/whatsapp-message-templates) in CleverTap.                                              | `https://<region>-dashboard.clevertap.com/v1/whatsapp/templates`               |
| _Update Template_         | Updates an existing [template](https://docs.clevertap.com/docs/whatsapp-message-templates) identified by its template ID.                                        | `https://<region>-dashboard.clevertap.com/v1/whatsapp/templates/<TEMPLATE_ID>` |
| _Get Single Flow_         | Retrieves the details of a specific [WhatsApp Flow](https://docs.clevertap.com/docs/whatsapp-flows) by its flow ID.                                              | `https://<region>-dashboard.clevertap.com/v1/whatsapp/flows/<FLOW_ID>`         |
| _Create Flow_             | Creates a new [WhatsApp Flow](https://docs.clevertap.com/docs/whatsapp-flows) in CleverTap.                                                                      | `https://<region>-dashboard.clevertap.com/v1/whatsapp/flows`                   |
| _Update Flow (Meta Data)_ | Updates only the metadata of an existing [Flow](https://docs.clevertap.com/docs/whatsapp-flows), such as its name or description, without modifying its content. | `https://<region>-dashboard.clevertap.com/v1/whatsapp/flows/<FLOW_ID>`         |

> 📘 Note share the same base URL. The HTTP method determines the operation. `GET` retrieves templates and `POST` sends a message. Refer to your Limechat dashboard for the correct method to use with each endpoint.

### URL Placeholders

The following table describes the placeholders in each endpoint URL:

| Placeholder     | Description                                                                                                                                      | How to find it                                                                                                                                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<region>`      | The subdomain prefix that corresponds to the data center region where your CleverTap account is hosted. For example, `sk1`, `in1`, `us1`, `eu1`. | The exact, pre-filled URLs for your account are displayed in the _Proxy Endpoints_ section of your dashboard after saving. To identify your region manually, refer to [Regions](https://developer.clevertap.com/docs/common-api-components#region). |
| `<TEMPLATE_ID>` | The unique identifier of the WhatsApp template you want to update.                                                                               | Navigate to _Settings > Channels > WhatsApp > WhatsApp Direct > Templates_ and copy the ID of the required template.                                                                                                                                |
| `<FLOW_ID>`     | The unique identifier of the WhatsApp Flow you want to retrieve or update.                                                                       | Navigate to _Settings > Channels > WhatsApp > WhatsApp Direct > Flows_ and copy the ID of the required flow.                                                                                                                                        |

> 📘 Note
>
> The _Proxy Endpoints_ section in your dashboard displays the fully resolved URLs with your region already populated. Copy directly from there to avoid errors.

### Token

CleverTap generates a unique _token_ for each chatbot configuration after the initial save. Limechat uses this token to authenticate its requests to the proxy endpoints above. Click the eye icon to reveal the token value and the copy icon to copy it to your clipboard.

> ⚠️ Important
>
> Resetting the token immediately invalidates the previous token. Click **Reset Token** to revoke the current token and generate a new one. Update the new token in your Limechat dashboard to avoid disrupting active chatbot operations.

## Manage Chatbot Configurations

All configured chatbots are listed on the _Chatbots_ tab. Each entry displays the chatbot name, mobile number, status, creation date, and the user who created it.

### Chatbot Status

The following table describes the possible statuses for a chatbot configuration:

| Status    | Description                                                                            |
| --------- | -------------------------------------------------------------------------------------- |
| _Running_ | The chatbot is active and receiving incoming messages from the linked WhatsApp number. |
| _Paused_  | The chatbot is inactive. Incoming messages are not forwarded to Limechat.              |

### Available Actions

To manage an existing chatbot, click the ellipsis (⋮) next to the chatbot connection. The following actions are available:

* **Pause**: Temporarily stops message forwarding to Limechat. The configuration is retained and can be resumed at any time.
* **Delete**: Permanently removes the chatbot configuration. This action cannot be undone.

## FAQs