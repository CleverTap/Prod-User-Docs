---
title: Agent Hub
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

CleverAI<sup>TM</sup> brings AI into CleverTap in two ways.

- **Built-in agents**: They work directly inside your dashboard. They generate content, make optimization decisions, and automate core workflows, so you spend less time on manual setup and more time on strategy. Each agent sits in one of three layers depending on what it is doing for you: **Creator Agents generate content, Intelligent Agents make optimization decisions, and Workflow Agents automate the busywork**.
- **CleverTap MCP**: It connects Claude, ChatGPT, and Cursor directly to your CleverTap account, so you can create segments, pull analytics, and check campaign performance in natural language without switching tabs or manually exporting data. Access through MCP mirrors your dashboard permissions.

Together, the two cover both sides of working with AI in CleverTap: agents that act inside the platform when you are already there, and a connection that brings the platform to you when you are working somewhere else.

This document is the directory for everything. Use it to find the right agent for what you are trying to do.

# Manage Agents

This section explains how to view and control agents from the _Agents_ page.

Each agent, whether a Creator, Intelligent, or Workflow agent, has an enable/disable toggle in its detail panel. To view or change an agent's status, go to _Settings_ > _CleverAI_ > _Agents_, where all agents are listed. Select an agent from the list, and toggle its status on or off in the top-right corner of the detail panel.

<Callout icon="📘" theme="info">
  #### Permissions and Scope

  Only account admins can enable or disable an agent, and the change applies only to the current account. It does not extend to other accounts in your organization.
</Callout>

The following image shows the status of the Image Creator Agent disabled:


<Image src="https://files.readme.io/6c8b2625034250dc399eb9a928fafb5e900f5d17121d84b78da8986409c9fd3b-2026-09-07_12-35-38_1.gif" alt="CleverTap Agents settings page showing a list of Creator and Intelligent agents, with Image Creator selected and its configuration details displayed on the right." align="center" caption="Turning Off an Agent" border={true} />


Disabling an agent blocks it from starting any new activity, but does not stop work already in progress. For example, if you disable IntelliNode after publishing a journey that uses it, the journey's existing nodes continue running, and jobs already dispatched by other agents complete normally. Only new invocations, such as publishing a new journey or scheduling a new job, are blocked once the agent is off.

# Creator Agents

Generates on-brand, contextual content in seconds: Copy, Images, and Templates.

<Cards>
  <Card title="Scribe" href="https://docs.clevertap.com/docs/scribe-1">

  </Card>

  <Card title="Image Creator" href="https://docs.clevertap.com/docs/image-creator">

  </Card>

  <Card title="Email Template Creator" href="https://docs.clevertap.com/docs/email-template-creator">

  </Card>

  <Card title="WhatsApp Template Creator" href="https://docs.clevertap.com/docs/whatsapp-template-creator">

  </Card>
</Cards>

# Intelligent Agents

Continuously evaluates and optimizes performance at the impression level: timing, channel, path, variant, and audience decisions.

<Cards>
  <Card title="IntelliTime" href="https://docs.clevertap.com/docs/best-time">

  </Card>

  <Card title="IntelliChannel" href="https://docs.clevertap.com/docs/intellichannel">

  </Card>

  <Card title="IntelliNODE" href="https://docs.clevertap.com/docs/intellinode">

  </Card>

  <Card title="IntelliAB" href="https://docs.clevertap.com/docs/intelliab">

  </Card>

  <Card title="Recommendations" href="https://docs.clevertap.com/docs/recommendations-agent">

  </Card>

  <Card title="Predictions" href="https://docs.clevertap.com/docs/predictions">

  </Card>
</Cards>

# Workflow Agents

Automates core platform workflows to reduce time-to-live: Segment creation, Journey building, Analytics.

<Cards>
  <Card title="Segment Builder" href="https://docs.clevertap.com/docs/segment-builder">

  </Card>

  <Card title="Journey Builder" href="https://docs.clevertap.com/docs/journey-builder">

  </Card>

  <Card title="Analytics Builder" href="https://docs.clevertap.com/docs/analytics-builder">

  </Card>

  <Card title="AI Schema" href="https://staging.docs.user.clevertap.net/docs/schema#ai-generated-descriptions-for-custom-events">

  </Card>

  <Card title="NPS Insights" href="https://docs.clevertap.com/docs/nps-insights">

  </Card>

  <Card title="CleverTap MCP" href="https://docs.clevertap.com/docs/clevertap-mcp">

  </Card>
</Cards>
