---
title: PII Tokenization
excerpt: >-
  Learn how PII Tokenization secures sensitive customer data by replacing
  Personally Identifiable Information (PII) with tokenized substitute values
  before it is shared with CleverTap or CPaaS providers.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

CleverTap’s PII Tokenization feature addresses a core enterprise challenge of how to utilize personal data for engagement without storing or processing PII within CleverTap’s infrastructure. Tokenization solves this by replacing PII with tokens, such as tokenized email addresses or phone numbers. CleverTap processes only these tokens, while the PII remains securely stored in the customer’s environment.

Access to PII is controlled through a secure vault and is used only during message delivery through approved, secure CPaaS integrations. This ensures that PII is accessed only at the time of sending, for delivery purposes, and only through compliant pipelines.

# Significance of Tokenization

Tokenization enables enterprises to utilize CleverTap for personalization, segmentation, and engagement without transferring or storing PII within CleverTap systems.

* _Compliance with Regulations_: Many countries enforce strict rules regarding the storage and transfer of PII. With Tokenization, CleverTap never stores PII.

* _Enterprise Security_: Sensitive data remains within your controlled systems, significantly reducing the risk of exposure.

* _Continued Engagement_: You can still personalize campaigns and journeys using tokens. For example, CleverTap can segment by _tokenized email domain_ or _tokenized phone region_ without requiring PII.

* _Layered Protection_: Tokenization can be used in conjunction with encryption to add a layer of security.

# Tokenization Framework

The Tokenization framework includes the following components:

* _Vault_: A secure token–PII mapping store (CT Vault or customer-managed), containing a protected token mapping table.
* _Dispatcher_: A service that is either CleverTap-hosted or customer-hosted, resolves tokens into PII only at send time for message delivery. This removes the need for customers to build token resolution logic.

Tokenization occurs only once, when the vault first receives PII and returns the corresponding tokens. Token resolution occurs only at message dispatch. Tokenization introduces additional latency as it requires network communication and vault lookups.

The following image illustrates the PII tokenization workflow:

<Image align="center" alt="PII Tokenization Workflow" border={true} caption="PII Tokenization Workflow" src="https://files.readme.io/2cfea272c169283a176554e63e275f50e14437079ef974c0685f5288fc33193d-image.png" />

## Sample Tokenization Workflow

An email address such as [user@example.com](mailto:user@example.com) can be tokenized into a surrogate value such as [erty@glaoytt.zxc](mailto:erty@glaoytt.zxc).

At send time, either CleverTap's Off-Prem Dispatch Server or the customer’s On-Prem Dispatch Server makes a [Detokenize API ](https://developer.clevertap.com/docs/get-value-ap) request to the customer’s token vault. The vault returns the corresponding PII value, which is then used in the final payload sent to the CPaaS provider for delivery.

# Supported Data for Tokenization

You can tokenize the following data:

* _Personally Identifiable Information (PII)_: Personal information such as email addresses and phone numbers.
* _Protected Health Information (PHI)_: If operating in regulated healthcare industries.
* _Other sensitive attributes_: Any information that must remain in your systems.

Non-sensitive user or event attributes, such as city, device type, or engagement preferences, can still be stored directly in CleverTap for segmentation and reporting.

# Deployment Models

The tokenization workflow can be implemented using different deployment models, depending on where message dispatch and token resolution occur.

The following are the two dispatch models supported:

* _On-Prem Dispatch_: Dispatcher runs within the customer’s infrastructure. PII never leaves the customer environment.
* _Off-Prem Dispatch_: Dispatcher runs within CleverTap. PII is resolved securely at the time of sending; however, CleverTap does not store it.

Customer data undergoes a single tokenization process; the dispatch model only changes where token resolution occurs.

# Off-Prem Message Dispatch

In the Off-Prem model, CleverTap manages message dispatch while the customer retains complete control of PII. The following steps describe how tokenized data is processed and resolved during campaign execution.

