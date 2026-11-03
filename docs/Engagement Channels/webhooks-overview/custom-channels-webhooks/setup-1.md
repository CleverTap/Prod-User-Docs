---
title: 'Setup '
excerpt: Learn how to create and configure a webhook in CleverTap.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Setting up a Custom Channel (Webhook) is a two-step process. In the first step, _Setup_, you configure where CleverTap sends the request, how it authenticates with your provider, and what the request body looks like. For example, you might point to your messaging provider's API endpoint, add an authorization header, and define a JSON body with placeholders for the message content. In the second step, _Identity & Callbacks_, you configure how CleverTap identifies which user a message is meant for, for example by matching on phone number, and how delivery events from your provider, such as a message being read or replied to, are recorded back on the user's profile in CleverTap.

This document covers the following:

- [Create a Webhook](#create-a-webhook)
- [Configure Identity and Callbacks](#configure-identity-and-callbacks)
- [Manage Webhooks](#manage-webhooks)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

## Create a Webhook

The _Setup_ step defines the destination endpoint, authentication method, and request payload structure for the webhook.

To create a webhook:

1. Navigate to _Settings > Channels > Webhooks_.

2. Click **Add Webhook**.

   {/* Screenshot: Webhooks listing page empty state */}

   <Callout icon="📘" theme="info">
     ### IP Whitelisting

     For additional security, whitelist the following CleverTap IP addresses on your webhook endpoint: `13.124.142.16`, `52.79.51.100`.
   </Callout>

3. Enter a _Name_ for the webhook.

4. Under _Destination URL_, select the HTTP method and enter the endpoint URL. The following methods are available: **POST**, **GET**, **DELETE**, and **PUT**.

   <Callout icon="📘" theme="info">
     ### Note

     If you do not have an endpoint available during setup, use [requestcatcher.com](https://requestcatcher.com) to create a temporary test endpoint.
   </Callout>

5. Under _Authentication Type_, select the authentication method and complete the configuration. For details on each method, refer to the tabs below.(@krishna, this table seems broken, refer to my comment on Client credentials with JWT tab)

<Tabs>
  <Tab title="No Authentication">
    No Auth sends requests to your endpoint without an authorization header. Select this option for endpoints that handle their own security through the _Headers_ tab or do not require authentication. For more information, refer to [No Authentication](https://staging.docs.user.clevertap.net/docs/webhook-concepts#no-authentication).
  </Tab>

  <Tab title="Basic Authentication">
    Basic Auth sends an `Authorization` header with every request using a Base64-encoded username and password pair. It is straightforward to implement and best suited for endpoints on secure internal infrastructure. For more information, refer to [Basic Authentication](https://staging.docs.user.clevertap.net/docs/webhook-concepts#basic-authentication).

    When _Basic Auth_ is selected, enter the following:

    - _Username_: The username credential for your endpoint.
    - _Password_: The password credential for your endpoint.

    {/* Screenshot: Setup tab with Basic Auth selected showing Username and Password fields */}
  </Tab>

  <Tab title="OAuth 2.0">
    OAuth 2.0 authenticates requests using short-lived access tokens obtained from your authorization server. Select the grant type that matches your authorization server's configuration. For more information on each grant type, refer to [OAuth 2.0](https://staging.docs.user.clevertap.net/docs/webhook-concepts#oauth-20).&#x20;

    <Tabs>
      <Tab title="Password Credentials">
        Password Credentials uses a resource owner's username and password to obtain an access token directly from your authorization server. For more information, refer to [Password Credentials](https://staging.docs.user.clevertap.net/docs/webhook-concepts#password-credentials).

        Enter the following fields:

        | Field                 | Description                                                                                                                                        |
        | --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
        | Client ID             | The unique identifier issued to CleverTap by the authorization server.                                                                             |
        | Client Secret         | The confidential key issued to CleverTap, used alongside the Client ID to authenticate the application.                                            |
        | Username              | The resource owner's username. Required for Password Credentials.                                                                                  |
        | Password              | The resource owner's password. Required for Password Credentials.                                                                                  |
        | Scopes                | The permissions requested by CleverTap, controlling which parts of the account it can access.                                                      |
        | Access Token URL      | The authorization server endpoint where CleverTap requests an access token.                                                                        |
        | Refresh Token URL     | The authorization server endpoint where CleverTap requests a new access token when the current one expires.                                        |
        | Client Authentication | How CleverTap authenticates to the authorization server. Options: _Send Basic Authentication in Header_ or _Send Bearer Authentication in Header_. |
        | Additional Parameters | Any additional key-value parameters required by your authorization server.                                                                         |

        Click **Generate Token**. CleverTap calls the authorization server and displays the generated token response. Map the _Access token_, _Refresh token_, and _Expiry_ from the response.

        {/* Screenshot: Password Credentials with generated token response and mapping fields */}
      </Tab>

      <Tab title="Client Credentials">
        Client Credentials uses a Client ID and Client Secret to obtain an access token without requiring user credentials, making it suited for server-to-server authentication. For more information, refer to [Client Credentials](https://staging.docs.user.clevertap.net/docs/webhook-concepts#client-credentials).

        Enter the following fields:

        | Field                 | Description                                                                                                                                        |
        | --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
        | Client ID             | The unique identifier issued to CleverTap by the authorization server.                                                                             |
        | Client Secret         | The confidential key used alongside the Client ID to authenticate CleverTap.                                                                       |
        | Scopes                | The permissions requested by CleverTap.                                                                                                            |
        | Access Token URL      | The authorization server endpoint where CleverTap requests an access token.                                                                        |
        | Client Authentication | How CleverTap authenticates to the authorization server. Options: _Send Basic Authentication in Header_ or _Send Bearer Authentication in Header_. |
        | Additional Parameters | Any additional key-value parameters required by your authorization server.                                                                         |

        Click **Generate Token**. Map the _Access token_ and _Expiry_ from the response.

        {/* Screenshot: Client Credentials with generated token response */}
      </Tab>

      <Tab title="Client Credentials with JWT">
        Client Credentials with JWT signs a JSON Web Token using a private key to authenticate with your authorization server, adding a layer of cryptographic security over standard Client Credentials. For more information, refer to [Client Credentials with JWT](https://staging.docs.user.clevertap.net/docs/webhook-concepts#client-credentials-with-jwt).

        **Generate the Public Key**

        1. Click **Regenerate key** to generate the public-private key pair.
        2. Copy the generated public key and paste it into your OAuth server's configuration.

           <Callout icon="📘" theme="info">
             ### Note

             Supported signing algorithms: `RS256`, `RS384`, and `RS512`. Clicking **Regenerate key** invalidates all previously generated keys.
           </Callout>

        **Configure the Client Assertion Header (@krishna, shouldnt these be treated as steps too ?)**

        Enter the following fields under _Client Assertion Header_:

        | Field                 | Description                                                                        |
        | --------------------- | ---------------------------------------------------------------------------------- |
        | Algorithm             | The algorithm used to sign the JWT. Supported values: `RS256`, `RS384`, `RS512`.   |
        | Type                  | The type of token.                                                                 |
        | Key ID                | Identifies which public key the authorization server uses to verify the signature. |
        | Content Type          | The content type of the JWT.                                                       |
        | Critical              | Headers that must be processed by the recipient, such as expiration and audience.  |
        | Additional Parameters | Any additional header parameters required by your authorization server.            |

        **Configure the Client Assertion Payload**

        Enter the following fields under _Client Assertion payload_:

        | Field                 | Description                                                                                                           |
        | --------------------- | --------------------------------------------------------------------------------------------------------------------- |
        | Issuer                | The Client ID that created and sent the JWT.                                                                          |
        | Subject               | The client ID or user the token is issued for.                                                                        |
        | Audience              | The intended recipient of the token, typically the authorization server's token endpoint.                             |
        | Use Issued At         | Whether to include the token creation timestamp. Recommended: _Yes_.                                                  |
        | JWT ID                | A unique identifier for the token. Options: _Enter Id manually_, _Random Generate Id_, _Not required_, or _Enter ID_. |
        | Expiration Time       | When the token expires. Options: _Set time_, _Set by CleverTap (24hrs)_, or _Not required_.                           |
        | Additional Parameters | Any additional claim parameters required by your authorization server.                                                |

        Click **Generate assertion key** to create the JWT.

        **Complete the Configuration**

        Enter the following remaining fields:

        | Field                      | Description                                                                                                                                        |
        | -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
        | Client ID                  | The unique identifier issued to CleverTap by the authorization server.                                                                             |
        | Client Assertion Type      | The method CleverTap uses to authenticate itself using the signed JWT.                                                                             |
        | Scopes                     | The permissions requested by CleverTap.                                                                                                            |
        | Refresh Token URL          | The authorization server endpoint for obtaining a new access token when the current one expires.                                                   |
        | Client Authentication Type | How CleverTap authenticates to the authorization server. Options: _Send Basic Authentication in Header_ or _Send Bearer Authentication in Header_. |
        | Additional Parameters      | Any additional key-value parameters required by your authorization server.                                                                         |

        Click **Regenerate Token**. Map the _Access token_ and _Expiry_ from the generated response.

        {/* Screenshot: Client Credentials with JWT showing complete configuration */}
      </Tab>
    </Tabs>
  </Tab>
</Tabs>

6. Under _Headers_, click **Add Headers** to add any request headers required by your endpoint. Enter a key and value for each header.

   Header values support the following system replacement variables, resolved automatically when the webhook fires:

   | Variable        | Resolves to                                                                                               |
   | --------------- | --------------------------------------------------------------------------------------------------------- |
   | `$$MessageID`   | A unique identifier generated for the dispatched webhook request.                                         |
   | `$$CallbackURL` | The callback URL configured for this webhook, or CleverTap's default callback URL if none is set.         |
   | `$$To`          | The value of the _Identity_ property configured under _Identity & Callbacks_, resolved for the recipient. |

   <Callout icon="🚧" theme="warn">
     ### Header Personalization Is Limited

     Header values only resolve the three variables above, that is,  arbitrary profile properties and Liquid tags are not supported in headers. If a variable can't resolve (for example, `$$To` when no Identity property is configured), the header is sent with an empty value rather than being removed, and the request still goes through.
   </Callout>

   <Callout icon="📘" theme="info">
     ### Note

     For security, header values are automatically stripped of carriage return and line feed characters after the variable resolves, to prevent header injection. This applies to header values only, not header names, and does not apply to the `Authorization` header set by Basic Authentication or OAuth 2.0. (@krishna, was this comment resolved by Jitendra ?)
   </Callout>

   {/* (@Jithendra - please confirm the current rollout status/label for this capability before this goes live, and confirm whether templated JSON-body webhooks are covered by the same rollout gate as other webhook types — engineering's code suggests the templated-body path may bypass the usual flag check.) */}

7. Under _Parameters_, select the format for the request payload:

   - _None_: No request body is sent.
   - _x-www-form-urlencoded_: Sends parameters as form-encoded key-value pairs. Click **Add Parameter** under _Key-value pairs_ to add each parameter.
   - _JSON_: Sends a JSON request body. Enter the payload structure in the _Request body_ editor. Use `$$variableName` syntax to define placeholders whose values will be supplied at campaign send time. `$$template` is a reserved variable that is replaced by the Body JSON of the Webhook Template selected in the campaign. For more information, refer to [Webhook Templates](doc:webhook-templates).

   {/* Screenshot: Setup tab with JSON selected showing Request body editor */}

8. Click **Next** to proceed to _Identity & Callbacks_.

## Configure Identity and Callbacks

The _Identity & Callbacks_ step defines how CleverTap identifies users on this channel, controls message delivery, and maps delivery events from your provider back to CleverTap user profiles.

All fields on this step are optional. Enable each field by selecting its checkbox.

{/* Screenshot: Identity & Callbacks tab with all checkboxes unchecked */}

| Field           | Description                                                                                                                                                                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Identity        | The CleverTap user property that identifies recipients on this channel. This can be any user property marked as an identity, such as phone number or email.                                                                                    |
| Opt-in property | The user property that controls reachability on this channel. Only users with this property enabled on their profile receive messages. This can be managed through user properties on the user's profile.                                      |
| Hashing         | The algorithm used to hash identity values before sending them to your provider. (@krishna, the whole purpose of hashing is to protect sensitive information, that shoudl be mentioned here rather than the techncial translation of the term) |
| Encryption      | The encryption method applied to the payload before sending.                                                                                                                                                                                   |
| Event tracking  | Maps delivery and engagement events from your provider to CleverTap properties. For configuration steps, refer to [Add Event Mapping](#add-event-mapping).                                                                                     |

{/* Screenshot: Identity & Callbacks tab with all fields enabled and configured */}

### Add Event Mapping

Event mapping connects your provider's delivery and engagement callbacks to CleverTap system events, so each campaign notification fires the corresponding CleverTap event on the user's profile.

To add an event mapping:

1. Enable _Event tracking_ by selecting its checkbox.
2. Click **Add Event Mapping**.
3. In the _Add event mapping_ modal, select the CleverTap event from the _Event_ dropdown that corresponds to this callback, for example _Notification Viewed_.
4. Paste a sample payload from your provider for this event into the text area.
5. Click **Auto Fill Properties**. CleverTap parses the sample payload and pre-populates the property mapping fields.
6. Review the generated mappings. Each row consists of an _Event_ property and a _Meta_ property that correspond to fields in your provider's payload.
7. Click **Add Mapping**.

{/* Screenshot: Add event mapping modal with sample payload pasted and fields auto-filled */}

The following example shows a completed mapping for a _Notification Viewed_ event. The provider sends this callback payload when a user views a notification:

```json
{
  "notification": [
    {
      "notify": "176089716044431585048020",
      "meta": "ibpDemoPly",
      "to": "447415774332",
      "sentAt": "2025-10-18T13:52:42.878+0000",
      "seenAt": "2025-10-18T13:52:42.878+0000"
    }
  ]
}
```

After pasting the payload and clicking **Auto Fill Properties**, CleverTap parses the payload and pre-populates the mapping fields. In this example, the _Event_ property maps to `messageId` and the _Meta_ property maps to `from`. Click **Add Mapping** to save it.

{/* Screenshot: Add event mapping modal showing Notification Viewed with filled mapping fields */}

Repeat these steps to add mappings for additional events.

After the webhook is saved, CleverTap generates a callback URL for it. Your provider uses this URL to send delivery and engagement data back to CleverTap. To copy the callback URL, go to _Settings > Channels > Webhooks_ and click **Copy Callback URL** on the relevant webhook row.

After the webhook is configured and a campaign has been published, the events mapped under _Event tracking_ are fired on user profiles each time your provider sends a callback. You can view these events on individual profiles by navigating to _Segments > Find People_, searching for a user, and opening the _Activity_ tab. The mapped events, such as _Notification Viewed_, _Notification Delivered_, and _Notification Replied_, appear in the activity feed alongside other CleverTap events. You can also use these events as segment filters, campaign qualification criteria, or analytics dimensions across the platform.

{/* Screenshot: Find People Activity tab showing Notification Viewed, Notification Delivered, and Notification Replied events on a user profile */}

{/* Screenshot: Identity & Callbacks tab showing a completed event mapping */}

## Manage Webhooks

The Webhooks listing page displays all configured webhooks for your project.

{/* Screenshot: Webhooks listing page with existing webhooks */}

The table shows the following columns for each webhook: _Webhook Name_, _Webhook URL_, _Created By_, _Created On_, and _Updated By_. Use the search bar at the top to filter webhooks by name. (@krishna, are we not going to explain the table here?)

To copy the callback URL for a webhook, hover over the webhook row and click **Copy Callback URL**.

## FAQs

**Q. What are the timeouts and retry limits for webhooks?**

A. The timeout for webhooks is 5 seconds with a retry limit of 2 attempts. If the endpoint fails to respond within 5 seconds, CleverTap retries the request. If the retry also fails, the campaign stats page records the error as "Webhook Dispatch Failed." For more information, refer to [Platform Considerations](https://docs.clevertap.com/docs/platform-considerations).

## Next Steps

After saving the webhook, build a message template for it in Content Manager.

- Refer to [Webhook Templates](https://staging.docs.user.clevertap.net/docs/webhook-templates) to create a template for this webhook.
- Refer to [Create Message](https://staging.docs.user.clevertap.net/docs/webhook-create-message) to create a campaign using this webhook.