---
title: Segmentation Agent
excerpt: Generate segment query results with a prompt.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Segmentation Agent allows you to create precise user segments using natural language prompts. The system converts your prompt into structured segment rules that you can further customize using the Query Builder.

This feature helps marketing and product teams create granular segments without needing prior knowledge of event structure, properties, or filter logic.

> 📘 Private Beta
>
> Currently, this feature is released in Private Beta. If you want access to this feature, contact your Customer Success Manager.

Prompt-Based Segmentation has three stages:

1. **AskAI**\
   Enter your segment description using plain language. For example:\
   *"Active iOS users who haven’t made a purchase in the last 30 days."*

2. **Query Builder**\
   The system converts the prompt into rules using attributes such as user properties, events, or time filters. These rules are editable and appear on the panel.

3. **Segment Insights**\
   Once rules are generated, the system displays user counts, channel reachability (Push, Email, SMS, and so on), and sample users for the Past Behavior Segment.

4. **Edit and Save**\
   You can refine rules, add new conditions, or group rules as needed. Once finalized, click **Save Segment** to create your new segment.

<Image alt="prompt to segmentation " align="center" border={true} src="https://files.readme.io/a1e58df79c482d230da07227df6cac1cfff89b4b43aa3d2fb901da257a8acd8a-promp_to_segmentation_demo.png">
  Analytics Agent
</Image>

# Create a Segment with Prompt

From the CleverTap dashboard:

1. Go to *Segments* > *Create Segment*. Select the required type of segment. 

<Image alt="Generate Query" align="center" border={true} src="https://files.readme.io/6601948ffbf628c51460cf74209612fa94ee32bdf7a793150846a752e5170440-prompt_to_segmentation_gif.gif">
  Generate Query
</Image>

2. In the **Ask AI** prompt box, enter a clear description.\
   *Example: "Active iOS users who haven't purchased in the last 15 days."*

```
 The agent understands your input and generates a matching query. 
```

3. In the *Query Builder*, review and adjust the query:

* Event filters, for example,  *Charged* or  *Visited Product Page*. 
* User Properties for example,  *OS = iOS*.

2. Use *Add Rule* or *Add Rule Group* to include more logic. For more information, refer to [Segmentation Rules](https://docs.clevertap.com/docs/segmentation-rules).
3. On the right panel, check *Segment Insights*. It will show details such as:

   * Total users in the segment.
   * Reachability by channel (Push, Email, and so on).
   * Sample user list.
4. Click **Save Segment** to store and reuse this segment in campaigns.
5. Click the ![](https://files.readme.io/692ff531d0159b637af61e9ba6651b4e9e368a182c54c995cecf31e5e3ae2770-export_user_profiles.png) icon in the *New Analysis* section to export your data.
6. To create a new segment, click the New Thread ![](https://files.readme.io/703c02ae3a62e289aef7a6348ee8da943a0ed61817a6b93d585296aa9da17874-allthreadsicon.png) icon. 

You can refer to the previous chats by clicking the All threads ![](https://files.readme.io/695b5aa2683faac88af4d44d0a682ef585a7326ea7da29b3bef4148388b4a6df-allthreadicon.png) icon.

> 📘 Note
>
> You can combine multiple behaviors, conditions, and filters in a single prompt or edit the generated query as needed.

# Prompt Segment Operations

You can perform several operations on the Ask AI window for ease of use.

## Expand or Collapse Sections

Click the ![](https://files.readme.io/01d9cdce28910c60dd5033828094d5bf6b91e586cb13044ad8dde55dde7012ae-Expand_window_icon.png) icon to expand or collapse sections.

## Toolbar

The floating toolbar on the dashboard allows you to select the required section on the Segmentation screen. You can also rearrange the order of the sections by clicking the ![](https://files.readme.io/7fad1fd24fc16c4579dfbb0c4d8a2da17be3dc9ce33ebda3a130e520786ca687-rearrange_icon.png) icon on the toolbar. 

<Image alt="Segmentation Toolbar" align="center" width="50% " src="https://files.readme.io/b541f3f0707ecf8057d5f3be7183d6a049f73e9ef274855061dc743dae9339e1-ChatGPT_Image_Aug_21_2025_01_04_46_AM.png">
  Segmentation Toolbar
</Image>

# Best Practices

* Use simple and specific prompts.
* Include platforms (iOS/Android), events, or date ranges.
* Review generated conditions for accuracy before saving.
* Save frequently used prompts as named segments.

# FAQs

### How is my data used and sent to OpenAI?

Your data is never used to train OpenAI models, and is deleted by OpenAI within 30 days. To generate AI output through CleverTap AI features that leverage OpenAI, CleverTap sends your prompt along with event names, event properties, user properties, segment names or IDs, or any other relevant input to OpenAI. The input sent to OpenAI by CleverTap does not identify you or your users unless you choose to include identifiable information in your prompt. CleverTap provides no warranties regarding the AI-generated content, including the output. For more information, see OpenAI’s [Enterprise Privacy Policy](https://openai.com/enterprise-privacy).

### Is there a limit to the thread history?

There is no limit to the thread history. The threads are stored locally at the browser level.

### What if my prompt isn't clear?

The system will suggest clarifications or partial matches. Try rephrasing the input.

### Can I add multiple events in one prompt?

Yes. You can say: *"Users who viewed product but didn’t purchase in the last 7 days."*

### Does it support AND/OR conditions?

Yes. Use rule groups to apply logical combinations. The builder uses AND by default and supports nested logic.

### Can I preview users in a segment?

Yes. The Segment Insights panel shows sample users and reachability.

### Can I create queries using custom lists ?

This feature is not supported for custom lists.
