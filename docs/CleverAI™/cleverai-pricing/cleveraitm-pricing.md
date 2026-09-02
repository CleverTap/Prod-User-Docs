---
title: CleverAI™ Pricing Fix
excerpt: >-
  Understand how CleverAI™ Tokens and Blocks work, what each CleverAI™ agent
  costs to run, and how to manage, monitor, and expand your organization's AI
  usage from the CleverTap dashboard.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

CleverAI™ is a group of AI agents built into CleverTap that includes agents such as Scribe, Image Creator, Segment Builder, Predictions, Recommendations, and more. This document explains how CleverTap measures and manages usage of these agents so your organization always knows what it has access to, how much it has used, and how to get more.

CleverAI™ Billing is the commercial and metering layer underneath CleverTap's suite of AI agents. It governs the following three things:

1. Which AI capabilities can you access via the CleverAI™ plan tiers?
2. How the usage of prompt-based agents is metered and charged?
3. How is the usage of capacity-configured Machine Learning (ML) capabilities metered and charged?

CleverAI Billing works on two models, depending on the type of agent:

| Model                 | How does it work?                                                                                                                                                                                                                     | Used by                                                                                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **CleverAI™ Tokens**  | Every time you ask a prompt-based agent to do something, it uses a set number of Tokens.                                                                                                                                              | Scribe, Image Creator, Email Template Creator, WhatsApp Template Creator, Segment Builder, Journey Builder, Analytics Builder, AI Schema, NPS Insights |
| **Blocks & Capacity** | You configure a certain number of active recommendations, predictions, or journey experiments. Once configured, you can use them as much as you want, and you are billed for the capacity you have set up, not for each time it runs. | Recommendations, Predictions, IntelliNode, IntelliAB, IntelliChannel                                                                                   |

> **📘 Who can manage CleverAI™ billing?**
> Only Admins can view CleverAI™ Token and Block balances, turn agents on or off, manage allocation across projects, or request more quota. If you are not an admin, you can still use any agent your admin has enabled.

Before using this guide, remember to understand the following three things:

