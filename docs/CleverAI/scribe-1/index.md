---
title: Scribe
excerpt: 'Learn how to generate message copies across all campaigns with AI. '
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Scribe helps you instantly create, edit, or refine message copy for your campaigns directly within CleverTap, using these brand-specific details as its foundation. It goes beyond standard AI copy generation by using your [Brand Context,](doc:brand-context) where you save your brand's voice, tone, and preferences, with insights from your past high-performing campaigns. This ensures that every message aligns with your brand voice and is inspired by what has already driven results for your audience.

<Callout icon="📘" theme="info">
  ### Availability

  Scribe is available in Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

Scribe reduces manual effort, speeds up campaign creation, and helps you produce consistent, on-brand copy that is aligned with your engagement goals. With Scribe, you can do the following:

- Save time creating campaigns by generating copy directly in the campaign builder, without switching tools or re-entering context.
- Maintain brand consistency at scale by automatically applying your Brand Context across all messages.
- Create effective copy by learning from your past high-performing campaigns, rather than relying on generic AI suggestions.
- Generate multiple message variations quickly to test and optimize performance.
- Improve team speed and consistency by reducing manual rewrites and reviews.

# Learn How Scribe Works

Scribe is embedded within the campaign's Message Editor and generates copy using three inputs:

- _Campaign Intent_: The prompt you provide describes what you are trying to achieve in this campaign. For example, _Re-engage users who abandoned their cart with items still available_ or _Bring back dormant users who haven’t opened the app in 14 days_.
- _Brand Kit and Brand Context_: Scribe draws from your Brand Kit and Brand Context, which acts as the foundational system prompt for all AI features and captures your brand name, industry, and voice at the account level.&#x20;
- _Past Campaign Look-back_: Set in Brand Kit, this determines how far back Scribe looks when identifying relevant past campaigns to use as inspiration for the current prompt.

# Supported Channels

Scribe supports the following channels:

- SMS
- Email
- Web-Native
- Web-popup
- Native Display
- App Inbox
- InApp

# Generate Copy using a Prompt

