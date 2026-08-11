---
title: Analytics Builder
excerpt: Generate advanced queries and visual reports with a simple prompt.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

<br />

Analytics Builder lets you generate advanced queries and visual reports simply by describing your intent in plain language. This AI-powered agent saves time by eliminating the need to create advanced queries or manually navigate query builder menus.

Use this feature to quickly explore user behavior or product usage by entering a natural language prompt.

<Callout icon="📘" theme="info">
  ### Private Beta

  Currently, this feature is a Private Beta Release. If you want access to this feature, contact your CSM or Account Manager.
</Callout>

Analytics Builder has three stages:

1. **AskAI**<br />Enter your prompt in the **AskAI** input box. For example: _"Show me active users trend for the past week."_

2. **Query Builder**<br />The agent interprets your prompt and runs a structured query. You can edit this query to further customize filters, events, or metrics as required.

3. **Analysis Output**<br />The query analysis is available in the _Analysis_ section. If you modified the query, click **View Analysis** to run it again. The output appears in the Analysis section.


<Image src="https://files.readme.io/bad38a738c048e519181618f281ecdf8f1149ea6fc2ac64586dd4ff262173213-image.png" alt="Visual for Analytics" align="center" border={true} />


# Generate Analytics Insights

To use Analytics Builder:

1. From the CleverTap dashboard, go to Analytics, and select New Trends, Funnels, or Flows.


<Image src="https://files.readme.io/41e93af4dff81c8552b7905cc8cccb1ee91d0ad02509a727dcccc3164ba54c3e-2025-09-18_20-15-35.gif" alt="Generate Insights" align="center" border={true} />


2. Enter your question in the _AskAI_ input box. For Example: _"Show me active users trend for the past week_".
3. The system will generate a query in the _Query Builder_. Edit the query to modify any fields, filters, or event parameters.
4. View results in the _Analysis_ section.
5. To generate a new query, click the **New Thread** ![](https://files.readme.io/703c02ae3a62e289aef7a6348ee8da943a0ed61817a6b93d585296aa9da17874-allthreadsicon.png) icon.

You can refer to the previous threads by clicking the **All threads** ![](https://files.readme.io/695b5aa2683faac88af4d44d0a682ef585a7326ea7da29b3bef4148388b4a6df-allthreadicon.png) icon. It shows your past queries. Click the queries to show the results. You can also go back to the previous questions in this thread to view the results.


<Image src="https://files.readme.io/7ba040667071f1d6cbe95c0de44d1d6973d28822be2f16cce2c7f50ed2372b37-Previous_Thread_Analytics_prompt.gif" alt="Previous Threads and queries" align="center" border={true} />


# Best Practices

Follow these best practices to get the best results:

- Use descriptive, focused prompts.
  - _Do_: "Show monthly sign-ups by platform."
  - _Avoid_: "Tell me everything about users."
- Include time frames and event types for better precision.
- Use domain-specific language familiar to your workspace.

# FAQs

### Can I edit the generated query?

Yes. You can modify the filters, time range, and logic in the _Query Builder_ section.

### What types of Analytics are supported?

This feature supports new Trends, Funnels, and Flows.

### How is my data used and sent to OpenAI?

Your data is never used to train OpenAI models, and is deleted by OpenAI within 30 days. To generate AI output through CleverTap AI features that leverage OpenAI, CleverTap sends your prompt along with event names, event properties, user properties, segment names or IDs, or any other relevant input to OpenAI. The input sent to OpenAI by CleverTap does not identify you or your users unless you choose to include identifiable information in your prompt. CleverTap provides no warranties regarding the AI-generated content, including the output. For more information about OpenAI's data handling, refer to OpenAI’s [Enterprise Privacy Policy](https://openai.com/enterprise-privacy).

### Why can't I see my conversation threads ?

Clearing your browser storage will also clear your conversation threads.&#x20;

### Is there a limit to the thread history?

There is no limit to the thread history. The threads are stored locally at the browser level.

### What if my prompt is unclear?

The system will prompt you to rephrase. Use direct and specific language for better interpretation.

### Are custom events supported?

Yes. All custom events configured in your workspace are supported.
