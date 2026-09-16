---
title: Documentation Access for AI Agents
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Give AI agents and coding assistants access to CleverTap documentation through machine-readable documentation formats.

CleverTap documentation supports AI-friendly access through:

* `llms.txt` — an index of documentation pages.
* Markdown pages — documentation content without the HTML page interface.
* User Documentation — information about using CleverTap.
* Developer Documentation — information about integrating CleverTap.
* CleverTap MCP — access to your CleverTap account through supported AI clients.

<Callout icon="❕" theme="warn">
  ### MCP Information

  - CleverTap MCP and documentation access serve different purposes.
  - **Documentation access** helps an AI agent find and understand CleverTap documentation.
  - **CleverTap MCP** lets an AI client interact with a connected CleverTap account.
</Callout>

## Quick start

Choose the option that matches your task.

| If you want to...                                        | Use                     |
| -------------------------------------------------------- | ----------------------- |
| Find relevant CleverTap documentation                    | `llms.txt`              |
| Read a specific documentation page                       | `.md`                   |
| Ask about CleverTap features                             | User Documentation      |
| Ask about SDKs, APIs, or integrations                    | Developer Documentation |
| Work with data or perform actions in a CleverTap account | CleverTap MCP           |

### Find documentation

Use the User Documentation index for questions about CleverTap features:

`https://docs.clevertap.com/llms.txt`

Use the Developer Documentation index for questions about SDKs, APIs, and integrations:

`https://developer.clevertap.com/llms.txt`

### Read a specific page

Append `.md` to a documentation page URL.

For example:

`https://docs.clevertap.com/docs/getting-started.md`

or:

`https://developer.clevertap.com/docs/android-quickstart-guide.md`

Markdown provides the page content without the surrounding website interface.

## How AI agents should use CleverTap documentation

Use a two-step workflow:

1. **Find the relevant documentation.** Start with the appropriate `llms.txt` index.
2. **Read the relevant page.** Retrieve the Markdown version of the page you need.

This keeps the agent focused on relevant documentation instead of loading the entire documentation site.

### Find the right documentation source

Use **User Documentation** when the question is about using CleverTap.

Examples include:

* Creating and managing segments
* Creating campaigns
* Building Journeys
* Configuring messaging channels
* Analyzing campaign performance
* Understanding user profiles and events
* Using CleverTap features and workflows

Use **Developer Documentation** when the question is about implementing CleverTap.

Examples include:

* Integrating an SDK
* Tracking events
* Managing user profiles
* Using APIs
* Configuring webhooks
* Troubleshooting an integration
* Working with a specific platform or SDK

## User Documentation

The User Documentation explains how to use the CleverTap platform.

Core topics include:

* Users and user profiles
* Events and event properties
* Segments
* Campaigns
* Messaging channels
* Journeys
* Analytics and reports
* Data management
* Integrations
* Personalization

Start with:

`https://docs.clevertap.com/llms.txt`

For example, an AI agent can use the documentation to answer:

* How do I create a segment of users who purchased in the last 30 days?
* What is the difference between Past Behavior and Live User Behavior segments?
* How do I create a Journey for users who viewed a product but did not purchase it?
* How do Journey versions work?
* How do I measure campaign conversions?
* Which messaging channel should I use for a particular use case?

## Developer Documentation

The Developer Documentation explains how to integrate CleverTap into applications and backend systems.

Core topics include:

* SDKs
* Events
* User profiles
* APIs
* Authentication
* Webhooks
* SDK configuration
* Platform-specific integrations
* Developer implementation and troubleshooting

Start with:

`https://developer.clevertap.com/llms.txt`

For example, an AI agent can use the documentation to answer:

* How do I integrate the CleverTap Android SDK?
* How do I track a custom event?
* How do I update a user profile?
* How do I authenticate a CleverTap API request?
* How do I troubleshoot missing events?
* How do I configure CleverTap for a React Native application?

## Use Markdown pages

Use a Markdown page when you already know which documentation page contains the information you need.

To get a Markdown version, append `.md` to the page URL.

For example:

`https://docs.clevertap.com/docs/getting-started.md`

This is useful when you want to:

* Give an AI agent a specific documentation page.
* Reduce unnecessary context.
* Use documentation in a coding assistant.
* Read documentation without the website navigation and other interface elements.

## Use documentation indexes

The `llms.txt` files provide an index of CleverTap documentation that AI agents can use to discover relevant pages.

### User Documentation

`https://docs.clevertap.com/llms.txt`

Use this index for product and platform documentation.

### Developer Documentation

`https://developer.clevertap.com/llms.txt`

Use this index for SDK, API, and implementation documentation.

When the index contains a page that matches the question, retrieve that page directly.

