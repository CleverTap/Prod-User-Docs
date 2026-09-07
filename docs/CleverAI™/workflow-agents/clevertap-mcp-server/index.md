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

MCP tools are pre-built functions that AI clients invoke using natural language to perform actions within a connected platform. The CleverTap MCP server provides such tools for Claude, ChatGPT, and Cursor, enabling you to query, manage campaigns, build segments, and explore customer data, all without leaving your AI interface.<br />For more information on how to integrate CleverTap MCP, refer to [CleverTap MCP Server Integration Guide](doc:clevertap-mcp-server-integration-guide).

<Callout icon="📘" theme="info">
  ### Public Beta

  This feature is currently available in Public Beta for selected customers.&#x20;
</Callout>

The following table lists all available tool categories and the tools within each category:

| Category                                                   | Tools                                                                                           |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [Account Management](doc:clevertap-mcp#account-management) | `list_my_accounts`, `select_account`                                                            |
| [Analytics](doc:clevertap-mcp#analytics)                   | `analytics`                                                                                     |
| [Event Analytics](doc:clevertap-mcp#event-analytics)       | `get_event_count`, `get_top_property_counts`,`get_events`                                       |
| [Profile Analytics](doc:clevertap-mcp#profile-analytics)   | `get_profile_count`, `get_realtime_count`                                                       |
| [Segments](doc:clevertap-mcp#segments)                     | `list_segments`, `get_segment`                                                                  |
| [Campaigns](doc:clevertap-mcp#campaigns)                   | `list_campaigns`, `get_campaign_report`, `get_message_report`,`create_campaign_draft`           |
| [Journeys](doc:clevertap-mcp#journeys)                     | `list_journeys`,`get_journey_report`                                                            |
| [Templates](doc:clevertap-mcp#templates)                   | `create_email_template`, `update_email_template`,  `list_email_templates`, `get_email_template` |

<Callout icon="📘" theme="info">
  ### **Access Limitations**

  MCP access requires CleverTap SSO login. RBAC authorization is applied same as Dashboard.
</Callout>

# Account Management

You can use the following tools to manage your CleverTap account:

| Tool / Function    | Description                                                                                                                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `select_account`   | Sets the active CleverTap account for all subsequent tool calls in the session. The account ID is passed as a parameter.                                                    |
| `list_my_accounts` | Lists all CleverTap accounts that the authenticated user has access to, including account names and identifiers. For example: List all CleverTap accounts I have access to. |

# Analytics

Runs an `analytics` query from a natural language prompt. This endpoint supports Trends, Funnels, Cohorts, Flows, and Pivots, and returns the generated CQL and results. For example, the prompt "Show me the daily trend of Charged events for the last 30 days" is handled by the `analytics` tool. For simple counts, use `get_event_count` or `get_profile_count` instead.

## Event Analytics

The following table shows the tools available for querying event-level data, including counts, trends, and property distributions identified by the AI client:

| Tool / Function           | Description                                                                                                                                                                     |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `get_event_count`         | Returns the total count of a specific event within a given date range, with optional filters on event properties. For example: How many App Launched events occurred last week? |
| `get_top_property_counts` | Returns the most or least frequently occurring values for a specific event property, useful for understanding the distribution of user behavior.                                |
| `get_events`              | Discovers all events tracked in the account, both custom and system (for example, App Launched, Charged, Notification Clicked), including their property names.                 |

## Profile Analytics

The following table lists the tools available for analyzing user profile data, from historical behavior-based counts to real-time active user metrics:

| Tool / Function      | Description                                                                                                                                                                                                |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `get_profile_count`  | Returns the count of unique user profiles that have performed a specific event within a date range, with optional property filters. For example: How many unique users made a purchase in the last 7 days? |
| `get_realtime_count` | Returns the number of active users on the platform in the last 5 minutes, providing a live pulse of current traffic.                                                                                       |

# Segments

The following table shows the tools available for managing user segments. Segment creation via MCP is currently limited to Past Behavior Segments (PBS) and requires Admin access:

| Tool / Function | Description                                                                                                                  |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `list_segments` | Returns a list of all segments defined in the CleverTap account, with names and basic metadata.                              |
| `get_segment`   | Retrieves detailed information about a specific segment, including its definition criteria, estimated reach, and trend data. |

# Campaigns

You can create a campaign draft in CleverTap directly from an MCP client. This tool currently supports only the Push channel. After creating the Push Campaign, you must manually publish the draft from the CleverTap dashboard.

The following table lists the tools available for managing and reporting on campaigns:

| Tool / Function         | Description                                                                                                                                                                                                                                        |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list_campaigns`        | Lists all campaigns within a specified date range, including campaign names, types, and other details. For example: Show me all campaigns that ran in April 2026.                                                                                  |
| `get_campaign_report`   | Retrieves the complete configuration overview for a specific campaign, identified by its campaign ID. This includes the audience, goal, schedule, DND settings, channel-specific configurations, and engagement metrics for a selected date range. |
| `get_message_report`    | Returns a summary report of messages sent by CleverTap within a given date range, aggregated across campaigns and channels.                                                                                                                        |
| `create_campaign_draft` | Creates a new campaign in draft state. The draft must be reviewed and published manually from the CleverTap dashboard before going live. Currently supported for Push.                                                                             |

# Journeys

The following table lists the tools available for viewing and reporting on Journeys configured in your CleverTap account:

| Tool / Function      | Description                                                                                                                                                    |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list_journeys`      | Returns a list of all Journeys configured in the CleverTap account, including journey names and statuses. For example: List all active Journeys in my account. |
| `get_journey_report` | Fetches a detailed performance report for a specific Journey by its ID, including engagement metrics.                                                          |

# Templates

The following table lists the tools available for managing email templates. Delete operations are restricted to templates created by the authenticated user.

| Tool / Function         | Description                                                                                                                                                           |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `create_email_template` | Creates a new email template with a specified name, subject, sender details, and HTML body content. For example: Create an email template for our monthly newsletter. |
| `update_email_template` | Identifies an email template by ID and updates it.                                                                                                                    |
| `list_email_templates`  | Returns a list of all email templates available in the account, with names and metadata.                                                                              |
| `get_email_template`    | Retrieves the full details of a specific email template by its ID, including the complete HTML body and configuration.                                                |

<Callout icon="📘" theme="info">
  ### **Support and Feedback**

  For questions, issues, or feedback, contact your CleverTap Customer Success Manager.
</Callout>
