---
title: CleverTap MCP Server Integration Guide
excerpt: >-
  Learn how to connect and configure the CleverTap MCP with your preferred AI
  client to interact with your CleverTap account using natural language.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

CleverTap MCP (Model Context Protocol) connects CleverTap directly to AI clients, including Anthropic Claude and ChatGPT. This guide helps you get the CleverTap MCP up and running in your preferred AI client so you can start interacting with your CleverTap account using natural language. For more information on MCP Tools, refer to [CleverTap Tools Reference](doc:clevertap-mcp-tools-reference).

<Callout icon="📘" theme="info">
  **Early Access**

  This integration is in early access and provided as-is for evaluation. Report issues to your CleverTap Customer Success representative.
</Callout>

# Supported AI Clients

The CleverTap MCP server is compatible with the following AI clients:

* Anthropic Claude (web, desktop, and mobile)
* ChatGPT

<Tabs>
  <Tab title="Anthropic Claude">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in Claude:

    1. Add Custom Connector
    2. [Connect the CleverTap MCP](doc:clevertap-mcp-server-integration-guide#connect-the-clevertap-mcp)
    3. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat)
    4. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection)

    ## Add Custom Connector

    To add a custom connector manually in Claude, follow the steps:

    1. Open Claude.
    2. Go to *Settings > Connectors*. You can see a note that Connectors have moved to **Customize**.
    3. Click **Customize.**
    4. Click **+** to choose *Add custom connector*.
    5. Enter the connector details:
       1. Name: `CleverTap`
       2. URL: `https://us1.mcp-server.clevertap.com/mcp`
    6. Click **Add**, then **Connect**. The connector is saved and authenticated via CleverTap SSO.

    The following image shows the *Claude Settings*:

    <Image align="center" border={true} src="https://files.readme.io/2bf1eb316e3d20774c2bd7ffb09b90052ff55e870e5505e879e017a8cf8eddd9-image.png" width="60% " />

    ## Connect the CleverTap MCP

    The following steps explain how to connect the CleverTap MCP connector in Claude:

    1. Go to *Settings > Connectors > Browse Connectors*.
    2. Click **Connect** on CleverTap MCP.
    3. Click **Configure** after connecting. This shows the full list of tools and functionality available through the MCP.

    The following image shows the “us1“ endpoint connector:

    <Image align="center" border={true} src="https://files.readme.io/e7dd99a6f0c9dd5256c92535514714cf6f19bd9636b5e9262ee86c381a9d384a-image.png" width="60% " />

    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active Claude chat session:

    1. Open a new chat in Claude to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **Connectors**. A fly-out panel appears.
    4. Toggle *CleverTap MCP* on. The connector is now active for this chat session.

    The following image shows the chat screen connector with CleverTap MCP toggle enabled:

    <Image align="center" border={true} src="https://files.readme.io/421fb802ee44bd2dd28b4dcb14a638c0cc5174808ef0580f7cc051437ad60bcf-image.png" width="65% " />

    ## Verify the Connection

    Once the connector is enabled, run the following test query in the chat:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** Claude replies with your CleverTap account email and a list of projects grouped by region.

    The following image shows Claude's response with CleverTap projects listed:

    <Image align="center" border={true} src="https://files.readme.io/7da532fe9ad64ebdd1c9129dadaefb001656a2c17a9ae248de1b79d09b04d510-image.png" width="65% " />
  </Tab>

  <Tab title="ChatGPT">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in ChatGPT:

    1. Add CleverTap as a Custom App
    2. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat-1)
    3. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection-1)

    ## Add CleverTap as a Custom App

    To add CleverTap as a custom app in ChatGPT, follow the steps:

    1. Open *ChatGPT > Profile icon > Settings > Apps*.
    2. Enable *Developer Mode*.
    3. Return to *Apps* and click **Create app**. This displays the custom app creation form.
    4. Fill in the app details:
       * **Name:** `CleverTap`
       * **Description:** `CleverTap MCP server for analytics and engagement`(optional)
       * **MCP URL:**`https://us1.mcp-server.clevertap.com/mcp`
       * **Authentication:**`OAuth` (default)
    5. Click **Save**. You will be redirected to the CleverTap dashboard for SSO login.

    The following image shows the ChatGPT settings:

    <Image align="center" border={true} src="https://files.readme.io/6b28f67ecb5ed0e3ef8be733846bc6e0efca921e8a87dced3389eb7d7afe7cf8-image.png" width="60% " />

    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active ChatGPT chat session:

    1. Open a new chat in ChatGPT to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **More**.
    4. Select *CleverTap* from the submenu. CleverTap appears as a listed connector.
    5. Click **CleverTap** to enable it. The CleverTap icon appears in the chat input bar alongside the **+** icon.

    The following image shows after enabling the CleverTap connector:

    <Image align="center" border={true} src="https://files.readme.io/5993bae444d5f104c17bf0cc914e6dacee70b31d56894a132289ed9396cea517-image.png" width="60% " />

    Once enabled, you can see the CleverTap icon appear in the chat input bar alongside the + icon.

    <Image align="center" border={true} src="https://files.readme.io/536b6831672fa7622b906c75685c8837a2e8948362585f698456d9a9752d021e-image.png" width="60% " />

    ## Verify the Connection

    Once CleverTap is active in the chat, run the following test query:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** ChatGPT displays a "Called tool" indicator and replies with your CleverTap projects grouped by region (US, Singapore, Europe, and so on).

    The following image shows ChatGPT's response with CleverTap accounts listed:

    <Image align="center" border={true} src="https://files.readme.io/2d0df97bef7d9730449ac4714f028d6a6d8d80db60bceb1f2d722eb024d1f2ce-image.png" width="60% " />
  </Tab>