Use a prompt to quickly generate campaign copy tailored to your goals. Before generating content, set the [Brand Context](https://docs.clevertap.com/docs/brand-context), select the appropriate [Brand Kits,](https://docs.clevertap.com/docs/brand-kit) and configure [Content Settings](https://docs.clevertap.com/docs/scribe-1#content-settings) to guide tone, style, and language.

<Callout icon="📘" theme="info">
  ### Steps may vary slightly by channel

  The steps below use Push as the example. For channel-specific fields and behavior, refer to Supported Channels.
</Callout>

To generate copy using Scribe, follow the given steps:

1. Open your _Campaign Editor_.
2. Clic&#x6B;**&#x20;Scribe** to generate both _Title_ and _Message_. The _Title_ is the short, attention-grabbing headline of your message (for example, a push notification's title bar text), while the _Message_ is the main body content that carries the full context or call to action. You can also click the ![](https://files.readme.io/935fb6454c1119d8ecbbcb60baaa21dd7d7fbd62688f5c4fc3a5590b17a9c46e-Clever_AI_icon.png) icon in the _Title_ or _Message_ fields to generate content specifically for that field.


<Image src="https://files.readme.io/c494872561cd51cc5adad39e4a09d02ce8477de4b41e9fcb557aefe241da3be9-2026-08-14_16-19-59.jpg" align="center" caption="Campaign Editor" border={true} />


3. In the new window, describe the intent of the campaign, or what you want the message to achieve. For example, _Bring back dormant users who haven’t opened the app in 14 days_ or _Promote the Friday sale for premium plans_. The _Scribe_ window also displays some sample prompts to help you get started.


<Image src="https://files.readme.io/accc7debb8c45f7923a97765be9cbf7d9dd9f7176e6cf5eb1599cc7139db7754-2026-08-11_16-44-55.jpg" align="center" caption="Scribe Prompt Window" border={true} />


4. Select the Brand Kit and configure Content Settings (such as tone, emotion, or personalization) based on your campaign needs.
5. Click the ![](https://files.readme.io/764e6202e87af763be5fe1711eb756251036bcdc9064d72195a8c915a53bef5b-2026-01-21_14-16-28.png) icon to generate the copy. You can preview how the copy looks in real time within the device preview.
6. The Scribe creates multiple variations based on your prompt and settings. It also refers to past campaigns and lists the templates for those campaigns.


<Image src="https://files.readme.io/0c9ea05ffa0f0012ea9dd45a0bbc75cac6e204b18337b729d7bac115e97a8c16-2026-01-21_13-14-46_1.gif" align="center" caption="Generate Copy Variations" border={true} />


7. To refine the generated copy, select the output you want and click **Improve**. You are navigated to the prompt pane to rewrite the copy. For example, you can prompt to make the copy shorter, friendlier, sound more urgent, and so on.


<Image src="https://files.readme.io/fcdef699d9fd84361ee1b2bf7230eda931b6f744dd39bf91ec67f1ead5073c4f-2026-01-21_14-32-05_1.gif" align="center" border={true} />


8. Click **Use Content** to insert the selected copy into your campaign.

<Callout icon="📘" theme="info">
  ### Optimize Output with Detailed Prompts

  The Scribe relies on the clarity of your prompt to generate accurate, high-quality copies. The more specific you are about the goal, audience, tone, and so on, the better the output aligns with your campaign goals.
</Callout>

# Brand Kits and Content Settings

The Scribe provides controls to guide the style and tone of the generated copy, using [Brand Kit,](https://docs.clevertap.com/docs/brand-kit) and [Content Settings](https://docs.clevertap.com/docs/scribe-1#content-settings).


<Image src="https://files.readme.io/7546019ad6cb4f35ba28555e5fdd97af307e96611ef1b9c7585f383a629e1c3c-2026-08-11_16-44-55.jpg" align="center" caption="Core Brand and Content Settings" border={true} />


## Brand Kits

Click **Brand Kits** to view your brand’s tone, campaign reference period, creativity, and more for your content. If you have configured multiple brand kits, select the appropriate one before generating content. Click **Apply to this Thread**.

You can also configure a custom kit for the current thread. This helps align generated copy with your brand’s preferred tone and instructions.


<Image src="https://files.readme.io/dc75bdba4901ee9c32d35004db661733d1d9e1e8e935d32b2f96163b77b51f66-bc9c2aecf542c8a8a2dd1572ed3dd1194dc108625051a7733719b3fd8b3d508a-2026-01-21_15-41-55.jpg" align="center" caption="Brand Kits" border={true} />


Scribe also inherits settings from your Brand Context, which defines your brand's core identity and tone at the account level. Brand Context applies across all AI features and works alongside your Brand Kit to shape generated copy.

<Callout icon="📘" theme="info">
  #### **Note**

  - Locked Brand Kits cannot be edited in the campaign flow because they are meant to enforce brand consistency across teams. Locking a kit prevents campaign-level users from overriding approved brand styles.
  - Any changes made to a Brand Kit from the campaign flow apply only to the current thread. This allows you to experiment with copy variations without permanently changing your account-level Brand Kit.
  - If a prompt conflicts with Brand Kit settings, the agent automatically follows the Brand Kit settings to maintain consistency.

  For more information on setting up and using brand kits, refer to [Brand Kit](https://docs.clevertap.com/docs/brand-kit).
</Callout>

## Content Settings

You can customize how content is written using _Content Settings_. To configure the Content Settings, follow the given steps:

1. Click the ![](https://files.readme.io/24934bf75abfbb60b6e472ec6eada7c29619243e8bc94c147b88ae0c6b0bc1e6-image.png) icon in the _Scribe_ window to configure the following options:

- _Language_: Choose the language for the generated copy.
- _Script_: Select the writing system used for the selected language (for example, if your selected language is Hindi, choose Devanagari script for `नमस्ते` or Latin script for `Namaste`.)
- _Emotions_: Define the emotional tone, such as Neutral, FOMO, Trust, Joy, Surprise, and Anticipation.
- _Content Type_: Select the writing style, such as Catchphrase, Punchy, Throwback, and so on.
- _Personalization_: Enable this option to include personalization placeholders (for example, `Name` or `City`) wherever relevant.
- _Emojis_: Enable this option to allow emojis when they fit the message tone and channel.

2. Click **Apply** to save your settings before generating content.


<Image src="https://files.readme.io/ae59d8cd4fdf42dc820244afab4a5ad211bcdb0f08ba0136ef6943aaf99f89b0-2026-08-11_16-47-24.jpg" align="center" caption="Content Settings for Scribe" border={true} />


# Threads

Once you start generating copy, CleverTap automatically saves your sessions under the Threads ![](https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png) tab. Each session is stored as a thread, which preserves your prompts, refinements, and generated outputs, helping you resume from where you left off without losing context.


<Image src="https://files.readme.io/17984a458523dbff48429223ffae643cbb5016bee6692c77163d9838d2ea5b99-2026-08-11_16-46-35.jpg" align="center" caption="All Threads" />


## Thread Functionality

Threads are scoped to your _Account, Agent, and User,_ ensuring that your history remains personalized and relevant. All threads for your account appear in the _All Threads_ popup. A thread becomes the context for your next generation, allowing Clever.AI to remember your prior brand preferences or edits. They are not tied to specific campaigns; they persist across multiple campaigns for seamless continuity.

If multiple users from the same account use AI tools:

- Each user sees only their own threads and the latest image generation session that they have participated in.
- Threads are separate for Segmentation, Analytics, Image Creator, and Scribe, even under the same account.

## Manage Threads

From the _All Threads_ popup, you can do the following:

- Revisit previously generated copy to review or compare variations.
- Continue refining copy within the same context without starting over.
- Reuse effective messages across campaigns with similar goals.

# Best Practices for Writing Prompts

The Scribe relies heavily on the clarity of your prompt. Follow these best practices to get better results:

- Clearly state the goal of the message
  _Example: “Re-engage users who haven’t opened the app in 14 days.”_
- Mention the audience
  _Example: “Users who abandoned cart.”_
- Define the tone or emotion
  _Example: friendly, urgent, reassuring._
- Avoid vague prompts that lack context, such as _write a notification_ or _marketing copy_.
- All generated copies must be reviewed by your internal brand and legal teams before use in public campaigns.
- Avoid including any personal or confidential information in AI prompts. Keep descriptions focused on creative intent.

You can refine the output by adjusting the prompt, changing Content Settings (emotion, tone, personalization), or regenerating content multiple times. Each variation helps you explore different angles until the copy matches your intent. For more information, refer to [Generate High-Impact Copy with Effective Prompts.](https://docs.clevertap.com/docs/effective-prompts-for-ai-designer-agent)

Refer to the table below for difference between vague and effective prompts:&#x20;

<Table>
  <thead>
    <tr>
      <th>
        Vague Prompt
      </th>

      <th>
        Effective Prompt
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Write a push notification
      </td>

      <td>
        You are a lifecycle marketing copywriter for a consumer app.<br />Create high-converting copy to re-engage users who haven’t opened the app in 14 days.<br />Deliver:

        - A concise title
        - A clear, benefit-led message<br />Keep the tone friendly and trustworthy, and include a gentle CTA.
      </td>
    </tr>

    <tr>
      <td>
        Create marketing copy
      </td>

      <td>
        Create high-converting copy to promote the Friday sale to existing users. Add a title with 3 words, and a clear message highlighting the main offer or benefit.<br />Use a sense of urgency, keep the tone modern and trustworthy, and include a gentle CTA.
      </td>
    </tr>

    <tr>
      <td>
        Notify users about an offer
      </td>

      <td>
        Create high-converting message to notify existing users about a limited-time offer.<br />Deliver a title and a clear message explaining the value of the offer<br />Keep the tone helpful and persuasive, and include a gentle CTA.
      </td>
    </tr>

    <tr>
      <td>
        Notify users about items left in cart
      </td>

      <td>
        Create high-converting push message to remind cart abandoners about items left behind. Add a clear message nudging users to complete their purchase<br />Keep the tone fun, casual, and action-oriented, and include a gentle CTA.
      </td>
    </tr>

    <tr>
      <td>
        Announce a feature
      </td>

      <td>
        You are a marketing copywriter for a consumer app.<br />Create high-converting copy to encourage existing users to try a new feature. It should include a clear message highlighting the primary benefit of the feature<br />Keep the tone informative and trustworthy, and include a CTA.
      </td>
    </tr>
  </tbody>
</Table>

# Additional Resources

For more information, refer to the following resources:

- [Generate High-Impact Copy with Effective Prompts](https://docs.clevertap.com/docs/effective-prompts-for-ai-designer-agent)
- [Brand Context](https://docs.clevertap.com/docs/brand-context)
- [Scribe: FAQs](https://docs.clevertap.com/docs/scribe-faqs-1)
- [CleverTap Terms & Disclaimer](doc:clevertap-aienabled-feature-disclaimer-terms)&#x20;
