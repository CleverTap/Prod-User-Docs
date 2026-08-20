---
title: 'Analytics Builder: Build with AI'
excerpt: Generate advanced queries and visual reports with a simple prompt.
deprecated: false
hidden: false
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
  ### Availability

  Analytics Builder is available in Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

Analytics Builder has three stages:

1. **Analytics Builder**<br />Enter your prompt in the **Analytics Builder** input box. For example: _"Show me active users trend for the past week."_

2. **Query Builder**<br />The agent interprets your prompt and runs a structured query. You can edit this query to further customize filters, events, or metrics as required.

3. **Analysis Output**<br />The query analysis is available in the _Analysis_ section. If you modified the query, click **View Analysis** to run it again. The output appears in the Analysis section.&#x20;


<Image src="https://files.readme.io/d8814da41ef40cc73ca81c01fc41bd352fc277e422684a6ba46813d739d134b6-image.png" alt="analytics builder example" align="center" caption="Analytics Builder Example" border={true} />


# Generate Analytics Insights

To use Analytics Builder:

1. From the CleverTap dashboard, go to Analytics, and select New Trends, Funnels, or Flows.&#x20;

2) Enter your question in the _Analytics Builder&#x20;_&#x69;nput box. For Example: _"Show me active users trend for the past week_".
3) The system will generate a query in the _Query Builder_. Edit the query to modify any fields, filters, or event parameters.
4) View results in the _New Analysis_ section.
5) To generate a new query, click the **New Thread** ![](https://files.readme.io/703c02ae3a62e289aef7a6348ee8da943a0ed61817a6b93d585296aa9da17874-allthreadsicon.png) icon.

You can refer to the previous threads by clicking the **All threads** ![](https://files.readme.io/695b5aa2683faac88af4d44d0a682ef585a7326ea7da29b3bef4148388b4a6df-allthreadicon.png) icon. It shows your past queries. Click the queries to show the results. You can also go back to the previous questions in this thread to view the results.

# Prompt Segment Operations

You can perform several operations on the Segment Builder window for ease of use.

## Expand or Collapse Sections

Click the ![](https://files.readme.io/01d9cdce28910c60dd5033828094d5bf6b91e586cb13044ad8dde55dde7012ae-Expand_window_icon.png) icon to expand or collapse sections.

## Toolbar

The floating toolbar on the dashboard allows you to select the required section on the Segmentation screen. You can also rearrange the order of the sections by clicking the ![](https://files.readme.io/7fad1fd24fc16c4579dfbb0c4d8a2da17be3dc9ce33ebda3a130e520786ca687-rearrange_icon.png) icon on the toolbar.


<Image src="https://files.readme.io/b541f3f0707ecf8057d5f3be7183d6a049f73e9ef274855061dc743dae9339e1-ChatGPT_Image_Aug_21_2025_01_04_46_AM.png" alt="Segmentation Toolbar" align="center" width="50% " />


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

### Why can't I see my conversation threads?

Clearing your browser storage will also clear your conversation threads.&#x20;

### Is there a limit to the thread history?

There is no limit to the thread history. The threads are stored locally at the browser level.

### What if my prompt is unclear?

The system will prompt you to rephrase. Use direct and specific language for better interpretation.

### Are custom events supported?

Yes. All custom events configured in your workspace are supported.