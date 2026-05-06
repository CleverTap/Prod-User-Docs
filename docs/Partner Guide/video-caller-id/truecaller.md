---
title: Truecaller
excerpt: Verified Caller ID Partner
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

[Truecaller for Business](https://business.truecaller.com) is a verified business calling and messaging platform that displays a brand's verified name, logo, and contextual messaging on the recipient's call screen. The integration with CleverTap connects audience segmentation and campaign orchestration to Truecaller's Verified Campaigns channel via an outbound webhook, enabling branded call-screen experiences to be triggered for the right user at the right moment.

With this integration, you can:

* Trigger Verified Campaigns post-call pop-ups, missed call pop-ups, and sticky messages from CleverTap segments and journeys.
* Personalize the title, subtitle, CTA, and deep link of the call-screen experience using CleverTap user profile attributes and event properties.
* Orchestrate Truecaller as a channel alongside push, email, SMS, in-app, and WhatsApp inside a single CleverTap journey.
* Reach only opted-in audiences by qualifying users through CleverTap segment filters before the webhook fires.
* Measure downstream conversions in CleverTap by associating goal events such as `call_completed` or `payment_made` with the Truecaller campaign.

The following image shows the high-level data flow:

<Image align="center" border={true} caption="Truecaller and CleverTap Integration Flow" src="https://files.readme.io/875fccbb5303c32d80ae6d0fc09b6fd2a1024c0451e5b80b716a6b090ea3220c-Truecaller_and_CleverTap_Integration_Flow.svg" />

For more information about Truecaller for Business, refer to [Truecaller for Business documentation](https://docs.truecaller.com/truecaller-for-business).

# Prerequisites for Integration

Ensure you have the following before starting the integration:

* An active Truecaller for Business account with a Customer Experience Solution subscription that includes Verified Campaigns.
* An active CleverTap account with the Webhook channel enabled. If the Webhook channel is not visible under _Settings_ > _Channels_, contact the CleverTap account team to enable it.
* A Truecaller Verified Campaign template (post-call pop-up, missed call pop-up, sticky message, or business profile) created in the Truecaller Business Console, with the resulting `campaign_id`.
* The Truecaller Webhook Destination URL, Organization ID, and Webhook Token from the Truecaller Business Console.
* A CleverTap user profile attribute that holds the recipient's phone number in E.164 format (for example, `+919619300858`). This is typically `Profile.Phone`.

# Integrate Truecaller with CleverTap

The integration process involves the following four major steps:

1. [Create Verified Campaign Template in Truecaller](doc:truecaller#create-verified-campaign-template-in-truecaller).
2. [Copy Webhook Credentials from Truecaller Business Console](doc:truecaller#copy-webhook-credentials-from-truecaller-business-console).
3. [Create Truecaller Webhook Connector in CleverTap](doc:truecaller#create-truecaller-webhook-connector-in-clevertap).
4. [Create Webhook Campaign in CleverTap](doc:truecaller#create-webhook-campaign-in-clevertap).

## Create Verified Campaign Template in Truecaller

The template defines the visual content (title, subtitle, CTA, deep link, theme) that appears on the recipient's device. Each template is assigned a `campaign_id` that the CleverTap webhook payload references.

To create a post-call pop-up template, perform the following steps:

1. Sign in to the Truecaller Business Console at [business.truecaller.com/signin](https://business.truecaller.com/signin).
2. From the left navigation, select _Verified Campaigns_, and then select _Template Generator_.
3. Select **Post-call Pop-up** as the campaign type.
4. Enter the display fields, such as title (for example, _CleverTap_), subtitle (for example, _Engagement Platform_), CTA text, and deep link.
5. Upload the required marketing assets, such as the logo and banner image, if not already present.
6. Click **Save and generate template**.
7. Copy the `campaign_id` assigned to the saved template (for example, `CleverTap10`). This value is required in the CleverTap webhook payload.

The template is now visible under _Verified Campaigns_ > _Campaigns_ in the Truecaller Business Console

<Image align="center" border={true} caption="Truecaller-Verified Campaign Template Generator" src="https://files.readme.io/5beffd92f6a17811edfc9d995b85b315a09a621b0ad800ba98b8947b472487c3-Template_Generator.png" />

## Copy Webhook Credentials from Truecaller Business Console

CleverTap uses two values from Truecaller to authenticate every webhook call: the Organization ID and the Webhook Token. Both are configured in the Truecaller Business Console.

To copy the webhook credentials, perform the following steps:

1. From the Truecaller Business Console left navigation, select _Webhook Setup_.
2. Copy the Organization ID. This is a 16-character UUID assigned to the Truecaller account.
3. Click **Regenerate token** to view the Webhook Token, then copy it. Store the token securely; it functions like a password.

<Image align="center" border={true} caption="Truecaller Webhook Setup" src="https://files.readme.io/9eec9564fcbcda7596ffe1bd7473bda77d3d90fba4311fdf7b089d79e9d8c0b1-Truecaller_Webhook_Setup.svg" />

## Create Truecaller Webhook Connector in CleverTap

The webhook connector tells CleverTap where to send the payload and which authentication headers to attach. It is configured once per Truecaller account and reused across multiple campaigns.

To create the webhook connector, perform the following steps:

1. From the CleverTap dashboard, select _Settings_, select _Channels_, and then select _Webhook_.

2. Click **+ New Webhook**.

3. In the _Name_ field, enter a descriptive name, for example, _Truecaller_.

4. Set the **HTTP method** to `POST`, and set the **Destination URL** to:

   ```http
   https://enterprise-webhooks-noneu.truecaller.com/v2/campaigns
   ```

5. Under **Headers**, add the following three key-value pairs:

   | Key            | Value                            |
   | -------------- | -------------------------------- |
   | `X-Org-ID`     | `{{your 16-character org UUID}}` |
   | `X-Org-Token`  | `{{your webhook token}}`         |
   | `Content-Type` | `application/json`               |

6. Click **Save**.

<Image align="center" border={true} caption="Create Truecaller Webhook Connector in CleverTap" src="https://files.readme.io/99ceec4543fb10f89174433bdf31668e3876db5575dbc8451a0a908ce1e26a57-Create_Truecaller_Webhook_Connector_on_CleverTap.webp" />

## Create Webhook Campaign in CleverTap

The campaign defines who receives the Verified Campaign and when. The custom JSON body composed in the _What_ step references the `campaign_id` from Truecaller and uses CleverTap personalization tags to populate the recipient phone number.

To create the campaign, perform the following steps:

1. From the CleverTap dashboard, select _Campaigns_, and then click **+ Campaign**.

2. Select **Webhook** as the channel.

3. Define the target audience using segment filters. For example, qualify users opted in for calls or users in a specific lifecycle segment.

4. Set the campaign trigger:
   * Select **Scheduled** for batch outbound calls.
   * Select **Event-triggered** for real-time personalization aligned with call timing.

5. Select the _Truecaller_ webhook connector created in the previous section.

6. In the _What_ step, under _Message_, select **Custom body**.

7. Compose the JSON payload. The following example references `campaign_id` from Truecaller and uses the `Profile.Phone` personalization tag for the recipient phone number:

   <Image align="center" border={true} caption="CleverTap Webhook Campaign - Custom Body Configuration" src="https://files.readme.io/fcdd05bf26f2e23be85378f1f0923f3a50f1ec6397aecb41f067b9573a3e390d-CleverTap_Webhook_Campaign.svg" />

   ```json
   {
     "campaign_id": "CleverTap10",
     "receiver_number": "{{ Profile.Phone | default: '0000000000' }}",
     "contents": [
       {
         "display_unit": "cid",
         "title": "CleverTap",
         "sub_title": "Engagement Platform",
         "ttl": "1"
       }
     ]
   }
   ```

8. Click **Preview and Test**, then send a test to a phone number registered on Truecaller.

9. Place a call from the registered business number to the test device and confirm the post-call pop-up renders with the configured title, subtitle, and branding.

10. From the Truecaller Business Console, select _Campaigns_ and confirm the test payload was received.

11. Click **Publish** to launch the campaign.

<Callout icon="📘" theme="info">
  #### Note

  Always confirm that `receiver_number` resolves from the user profile in the test send, rather than falling back to the default value. A campaign that always fires to the default value will not reach real users.
</Callout>

After the integration is live, Truecaller can be orchestrated alongside other CleverTap channels in segmentation, journeys, and personalization workflows.

### Create Live Segment of Truecaller-Eligible Users

To target only users who have opted in for verified calls, create a Live Segment that filters on a custom profile attribute such as `truecaller_opt_in`.

To create the segment, perform the following steps:

1. From the CleverTap dashboard, select _Segments_, and then click **+ Segment**.
2. Select **Live Segment**.
3. Add a filter on the user property `truecaller_opt_in` equals `true`.
4. Add an additional filter for users with a non-empty `Profile.Phone`.
5. Click **Save**.

### Trigger Truecaller Campaign from Journey

Inside a CleverTap journey, the Truecaller webhook can be added as a step that fires after a qualifying event.

To add a Truecaller step to a journey, perform the following steps:

1. From the CleverTap dashboard, select _Journeys_, and then click **+ Journey**.

2. Select an entry trigger, such as the event `order_placed`.

3. Add a _Webhook_ action node.

4. Select the **Truecaller** webhook connector.

5. Compose the custom body using event properties for personalization, for example:

   ```json
   {
     "campaign_id": "CleverTap10",
     "receiver_number": "{{ Profile.Phone | default: '9619300858' }}",
     "contents": [
       {
         "display_unit": "cid",
         "title": "Order Confirmed",
         "sub_title": "Your order #{{ event.order_id }} ships tomorrow",
         "ttl": "1"
       }
     ]
   }
   ```

6. Click **Save** and **Publish** the journey.

<Callout icon="📘" theme="info">
  #### Additional Template Types

  For additional template types (sticky message ID, missed call pop-up, business profile), refer to [Verified Campaigns](https://docs.truecaller.com/truecaller-for-business/verified-campaigns) under Truecaller documentation.
</Callout>

# Troubleshooting

The following table lists common issues and their resolutions:

| Issue                                                           | Resolution                                                                                                                                                             |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Webhook returns HTTP 401 or 403                                 | Verify that `X-Org-ID` matches the Organization ID and `X-Org-Token` matches the current Webhook Token in the Truecaller Business Console.                             |
| Webhook returns HTTP 404 or "campaign not found"                | Confirm that `campaign_id` in the payload exactly matches the ID of a saved template in _Verified Campaigns_ > _Campaigns_.                                            |
| Webhook returns HTTP 400 with "invalid receiver_number"         | Ensure `Profile.Phone` is stored in E.164 format with the leading `+` and country code. Update the user profile or apply a Liquid transform.                           |
| Pop-up does not appear on the test device                       | Confirm the test device has Truecaller installed, is signed in, and the test phone number is registered. Verify the call originates from the verified business number. |
| `receiver_number` falls back to the default value in test sends | Test with a user profile that has `Profile.Phone` set. The default is only meant as a syntactic fallback, not a real recipient.                                        |
| Webhook delivery failures in CleverTap logs                     | Review HTTP response codes under _Settings_ > _Channels_ > _Webhook logs_. Common causes are revoked tokens, expired campaigns, or DNS issues.                         |
| EU customer payloads rejected by the `noneu` endpoint           | Replace the destination URL with the EU endpoint shown in the Truecaller console _Webhook Destination URL_ field.                                                      |

For Truecaller-specific configuration questions, refer to [Truecaller for Business documentation](https://docs.truecaller.com/truecaller-for-business) or contact the Truecaller for Business support team.

# Verify Integration

Confirm the following before moving the integration to production:

* A Verified Campaign template is saved in the Truecaller Business Console with a known `campaign_id`.
* The Webhook Destination URL, Organization ID, and Webhook Token are copied from the Truecaller console and stored securely.
* A CleverTap webhook connector named _Truecaller_ is saved with the correct destination URL and the three authentication headers.
* A test campaign sent through the connector returns a success response in CleverTap webhook logs and appears in the Truecaller Campaign Insights.
* The post-call pop-up renders correctly on a registered test device with the expected title, subtitle, branding, and CTA.
* `receiver_number` resolves from the user profile in test sends, not from the default fallback value.
* A goal event (for example, `call_completed` or `payment_made`) is associated with the campaign for downstream conversion tracking.
* Regulatory requirements for outbound calling in the target geography (for example, DLT registration in India) are satisfied.

After all checks pass, the integration is ready for production use.
