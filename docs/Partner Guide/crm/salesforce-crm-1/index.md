---
title: Salesforce CRM
excerpt: Customer Relationship Management
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

[Salesforce](https://www.salesforce.com/) is a leading Customer Relationship Management (CRM) platform that manages leads, contacts, accounts, opportunities, and support activities across sales, marketing, and service functions. It centralizes structured customer data and tracks critical lifecycle interactions.

CleverTap's native Salesforce integration combines structured CRM data with behavioral insights gathered from digital touchpoints. Delivered via the CleverTap managed package (namespace: CleverTap) on the [Salesforce AppExchange](https://appexchange.salesforce.com/appxListingDetail?listingId=6d0bd1f7-9c5c-484d-87cd-cfc0c68827ca), it supports a data flow that sends CRM records to CleverTap in real-time or in batches. Customers can also send engagement data from CleverTap back to Salesforce using the CleverTap Webhook integration.

This enables marketing, sales, and support teams to deliver contextual, timely customer experiences throughout the full lifecycle.

# Key Benefits

The following benefits help you maintain a connected customer data strategy while enabling targeted engagement across every stage of the customer lifecycle:

* **Unified Customer Profiles**

  Bring Salesforce records, such as contacts, leads, accounts, opportunities, or custom objects, into CleverTap as profile data to create a centralized view of your customer.
* **CRM-Driven Segmentation**

  Build dynamic audience segments in CleverTap using Salesforce attributes such as lead stage, industry, or deal value
* **CRM-Triggered Engagement**

  Use CRM lifecycle changes, such as task creation, opportunity updates, case resolutions, or custom object changes, as triggers for CleverTap Journeys, campaigns, and messages.
* **Behavioral Data in CRM**

  Export user activity, campaign engagement, and survey responses from CleverTap into Salesforce to help sales teams prioritize outreach and track conversion.
* **Automated Lead Enrichment**

  Use CleverTap campaigns to capture user signals (for example, NPS responses or feedback surveys) and push them into Salesforce objects for sales or success follow-up. (@Parth: how is this different from the above bullet?)

# How Integration Works

The integration supports bi-directional data flow, each configured independently:

|                                     | Mechanism                                                                                                                 | Use Case                                                                               |
| :---------------------------------- | :------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------- |
| **Salesforce → CleverTap (Import)** | CleverTap-managed package with Apex triggers, Queueable jobs, and Record-Triggered Flows (for custom objects).            | You want CRM records and activity to drive engagement in CleverTap.                    |
| **CleverTap → Salesforce (Export)** | CleverTap webhook channel secured with OAuth 2.0 Client Credentials, targeting a custom Apex REST endpoint in Salesforce. | You want engagement data, survey responses, or campaign signals to enrich CRM records. |

# Prerequisites for Integration

Before configuring the integration, ensure you have the following:

### Salesforce

* A valid Salesforce account on Enterprise, Unlimited, or Performance edition with API access enabled.
* Permission to access Object Manager, App Manager, Flow Builder, and Apex Classes.
* The CleverTap-managed package is installed from AppExchange (namespace: CleverTap).
* The CleverTap Integration Access permission set is assigned to users configuring the integration.

### CleverTap

* Admin access to the CleverTap dashboard.
* Your CleverTap Account ID, Passcode, and Region are available under Settings > Project.

# Getting Started

Configure the integration in the direction (or directions) that match your use case:

* [**Import Data from Salesforce to CleverTap**](doc:salesforce-import#configure-field-level-filters): You can sync profiles, events, and custom objects from Salesforce CRM into CleverTap.
* [**Export Data from CleverTap to Salesforce**](doc:salesforce-export): You can push engagement data, campaign responses, and survey results from CleverTap into Salesforce custom objects using OAuth 2.0-secured webhooks.

<br />