</Tabs>


<Tabs>
  <Tab title="Anthropic Claude">

  # Integration Steps

    The following steps help you to integrate CleverTap MCP in Claude:

    1. Add Custom Connector
    2. [Connect the CleverTap MCP](doc:clevertap-mcp-server-integration-guide#connect-the-clevertap-mcp)
    3. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat)
    4. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection)

    ## Add Custom Connector

    To add a custom connector manually in Claude, follow the steps:

    1. Open Claude.
    2. Go to *Settings > Connectors*. You can see a note that Connectors have moved to **Customize**.
    3. Click **Customize.**
    4. Click **+** to choose *Add custom connector*.
    5. Enter the connector details:
       1. Name: `CleverTap`
       2. URL: `https://us1.mcp-server.clevertap.com/mcp`
    6. Click **Add**, then **Connect**. The connector is saved and authenticated via CleverTap SSO.

    The following image shows the *Claude Settings*:

    <Image align="center" border={true} src="https://files.readme.io/2bf1eb316e3d20774c2bd7ffb09b90052ff55e870e5505e879e017a8cf8eddd9-image.png" width="60% " />

    ## Connect the CleverTap MCP

    The following steps explain how to connect the CleverTap MCP connector in Claude:

    1. Go to *Settings > Connectors > Browse Connectors*.
    2. Click **Connect** on CleverTap MCP.
    3. Select the connector with the`us1` endpoint.
    4. Click **Configure** after connecting. This shows the full list of tools and functionality available through the MCP.

    The following image shows the “us1“ endpoint connector:

    <Image align="center" border={true} src="https://files.readme.io/e7dd99a6f0c9dd5256c92535514714cf6f19bd9636b5e9262ee86c381a9d384a-image.png" width="60% " />

    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active Claude chat session:

    1. Open a new chat in Claude to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **Connectors**. A fly-out panel appears.
    4. Toggle *CleverTap MCP* on. The connector is now active for this chat session.

    The following image shows the chat screen connector with CleverTap MCP toggle enabled:

    <Image align="center" border={true} src="https://files.readme.io/421fb802ee44bd2dd28b4dcb14a638c0cc5174808ef0580f7cc051437ad60bcf-image.png" width="65% " />

    ## Verify the Connection

    Once the connector is enabled, run the following test query in the chat:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** Claude replies with your CleverTap account email and a list of projects grouped by region.

    The following image shows Claude's response with CleverTap projects listed:

    <Image align="center" border={true} src="https://files.readme.io/7da532fe9ad64ebdd1c9129dadaefb001656a2c17a9ae248de1b79d09b04d510-image.png" width="65% " />
  </Tab>

  <Tab title="ChatGPT">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in ChatGPT:

    1. Add CleverTap as a Custom App
    2. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat-1)
    3. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection-1)

    ## Add CleverTap as a Custom App

    To add CleverTap as a custom app in ChatGPT, follow the steps:

    1. Open *ChatGPT > Profile icon > Settings > Apps*.
    2. Enable *Developer Mode*.
    3. Return to *Apps* and click **Create app**. This displays the custom app creation form.
    4. Fill in the app details:
       * **Name:** `CleverTap`
       * **Description:** `CleverTap MCP server for analytics and engagement`(optional)
       * **MCP URL:**`https://us1.mcp-server.clevertap.com/mcp`
       * **Authentication:**`OAuth` (default)
    5. Click **Save**. You will be redirected to the CleverTap dashboard for SSO login.

    The following image shows the ChatGPT settings:

    <Image align="center" border={true} src="https://files.readme.io/6b28f67ecb5ed0e3ef8be733846bc6e0efca921e8a87dced3389eb7d7afe7cf8-image.png" width="60% " />

    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active ChatGPT chat session:

    1. Open a new chat in ChatGPT to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **More**.
    4. Select *CleverTap* from the submenu. CleverTap appears as a listed connector.
    5. Click **CleverTap** to enable it. The CleverTap icon appears in the chat input bar alongside the **+** icon.

    The following image shows after enabling the CleverTap connector:

    <Image align="center" border={true} src="https://files.readme.io/5993bae444d5f104c17bf0cc914e6dacee70b31d56894a132289ed9396cea517-image.png" width="60% " />

    Once enabled, you can see the CleverTap icon appear in the chat input bar alongside the + icon.

    <Image align="center" border={true} src="https://files.readme.io/536b6831672fa7622b906c75685c8837a2e8948362585f698456d9a9752d021e-image.png" width="60% " />

    ## Verify the Connection

    Once CleverTap is active in the chat, run the following test query:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** ChatGPT displays a "Called tool" indicator and replies with your CleverTap projects grouped by region (US, Singapore, Europe, and so on).

    The following image shows ChatGPT's response with CleverTap accounts listed:

    <Image align="center" border={true} src="https://files.readme.io/2d0df97bef7d9730449ac4714f028d6a6d8d80db60bceb1f2d722eb024d1f2ce-image.png" width="60% " />
  </Tab>
</Tabs>

<br />
