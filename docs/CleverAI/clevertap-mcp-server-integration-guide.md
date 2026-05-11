---
title: CleverTap MCP Server Integration Guide
excerpt: >-
  Learn how to connect and configure the CleverTap MCP server with your
  preferred AI client to interact with your CleverTap account using natural
  language.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

CleverTap MCP (Model Context Protocol) is a beta server that connects CleverTap directly to AI clients, including Anthropic Claude and ChatGPT. This guide helps you get the CleverTap MCP up and running in your preferred AI client so you can start interacting with your CleverTap account using natural language.

<Callout icon="📘" theme="info">
  **Early Access**

  This integration is in early access and provided as-is for evaluation. Bugs, inconsistencies, or unexpected behavior may occur. Report issues to your CleverTap Customer Success representative.
</Callout>

# Supported AI Clients

The CleverTap MCP server is compatible with the following AI clients:

* Anthropic Claude (web, desktop, and mobile)
* ChatGPT

# Integration with Claude

This section walks you through the steps to connect and use CleverTap MCP with Anthropic Claude.

## Prerequisites

The following prerequisite must be met before connecting CleverTap MCP to Claude.

### Add Custom Connector

To add a custom connector manually in Claude, follow the steps:

1. Open _Claude > Settings > Connectors_
2. Go to the Connectors section in your Claude settings.
3. Click **Add custom connector**. This opens the custom connector form.
4. Enter the connector details:
   1. Name: `CleverTap`
   2. URL: `https://us1.mcp-server.clevertap.com/mcp`
5. Click **Add**, then **Connect**. The connector is saved and authenticated via CleverTap SSO.

The following image shows the _Claude Settings_:

<Image align="center" border={true} caption="Add Custom Connector" src="https://files.readme.io/fe09788e677ec71bfced3047e27a1e9d697083f8916ce93a3857f8f738e30b83-image.png" width="65% " />

# Integration Steps

The following steps help you to integrate CleverTap MCP in Claude:

1. Connect the CleverTap MCP
2. Enable in a Chat
3. Verify the Connection

## Connect the CleverTap MCP

The following steps explain how to connect the CleverTap MCP connector in Claude:

1. Open Claude (web or desktop app). Any Claude interface supports connectors.
2. Go to _Settings > Connectors > Browse Connectors_.
3. Click **Connect** on CleverTap MCP Beta.
4. Select the connector with the `us1` endpoint.
5. Click **Configure** after connecting. This shows the full list of tools and functionality available through the MCP.

The following image shows the “us1“ endpoint connector:

<Image align="center" border={true} caption="Connect the CleverTap MCP" src="https://files.readme.io/e7dd99a6f0c9dd5256c92535514714cf6f19bd9636b5e9262ee86c381a9d384a-image.png" width="60% " />

## Enable in a Chat

The following steps explain how to enable the CleverTap MCP connector within an active Claude chat session:

1. Open a new chat in Claude to start a fresh conversation.
2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
3. Click **Connectors**. A fly-out panel appears.
4. Toggle _CleverTap MCP_ on. The connector is now active for this chat session.

The following image shows the chat screen connector with CleverTap MCP Beta toggle enabled:

<Image align="center" border={true} caption="Enable in a Chat" src="https://files.readme.io/421fb802ee44bd2dd28b4dcb14a638c0cc5174808ef0580f7cc051437ad60bcf-image.png" width="65% " />

## Verify the Connection

Once the connector is enabled, run the following test query in the chat:

**Test Prompt:** What are the projects on CleverTap that my account is currently part of?

**Expected Response:** Claude replies with your CleverTap account email and a list of projects grouped by region.

The following image shows Claude's response with CleverTap projects listed:

<Image align="center" border={true} caption="Test Prompt and Response in Claude" src="https://files.readme.io/7da532fe9ad64ebdd1c9129dadaefb001656a2c17a9ae248de1b79d09b04d510-image.png" width="65% " />

# Integrate CleverTap MCP with ChatGPT

This section walks you through the steps to connect and use CleverTap MCP with ChatGPT.

## Prerequisites

The following prerequisites must be met before connecting CleverTap MCP to ChatGPT:

### Add CleverTap as a Custom App

To add CleverTap as a custom app in ChatGPT, follow the steps:

1. Open _ChatGPT > Profile icon > Settings > Apps_.
2. Enable _Developer Mode_.
3. Return to _Apps_ and click **Create app**. This displays the custom app creation form.
4. Fill in the app details:
   * **Name:** `CleverTap`
   * **Description:** `CleverTap MCP server for analytics and engagement` (optional)
   * **MCP Server URL:**`https://us1.mcp-server.clevertap.com/mcp`
   * **Authentication:**`OAuth` (default)
5. Click **Save**. You will be redirected to the CleverTap dashboard for SSO login.

The following image shows the ChatGPT settings:

<Image align="center" border={true} caption="ChatGPT Settings" src="https://files.readme.io/6b28f67ecb5ed0e3ef8be733846bc6e0efca921e8a87dced3389eb7d7afe7cf8-image.png" width="60% " />

# Integration Steps

The following steps help you to integrate CleverTap MCP in ChatGPT:

1. Enable in a Chat
2. Verify the Connection

## Enable in a Chat

The following steps explain how to enable the CleverTap MCP connector within an active ChatGPT chat session:

1. Open a new chat in ChatGPT to start a fresh conversation.
2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
3. Click **More**.
4. Select _CleverTap_ from the submenu. CleverTap appears as a listed connector.
5. Click **CleverTap** to enable it. The CleverTap icon appears in the chat input bar alongside the **+** icon.

The following image shows after enabling the CleverTap connector:

<Image align="center" border={true} caption="Enable in a Chat" src="https://files.readme.io/5993bae444d5f104c17bf0cc914e6dacee70b31d56894a132289ed9396cea517-image.png" width="60% " />

Once enabled, you can see the CleverTap icon appear in the chat input bar alongside the + icon.

<Image align="center" border={true} caption="CleverTap icon in Chat Input Bar" src="https://files.readme.io/536b6831672fa7622b906c75685c8837a2e8948362585f698456d9a9752d021e-image.png" width="60% " />

## Verify the Connection

Once CleverTap is active in the chat, run the following test query:

**Test Prompt:** What are the projects on CleverTap that my account is currently part of?

**Expected Response:** ChatGPT displays a "Called tool" indicator and replies with your CleverTap projects grouped by region (US, Singapore, Europe, and so on).

The following image shows ChatGPT's response with CleverTap accounts listed:

<Image align="center" border={true} caption="Test Prompt and Response in ChatGPT" src="https://files.readme.io/2d0df97bef7d9730449ac4714f028d6a6d8d80db60bceb1f2d722eb024d1f2ce-image.png" width="60% " />
