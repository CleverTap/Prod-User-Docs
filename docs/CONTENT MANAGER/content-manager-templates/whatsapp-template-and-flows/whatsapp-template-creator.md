---
title: 'WhatsApp Template Creator: Generate with AI'
excerpt: >-
  Use CleverTap's Template Builder Agent to generate WhatsApp template content
  with AI
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Template Builder Agent helps you create WhatsApp templates faster using generative AI. Instead of starting from a blank Template Form, you describe your intent in natural language and let AI generate a template that you can further refine.

Use this feature to:

- Generate template, body, copy, and structure quickly.
- Experiment with tone, offers, or calls to action.
- Accelerate template creation without writing content from scratch.

This experience is designed to reduce time-to-live while keeping you in full control of the final template.&#x20;

<Callout icon="📘" theme="info">
  ### Availability

  WhatsApp Template Creator agent is available in Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

This document covers the following:

- [Create a WhatsApp Template Using the Template Builder Agent](doc:whatsapp-template-creator#create-a-whatsapp-template)
- [Configure Content Settings](doc:whatsapp-template-creator#configure-content-settings)
- [Customize Templates for Brand Consistency](doc:whatsapp-template-creator#customize-templates-for-brand-consistency)
- [Manage Generated Templates](doc:whatsapp-template-creator#manage-generated-templates)

## Create a WhatsApp Template

Consider an example where you want to create a limited-time offer template announcing a Diwali sale to existing customers. To create the template, perform the following steps:

1. Navigate to _Content Manager > Templates > WhatsApp_.

2. Select the required WABA account, then click **Create Template**.

3. Select a Layout category or a Pre-built template, as you would for any WhatsApp template.

4. In the **AskAI** panel, enter a prompt that explains what you want to create. For example:

   ```
   Create a limited-time offer template for a Diwali sale offering 20% off for existing customers. Use a festive, friendly tone. Include an offer expiration timer and a clear call-to-action to shop the sale.
   ```

5. Review the generated fields in the Template Form, and refine using follow-up prompts. For example, "Make the offer title shorter" or "Make the tone more festive."

6. (Optional) Customize the template in the Template Form after it is generated. For example:
   - Edit any field directly in the Template Form.
   - Add or remove buttons or media.
   - Replace AI-generated copy with custom messaging where needed.

7. Review the message in the _Preview_ panel, then click **Send for Approval**.


   <Image src="https://files.readme.io/10b350811733b65ae2372c2dc1f3bdc8ce7f6cd882daf9f40111bfbacdac72b6-ask_AI_Whatsapp.png" align="center" caption="Create Template with AI" border={true} />


<Callout icon="🚧" theme="warn">
  ### Availability

  - The Template Builder Agent is available only for WhatsApp Direct
  - The Template Builder Agent is not available for Authentication templates.
</Callout>

## Configure Content Settings

[Content Settings](doc:scribe1#content-settings) let you control how the Template Builder Agent generates your template content before you prompt it.

## Customize Templates for Brand Consistency

The Template Builder Agent integrates with Brand Kit, so generated templates follow your predefined brand colors, tone, and guidelines. You can select a Brand Kit from the AskAI panel before you prompt. For availability, access, and setup, refer to [Brand Context](doc:brand-context).

## Manage Generated Templates

WhatsApp templates generated with AI persist only when you submit them, and you can restore earlier versions within a generation session.

You can retrieve any previous version generated during a session by clicking **Click to restore this version**.


<Image src="https://files.readme.io/61250dbb8f4b89b57fbcd30969e0de3a361014a805360bed4225c4eeec275b83-restore_version.png" align="center" caption="Restore Version" border={true} />


<Callout icon="🚧" theme="warn">
  ### Unsubmitted Content Is Not Saved

  AI-generated content is not saved as a reusable draft. A template is saved only when you click **Send for Approval**. After Meta approves it, the template is reusable across campaigns like any other approved template. If you close the editor without submitting, reopen your generation session from Threads to continue where you left off.
</Callout>

### Threads

Once you start generating Templates, it automatically saves your sessions under the <img src="https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png" valign="middle" height="20"> panel. Each session is stored as a **thread**, which captures your prompts, refinements, and generated outputs, helping you resume from where you left off without losing context. If you clear your browser storage or use a different browser or device, your threads will not be available.

#### Thread Behavior

Threads are scoped to your **Account**, **Agent**, and **User**, ensuring that your history remains relevant. All threads for your account appear in the **All Threads** popup. A thread becomes the context for your next generation, allowing Clever.AI to remember your prior style, brand preferences, or edits. Threads are not tied to specific templates; they persist across multiple templates for seamless continuity.

If multiple users from the same account use AI tools, each user sees only their own threads and the latest template generation session in which they have participated.

#### Manage Threads

The **All Threads** popup lists each thread with its _Thread Name_, _Created On_, and _Last Updated_ dates. From this view, you can:


<Image src="https://files.readme.io/0227727a7e39055adfc0b85b24db696c91645bb4885e08f6b883dde5e9749376-all_threads_-_ask_ai.png" align="center" caption="All Threads" border={true} />


- Select a thread and click **Load Thread** to continue generating or editing templates using the same context.
- Review and compare multiple template versions created during that session.
- Restore or reuse previously generated templates without regenerating them.

<Callout icon="💡" theme="default">
  #### Tip

  This behavior works because the AskAI conversation thread stays open in your browser session, keeping your message history and template state in memory. As long as you are in the same thread, you need not restart a session. You can type your next instruction directly in the chat. For example: "_Shorten the offer title and make the tone more festive._" The AI applies the edit using the accumulated context from your earlier prompts, including brand styling and tone. If you close the tab, clear browser storage, or open a new session, this continuity breaks and you will need to start fresh.
</Callout>

## Additional Resources

<Cards columns="2">
  <Card title="Brand Context" href="doc:brand-context" target="https://docs.clevertap.com/docs/brand-kit">
    Apply predefined visual assets and typography for brand consistency.
  </Card>

  <Card title="AI-Enabled Feature Disclaimer & Terms" href="doc:clevertapai-terms-disclaimer" target="https://docs.clevertap.com/docs/clevertap-aienabled-feature-disclaimer-terms">
    Review the terms that apply to CleverTap's AI-enabled features.
  </Card>
</Cards>
