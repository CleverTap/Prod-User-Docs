---
title: FirstConnectt
excerpt: >-
  Understand how to integrate FirstConnectt with CleverTap for WhatsApp
  communication
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

FirstConnectt is a CPaaS provider that enables businesses to engage customers across multiple channels. Its integration with CleverTap lets businesses send WhatsApp campaigns directly from the CleverTap dashboard using FirstConnectt's WhatsApp Business API infrastructure, with DLR tracking for delivery status and campaign performance visibility.

Here are a few use cases where businesses can integrate FirstConnectt with CleverTap: (@Dronal: in the SMS doc, we had a title for all the bullets - let's have it here also.)

- **Approved Templates**: Send WhatsApp campaigns using Meta-approved templates.
- **Triggers**: Trigger transactional and promotional messages based on CleverTap segments and user behavior.
- **Delivery Tracking**: Track delivery status and inbound user messages using CleverTap callbacks.

<Callout icon="🚧" theme="warn">
  #### Support for Integration

  This integration is managed and supported by FirstConnectt. For any questions or issues related to this integration, contact [FirstConnectt support](mailto:care@firstconnectt.com).
</Callout>

## Prerequisites for Integration

Before configuring FirstConnectt as your WhatsApp provider in CleverTap, ensure the following are in place:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- You have an active FirstConnectt account with access to the WhatsApp Business API (WABA).
- A WhatsApp Business number is provisioned and active in FirstConnectt.
- Meta-approved WhatsApp message templates are available in your FirstConnectt dashboard.

<Callout icon="📘" theme="info">
  #### Note

  If you are new to FirstConnectt or have not yet completed WhatsApp onboarding, reach out to [FirstConnectt support](mailto:care@firstconnectt.com).
</Callout>

## Configure CleverTap Dashboard

To configure the CleverTap dashboard, connect FirstConnectt as your WhatsApp provider using the Generic WhatsApp provider option.

1. Go to _Settings >&#x20;_**Channels**_&#x20;>&#x20;_**WhatsApp** in the CleverTap dashboard.
2. Select the **WhatsApp Connect** tab.

3) Click **+ Provider Configuration**.


<Image src="https://files.readme.io/e57defd7f934c85cd072e54ef45d3ed96fd57ee5ac2d328d44535a251a7c3f6f-Screenshot_2026-10-08_at_14.51.57.png" alt="The WhatsApp Connect tab located in the WhatsApp Channel." align="center" caption="The WhatsApp Connect tab in the WhatsApp Channel" border={true} />


3. Under _Provider_, select **Generic (Other)** from the dropdown.
4. Enter the following details:

| Field                        | Details                                                                                                                                                                                                                                                                           |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname                     | Enter a unique name for this provider. For example: `FirstConnectt`.                                                                                                                                                                                                              |
| Inbound Message Callback URL | This URL is generated automatically by CleverTap. Copy it and share it with FirstConnectt to receive inbound WhatsApp messages. For more information on setup instructions, refer to [Set Up CleverTap Callbacks in FirstConnectt](#set-up-clevertap-callbacks-in-firstconnectt). |
| Delivery Report Callback URL | This URL is generated automatically by CleverTap. Copy it and share it with FirstConnectt to receive delivery status updates. For more information on setup instructions, refer to [Set Up CleverTap Callbacks in FirstConnectt](#set-up-clevertap-callbacks-in-firstconnectt).   |
| Mobile Number                | Enter your WhatsApp Business number with the country code. For example: `+91888XXXXXX`.                                                                                                                                                                                           |
| Request Type                 | Select _POST_.                                                                                                                                                                                                                                                                    |
| HTTP Endpoint                | Enter the WhatsApp API endpoint provided by FirstConnectt during onboarding. The URL must begin with `https://connecttone.io/api/v1/meta/clevertap`.                                                                                                                              |


<Image src="https://files.readme.io/84855f655fa5c0322ef6ad85d37c72b447d1e51dde2d8049a97ea78ff2c62110-Screenshot_2026-10-08_at_15.07.36.png" align="center" caption="Provider Configuration section for WhatsApp" border={true} />


6. Under _Headers_, add the following key-value pairs using the credentials shared by FirstConnectt during onboarding:

| Key             | Value              |
| --------------- | ------------------ |
| `Authorization` | `Bearer <API_KEY>` |
| `Content-Type`  | `application/json` |

Replace `<API_KEY>` with the API key provided by FirstConnectt.


<Image src="https://files.readme.io/49e7aca7933cdd6a96aa373e3b800abb4140688169d12a0f1cea68d6f07e9537-Screenshot_2026-10-08_at_15.14.21.png" align="center" caption="Key Value Pairs for WhatsApp Channel" border={true} />


7. Select the following optional settings as required:
   - **Set auto-reply for users not tracked on CleverTap**: Automatically replies to users who send a WhatsApp message but are not tracked in the CleverTap dashboard.
   - **Mark this as a default**: Makes FirstConnectt the default provider for all WhatsApp messages.

8. (Optional) Set _Maximum Concurrent API Requests_ to a value between 30 and 1,000, based on your requirements and FirstConnectt's throughput limits.

9. Click **Send Test** to verify the configuration, then click **Save**.


<Image src="https://files.readme.io/9d500c91c46beb999a650b0e0c3bf680eafb01b96722126bc81d7a6e67f2f5cb-Screenshot_2026-10-08_at_15.18.10.png" align="center" caption="Test WhatsApp Option" border={true} />


## Set Up CleverTap Callbacks in FirstConnectt

Setting up callbacks lets FirstConnectt send delivery reports and inbound WhatsApp messages back to CleverTap for accurate reporting and two-way messaging.

1. In CleverTap, go to _Settings > Channels >&#x20;_&#x57;hatsAp&#x70;_&#x20;>&#x20;_**_WhatsApp Connect_**.
2. Open your FirstConnectt provider by clicking its nickname.
3. From the _Provider Configuration_ form, copy the following auto-generated URLs:
   - _Inbound Message Callback URL_
   - _Delivery Report Callback URL_


<Image src="https://files.readme.io/84855f655fa5c0322ef6ad85d37c72b447d1e51dde2d8049a97ea78ff2c62110-Screenshot_2026-10-08_at_15.07.36.png" align="center" caption="Provider Configuration section for WhatsApp" border={true} />


<Callout icon="🚧" theme="warn">
  #### Warning

  Copy each callback URL exactly as it appears in the CleverTap dashboard. An incorrect URL will prevent delivery reports and inbound messages from reaching CleverTap.
</Callout>

4. Log in to your FirstConnectt dashboard and go to _Config > WABA Onboarding > Webhook URL_.
5. Paste the callback URLs, select **CleverTap** as the integration type, and complete the configuration.
6. Click **Save** to apply the changes.

## Add WhatsApp Message Templates

WhatsApp message templates are reusable, Meta-approved messages you can send at scale for alerts, reminders, and promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

## Create Campaign

For detailed instructions on creating a WhatsApp campaign with FirstConnectt as your provider, refer to [Create WhatsApp Campaign](doc:create-message-whatsapp).

## Create Journey

For detailed instructions on creating a WhatsApp journey using FirstConnectt as your provider, refer to [WhatsApp Flows](doc:whatsapp-flows).