1. Customer app sends PII to the token vault.
2. Vault API returns tokens.
3. Tokens are sent to CleverTap.
4. During message execution, CleverTap’s message dispatch server requests PII from the token vault using the [Get Value](https://developer.clevertap.com/docs/get-value-api) API.
5. CleverTap sends the final payload with resolved PII to the CPaaS provider for message delivery.

> 📘 **Note**
>
> PII flows only transiently in memory during dispatch and is not stored, even during delays or retries.

# On-Prem Message Dispatch

The following sequence summarizes how tokenized customer data is transferred from the customer environment to CleverTap and then to the customer’s On-Prem dispatch server.

1. Customer app sends PII to the token vault.
2. Vault returns tokens.
3. Tokens are sent to CleverTap.
4. During dispatch, CleverTap triggers the customer-hosted On-Prem Dispatch Server using a secure HTTPS request.

The On-Prem dispatch server resolves tokens via the token vault and delivers the final payload to the CPaaS provider.

This approach enables customers to achieve the following goals:

* Maintain compliance with enterprise data policies.
* Continue using CleverTap for Segments, Personalization, Campaigns, Journeys, and Reporting.
* Ensure sensitive data is safeguarded within the customer’s environment.

> 📘 **Note**
>
> PII never leaves the customer’s infrastructure.

# Tokenization Components

The following table shows the various components involved in Tokenization:

| **Component**        | **Description**                                             |
| -------------------- | ----------------------------------------------------------- |
| Token Vault Database | Secures token–PII mapping store controlled by the customer. |
| Get Token API        | Converts PII to tokens before ingestion into CleverTap.     |
| Resolve Token API    | Returns PII from tokens during message dispatch.            |
| Message Dispatcher   | Resolves tokens at send time; may run Off-Prem or On-Prem.  |

# Setup

The [setup](doc:pii-tokenization#enable-tokenization) steps guide you through implementation. Before enabling Tokenization, ensure that you follow the prerequisites.

## Prerequisites

To implement PII Tokenization successfully, check the following requirements:

* **Token Vault Database**

  * A secure vault deployed in your environment (Oracle, GCP, or equivalent).
  * HTTPS (SSL, port 443) enabled; self-signed certificates are not supported.

* **API Readiness**

  * REST APIs must support at least 50 concurrent connections.
  * Each API call must be able to resolve batches of up to 500 tokens per request.
  * API responses must complete within 60 seconds.
  * Support for retries with exponential backoff in case of transient failures.

* **Authentication & Security**

  * Vault APIs must use secure authentication (Keycloak).
  * Subscriber key (or customer ID) must exist for each user profile.
  * All logging must exclude raw PII and store only tokens or metadata.

* **Operational Readiness**

  * Infrastructure must be monitored for uptime and performance.
  * STOP/Unsubscribe handling must work via tokens.
  * Production connectivity must be tested with CleverTap dispatch servers (Off-Prem) or customer-managed On-Prem Dispatch Server.

## Enable Tokenization

The following steps outline the setup required to enable secure Tokenization with CleverTap, from preparing your token vault to integrating the SDK, configuring message dispatch, and validating the whole workflow before production rollout:

1. [Prepare the Token Vault](doc:pii-tokenization#prepare-the-token-vault)
2. [Configure Message Dispatch](doc:pii-tokenization#configure-message-dispatch)
3. [Test the Integration](doc:pii-tokenization#test-the-integration)
4. [Rollout and Monitor](doc:pii-tokenization#rollout-and-monitor)

### Prepare the Token Vault

Set up a secure foundation to store, manage, and audit all tokenized PII in your environment.

* Deploy a secure Vault DB in your environment and enable logging and monitoring for token transactions.
* Ensure logging and monitoring are enabled for all token transactions.

### Configure Message Dispatch

Enable the dispatch layer to resolve tokens into PII during message delivery securely.

* **Off-Prem Dispatch**

  * Allow CleverTap’s dispatch server to securely call the [Get Value API](https://developer.clevertap.com/docs/get-value-api) during message delivery.
  * Ensure network allowlisting is configured for CleverTap’s IP ranges.

* **On-Prem Dispatch**

  * Deploy and configure the On-Prem Dispatch Server to resolve tokens and deliver payloads to CPaaS providers.
  * Check that it can access the Token Vault and resolve tokens into PII for CPaaS delivery.

#### Callback Process

When messages are dispatched via CPaaS, the token vault or dispatch server must send asynchronous callbacks to CleverTap with delivery status updates.

* Callbacks must contain message IDs, not PII.
* Requests must be authenticated (API key or mTLS).
* Failed callbacks must use retry logic with exponential backoff.

### Test the Integration

Run end-to-end tests covering the following:

* Token creation
* Token resolution
* Campaign or journey execution
* STOP/unsubscribe workflows

Verify that CleverTap stores only tokens and non-PII attributes.

### Rollout and Monitor

Move to production with safeguards in place and continuous monitoring of token operations.

* Enable Tokenization for production traffic.
* Monitor the following continuously:

  * Vault API latency and error rates
  * Token creation/expiry/rotation logs
  * Dispatch SLAs (delivery times, retries)
* Establish incident handling processes for token resolution failures.

## PII-Based Engagement Workflow

The following workflow steps provide the data flow when sending a Campaign or Journey with PII Tokenization enabled.

1. [Triggers the Campaign](doc:pii-tokenization#triggers-the-campaign)
2. [Retrieves Tokenized User Data](doc:pii-tokenization#retrieves-tokenized-user-data)
3. [Prepares the Message for Dispatch](doc:pii-tokenization#prepares-the-message-for-dispatch)
4. [Delivers the Dispatch Request to CPaaS](doc:pii-tokenization#delivers-the-dispatch-request-to-cpaas)
5. [Deletes Resolved PII Immediately](doc:pii-tokenization#deletes-resolved-pii-immediately)
6. [Delivers the Message through CPaaS](doc:pii-tokenization#delivers-the-message-through-cpaas)
7. [Receives Delivery Reports from CPaaS](doc:pii-tokenization#receives-delivery-reports-from-cpaas)
8. [Updates Campaign Analytics](doc:pii-tokenization#updates-campaign-analytics)

#### Triggers the Campaign

A campaign or journey is triggered in CleverTap based on segmentation, user activity, or event rules.

#### Retrieves Tokenized User Data

CleverTap uses tokens and non-PII attributes stored on its platform to identify qualified users for the campaign.

#### Prepares the Message for Dispatch

Depending on your deployment model:

* _Off-Prem_: CleverTap’s Message Dispatch Server requests PII values from your token vault using the [Get Value API](https://developer.clevertap.com/docs/get-value-api).
* _On-Prem_: Your On-Prem Dispatch Server retrieves PII values directly from the token vault.

#### Delivers the Dispatch Request to CPaaS

* The resolved PII (for example, email address or mobile number) is combined with campaign content.
* The complete payload is sent to your configured CPaaS provider (for example, SMS, Email, WhatsApp, Push).

#### Deletes Resolved PII Immediately

* If Off-Prem dispatch is used, CleverTap processes the resolved PII only in-memory during message delivery and does not store it.
* In the On-Prem model, CleverTap never accesses the resolved PII.

#### Delivers the Message through CPaaS

The CPaaS provider delivers the message to the end customer.

#### Receives Delivery Reports from CPaaS

* The CPaaS provider returns delivery and engagement status data (for example, delivered, failed, read).
* CleverTap maps this data back to the campaign using unique message IDs.
* Any PII present in provider receipts is discarded; only anonymized delivery insights are stored in CleverTap.

#### Updates Campaign Analytics

CleverTap updates campaign dashboards and reports with delivery metrics, conversions, and engagement insights, all without referencing raw PII.

## Roles and Responsibilities

To successfully implement Tokenization, both the customer and CleverTap have specific roles. The table below summarizes the division of responsibilities:

| **Party** | **Responsibilities**                                                                                                                                                                                                                                                                                                                |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Customer  | Tokenize all historic PII records.<br />- Call Get Token API before sending new PII into CleverTap.<br />- Provide and maintain infrastructure (Vault DB, On-Prem server if required, and network).<br />- Handle unsubscribe and STOP requests using tokens.<br />- Log request and response payloads for auditing and compliance. |
| CleverTap | Provide the Vault API for token exchange.<br />- Provide and support the On-Prem Dispatcher (if applicable).<br />- Ensure CleverTap processes and stores only tokens and non-PII data.                                                                                                                                             |

# FAQs

### Does CleverTap store PII?

No. CleverTap stores only tokens and non-PII data.

### Can Tokenization be combined with Encryption?

Yes. For example, some enterprises encrypt both the Vault DB and API calls while also using Tokenization.
