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

CleverTap MCP (Model Context Protocol) connects CleverTap directly to AI clients, including Anthropic Claude, ChatGPT, and Cursor. This guide helps you get the CleverTap MCP up and running in your preferred AI client so you can start interacting with your CleverTap account using natural language. For more information on MCP Tools, refer to [CleverTap Tools Reference](doc:clevertap-mcp-tools-reference).

<Callout icon="📘" theme="info">
  ### **Early Access**

  This integration is in early access and provided as-is for evaluation. Report issues to your CleverTap Customer Success representative.
</Callout>

# Supported AI Clients

The CleverTap MCP server is compatible with the following AI clients:

- Anthropic Claude (web, desktop, and mobile)
- ChatGPT
- Cursor

<Callout icon="📘" theme="info">
  ### **Access Limitations**

  Currently, only Admin access is supported. RBAC, PII handling, and Teams are not supported in CleverTap MCP.
</Callout>

<Tabs>
  <Tab title="Anthropic Claude">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in Claude:

    1. [Add Custom Connector](doc:clevertap-mcp-server-integration-guide#add-custom-connector-1)
    2. [Connect the CleverTap MCP](doc:clevertap-mcp-server-integration-guide#connect-the-clevertap-mcp)
    3. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat)
    4. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection)

    ## Add Custom Connector

    To add a custom connector manually in Claude, follow the steps:

    1. Open Claude.
    2. Go to _Settings > Connectors_. You can see a note that Connectors have moved to **Customize**.
    3. Click **Customize.**
    4. Click **+** to choose _Add custom connector_.
    5. Enter the connector details:
       - Name: `CleverTap`
       - URL: `https://us1.mcp-server.clevertap.com/mcp`
    6. Click **Add**, then **Connect**. You will be redirected to the CleverTap dashboard for SSO login.
    7. Follow the prompts to complete sign-in. Once authenticated, your CleverTap MCP connector is ready to use.

    The following image shows the _Claude Settings_:


    <Image src="https://files.readme.io/2bf1eb316e3d20774c2bd7ffb09b90052ff55e870e5505e879e017a8cf8eddd9-image.png" align="center" width="60% " border={true} />


    ## Connect the CleverTap MCP

    The following steps explain how to connect the CleverTap MCP connector in Claude:

    1. Go to _Settings > Connectors > Browse Connectors_.
    2. Click **Connect** on CleverTap MCP.
    3. Click **Configure** after connecting. This shows the full list of tools and functionality available through the MCP.

    The following image shows the “us1“ endpoint connector:


    <Image src="https://files.readme.io/e7dd99a6f0c9dd5256c92535514714cf6f19bd9636b5e9262ee86c381a9d384a-image.png" align="center" width="60% " border={true} />


    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active Claude chat session:

    1. Open a new chat in Claude to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **Connectors**. A fly-out panel appears.
    4. Navigate to the CleverTap MCP settings in your dashboard. Check the status of the CleverTap MCP toggle:
       - If it is already ON, leave it as is, no action needed.
       - If it is OFF, toggle to turn it ON.

    The following image shows the chat screen connector with CleverTap MCP toggle enabled:


    <Image src="https://files.readme.io/421fb802ee44bd2dd28b4dcb14a638c0cc5174808ef0580f7cc051437ad60bcf-image.png" align="center" width="65% " border={true} />


    ## Verify the Connection

    Once the connector is enabled, run the following test query in the chat:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** Claude replies with your CleverTap account email and a list of projects grouped by region.

    The following image shows Claude's response with CleverTap projects listed:


    <Image src="https://files.readme.io/7da532fe9ad64ebdd1c9129dadaefb001656a2c17a9ae248de1b79d09b04d510-image.png" align="center" width="65% " border={true} />

  </Tab>

  <Tab title="ChatGPT">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in ChatGPT:

    1. [Add Custom Connector](doc:clevertap-mcp-server-integration-guide#add-custom-connector-1)
    2. [Enable in a Chat](doc:clevertap-mcp-server-integration-guide#enable-in-a-chat-1)
    3. [Verify the Connection](doc:clevertap-mcp-server-integration-guide#verify-the-connection-1)

    ## Add Custom Connector

    To add CleverTap as a custom app in ChatGPT, follow the steps:

    1. Open _ChatGPT > Profile icon > Settings > Apps > Advanced Settings_.
    2. Enable _Developer Mode_.
    3. Return to _Apps_ and click **Create app**. This displays the custom app creation form.
    4. Fill in the app details:
       - **Name:** `CleverTap`
       - **Description:** `CleverTap MCP server for analytics and engagement`(optional)
       - **MCP URL:**`https://us1.mcp-server.clevertap.com/mcp`
       - **Authentication:**`OAuth` (default)
    5. Click **Save**. You will be redirected to the CleverTap dashboard for SSO login.
    6. Follow the prompts to complete sign-in. Once authenticated, your CleverTap MCP connector is ready to use.

    The following image shows the ChatGPT settings:


    <Image src="https://files.readme.io/6b28f67ecb5ed0e3ef8be733846bc6e0efca921e8a87dced3389eb7d7afe7cf8-image.png" align="center" width="60% " border={true} />


    ## Enable in a Chat

    The following steps explain how to enable the CleverTap MCP connector within an active ChatGPT chat session:

    1. Open a new chat in ChatGPT to start a fresh conversation.
    2. Click the **+** icon at the bottom-left of the chat input. This opens the tools/connectors menu.
    3. Click **More**.
    4. Select _CleverTap_ from the submenu. CleverTap appears as a listed connector.
    5. Click **CleverTap** to enable it. The CleverTap icon appears in the chat input bar alongside the **+** icon.

    The following image shows after enabling the CleverTap connector:


    <Image src="https://files.readme.io/5993bae444d5f104c17bf0cc914e6dacee70b31d56894a132289ed9396cea517-image.png" align="center" width="60% " border={true} />


    Once enabled, you can see the CleverTap icon appear in the chat input bar alongside the + icon.


    <Image src="https://files.readme.io/536b6831672fa7622b906c75685c8837a2e8948362585f698456d9a9752d021e-image.png" align="center" width="60% " border={true} />


    ## Verify the Connection

    Once CleverTap is active in the chat, run the following test query:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** ChatGPT displays a "Called tool" indicator and replies with your CleverTap projects grouped by region (US, Singapore, Europe, and so on).

    The following image shows ChatGPT's response with CleverTap accounts listed:


    <Image src="https://files.readme.io/2d0df97bef7d9730449ac4714f028d6a6d8d80db60bceb1f2d722eb024d1f2ce-image.png" align="center" width="60% " border={true} />

  </Tab>

  <Tab title="Cursor">
    # Integration Steps

    The following steps help you to integrate CleverTap MCP in Cursor:

    1. [Add the CleverTap MCP Server](doc:clevertap-mcp-server-integration-guide#add-the-clevertap-mcp-server)
    2. [Connect and Authenticate](doc:clevertap-mcp-server-integration-guide#connect-and-authenticate)
    3. [Confirm the Tools Availability](doc:clevertap-mcp-server-integration-guide#confirm-the-tools-availability)
    4. [Run a Test Query](doc:clevertap-mcp-server-integration-guide#run-a-test-query)

    ## Add the CleverTap MCP Server

    To add the CleverTap MCP server manually in Cursor, follow the steps:

    1. Open _Cursor > Cursor Settings > Tools & MCPs_.
    2. Under _Installed MCP Servers_, click **Add Custom MCP**. This opens `mcp.json`.
    3. Add the following entry to `mcp.json`.

    The following is a sample entry:

    ```json
    {
      "mcpServers": {
        "CleverTap": {
          "url": "https://us1.mcp-server.clevertap.com/mcp"
        }
      }
    }
    ```

    <Callout icon="📘" theme="info">
      ### Note

      Use the _us1_ endpoint URL shown above, the same endpoint used for the Claude and ChatGPT setup.
    </Callout>

    4. Save the file and switch back to the _Cursor Settings_ tab.

    ## Connect and Authenticate

    The following steps explain how to connect and authenticate the CleverTap MCP server in Cursor:

    1. In _Tools & MCPs_, locate CleverTap under _Installed MCP Servers_. It shows a "Needs authentication" status.
    2. Click **Connect**.
    3. Complete the CleverTap login and authorization in the browser window that opens.

    Once connected, CleverTap shows as active, with a Logout option, a green toggle, and a live tool count, for example, 24 tools, 2 prompts, 3 resources enabled.

    ## Confirm the Tools Availability

    Click the tool count dropdown, or **Show more**, next to CleverTap to expand and view the full list of available tools.

    The following image shows the expanded list of CleverTap MCP tools available in Cursor:


    <Image src="https://files.readme.io/d9fa82973163530f737769f0026f7bbe3582fc3289fd22927ed0afa4cdc62a65-image.png" align="center" caption="Available CleverTap MCP tools" border={true} />


    ## Run a Test Query

    In a Cursor chat or agent session, run the following test query:

    **Test Prompt:** What are the projects on CleverTap that my account is currently part of?

    **Expected Response:** Cursor calls the CleverTap tool and replies with your CleverTap account email and a list of projects grouped by region.
  </Tab>
</Tabs>

# FAQs

### What is MCP?

MCP (Model Context Protocol) is an open standard that lets AI assistants such as Claude connect directly to external tools and data sources. Instead of copying and pasting data into a chat, MCP lets Claude securely fetch live data from a platform such as CleverTap and act on it in real time, all within the conversation.

### Does enabling the connector in Settings automatically activate it in every chat?

No. You need to turn it on per chat. Click the **+** icon in the chat input, open Connectors, and toggle CleverTap ON for each new session.

### Is it possible to work with multiple CleverTap projects in one chat session?

Yes. Claude can list all projects linked to your account and switch context between them within the same session when you specify the project or region by name.
