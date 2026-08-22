---
title: 'Segment Builder: Build with AI'
excerpt: Generate segment query results with a prompt.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Segment Builder allows you to create precise user segments using natural language prompts. The system converts your prompt into structured segment rules that you can further customize using the Query Builder.

This feature helps marketing and product teams create granular segments without needing prior knowledge of event structure, properties, or filter logic.

<Callout icon="📘" theme="info">
  ### Availability

  Segment Builder is available on Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

Prompt-Based Segmentation has the following stages:

1. **Segment Builder**<br />Enter your segment description using plain language. For example:<br />_"Active iOS users who haven’t made a purchase in the last 30 days."_

2. **Query Builder**<br />The system converts the prompt into rules using attributes such as user properties, events, or time filters. These rules are editable and appear on the panel.

3. **Segment Insights**<br />Once rules are generated, the system displays user counts, channel reachability (Push, Email, SMS, and so on), and sample users for the Past Behavior Segment.

4. **Edit and Save**<br />You can refine rules, add new conditions, or group rules as needed. Once finalized, click **Save Segment** to create your new segment.


<Image src="https://files.readme.io/49d0e555e37806a814cd4036dc6bf8aad9856bf28704079eb68e0c132207bf9a-image.png" alt="Segment Builder Example" align="center" caption="Segment Builder Example" border={true} />


# Create a Segment with Prompt

From the CleverTap dashboard:

1. Go to _Segments_ > _Create Segment_.&#x20;
2. Select the required type of segment.

3) In the **Segment Builder** prompt box, enter a clear description.<br />_Example: "Active iOS users who haven't purchased in the last 15 days."_

```
 The agent understands your input and generates a matching query. 
```

3. In the _Query Builder_, review and adjust the query for any of the following:

- Event filters, for example,  _Charged_ or  _Visited Product Page_.
- User Properties, for example,  _OS = iOS_.

4. Use _Add Rule_ or _Add Rule Group_ to include more conditions and filters. For more information, refer to [Segmentation Rules](https://docs.clevertap.com/docs/segmentation-rules).
5. On the right panel, check _Segment Insights_. It will show details such as:

- Total users in the segment.
- Reachability by channel (Push, Email, and so on).
- Sample user list.

6. Click the **Save Segment** button in the top right of the page to store and reuse this segment in campaigns.&#x20;
7. Click the ![](https://files.readme.io/692ff531d0159b637af61e9ba6651b4e9e368a182c54c995cecf31e5e3ae2770-export_user_profiles.png) icon in the _Segment Insights_ section to export your data.
8. To create a new segment, click the New Thread ![](https://files.readme.io/703c02ae3a62e289aef7a6348ee8da943a0ed61817a6b93d585296aa9da17874-allthreadsicon.png) icon.

You can refer to the previous chats by clicking the All threads ![](https://files.readme.io/695b5aa2683faac88af4d44d0a682ef585a7326ea7da29b3bef4148388b4a6df-allthreadicon.png) icon.

<Callout icon="📘" theme="info">
  ### Note

  You can combine multiple behaviors, conditions, and filters in a single prompt or edit the generated query as needed.
</Callout>

# Prompt Segment Operations

You can perform several operations on the Segment Builder window for ease of use.

## Expand or Collapse Sections

Click the ![](https://files.readme.io/01d9cdce28910c60dd5033828094d5bf6b91e586cb13044ad8dde55dde7012ae-Expand_window_icon.png) icon to expand or collapse sections.

## Toolbar

The floating toolbar on the dashboard allows you to select the required section on the Segmentation screen. You can also rearrange the order of the sections by clicking the ![](https://files.readme.io/7fad1fd24fc16c4579dfbb0c4d8a2da17be3dc9ce33ebda3a130e520786ca687-rearrange_icon.png) icon on the toolbar.


<Image src="https://files.readme.io/b541f3f0707ecf8057d5f3be7183d6a049f73e9ef274855061dc743dae9339e1-ChatGPT_Image_Aug_21_2025_01_04_46_AM.png" alt="Segmentation Toolbar" align="center" width="50% " />


# Best Practices

- Use simple and specific prompts.
- Include platforms (iOS/Android), events, or date ranges.
- Review generated conditions for accuracy before saving.
- Save frequently used prompts as named segments.

# FAQs

### How is my data used and sent to OpenAI?

Your data is never used to train OpenAI models, and is deleted by OpenAI within 30 days. To generate AI output through CleverTap AI features that leverage OpenAI, CleverTap sends your prompt along with event names, event properties, user properties, segment names or IDs, or any other relevant input to OpenAI. The input sent to OpenAI by CleverTap does not identify you or your users unless you choose to include identifiable information in your prompt. CleverTap provides no warranties regarding the AI-generated content, including the output. For more information, see OpenAI’s [Enterprise Privacy Policy](https://openai.com/enterprise-privacy).

### Is there a limit to the thread history?

There is no limit to the thread history. The threads are stored locally at the browser level.

### What if my prompt isn't clear?

The system will suggest clarifications or partial matches. Try rephrasing the input.

### Can I add multiple events in one prompt?

Yes. You can say: _"Users who viewed product but didn’t purchase in the last 7 days."_

### Does it support AND/OR conditions?

Yes. Use rule groups to apply logical combinations. The builder uses AND by default and supports nested logic.

### Can I preview users in a segment?

Yes. The Segment Insights panel shows sample users and reachability.

### Can I create queries using custom lists ?

This feature is not supported for custom lists.
