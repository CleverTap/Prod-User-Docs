---
title: CleverTap MCP Server
excerpt: >-
  Learn how to use CleverTap MCP tools to query, manage campaigns, build
  segments, and explore customer data using natural language through AI clients
  like Claude and ChatGPT.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

MCP tools are pre-built functions that AI clients invoke using natural language to perform actions within a connected platform. The CleverTap MCP server provides such tools for Claude and ChatGPT, enabling you to query, manage campaigns, build segments, and explore customer data, all without leaving your AI interface.<br />For more information on how to integrate CleverTap MCP, refer to [CleverTap MCP Server Integration Guide](doc:clevertap-mcp-server-integration-guide).

<Callout icon="📘" theme="info">
  #### Availability

  CleverTap MCP is currently released in Public beta. To enable this feature, contact your Customer Success Manager.&#x20;
</Callout>

The following table lists all available tool categories and the tools within each category:

| Category                                                                   | Tools                                                                                     |
| :------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------- |
| [Account Management](doc:clevertap-mcp-tools-reference#account-management) | List My Account, Select Account                                                           |
| [Analytics](doc:clevertap-mcp-tools-reference#analytics)                   | Run Analytics Query                                                                       |
| [Event Analytics](doc:clevertap-mcp-tools-reference#event-analytics)       | Get Event Count, Get Top Property Counts, Get Custom Events, Relevant Events              |
| [Profile Analytics](doc:clevertap-mcp-tools-reference#profile-analytics)   | Get Profile Count, Get Real Time Count                                                    |
| [Segments](doc:clevertap-mcp-tools-reference#segments)                     | List Segment, Get Segment, Relevant Segments                                              |
| [Campaigns](doc:clevertap-mcp-tools-reference#campaigns)                   | List Campaigns, Get Campaign Reports, Get Message Reports, Create Campaign In Draft       |
| [Journeys](doc:clevertap-mcp-tools-reference#journeys)                     | List Journeys, Get Journey Reports                                                        |
| [Templates](doc:clevertap-mcp-tools-reference#templates)                   | Create Email Templates, Update Email Templates, List Email Templates, Get Email Templates |

<Callout icon="📘" theme="info">
  ### Access

  All tools require Admin access on the target CleverTap project.
</Callout>

# Account Management

You can use the following tools to manage your CleverTap account:

| Tool / Function | Description                                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Select Account  | Sets the active CleverTap account for all subsequent tool calls in the session. The account ID is passed as a parameter.                                                    |
| List My Account | Lists all CleverTap accounts that the authenticated user has access to, including account names and identifiers. For example: List all CleverTap accounts I have access to. |

# Analytics

Runs an analytics query from a natural language prompt. This endpoint supports trends, funnels, cohorts, flows, and pivots, and returns the generated CQL and results. For example, Show me the daily trend of Charged events for the last 30 days.

## Event Analytics

The following table shows the tools available for querying event-level data, including counts, trends, property distributions, and relevant events identified by the AI client:

| Tool / Function         | Description                                                                                                                                                                     |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Get Event Count         | Returns the total count of a specific event within a given date range, with optional filters on event properties. For example: How many App Launched events occurred last week? |
| Get Top Property Counts | Returns the most or least frequently occurring values for a specific event property, useful for understanding the distribution of user behavior.                                |
| Get Custom Events       | Fetches the list of all custom events tracked in the CleverTap account, including event names and metadata.                                                                     |
| Relevant Events         | Analyzes account data and identifies the most relevant events for a given use case or question.                                                                                 |

## Profile Analytics

The following table lists the tools available for analyzing user profile data, from historical behavior-based counts to real-time active user metrics:

| Tool / Function     | Description                                                                                                                                                                                                |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Get Profile Count   | Returns the count of unique user profiles that have performed a specific event within a date range, with optional property filters. For example: How many unique users made a purchase in the last 7 days? |
| Get Real-Time Count | Returns the number of active users on the platform in the last 5 minutes, providing a live pulse of current traffic.                                                                                       |

# Segments

The following table shows the tools available for managing user segments. Segment creation via MCP is currently limited to Past Behavior Segments (PBS) and requires Admin access:

| Tool / Function   | Description                                                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| List Segment      | Returns a list of all segments defined in the CleverTap account, with names and basic metadata.                                                              |
| Get Segment       | Retrieves detailed information about a specific segment, including its definition criteria, estimated reach, and trend data.                                 |
| Relevant Segments | Identifies the most relevant existing segments in the user's natural-language prompt. It helps users avoid manually browsing through all available segments. |

# Campaigns

While you can create a draft campaign in MCP on CleverTap, it is available only for the Push Channel. After creating the Push Campaign, you must manually publish the draft from the CleverTap dashboard.

The following table lists the tools available for managing and reporting on campaigns:

| Tool / Function          | Description                                                                                                                                                                                                                                                   |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| List Campaigns           | Lists all campaigns within a specified date range, including campaign names, types, and other details. For example: Show me all campaigns that ran in April 2026.                                                                                             |
| Get Campaign Reports     | Retrieves the complete configuration overview for a specific campaign, identified by its campaign ID. This includes the audience, goal, schedule, DND settings, and channel-specific configurations, as well as engagement metrics for a selected date range. |
| Get Message Reports      | Returns a summary report of messages sent by CleverTap within a given date range, aggregated across campaigns and channels.                                                                                                                                   |
| Create Campaign In Draft | Creates a new campaign in draft state. The draft must be reviewed and published manually from the CleverTap dashboard before going live. **Current Support:** Only for Admin users and Push channels. Campaigns are created without personalization.          |

# Journeys

The following table lists the tools available for viewing and reporting on Journeys configured in your CleverTap account:

| Tool / Function     | Description                                                                                                                                                    |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| List Journeys       | Returns a list of all Journeys configured in the CleverTap account, including journey names and statuses. For example: List all active Journeys in my account. |
| Get Journey Reports | Fetches a detailed performance report for a specific Journey by its ID, including engagement metrics.                                                          |

# Templates

The following table lists the tools available for managing email templates. Delete operations are restricted to templates created by the authenticated user:

| Tool / Function        | Description                                                                                                                                                           |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Create Email Templates | Creates a new email template with a specified name, subject, sender details, and HTML body content. For example: Create an email template for our monthly newsletter. |
| Update Email Templates | Identifies an email template by ID and updates it.                                                                                                                    |
| List Email Templates   | Returns a list of all email templates available in the account, with names and metadata.                                                                              |
| Get Email Templates    | Retrieves the full details of a specific email template by its ID, including the complete HTML body and configuration.                                                |

<Callout icon="📘" theme="info">
  ### **Support and Feedback**

  For questions, issues, or feedback, contact your CleverTap Customer Success Manager.
</Callout>
