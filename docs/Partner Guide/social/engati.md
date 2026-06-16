---
title: Engati
excerpt: WhatsApp Provider
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Engati](https://engati.com/) is a conversational AI and WhatsApp engagement platform that enables businesses to automate customer conversations at scale. By integrating Engati with CleverTap, businesses can trigger WhatsApp campaigns and transactional messages using CleverTap’s customer data, segments, and journeys, while Engati handles message delivery and conversation workflows.

With this integration, businesses can:

- Send WhatsApp messages via Engati using Meta-approved templates.
- Trigger event-based and segment-driven WhatsApp campaigns from CleverTap.
- Capture delivery reports and inbound user messages using CleverTap callbacks.
- Combine CleverTap’s analytics and journey orchestration with Engati’s conversational automation.

> 🚧 Support for Integration
>
> Engati manages and continuously improves this integration.  The CleverTap and Engati integration has undergone stringent testing to ensure seamless functionality. For any questions or issues, contact [support@engati.com](mailto:support@engati.com) for support and resolution.

# Prerequisites for Integration

Check that you have the following:

- The WhatsApp Campaigns feature is enabled on your CleverTap account.
- An Engati account with WhatsApp Business (WABA) access.
- A provisioned WhatsApp Business number from Engati.
- WhatsApp message templates are approved by Meta on the Engati dashboard.

> 📘 Engati Onboarding and References
>
> This is applicable only if you are new to Engati or have not completed WhatsApp onboarding, refer to the following official resources:
>
> - [Engati Product Documentation & User Guide](https://help.engati.com/)
> - [Engati CleverTap Integration Guide](https://help.engati.com/clevertap)
>
> These resources help you understand Engati platform setup and WhatsApp readiness before proceeding with the CleverTap integration.

# Integrate Engati with CleverTap

This integration involves the following steps:

1. [Add CleverTap Integration in Engati](doc:engati#add-clevertap-integration-in-engati)
2. [Configure CleverTap Dashboard](doc:engati#configure-clevertap-dashboard)
3. (Optional) [Set Up Callbacks in Engati](doc:engati#set-up-callbacks-in-engati)

## Add CleverTap Integration in Engati

To add CleverTap integration in Engati, perform the following steps:

1. Go to _Integrations_ > _Cloud Integrations_ > _My Integrations_ in the Engati Dashboard.
2. Select _CleverTap_ from the list and click **Connect now**.


<Image src="https://files.readme.io/df2cfb27982f5239121bb6ed42193fe43d86de15ae63c388d49359604156266c-image.png" align="center" border={true} />


3. In the Integrations window, do the following:
   1. Select the _bot_ you want to integrate.
   2. Choose the _path_ that should receive traffic from CleverTap.
4. Click **Next** to proceed.

After you select the bot and path, the following integration details appear:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Column
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **HTTP Endpoint**
      </td>

      <td>
        - Read-only field with a copy option.
        - Use this as the **HTTP Endpoint** when configuring Engati as a WhatsApp provider in CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        **Delivery Report Callback URL**
      </td>

      <td>
        - Input field where you must paste the **Delivery Report Callback URL** generated in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Engati](doc:engati#set-up-callbacks-in-engati).
      </td>
    </tr>

    <tr>
      <td>
        **Authorization Header**
      </td>

      <td>
        Enter the following header details:

        - **Key:** `Authorization`
        - **Value:** `Basic <API Key>`. Engati automatically generates this API key for authentication.
      </td>
    </tr>
  </tbody>
</Table>

Keep the _HTTP Endpoint_ and _Authorization header_ handy for the CleverTap configuration steps.


<Image src="https://files.readme.io/bd8e75f2b4f8b0305cbde3332881b24ba792778bc61d5997d703f3e53c010a41-image.png" alt="Engati CleverTap Integration Setup" align="center" width="45% " caption="Engati CleverTap Integration Setup" border={true} />


## Configure CleverTap Dashboard

To configure Engati as your WhatsApp provider in CleverTap, perform the following steps:

1. Go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_.
2. Click **+ Add Provider** and select _Generic (Other)_ from the Provider list.


<Image src="https://files.readme.io/885f26f7e2110aab22dd2bda2eba90bc4c3e187863d865a407301bc495da3a4d-image.png" alt="Provider Setup" align="center" width="65%" caption="WhatsApp Provider Setup" border={true} />


3. Enter the following details:

| Field                        | Details                                                                                                                                                             |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nickname                     | Enter a name such as `Engati_WA`.                                                                                                                                   |
| Mobile Number                | Enter your WhatsApp Business number with the country code. For example, +918889500122.                                                                              |
| Request Type                 | Select `POST`.                                                                                                                                                      |
| HTTP Endpoint                | Paste the endpoint URL provided by Engati.<br />Check that the URL is in HTTPS format, that is, your URL must begin with `https://`                                 |
| Delivery Report Callback URL | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Engati](doc:engati#set-up-callbacks-in-engati). |
| Inbound Message Callback URL | This URL is generated automatically in the CleverTap dashboard. For more information, refer to [Set Up Callbacks in Engati](doc:engati#set-up-callbacks-in-engati). |

4. Under _Headers_, add the following:

| Key             | Value                    |
| --------------- | ------------------------ |
| `Authorization` | `Basic <Engati API Key>` |
| `Content-Type`  | `application/json`       |

5. (Optional) Select _Mark this as default_ to make this service provider the default for sending WhatsApp messages via Engati.
6. (Optional) Select _Set auto-reply for users not tracked on CleverTap_ to automatically reply to users who message on WhatsApp but are not tracked on the CleverTap dashboard.
7. (Optional) Set the _Maximum Concurrent API requests_ between 30 and 1000. Consider your requirements and the provider's limitations when defining this value.
8. Send a Test WhatsApp notification (refer to the following image).


<Image src="https://files.readme.io/c384922-sendtest.png" alt="Send a text message" align="center" caption="Send a Test Message on WhatsApp" border={true} />


## Set Up Callbacks in Engati

Callbacks ensure that delivery reports and inbound WhatsApp messages are synced back to CleverTap. To set up callbacks in Engati, perform the following steps:

1. In CleverTap, go to _Settings_ > _Channels_ > _WhatsApp_ > _WhatsApp Connect_ > _Provider Nickname_.
2. Copy the following URLs:

   - _Delivery Report Callback URL_
   - _Inbound Message Callback URL_
3. Go back to the Engati Dashboard and paste these URLs into the CleverTap integration configuration.
4. Save the configuration.


<Image src="https://files.readme.io/8422e19929f1eaab1b982d4d8a98785454eb8da322dcb9d4894562d55ce3dc5b-image.png" alt="Callback URLs" align="center" width="65%" caption="CleverTap Callback URLs" border={true} />


Once configured, Engati will send delivery updates and inbound user messages back to CleverTap. You can now broadcast WhatsApp messages directly from the CleverTap dashboard using Engati.

# Add WhatsApp Message Templates

WhatsApp message templates are reusable, pre-approved messages you can send to users at scale, such as alerts, reminders, or promotional campaigns. For detailed instructions on creating and testing WhatsApp message templates, refer to [WhatsApp Message Templates](doc:whatsapp-message-templates).

# Create Campaign

For detailed instructions on creating a WhatsApp campaign using Engati as the provider, refer to [Create WhatsApp Campaign](doc:whatsapp#section-creating-a-whatsapp-campaign).

# Create Journey

For detailed instructions on creating a WhatsApp journey using Engati as the provider, refer to [Create WhatsApp Journey](doc:engagement-nodes-whatsapp).
