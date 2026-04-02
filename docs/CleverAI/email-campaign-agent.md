---
title: Email Campaign Agent
excerpt: >-
  Learn how to create email templates faster by describing your intent and
  letting the Email Campaign Agent generate editable template.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

AI-powered Email Campaign Agent helps marketers create email templates and campaigns faster using generative AI. Instead of starting from a blank canvas, you can describe your intent in natural language and let AI generate an email template that you can further customize using the visual editor. You can use this feature when:

* Quickly generate email copy and layout ideas.
* Experiment with tone, messaging, or CTAs.
* Accelerate campaign creation without writing content from scratch.

This experience is designed to reduce time-to-live while keeping marketers in full control of the final email.

# Create Campaign Using Email Campaign Agent

This section walks through creating an email template using an example, so you can understand how the Email Campaign Agent fits into your workflow.

Consider an example where you want to create a promotional email announcing a new feature to existing users. To create an email template, perform the following steps:

1. Go to the _Campaigns_ page from the CleverTap dashboard.
2. Select _Email_ from the list of Messaging Channels.
3. Go to the _What_ section and click **Go to Editor**.
4. Select _Drag and Drop_ editor.

   <Image align="center" border={true} caption="Access Email Campaign Agent" src="https://files.readme.io/268194e9dafcf4c0bf2e2169f992e65fa972c6b50be096a24d5d2f15603dd3f0-Access_Email_Campaign_Agent.gif" />
5. In the AskAI section, enter a prompt that explains what you want to create. For example,

   <br />

   ```
   Create a promotional email announcing a new Instagram analytics feature for existing customers. Use a friendly but professional tone. Highlight one key benefit and include a clear call-to-action to explore the feature.
   ```

   <Image align="center" border={true} caption="Generate Template Using Email Campaign Agent" src="https://files.readme.io/dd198e9e429c75331f0e7f261dbe563620276941e693865a3cb7e1ce99914d1c-Generate_Template_Using_Email_Campaign_Agent.png" />
6. Review the generated template and refine the template using follow-up prompts. For example, "Make the tone friendly", "Change the CTA to focus on urgency", and so on.
7. (Optional) Customize the layout in the Email Editor after the template is generated. For example,
   * Edit text directly in the visual editor.
   * Add or remove sections, images, or buttons.
   * Replace AI-generated copy with custom messaging where needed.

Save the generated template to reuse individual sections or the entire template in future campaigns.

# Customize Template for Brand Consistency

Email Campaign Agent supports integration with CleverTap’s creative tool, such as Brand Kit, to help you maintain consistent branding across all messages. Using this feature, you can apply pre-defined visual assets, color palettes, and typography to maintain brand consistency across campaign messages. For more information, refer to [Brand Kits](doc:brand-kit).

<Image align="center" border={true} caption="Customize Template Using Brand Kit for Brand Consistency" src="https://files.readme.io/a8d1e54bd1e5d7f2abc905fd8507627f460f83dd71320afda2754ade8c394705-Access_Brand_Kit.png" />

# Manage Generated Templates

All AI-generated templates will be saved under the _Saved Templates_ section of the email editor and can be accessed via [Threads](https://docs.clevertap.com/docs/designer-agent#threads). Also, the images generated as a part of this process can be accessed via [AI Generated Images Folder](https://docs.clevertap.com/docs/designer-agent#ai-generated-images-folder).

## Threads

Once you start generating Templates, it automatically saves your sessions under the ![](https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png) tab. Each session is stored as a **thread**, which captures your prompts, refinements, and generated outputs, helping you resume from where you left off without losing context.

<Image align="center" alt="All Threads" border={true} caption="All Threads" src="https://files.readme.io/e18467fe443fb9cfb9105b317084b72c3fa08175240f3a71972d6b8d07a060d1-All_Email_Template_Threads.png" />

### How Threads Work

Threads are scoped to your **Account**, **Agent**, and **User**, ensuring that your history remains personalized and relevant. All threads for your account appear in the **All Threads** popup. A thread becomes the context for your next generation, allowing Clever.AI to remember your prior visual style, brand preferences, or edits. They are not tied to specific campaigns; they persist across multiple campaigns for seamless continuity.

If multiple users from the same account use AI tools:

* Each user sees only their own threads and the latest template generation session that they have participated in.
* Threads are separate for Segmentation, Analytics, Designer Agent, and Copywriter Agent, even under the same account.

### Manage Threads

From the **All Threads** view, you can:

* Reopen an older thread to continue generating or editing templates using the same context.
* Review and compare multiple template versions created during that session.
* Restore or reuse previously generated templates without regenerating them.

<Callout icon="💡" theme="default">
  #### **Tip**

  For subsequent edits, you need not restart a session. You can type your next instruction directly in the chat. For example: _“Make the background blue and add a 50% OFF badge in the corner.”_ The AI will update the existing template while maintaining your brand styling and earlier visual tone.
</Callout>

<br />