When the question is broader, search the index for the relevant topic and then retrieve the matching pages.

## Give documentation to an AI coding assistant

You can add the appropriate `llms.txt` URL to your AI tool's project instructions or rules.

For product-related work, use:

`https://docs.clevertap.com/llms.txt`

For development-related work, use:

`https://developer.clevertap.com/llms.txt`

Tell the AI tool to use CleverTap documentation as the source of truth for CleverTap-specific questions.

For example:

Use the current CleverTap Developer Documentation as the source of truth. Find the relevant documentation before generating code. Do not assume SDK or API behavior that is not documented.

## Example prompts

### Product and marketing teams

Use the User Documentation for questions about campaigns, segments, Journeys, messaging, and analytics.

Examples:

* "Use the CleverTap documentation to explain how Past Behavior Segments work."
* "Create a Journey for users who viewed a product but did not purchase it. Use the current Journey documentation."
* "What is the difference between Push Notifications, In-App, and App Inbox?"
* "How are campaign conversions measured?"
* "What conditions can I use to qualify users for a campaign?"

### Developers

Use the Developer Documentation for implementation questions.

Examples:

* "Use the current CleverTap Android documentation to show me how to integrate the SDK."
* "Show me how to track a custom event and pass event properties."
* "How do I update a user profile using the CleverTap API?"
* "Use the current API documentation to generate a request for this use case."
* "My events are not appearing in CleverTap. Use the Developer Documentation to help me troubleshoot the integration."

## CleverTap MCP

CleverTap MCP provides a live connection between supported AI clients and a CleverTap account.

It is different from `llms.txt` and Markdown documentation access.

Use **documentation access** when the AI agent needs to understand how CleverTap works.

Use **CleverTap MCP** when the AI client needs to access or interact with a CleverTap account.

CleverTap MCP currently supports AI clients including Claude, ChatGPT, and Cursor. Access requires CleverTap SSO, and RBAC permissions apply in the same way as they do in the CleverTap dashboard.

### What CleverTap MCP can do

CleverTap MCP supports account-specific workflows through natural language. Depending on the tools available to your account, you can use it to perform tasks such as:

* Explore CleverTap projects.
* Query CleverTap data.
* Create segments.
* Retrieve analytics.
* Check campaign performance.
* Perform other supported CleverTap operations.

CleverTap MCP is currently available as a public beta for selected customers. Contact your Customer Success Manager or raise a support ticket to enable it.

### Use documentation and MCP together

Documentation access and CleverTap MCP work together.

For example:

1. Use the CleverTap documentation to understand how a feature works.
2. Use CleverTap MCP to access the relevant account data or perform a supported action.
3. Use the documentation again when you need implementation or feature details.

This gives the AI agent both **CleverTap product knowledge** and **account context**.

## Recommended workflow

Follow this workflow when using an AI agent with CleverTap documentation.

### 1. Identify the task

Determine whether you need product or developer documentation.

* Product or marketing task → User Documentation
* SDK, API, or integration task → Developer Documentation
* Account-specific task → CleverTap MCP

### 2. Find the relevant documentation

Start with the appropriate `llms.txt` index.

Do not load the entire documentation set unless you need broad coverage.

### 3. Read the relevant pages

Retrieve the Markdown version of the pages that match the task.

### 4. Ask the AI agent to use the documentation

Tell the agent to use the current CleverTap documentation as its source of truth.

### 5. Verify account-specific information

Documentation explains how CleverTap works. It does not describe the current configuration or data in your CleverTap account.

For account-specific information, use CleverTap MCP or verify the information directly in the CleverTap dashboard.

## Best practices

### Use the current documentation

CleverTap features, SDKs, and APIs change over time.

Use the current documentation when generating code or making implementation decisions.

### Specify the platform

For SDK questions, tell the AI agent which platform you are using.

For example:

* Android
* iOS
* Web
* React Native
* Flutter
* Unity
* Cordova

### Provide the relevant context

Include information such as:

* The CleverTap feature you are using
* Your SDK or platform
* The API or endpoint you are working with
* The behavior you expect
* The problem you are seeing

This helps the AI agent identify the right documentation.

### Do not treat AI output as the source of truth

Ask the AI agent to use the current CleverTap documentation when answering questions.

If the generated answer conflicts with the documentation, follow the current documentation.

## Resources

| Resource                      | URL                                            |
| ----------------------------- | ---------------------------------------------- |
| User Documentation            | `https://docs.clevertap.com`                   |
| User Documentation index      | `https://docs.clevertap.com/llms.txt`          |
| Developer Documentation       | `https://developer.clevertap.com`              |
| Developer Documentation index | `https://developer.clevertap.com/llms.txt`     |
| CleverTap MCP                 | See the CleverTap MCP Server Integration Guide |
