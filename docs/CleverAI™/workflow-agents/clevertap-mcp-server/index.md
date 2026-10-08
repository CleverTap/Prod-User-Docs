---
title: CleverTap MCP Server
excerpt: >-
  Learn how to use CleverTap MCP tools to query, manage campaigns, build
  segments, and explore customer data using natural language through AI clients
  such as Claude, ChatGPT, and Cursor.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Model Context Protocol (MCP) tools are pre-built functions that AI clients invoke using natural language to perform actions within a connected platform. The CleverTap MCP server provides these tools for Claude, ChatGPT, and Cursor, enabling you to query analytics, create campaign drafts, and explore customer data without leaving your AI interface.&#x20;

For more information on how to integrate CleverTap MCP, refer to [CleverTap MCP Server Integration Guide](doc:clevertap-mcp-server-integration-guide).

<Callout icon="📘" theme="info">
  ### Private Beta

  This feature is currently available in Private Beta for selected customers.
</Callout>

The following table lists the categories and the tools within each category:

| Category                                                   | Tools                                                                                          |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [Account Management](doc:clevertap-mcp#account-management) | `list_my_accounts`, `select_account`                                                           |
| [Analytics](doc:clevertap-mcp#analytics)                   | `Analytics`                                                                                    |
| [Event Analytics](doc:clevertap-mcp#event-analytics)       | `get_event_count`, `get_top_property_counts`                                                   |
| [Profile Analytics](doc:clevertap-mcp#profile-analytics)   | `get_profile_count`, `get_realtime_count`                                                      |
| [Segments](doc:clevertap-mcp#segments)                     | `list_segments`, `get_segment`, `resolve_audience`, `estimate_audience`                        |
| [Campaigns](doc:clevertap-mcp#campaigns)                   | `list_campaigns`, `get_campaign_report`, `create_campaign_draft`,<br />`get_channel_providers` |
| [Journeys](doc:clevertap-mcp#journeys)                     | `list_journeys`, `get_journey_report`                                                          |
| [Templates](doc:clevertap-mcp#templates)                   | `create_email_template`, `update_email_template`, `list_email_templates`, `get_email_template` |

<Callout icon="📘" theme="info">
  ### **Access Limitations**

  MCP access requires CleverTap SSO login. RBAC authorization is applied same as dashboard.
</Callout>

# Account Management

You can use the following tools to manage your CleverTap account:

The following table lists the tools for viewing and selecting your CleverTap accounts:

| Tool / Function    | Description                                                                                                                                                             |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list_my_accounts` | Lists all CleverTap accounts that you can access, including account names and identifiers. <br />For example: List all CleverTap accounts I have access to.             |
| `select_account`   | Sets the active CleverTap account for all subsequent tool calls in the session. Pass the account ID as a parameter. <br />For example: Switch to my production account. |

# Analytics

Runs an `analytics` query from a natural language prompt. Use it for Trends, Funnels, Cohorts, Flows, and Pivots. The tool returns the CleverTap Query Language (CQL) query and the results. For example, the prompt,_&#x20;Show me the daily trend of Charged events for the last 30 days_ is handled by the `Analytics` tool. For simple counts, use tools such as `get_event_count` or `get_profile_count` instead.

## Event Analytics

The following table lists the tools for querying event counts and property value distributions:

| Tool / Function           | Description                                                                                                                                                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `get_event_count`         | Returns the total number of times an event occurred within a date range, with optional filters on event properties. <br />For example: How many App Launched events occurred last week?                                   |
| `get_top_property_counts` | Returns the most or least frequent values of an event property, which shows how a property is distributed across users. <br />For example: What are the most common values of a property of the Charged event this month? |

## Profile Analytics

The following table lists the tools available for analyzing user profile data, from historical behavior-based counts to real-time active user metrics:

| Tool / Function      | Description                                                                                                                                                                                 |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `get_profile_count`  | Returns the number of unique users who performed an event within a date range, with optional property filters. <br />For example: How many unique users made a purchase in the last 7 days? |
| `get_realtime_count` | Returns the number of users active in your account in the last 5 minutes. For example: How many users are active right now?                                                                 |

# Segments

The following table lists the tools for viewing saved segments and defining audiences before you use them in a campaign draft.

| Tool / Function     | Description                                                                                                                                                                                                                                                                                                              |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `list_segments`     | Lists the saved segments in your account, with names and basic metadata. You can filter by segment type or status. <br />For example: List all my past behavior segments.                                                                                                                                                |
| `get_segment`       | Returns the details of one segment, including its definition, current size, reachability, and size trend. <br />For example: Show me the definition and size of the Lapsed Buyers segment.                                                                                                                               |
| `resolve_audience`  | Converts a plain-English audience description into a verified query and a readable summary that you can check before use. The tool does not save the audience. <br />For example: Build an audience of users who added an item to their cart in the last 7 days but did not purchase.                                    |
| `estimate_audience` | Estimates the reach of an audience, showing the total matching users and the reachable users on each channel after opt-outs and Do Not Disturb (DND) are applied. The tool does not save the audience and does not support Live audiences. <br />For example: How many users does this audience reach on push and email? |

# Campaigns

You can create a campaign draft in CleverTap directly from an MCP client. After you create a draft, publish it from the CleverTap dashboard.

The following table lists the tools for viewing campaigns and creating campaign drafts:

| Tool / Function         | Description                                                                                                                                                                                                                                                                                                                             |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list_campaigns`        | Lists campaigns within a date range, including names, channels, types, and statuses. You can filter by status, channel, type, owner, label, or name. <br />For example: Show me all campaigns that ran in April 2026.                                                                                                                   |
| `get_campaign_report`   | Returns the full configuration for a campaign identified by its campaign ID, including the audience, goal, schedule, DND settings, and channel-specific settings. The report also includes engagement metrics for a date range that you select. <br />For example: Show me the performance of campaign 1234567890 for the last 30 days. |
| `create_campaign_draft` | Creates a campaign in draft state for Push, SMS, Email, Native Display, or In-App. Push, SMS, and Email drafts target a PBS or Live audience. Native Display and In-App drafts target a Live audience only. <br />For example: Create a push campaign draft offering 10% off to the Lapsed Buyers segment.                              |
| `get_channel_providers` | Returns the configured providers for Push, SMS, or Email. Push returns Android notification channel IDs. SMS and Email return provider nicknames and the default provider. <br />For example: Which email providers are configured in my account?                                                                                       |

# Journeys

The following table lists the tools available to view and report on journeys configured in your CleverTap account:

| Tool / Function      | Description                                                                                                                                                                                                      |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list_journeys`      | Lists the journeys in your account, including names and statuses. You can filter by status, type, and date range. <br />For example: List all active journeys in my account.                                     |
| `get_journey_report` | Returns the performance report for a single journey identified by its ID, including the overview and engagement metrics for each node. <br />For example: Show me the performance of the Welcome Series Journey. |

# Templates

The following table lists the tools available for managing email templates:

| Tool / Function         | Description                                                                                                                                                                                                                |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `create_email_template` | Creates an email template from a name, subject, sender details, and HTML body. <br />For example: Create an email template for our monthly newsletter.                                                                     |
| `update_email_template` | Updates an email template identified by its ID. The update replaces the whole template, so include all fields, not only the ones you change. <br />For example: Update the subject line of my Monthly Newsletter template. |
| `list_email_templates`  | Lists the email templates in your account, with names and basic metadata. <br />For example: List all my email templates.                                                                                                  |
| `get_email_template`    | Returns the full details of one email template, identified by its ID, including the HTML body and settings. <br />For example: Show me the HTML body of the Monthly Newsletter template.                                   |

<Callout icon="📘" theme="info">
  ### **Support and Feedback**

  For questions, issues, or feedback, contact your CleverTap Customer Success Manager.
</Callout>
