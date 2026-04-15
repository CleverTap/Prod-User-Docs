---
title: Karix
excerpt: Learn how to integrate Karix with CleverTap for WhatsApp communication.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Karix](https://www.karix.com/) is a global mobile engagement provider with more than 20 years of mobile CRM (mCRM) experience. Its cloud-based SaaS technology enables brands to intelligently personalize mobile communications for the omnichannel consumer, across both marketing and customer care interactions.

Karix provides WhatsApp Business communication APIs that enable brands to send real-time, template-based campaign messages to their customers. By integrating Karix with CleverTap, businesses can:

* Trigger personalized WhatsApp campaigns based on customer behavior or business rules, using pre-approved WhatsApp templates configured in Karix.
* Track message delivery and customer engagement using Karix's WhatsApp delivery reports and analytics.

<Callout icon="📘" theme="info">
  #### Support for Integration

  This integration is completed by Karix and they are dedicated to maintaining and enhancing it. The CleverTap and Karix integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact Karix for support and resolution. For more information about Karix's WhatsApp Business API, contact your Karix account manager or reach out to [Karix support](https://www.karix.com/contact/).
</Callout>

# Prerequisites for Integration

Check that you have the following:

* The WhatsApp Campaigns feature is enabled on your CleverTap account.
* A fully configured Karix account with WhatsApp Business API (WABA) access.
* The Karix account API Access Key, whitelisted by the Karix SysEng team in your AWS instance.
* At least one approved message template registered in Karix for testing.

# Configure CleverTap Dashboard

To set up Karix as your WhatsApp provider from the CleverTap dashboard:

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_.
2. Click **+ Provider Configuration** and select **Generic (Other)** from the _Provider_ list.

   <Image align="center" border={true} caption="Provider Configuration" src="https://files.readme.io/e7390b893c39b72aa215f702e00de5c663c7005bfd65e4c00a2dcd250bab05af-Provider_config.png" />
3. Enter the following details:

| _Field_                        | **Description**                                                                                                                                                    |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| _Provider_                     | Select **Generic (Other)** from the _Provider_ dropdown.                                                                                                           |
| _Nickname_                     | Enter a name that identifies Karix, for example, `Karix` or `Karix Mobile`.                                                                                        |
| _Mobile Number_                | Add your WhatsApp-integrated number with country code (for example, `91XXXXXXXXXX` for a WABA with the 91 prefix).                                                 |
| _Delivery Report Callback URL_ | This URL is generated automatically in the CleverTap dashboard. Refer to [Set Up CleverTap Callbacks in Karix](#set-up-clevertap-callbacks-in-karix).              |
| _Inbound Message Callback URL_ | This URL is generated automatically in the CleverTap dashboard. Refer to [Set Up CleverTap Callbacks in Karix](#set-up-clevertap-callbacks-in-karix).              |
| _Request Type_                 | Ensure the _Request Type_ is set to `POST`.                                                                                                                        |
| _HTTP Endpoint_                | Paste the following URL: `https://pod1-rcmapi.instaalerts.zone/rcmreceiver/api`                                                                                    |
| _Payload Version_              | `0.1` (populated by default; no input required).                                                                                                                   |
| _Headers_                      | Add the authorization headers provided by Karix. Refer to the [Headers](#headers) section below. Ensure there are no leading or trailing whitespaces in any field. |

4. (Optional) Select **Mark this as default** to set Karix as the default provider for sending WhatsApp messages.
5. (Optional) Select **Set auto-reply for users not tracked on CleverTap** to automatically reply to WhatsApp users who are not tracked on the CleverTap dashboard.
6. Click **Save**. This triggers a validation request without sending a message. A _Status: 200 / Success_ response confirms that the provider details have been saved successfully. If an error occurs, the associated payload and error type are displayed.

<Callout icon="📘" theme="info">
  #### Testing the Integration

  After saving the configuration, trigger a test campaign to a small user segment to validate the plugin. Avoid using **Send Test WhatsApp**, as it can produce inconsistent results. Running an actual campaign provides exact behavior and reliable output.
</Callout>

# Set Up CleverTap Callbacks in Karix

Callbacks ensure that delivery reports and inbound user messages from WhatsApp are synced back to CleverTap, enabling accurate tracking and engagement workflows.

<Image align="center" border={true} caption="Callbacks" src="https://files.readme.io/05dd51ba96f0b69fff0b47dfac0a2b08d5b38b8b7cbc972ee53eaacc4002948c-Provider_config.png" />

The _Delivery Report Callback URL_ and _Inbound Message Callback URL_ are automatically populated in the CleverTap dashboard under the provider configuration. Provide both URLs to the Karix provisioning team.

<Callout icon="⚠️" theme="warn">
  #### Important

  When sharing the callback URLs with the Karix provisioning team, explicitly state that these URLs are for the CleverTap integration. The backend configuration format for CleverTap differs from the standard Karix setup, and this must be noted for correct configuration.
</Callout>

# Headers

In the CleverTap dashboard, select the **Headers** checkbox to expand the section, then click **+ Key-Value Pair** to add the following:

<Image align="center" border={true} caption="Headers" src="https://files.readme.io/82ebb86cccb6705d7c4f856c58f1799df8f20eda9b761a056a0e2308af098f16-headers.png" />

| _Key_           | _Value_                                                               |
| --------------- | --------------------------------------------------------------------- |
| `Authorization` | `Bearer <API Key>` (include a space between `Bearer` and the API key) |
| `Content-Type`  | `application/json`                                                    |

To enable the URL shortener service, add the following key-value pair in headers:

| _Key_         | _Value_ |
| ------------- | ------- |
| `shorten_url` | `true`  |

The following table describes how the Visualize links (VL) setting behaves based on your account-level configuration and the `shorten_url` header value:

| _Account-Level VL Setting_ | _Header Key Value_  | _Final Outcome_ |
| -------------------------- | ------------------- | --------------- |
| On                         | `true`              | VL enabled      |
| On                         | `false` / (not set) | VL disabled     |

# Add WhatsApp Message Templates

To create WhatsApp campaigns, you must have pre-approved WhatsApp message templates saved in the CleverTap dashboard. Templates must first be approved in Karix before being added to CleverTap.

When configuring a template with a Call To Action button that uses Karix's URL shortener service, set the following in the Karix dashboard:

| _Field_            | _Value_                                                                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _Type_             | Call To Action                                                                                                                                                                                       |
| _Button Text 1_    | Your CTA label (maximum 25 characters)                                                                                                                                                               |
| _Type of action 1_ | Visit Website                                                                                                                                                                                        |
| _URL type_         | Dynamic                                                                                                                                                                                              |
| _Redirection URL_  | `https://1kx.in/{[1]}` — required when _URL type_ is set to **Dynamic**. `1kx.in` is Karix's URL shortener domain and `{[1]}` is a dynamic parameter replaced with the destination URL at send time. |

For detailed instructions on adding templates in CleverTap, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

# Create a Campaign

After completing the integration and adding templates, you can create WhatsApp campaigns using Karix as the provider. For detailed instructions, refer to [Create a WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

# Create a Journey

You can also use Karix as a WhatsApp provider within CleverTap Journeys to automate multi-step engagement workflows. For detailed instructions, refer to [Create a WhatsApp Journey](doc:engagement-nodes-whatsapp).
