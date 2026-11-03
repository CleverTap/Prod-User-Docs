---
title: Custom Channels (Webhooks)
excerpt: >-
  Use webhooks to deliver campaigns through any messaging or communication
  provider.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Custom Channels (Webhooks) trigger campaign messages the moment users take an action, such as completing a purchase, abandoning a session, or reaching a milestone, so your campaigns reach users in real time through the right channel.

Because webhooks work with any provider that accepts an HTTP request, you are not limited to CleverTap's built-in channels. Deliver messages through regional messaging platforms, communication tools, or any service your business uses, without waiting for a dedicated integration.

You configure a custom channel once and reuse it across multiple campaigns and journeys. You manage message content in Content Manager, and CleverTap natively handles audience segmentation, frequency caps, personalization, and analytics.

This document covers the following:

- [Webhook Components](#webhook-components)
- [Key Capabilities](#key-capabilities)
- [Quick Start](#quick-start)

## Webhook Components

A webhook-based custom channel has four components that work together to deliver a campaign message.

**Configure the Webhook**: Define the destination endpoint, authentication method, and base request payload in _Settings&#x20;_>_&#x20;Channels&#x20;_>_&#x20;Webhooks_. The base payload uses `$$variable` placeholders to mark the parts that are filled at send time. `$$template` is a reserved variable that is replaced by the message template selected in the campaign.

**Build Message Templates**: Create reusable message templates in _Content Manager > Templates > Webhook_. Each template defines the JSON body that replaces the `$$template` placeholder in the base request payload, and exposes its own variables for campaign-time personalization.

**Create Campaigns**: Select a webhook and a template when building a campaign or journey. CleverTap renders each template variable as a typed input field. Fill in each field with a static value or a personalized expression using profile properties, event properties, Liquid tags, or dynamic data sources.

**Track Delivery**: Configure event tracking in [Identity & Callbacks](doc:webhook-setup#configure-identity-and-callbacks). Your provider sends delivery and engagement callbacks to CleverTap's callback URL, which CleverTap fires as events on user profiles. These events are available for segmentation, analytics, and campaign targeting.

For a detailed explanation of each component, refer to [Webhook Concepts](doc:webhook-concepts).

## Key Capabilities

Webhooks bring custom delivery to every CleverTap feature you already use, from audience targeting and personalization to analytics and frequency management.

**Works with any provider**: Deliver campaigns through messaging providers, communication platforms, or internal services using standard HTTP. If your provider has an API endpoint, you can build a custom channel on it.

**Reusable templates**: Build message templates once in Content Manager and use them across multiple campaigns and journeys. Templates support any JSON structure your provider accepts.

**Full personalization support**: Personalize every template variable using user profile properties, event properties, Liquid tags, Linked Content, Recommendations, and Catalog send-time data.&#x20;

**Delivery intelligence**: Use CleverTap's full audience engine for webhook campaigns, including past behavior and live behavior targeting, user property filters, control groups, frequency caps, DND hours, and timezone-aware delivery.

**Closed-loop delivery tracking**: Map your provider's delivery and engagement callbacks to CleverTap events. View them on user profiles in _Find People_, use them in segments, and track them in campaign stats.

## Quick Start

The following steps walk you through setting up and running your first webhook campaign.

<Steps>
  <Step title="Set Up a Webhook">
    Navigate to *Settings > Channels > Webhooks* and configure your endpoint, authentication, and base request payload. Refer to [Set Up Webhooks](doc:webhook-setup).
  </Step>
  <Step title="Build a Message Template">
    Navigate to *Content Manager > Templates > Webhook* and create a template with the JSON body your provider expects. Refer to [Webhook Templates](doc:webhook-templates).
  </Step>
  <Step title="Create a Campaign">
    Navigate to *Campaigns*, create a new Webhook campaign, select your webhook and template, and fill in the message variables. Refer to [Create Message](doc:webhook-create-message).
  </Step>
  <Step title="Personalize the Message">
    Use profile properties, event properties, or dynamic data sources to personalize each template variable. Refer to [Personalize Message](doc:webhook-personalize-message).
  </Step>
  <Step title="Monitor Performance">
    Track delivery, engagement, and conversion metrics after publishing. Refer to [Webhooks Stats](doc:webhooks-stats).
  </Step>
</Steps>

<Cards columns="3">
  <Card title="Webhook Concepts" href="doc:webhook-concepts">

  </Card>

  <Card title="Set Up Webhooks" href="doc:webhook-setup">

  </Card>

  <Card title="Webhook Templates" href="doc:webhook-templates">

  </Card>

  <Card title="Create Message" href="doc:webhook-create-message">

  </Card>

  <Card title="Personalize Message" href="doc:webhook-personalize-message">

  </Card>

  <Card title="Webhooks Stats" href="doc:webhooks-stats">

  </Card>
</Cards>
