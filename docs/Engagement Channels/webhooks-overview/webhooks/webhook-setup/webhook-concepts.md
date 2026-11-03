---
title: Webhook Concepts
excerpt: Understand how webhooks work in CleverTap.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

A webhook is an HTTP request that CleverTap sends to a destination endpoint when a campaign runs. Webhooks power custom channels, which let you deliver campaigns through any messaging or communication provider, including providers without a dedicated CleverTap integration. A custom channel is an intermediary between CleverTap and your messaging provider. You plug in the provider of your choice and send campaigns to your users without managing the underlying platform, while CleverTap continues to manage targeting, journeys, orchestration, analytics, and guardrails.

Understanding the components of a webhook and how they interact helps you configure webhooks, create templates, and run campaigns correctly.

This document covers the following:

- [Custom Channel Architecture](#custom-channel-architecture)
- [Request Payload and Variables](#request-payload-and-variables)
- [Authentication](#authentication)
- [Identity and Callbacks](#identity-and-callbacks)

## Custom Channel Architecture

A webhook-based custom channel consists of four components that work together to deliver a campaign message to a user.

**Webhook Setup** defines where and how CleverTap sends your campaign messages to your provider. You specify the provider’s endpoint URL, the authentication method that confirms CleverTap is permitted to send requests, and a base payload, which is the JSON structure that every request to your provider follows. You define this structure once, and CleverTap reuses it for every message, filling in the values that change, such as the recipient and the message content, at send time.

**Webhook Templates** define the message content you send through a webhook. Each template follows the format your provider expects for a given message type, such as a text message or an image message. You build templates in Content Manager and attach each one to a specific webhook. When a campaign runs, CleverTap inserts the template’s content into the base payload, so every message reaches your provider in the correct format.

**Campaigns and Journeys** bring the webhook and template together. When you create a campaign, you select the webhook and a template built for it. The campaign editor displays each `$$variable` defined in the template as a field for you to fill in, and optionally personalize with user profile or event properties.

**Callbacks** close the loop. After your provider delivers the message, it sends delivery and engagement events back to CleverTap through the callback URL generated during webhook setup. CleverTap records these as events on user profiles, making them available in segments, analytics, and campaign targeting.

## Request Payload and Variables

The request payload is the data CleverTap sends to your provider with every campaign notification. CleverTap builds it from two layers that combine at send time:

- **Base payload**: defines the JSON structure that every request to your provider follows.
- **Template payload**: defines the message content that fills that structure for a given campaign.

You configure the **base payload** during webhook setup by entering the structure in the _Request body_ editor under _Parameters > JSON_. It sets the overall structure of the request, including the field names your provider expects. You write any value that changes with each message as a `$$variableName` placeholder. For example, the following base payload contains two placeholders:

```json
{
  "recipient": "$$recipient",
  "content": "$$template"
}
```

- `recipient`: the field in which your provider expects the recipient of the message. The `$$recipient` placeholder receives its value at send time.
- `content`: the field in which your provider expects the message. The `$$template` placeholder is replaced with the body JSON of the template you select in the campaign.

CleverTap reserves the `$$template` placeholder. You choose the names of all other placeholders, such as `$$recipient`, so that each name describes the value it represents. You can add as many placeholders as your provider's request requires. The field names on the left, such as `recipient` and `content`, must match what your provider's API expects.

The **template payload** is the body JSON of a webhook template. You create the template in _Content Manager_.

When a campaign sends, CleverTap replaces the `$$template` placeholder in the base payload with the full body JSON from the selected template. The result is the complete request body that CleverTap sends to your provider.

Variables in the template body JSON follow the same `$$variableName` syntax. These represent values that the campaign editor displays as fields when you create a campaign, such as an image URL or a text string. The datatype you assign to each variable in the template determines the input type that the campaign editor shows. For example, an Image variable displays image upload options, and a Boolean variable displays a True/False selector.

## Authentication

CleverTap supports three authentication methods for webhook endpoints, configured during webhook setup.

### No Authentication

With No Authentication selected, CleverTap sends requests to the endpoint without an Authorization header. This option is appropriate for internal endpoints or endpoints that manage their own token-based security through custom request headers.

### Basic Authentication

Basic Authentication sends an `Authorization` header with every request. The header value is the string `Basic`, followed by a space and the Base64-encoded form of `username:password`. You enter the credentials in the _Username_ and _Password_ fields during webhook setup.

For example, if the username is `webhook_user` and the password is `S3cureP@ss`, CleverTap encodes `webhook_user:S3cureP@ss` and sends the following header with every request:

```http
Authorization: Basic d2ViaG9va191c2VyOlMzY3VyZVBAc3M=
```

This method is straightforward to implement, but it transmits encoded credentials with each request. Base64 is an encoding, not encryption, so anyone who intercepts the header can decode it. Use this method for webhooks sent to internal systems behind a firewall or secure infrastructure.

### OAuth 2.0

OAuth 2.0 authenticates requests using short-lived access tokens rather than credentials, providing a more secure approach for external APIs. CleverTap obtains an access token from your authorization server and includes it in the request headers. Three grant types are available, each suited to a different authentication scenario.&#x20;

- Password Credentials: Suited to authorization servers that require a resource owner’s username and password.
- Client Credentials: Suited to server-to-server authentication where no user context is needed.
- Client Credentials with JWT: Suited to authorization servers that verify a signed JSON Web Token in place of a Client Secret.

#### Password Credentials

This grant type is appropriate when your authorization server requires direct user credentials and a refresh token is available to maintain a continuous session.

The Password Credentials grant type uses a resource owner’s username and password to obtain an access token. The flow works as follows:


<Image src="https://files.readme.io/50dbc41f055a335a6a001efa517efc3e067fb98366104439e88aa7918fd00f85-Password_Credentials.png" alt="Password Credentials Flow" align="center" width="75%" border={true} />


1. CleverTap sends the username, password, Client ID, and Client Secret to the authorization server.
2. The authorization server validates the credentials and returns an access token along with its expiration time.
3. CleverTap uses the access token to make authorized requests to your provider.
4. When the token expires, CleverTap uses the Refresh Token URL to obtain a new one without re-sending credentials.

#### Client Credentials

This grant type is appropriate for server-to-server authentication where no user context is needed.

The Client Credentials grant type uses only a Client ID and Client Secret to obtain an access token, without requiring user credentials. The flow works as follows:


<Image src="https://files.readme.io/0e139311bd9f0c65bbf95749855a9af4dc8c643d01b9c2fd3599e8eb34e494f9-Client_Credentials.png" alt="Client Credentials Flow" align="center" width="75%" border={true} />


1. CleverTap sends the Client ID and Client Secret to the authorization server.
2. The authorization server validates the credentials and returns an access token along with its expiration time.
3. CleverTap uses the access token to make authorized requests to your provider.

#### Client Credentials with JWT

This grant type is appropriate for server-to-server authentication where your authorization server verifies a signed JWT in place of a Client Secret, adding cryptographic security to the standard Client Credentials flow.

Client Credentials with JWT adds a layer of cryptographic security on top of the standard Client Credentials flow. Instead of sending credentials directly, CleverTap signs a JSON Web Token (JWT) using a private key and sends it to the authorization server. The server verifies the JWT using a corresponding public key before issuing an access token.

The flow works as follows:


<Image src="https://files.readme.io/b7d6d2ce41a7cee5ee410b52b9e2e0902d655d176594dab6076968e28a6ea332-JWT_1.png" alt="Client Credentials with JWT Flow" align="center" width="75%" border={true} />


1. CleverTap generates a public-private key pair. The public key is shared with your OAuth server; the private key remains with CleverTap.
2. CleverTap creates a Client Assertion, which is a signed JWT containing the Client ID, audience, expiration, and other claims.
3. CleverTap sends the Client Assertion to your authorization server.
4. Your authorization server uses the public key to verify the JWT signature. If the token is valid, the server issues an access token.
5. CleverTap uses the access token to make authorized requests to your provider.

JWT provides several security properties compared to standard credential-based flows:

- **Tamper resistance**: JWTs are signed with a private key. If an attacker modifies the token, the signature becomes invalid and the authorization server rejects it.
- **No credential transmission**: CleverTap does not send the Client Secret in each request. The signed JWT proves identity without exposing the underlying credential.
- **Short-lived tokens**: Access tokens are valid only for the configured expiration period. A compromised token has limited value because it expires quickly.
- **Self-contained**: The JWT carries all necessary claims, reducing reliance on server-side session state.

CleverTap supports the following signing algorithms for JWT: `RS256`, `RS384`, and `RS512`. Each requires an RSA public-private key pair. The private key signs the JWT; the public key verifies the signature.

## Identity and Callbacks

The Identity & Callbacks configuration connects your webhook to CleverTap’s user profile system. It defines how CleverTap identifies the recipient of a message, controls delivery eligibility and rate, and maps your provider’s delivery and engagement events back to CleverTap.

### Identity

The _Identity_ field specifies which CleverTap user property uniquely identifies a recipient on this channel. For example, a messaging provider that uses phone numbers as identifiers would map _Identity_ to the phone number user property. CleverTap uses this property to route each campaign message to the correct user on your provider's platform.

### Opt-In Property

The Opt-in property field specifies a Boolean user property that controls whether a user is eligible to receive messages on this channel. Only users whose profile has the value true for this property receive campaign messages through the webhook. This allows you to apply channel-level consent.

### Rate Limiting

The _Rate limit_ field controls the maximum number of messages CleverTap sends to your provider per second. The accepted range is 400 to 1200 messages per second, with a default of 1200. Setting a rate limit prevents your provider's API from being overwhelmed during large campaign sends, particularly for providers that enforce their own request-per-second limits.

### Hashing and Encryption

**Hashing** applies a cryptographic hash function to identity values before they are included in the request payload. This is useful when your provider requires or recommends that sensitive identifiers such as phone numbers or email addresses be hashed before transmission. CleverTap supports SHA-256 via Cryptography SHA-256.

**Encryption** applies an encryption algorithm to the payload before sending. This provides an additional layer of protection for the message content in transit. CleverTap supports ChaCha20 256-bit encryption.

### Event Tracking

Event tracking maps your provider's delivery and engagement callbacks to CleverTap events on user profiles. When your provider sends a callback to CleverTap's callback URL, CleverTap matches the payload to the configured event mapping and fires the corresponding event on the recipient's profile.

For example, if your provider sends a callback when a user views a notification, you map that callback to the CleverTap _Notification Viewed_ event. After a campaign runs, you can use _Notification Viewed_ as a segment filter, a campaign trigger, or an analytics dimension.

Each event mapping consists of:

- The CleverTap event the callback corresponds to (for example, _Notification Viewed_, _Notification Delivered_, or _Notification Replied_).
- One or more properties from the callback payload are mapped to event properties in CleverTap.

CleverTap generates a unique callback URL for each webhook after it is saved. Your provider sends delivery and engagement payloads to this URL. The events fired by these callbacks are then visible on user profiles in _Segments > Find People_ under the _Activity_ tab.