* [Billing Plan](https://docs.clevertap.com/docs/cleverai-pricing#billing-plan)
* [Role](https://docs.clevertap.com/docs/cleverai-pricing#role)
* [Glossary](https://docs.clevertap.com/docs/cleverai-pricing#glossary)

## Billing Plan

Each CleverTap billing Plan unlocks a different set of CleverAI™ agents for your organization to enable.

| Plan         | What it includes                                                                                         |
| ------------ | -------------------------------------------------------------------------------------------------------- |
| **CORE**     | Image Creator, Scribe (and their Brand Kit integration)                                                  |
| **PRO**      | Everything in CORE, plus Segment Builder, Analytics Builder, IntelliChannel, NPS Insights, and AI Schema |
| **ULTIMATE** | Everything in PRO, plus Journey Builder, Predictions, Recommendations, IntelliNode                       |

Your Plan determines which agents are _available_ to enable. It does not automatically turn them on. An admin still needs to enable each agent per project.

For more information, refer to [Enable/Disable an Agent](https://docs.clevertap.com/docs/cleverai-pricing#enabledisable-agents).

## Roles

Only Admins can manage CleverAI™ settings and view usage. Team members (non-admins) can use any agent an admin has already enabled for their project.

| Activity                            | Admin | Non-admin |
| ----------------------------------- | ----- | --------- |
| Use an enabled agent                | Yes   | No        |
| View CleverAI™ Token/Block balances | Yes   | No        |
| Turn agents on or off               | Yes   | No        |
| Manage allocation across projects   | Yes   | No        |
| Request more Tokens or Blocks       | Yes   | No        |
| View Audit Logs                     | Yes   | No        |

If you are a non-admin and hit a limit or find an agent disabled, every screen you see points you to contact your admin rather than showing you balances or settings directly.

## Glossary

Before using CleverAI™, get familiar with the following terms.

| Term                | What it means                                                                                                          |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Agent**           | A single CleverAI™ capability, such as Scribe, Predictions, or Journey Builder.                                        |
| **CleverAI™ Token** | The unit used to measure one response from a prompt-based agent.                                                       |
| **Block**           | The unit you purchase to expand your capacity for a configuration-based agent, such as Recommendations or Predictions. |
| **Capacity**        | Defines how many configuration-based agents you can have active at once. For example, 4 active Recommendations.        |
| **Allocation**      | How your organization's Tokens and Block capacity are split across projects.                                           |

# CleverAI™ Agents

CleverTap groups CleverAI™ agents into three families based on their functions. The table below lists every agent, what it does, how it is billed, and where to find its full documentation.

## Creator Agents

Creator Agents generate on-brand content, such as copy, images, and templates, directly from a prompt.

| Agent                                                          | What it does                                                                                                                              | Cost per response |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| [Scribe](https://docs.clevertap.com/docs/scribe-1)             | Generates on-brand campaign copy instantly from a prompt, blending your Brand Kit with insights from your best-performing past campaigns. | 3 Tokens          |
| [Image Creator](https://docs.clevertap.com/docs/image-creator) | Generates on-brand campaign images instantly from a prompt, automatically applying your Brand Kit's colors and style.                     | 5 Tokens          |

## Intelligent Agents

Intelligent Agents run continuously in the background, using your account's data to personalize content, predict behavior, or optimize journeys.

| Agent                                                                    | What it does                                                                                                                                             | How it is billed                                                                               |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [Recommendations](https://docs.clevertap.com/docs/recommendations-agent) | Surfaces the most relevant products or content for each user based on their browsing and purchase history, for use across Push, Email, In-App, and more. | 1 Block = 2 active recommendations (fixed capacity, does not reset)                            |
| [Predictions](https://docs.clevertap.com/docs/predictions)               | Forecasts user behaviors such as churn, conversion, uninstalls, and so on to build dynamic segments that update continuously.                            | 1 Block = 5 active predictions (fixed capacity, does not reset)                                |
| [IntelliChannel](https://docs.clevertap.com/docs/intellichannel)         | Identifies the channel each user engages with most across Push, Email, SMS, and WhatsApp, and keeps it updated as behavior changes.                      | Fair-usage capacity of 1,000 sends/month, expandable in Blocks of 1,000/month (resets monthly) |
| [IntelliNode](https://docs.clevertap.com/docs/intellinode)               | Tests up to seven journey paths at once and automatically routes users toward the best-converting path.                                                  | 1 Block = 7 active IntelliNodes (fixed capacity, does not reset)                               |
| [IntelliAB](https://docs.clevertap.com/docs/intelliab)                   | Continuously tests message variants and automatically shifts more traffic to the best-performing one, eliminating the need to manually declare a winner. | Block-based (capacity varies by configuration)                                                 |

## Workflow Agents

Workflow Agents speed up day-to-day tasks such as building segments, analyzing data, and setting up journeys.

| Agent                                                                                | What it does                                                                                                                                                                       | Cost per response |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- |
| [Analytics Builder](https://docs.clevertap.com/docs/analytics-builder)               | Turns a plain-language question into instant charts, trends, or breakdowns. It is the same analysis you would otherwise build manually.                                            | 5 Tokens          |
| [Segment Builder](https://docs.clevertap.com/docs/segment-builder)                   | Describes your audience criteria in a prompt and returns a ready-to-use segment, using the same AND/OR logic as CleverTap's NextGen Segment Builder.                               | 5 Tokens          |
| [Journey Builder](https://docs.clevertap.com/docs/journey-builder)                   | Describes your goal and target users, and builds an engagement journey with pre-filled nodes and scheduling.                                                                       | 13 Tokens         |
| [AI Schema](https://docs.clevertap.com/docs/schema#ai-generated-schema-descriptions) | Automatically generates clear, consistent descriptions for your custom events and properties as you create them, improving results from Segment Builder and Analytics Builder too. | 0 Tokens          |
| [NPS Insights](https://docs.clevertap.com/docs/nps-insights)                         | Analyzes open-ended NPS survey responses to surface themes, sentiment, and what is driving your promoters and detractors, requiring no manual reading.                             | 2 Tokens          |

## Other Agents

The following is an agent that fits into the "other agents" category:

| Agent                                                              | What it does                                                                                                                                                 | How it is billed                  |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------- |
| [Product Catalog](https://docs.clevertap.com/docs/product-catalog) | Manages your entire product catalog, such as names, prices, images, and attributes, in one place, powering personalized recommendations and dynamic content. | Block-based (1 block = 500K rows) |

<Callout icon="🚧" theme="warn">
  #### Chained agent calls add to the total cost

  A response can cost more than the base agent price.**&#x20;**&#x49;f an agent calls on another agent to complete your request, you are charged for all of it. For example, if Journey Builder (13 Tokens) also generates an email header using Scribe (3 Tokens) and a hero image using Image Creator (5 Tokens) as part of building your journey, the total cost for that one action is 13 + 3 + 5 = 21 Tokens. This is shown as a single entry in your usage history.
</Callout>

<Callout icon="📘" theme="info">
  #### **Multiple outputs in one prompt**

  If you ask an agent for multiple outputs in a single prompt, you are charged per output, not per prompt. For example, 5 image variations from Image Creator will be calculated as 5 images × 5 Tokens = 25 Tokens for that one request.
</Callout>

# View AI Allocation

The _AI Allocation_ page allows admins to view organization-wide balances and decide how much of each project gets. By default, all projects consume tokens and agent capacities from the organization's shared pool.

To view the AI allocation for your organization:

1. Go to _Organization_ > _AI Allocation_ from the CleverTap dashboard.
2. At the top, you will see:
   * **CleverAI™ Tokens**: A card showing the Promotional and Purchased Token balances, and their expiry date.
   * **CleverAI™ Blocks & Capacity**: A card showing the number of Blocks and the capacity for each Block-based agent.
3. Below both cards, the _Blocks & Capacity Allocation_ table lists every project, showing how much of each Token/Block type it is using — either a specific number or _Shared_ if it is drawing from the organization's common pool.


<Image src="https://files.readme.io/7891f7e98854147f24b06911f8f5b122bd6ff088db92994e7dbd94e386b37987-image.png" align="center" caption="View AI Allocation for an Organization" border={true} />


## Manage Allocation

The _Manage Allocation_ page allows you to distribute _Tokens_ and _Agent Capacity_ across projects. To do so:

1. From the AI Allocation page, click **Manage Allocation**.
2. Each project appears as its own card, showing its current allocation for every Token or Block type it uses, how much is available to the organization, and how much is used by the project.
3. To change a project's allocation, click **Edit**, then update the number next to any Token or Block type. The _Available to organization_ figure updates immediately as you type, so you can see whether your change fits the availability.
4. To add a new capability to a project's custom allocation, click **Add Agent**, choose the agent(s) to add, and click **Add**.
5. Select **Save** on each project card you have edited, or click **Done** when you have finished editing all projects.


<Image src="https://files.readme.io/a82a24883e0f942f9c8e66bd872e240eee36aae33e7cf7bbbd0236667ae31731-image.png" align="center" caption="Manage Custom Allocation" border={true} />


<Callout icon="🚧" theme="warn">
  #### **You can not allocate less than a project has already used**

  A project's allocation can never be set below what it has already consumed. If you need to reduce a project's Tokens or Blocks, first make sure its usage is below your target number.
</Callout>

## Delete a Project's Custom Allocation

Removing a project's custom allocation returns it to the organization's shared pool for drawing.

To remove all of a project's custom allocation at once:

1. Click **Edit** on the project's card.
2. Click the **Delete** icon.
3. Click **Delete** to confirm.


<Image src="https://files.readme.io/baf7c6932dc77ba41a35dd7a2aae6003a704d854a12b2c18042ab1b819f8832b-2026-08-17_19-45-47_1.gif" align="center" caption="Delete a Project's Custom Allocation" border={true} />


# Enable/Disable Agents

Every CleverAI™ agent is off by default for every project, even if your Plan includes it. An admin needs to turn each agent on before anyone on the project can use it.

To enable an Agent:

1. Go to _Settings_ > _CleverAI™_ > _Agents_ from the CleverTap dashboard.
2. Browse or search for the agent you want to enable, or select the agent to open its details panel. This shows:
   1. Enabled/Disabled status
   2. LLM used (which AI model powers this agent)
   3. Data center location
   4. Token usage (cost per query), for prompt-based agents, or Agent capacity, for Block-based agents
3. Turn on the toggle next to the agent's status to enable it for this project.


<Image src="https://files.readme.io/0e034d7d6797ea09306616c5de37546a3c5ebea032fed2e76c6994d0ed9fd290-2026-08-17_19-05-20_1.gif" align="center" caption="Turn On an Agent" border={true} />


<Callout icon="📘" theme="info">
  ### What Non-admins see?

  Non-admins can open the same _Settings > CleverAI_<sup>TM</sup> page to browse agents and read their descriptions, but the enable/disable toggle is not available to them. If a non-admin needs an agent turned on, they will need to ask their admin directly.
</Callout>

## View CleverAI™ Usage

Every organization can see how much of its CleverAI™ Tokens and Block capacity have been used, broken down by project.

To do so:

1. From the CleverTap dashboard, go to _Organization_ > _Billing_ > _My Plan_.

2. On the _Overview_ tab, you will see two balance cards:
   * **CleverAI™ Tokens**: Shows total, used, and remaining tokens, split into Promotional and Purchased, each with a percentage-used bar.


<Image src="https://files.readme.io/8e6ed80a039cf3a80ed3edf6693020aeb2e1f6397ce3fddae0d45aab598ef0a7-image.png" align="center" caption="View CleverAI™ Tokens Usage" border={true} />


* **CleverAI™ Blocks & Capacity**: Shows the total number of blocks, capacity, and capacity used for each Block-based agent, such as Recommendations, Predictions, IntelliNode, and IntelliAB.


  <Image src="https://files.readme.io/a56f1e28e08286512a07f90ae4dce785f8bd0f968ec72615efeca28b356c9475-image.png" align="center" caption="View CleverAI™ Blocks & Capacity" border={true} />


3. Click **View Detailed Breakdown** to open the _CleverAI™ Usage_ panel showing exactly how your Tokens or Block capacity usage is split across categories.


<Image src="https://files.readme.io/02826ada4ed413a08983c9bcefbd307e84be9f8a83e7579157b161422cba9f6b-2026-08-17_17-14-13_1.gif" align="center" caption="View Breakdown of CleverAI™ is a" border={true} />


4. Below the balance cards, two donut charts show _Tokens and Blocks & Capacity Usage by Projects_. You can toggle each chart between project and user views.


<Image src="https://files.readme.io/6d8105ca27dab80af66ff89318a0494090178d901f53b0b6f15b1eded9dc3e55-image.png" align="center" caption="View CleverAI™ Token and Agent Capacity Usage by Projects" border={true} />


<Callout icon="📘" theme="info">
  #### **Promotional CleverAI**<sup>TM</sup>**&#x20;Tokens**

  Promotional CleverAI<sup>TM</sup> Tokens are a one-time grant included with your contract, valid until your contract's end date. They are used before your Purchased Tokens and do not reset monthly.
</Callout>

# Request More Quota

When your organization needs more Tokens or Block capacity than it currently has, request more directly from the dashboard.

To do so:

1. Click **Request More Quota** from the _AI Allocation_ page, and a two-step form opens.


<Image src="https://files.readme.io/49d7d45433644e9905a524ca2e3b37b360b5e534273d0bb04492009709237b0b-image.png" align="center" caption="Request More Quota for an Organization" border={true} />


2. Select the required amount of CleverAI™ Tokens and Blocks. For example, 50,000 tokens, 7 blocks of Recommendations, 5 blocks of Predictions, and 4 blocks of IntelliNode.


<Image src="https://files.readme.io/868a2b2c76b52612986689b07e6ea674c736463c025020c638916df889d4194c-image.png" align="center" caption="Add Tokens and Blocks Requirements" border={true} />


3. Select **Next**.
4. Confirm your email, add a mobile number, and optionally add any notes about your specific request.


<Image src="https://files.readme.io/022da6f2418f2eb81c4c13be7bc4739aecdfcbe33c30620efa6492f523e058d0-image.png" align="center" caption="Add Contact Details to Request More Quota" border={true} />


5. Select **Request**.

<Callout icon="📘" theme="info">
  #### Note

  Once Tokens hit 100% for a project, prompt-based agents stop responding in that project until an admin reallocates existing Tokens or adds more.
</Callout>

## View Usage History with Audit Logs

Admins can trace exactly who used which agent, when, and what it cost. This is useful for understanding spending or investigating unexpected usage.

To do so:

1. Go to _Settings_ > _Audit Logs_ from the CleverTap dashboard.
2. Use the filters (date range, user, agent, project, or status) to narrow the list.
3. Select any row to open its _Log Details_ panel, showing the full response and metadata, including Tokens consumed and any chained agent calls that contributed to the total.
4. Select the export icon to download the current filtered view as a CSV.


<Image src="https://files.readme.io/4489dfe2cf692717262bf311491181b99afe2e63009854e3a9db1ebe284c9002-image.png" align="center" caption="View Audit Logs" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  Audit Logs are only available to admins. Non-admins who need this information should ask their admin.
</Callout>

# Contract Renewal and Expiry

Your CleverAI™ Tokens and Block capacity are tied to your contract term. If your contract lapses without renewal, your CleverAI™ Token and Block balances will both show as expired.

<Callout icon="👍" theme="okay">
  #### **Renewing before expiry keeps your Tokens**

  If you renew your contract before it lapses, any unused Tokens carry forward with their validity extended to match your new contract term. If your contract expires first, remaining balances are lost.
</Callout>

# CleverTap for Startups

If your organization is on the CleverTap for Startups program, the _My Plan_ page shows CleverAI™ Token usage alongside your regular Essentials plan usage and overages.

## Purchase Tokens

If you are on the CleverTap for Startups plan, you can buy additional CleverAI™ Tokens directly for use with Image Creator and Scribe:

1. From your _My Plan_ page, click **Purchase Tokens**.
2. Select a Token pack from the dropdown.
3. Complete the purchase.

This is a direct, self-serve purchase and does not require a request to the CleverTap team.

# Best Practices

Follow these recommendations to get the most out of your CleverAI™ Tokens and Block capacity:

* **Enable only the agents your team actively uses:** Idle agents cost nothing while off, and this keeps your _Settings_ > _CleverAI™_ > _Agents_ list easy to scan.
* **Check your My Plan page monthly:** Especially if you are running high-volume campaigns with Scribe, Image Creator, or Journey Builder, since these carry higher per-response Token costs.
* **Reallocate before you request more:** If one project is under its Token allocation while another is running low, reallocate from Manage Allocation as it is instant.
* **Watch for chained-agent costs:** Journey Builder and other orchestrating agents can invoke other agents behind the scenes, hence a single action may cost more Tokens than the base agent price suggests.
* **Renew before expiry, not after:** Renewing early preserves your unused Token balance; letting your contract lapse does not.

# Troubleshooting

If you run into one of the following common issues, check these troubleshooting steps before contacting support:

### An agent I need is greyed out and shows a _disabled_ message.

Ask your admin to enable it in _Settings > CleverAI™_, or, if you are the admin, refer to [Enable/Disable an Agent](https://docs.clevertap.com/docs/cleverai-pricing#enabledisable-agents).

### My team hit 100% of Tokens and cannot use the prompt-based agents.

An admin needs to either reallocate unused Tokens from another project (via _Manage Allocation_) or request more Tokens (via _Request More Quota_). Prompt-based agents will not respond again in that project until one of these happens.

### I tried to create a 3rd Recommendation, but the system won't let me.

You have reached your project's Recommendations capacity. Existing Recommendations keep working, but you cannot create a new one until capacity is freed up (by removing/reassigning an existing one) or expanded (via _Request More Quota_).

### Why did one action cost more Tokens than the agent's listed price?

Some agents call other agents behind the scenes. Check the _Audit Logs_ detail panel for that action to see the full breakdown.

### My contract expired, and I cannot access anything.

This is expected. Token and Block balances are tied to your contract term. Contact your Customer Success Manager to renew the contract, as nothing else in the dashboard can restore access until then.

# FAQs

Find answers to common questions about CleverAI™ Tokens, Blocks & Capacity, and billing:

### Do unused CleverAI™ Tokens roll over to the next month?

Tokens do not operate on a monthly cycle. They are valid for the entire term of your contract and are not reset monthly. Some Block-based agents (such as IntelliChannel) do reset their fair-usage capacity monthly, while others (such as Recommendations, Predictions, and IntelliNode) have a fixed capacity that never resets.

### Can I get a refund for a bad AI response?

No. Token usage is final once a response is generated.

### What happens if I ask for 5 images in one prompt?

You are charged for all 5. Token cost scales with how much the agent actually produces, not how many prompts you send.

### Can non-admins request more Tokens?

No. Only admins can request more Tokens or Blocks, or reallocate existing ones. Non-admins are directed to contact their admin.

### Is there a way to purchase Tokens instantly without waiting for CleverTap to respond?

Yes, but only if you are on the CleverTap for Startups plan and use **Purchase Tokens** on your _My Plan_ page. Enterprise customers submit a request via **Request More Quota**, and the CleverTap team reviews it.
