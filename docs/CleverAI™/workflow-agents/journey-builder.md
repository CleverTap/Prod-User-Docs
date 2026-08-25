---
title: 'Journey Builder: Build with AI'
excerpt: >-
  Learn how to build a Journey from a natural-language prompt using Journey
  Builder agent.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Journey Agent lets you create customer journeys using natural-language prompts. Describe your goal, for example, "Create a re-engagement journey for inactive users", and the system automatically converts it into a structured journey workflow.

<Callout icon="📘" theme="info">
  #### Availability

  Journey Agent is available on Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

Creating a journey using Journey Agent includes the following four key stages:

1. **AskAI**<br />Enter your journey objective in the Build with AI input field. For example, "Create a re-engagement journey for users inactive for 30 days."
2. **Journey Builder**<br />The system interprets your prompt and generates a visual journey with predefined triggers, actions, and conditions. You can modify these elements directly in the builder.
3. **Review Journey**<br />Review the generated journey to confirm the audience reach, key touchpoints, and engagement logic. You can proceed to manually edit the journey to make further tweaks.
4. **Publish Journey**<br />Once you have finished building the journey, click **Publish** to launch your journey. You can monitor its performance later in the Journey Dashboard.


<Image src="https://files.readme.io/f1f588e1e1b372711dd2e462d76616677d404ca2063b6580e19422ca7f2ba1c4-Journey_Using_Prompts_-_Overview.gif" align="center" caption="Journey Builder Agent" border={true} />


# Build a Journey with AI

To create a journey using prompts, perform the following steps:

1. Go to _Journeys_ and click **+ Journey**.

2. Select _Build with AI_.

3. In the AskAI prompt input field, enter your journey description. For example, `Create an onboarding journey for Ecommerce app`. The system generates a visual flow with:

   - **Entry**: The event or condition that triggers the journey (for example, App Installed).
   - **Actions**: Users receive a Push Notification.


   <Image src="https://files.readme.io/a51e50bf6a5c088e2fdb75bb045d4f1d0c965a6099af33e47a50d3e39e47d786-E-Commerce_Onboarding_Journey_Using_AI.gif" align="center" caption="Build Sample ECommerce Journey Using Prompr" border={true} />


4. Review the generated journey and refine it using follow-up prompts. For example, you can remove an SMS node and force users who engage with the Email campaign to exit.


   <Image src="https://files.readme.io/d31a89be5b0c38f0d20f1a0306cb07d5f9ebe6210f82173128c9c863aa981f2c-Modify_Generated_Journey.png" align="center" caption="Modify Journey Built Using Agent" border={true} />


5. Click **Proceed to Manual Builder**, then click **Publish** once you have reviewed your journey and are ready to activate it.

<Callout icon="📘" theme="info">
  #### Best Practices

  - Use clear, action-oriented prompts (for example, "Create a win-back journey for users who haven't opened the app in 14 days.").
  - Explicitly mention **which channels** you want to include in the journey (Push, Email, SMS, or WhatsApp).
  - Specify **wait periods or delays** between steps to help the system generate accurate timing in the journey.
  - Review the generated workflow before launch to verify conditions.
  - Save commonly used journeys for future use.
  - Test with a smaller audience before full rollout.
</Callout>

# Add Visuals and Brand Consistency

Journey Agent supports integration with CleverTap's creative tools to help you maintain consistent branding across all messages:

- **Brand Kits**: Apply pre-defined visual assets, color palettes, and typography to maintain brand consistency across campaign messages. For more information, refer to [Brand Kits](doc:brand-kit).


  <Image src="https://files.readme.io/cf626c650bbc751eb77e7581bb25a7496049962ea6c3bdac6d4dec55146782db-Brnad_Kits.png" align="center" caption="Applying Brand Kit to Journeys for Brand Consistency" border={true} />


- **Image Creator Agent**: Automatically generate or optimize creative assets using AI suggestions based on your campaign type. For more information, refer to [Image Creator](doc:image-creator).

# Manage Generated Journeys

Journeys created with Journey Agent land on the same Journey canvas used for manually built journeys. There is no separate list for AI-generated output.


<Image src="https://files.readme.io/7756cd1bf9edbaee95c6abcef4e6b9bbba86bf0096b0b7a340e1da2053891d50-Manage_Generated_Journeys.png" align="center" caption="Save Journey" border={true} />


- **Save as Draft**: The journey appears in the standard Journey List alongside manually created journeys.
- **Save as a Template**: The journey appears under the _Saved Templates_ tab on the Journey List page, and under a _Saved Templates_ group in the template gallery when creating a new journey.


  <Image src="https://files.readme.io/b616fc1328829919587614add97c35b7a82218676b72b2b742d42776c6eddb6c-Save_Journey_as_Template.gif" align="center" caption="Save Journey as Template" border={true} />


  You can access the Template gallery in two ways:

  - From the Journey canvas, click the Template gallery option at the top.
  - From the Journey setup popup.

# Threads

Every Journey Builder agent session is saved as a thread under the <img src="https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png" valign="middle" height="20" /> panel. A thread captures your prompts, refinements, and the resulting conversation, so you can return to a session and continue building from where you left off.&#x20;

Click <img src="https://files.readme.io/4ce730d20d0f4d879c8d272499d564cc1c0b9b9649413b634c914a63dbb72c48-New_Thread_Icon.png" valign="middle" height="30" /> to start a fresh session, or click <img src="https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png" valign="middle" height="20" /> to see previous sessions, listed by _Thread Name_, _Created On_, and _Last Updated_. Click **Load Thread** to reopen a session and continue the conversation.

<br />


<Image src="https://files.readme.io/0c531522839b2edf368956b1d2f0df1e7a7fd6d75ce4fc9e7f2ef6014fbaee56-All_Threads_-_Journey_Builder.png" align="center" caption="Access All Threads" border={true} />


## How Threads Work

Threads are stored locally in your browser and are not synced across devices or team members. Reopening the Journey Builder agent in a different browser or on a different device will not display threads created earlier. Save any journey you want to keep as a draft or template before switching devices.

### Manage Threads

From the **All Threads** view, you can:

- Reopen an older thread to continue generating or editing journeys using the same context.
- Review and compare multiple journeys created during that session.
- Reuse previously saved journeys or templates instead of regenerating them.

For subsequent edits, you need not restart a session. Select the thread and type your next instruction directly in the chat. For example: _"Add an SMS node after the Email node with a delay of 1 day."_ The AI updates the existing journey while preserving your prior nodes and settings.


<Image src="https://files.readme.io/e209a97d2fb68ee699f46760d6321a2a0fbedacecdb18a73620f513dea29947d-Journeys_IA_-_Post_Editing_Flow.jpg" align="center" caption="Edit Journey From Existing Thread" border={true} />


# FAQs

### How is my data used and sent to OpenAI?

Your data is never used to train OpenAI models, and is deleted by OpenAI within 30 days. To generate AI output using CleverTap AI features that leverage OpenAI, CleverTap sends your prompt along with event names, event properties, user properties, segment names or IDs, and any other relevant inputs to OpenAI. The input sent does not identify you or your users unless you choose to include identifiable information in your prompt. CleverTap provides no warranties regarding the AI-generated content, including the output. For more information, refer to [OpenAI's Enterprise Privacy Policy](https://openai.com/enterprise-privacy).

### Is there a limit to the thread history?

There is no limit to the thread history. Threads are stored locally at the browser level.