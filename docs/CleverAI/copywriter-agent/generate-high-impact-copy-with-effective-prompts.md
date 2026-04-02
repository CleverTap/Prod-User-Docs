---
title: Generate High-Impact Copy with Effective Prompts
excerpt: >-
  Learn how to create on-brand campaign copy with the AI Copywriter Agent using
  effective prompts. 
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The _Copywriter Agent_ generates compelling, high-conversion copy directly from your prompts. Whether you need a catchy headline for a flash sale or a persuasive call to action for an engagement campaign, a structured prompt ensures the output aligns with your brand’s unique voice and campaign goals.

This document helps you write prompts that produce creative, relevant, and brand-aligned copy for your push notifications.

<Callout icon="📘" theme="info">
  **Private Beta**

  Currently, this feature is released in Private Beta. If you want to access this feature, contact your Customer Success Manager.
</Callout>

Always review AI-generated copy for brand and legal compliance before publishing. Avoid including any confidential or personal information in your prompts. For more legal and compliance-related details, refer to [FAQs](https://docs.clevertap.com/docs/designer-agent#faqs).

# Writing Effective Prompts

An effective copy prompt does not just ask for "a message", but provides context, defines the tone, and sets the rules. By following a clear structure, you help the Copywriter Agent understand the _Who, What, and How_ of your campaign.

You can follow this simple structure to describe your copy idea in a way the Copywriter Agent understands easily:

### Define the Objective (What are you trying to achieve?)

Start with the goal. Is this for a seasonal sale, a cart abandonment reminder, or a feature announcement? Defining the intent helps the AI choose the right persuasive techniques.
_Example: "Write a push notification for a 24-hour flash sale on sports shoes."_

### Set the Tone and Personality (How should it sound?)

Describe the brand voice. Should it be witty and bold, or professional and reassuring? Mentioning your target audience here helps the AI tailor the vocabulary.
_Example: "Use an energetic, urgent tone that appeals to marathon runners and fitness enthusiasts."_

### State Constraints and Key Details (What must be included?)

Provide specific details, such as discount percentages, promo codes, or specific emojis you want to see. This ensures the copy is functional, not just creative.
_Example: "Mention 40% off. Include a fire emoji and a clear CTA to 'Shop the Sale'."_

### Combine All Three Parts

> **Prompt:** Write a push notification for a 24-hour flash sale on sports shoes for our "Spring Run" campaign.
> Use an energetic and urgent tone that appeals to marathon runners. Keep it punchy and exciting.
> Mention a 40% discount and use the code RUN40. Include a fire emoji and a call to action to "Shop the Sale."

**Result**

<Image align="center" border={true} caption="Generated Copy" src="https://files.readme.io/77de9961adee78579c4498ee04deb51ebd7ad78a5468413950b1ba64b21ed8fb-image.png" />

## Prompt Tips

The following are some useful tips when adding details to your prompts:

* **Specify the "Hook":** Tell the AI if you want to lead with a question, a bold statement, or a direct offer.
* **Define Your Audience:** Instead of "users," say "lapsed subscribers," "VIP members," or "first-time shoppers."
* **Use Power Words:** Ask the AI to use specific types of language, such as "scarcity-driven" (Only 2 left!) or "benefit-focused" (Sleep better tonight).
* **Avoid Vague Terms:** Instead of "Make it good," try "Make it humorous and use wordplay related to coffee."

# Sample Prompts

The following sample prompts show how detailed prompts improve the message quality, tone, and brand consistency. You can experiment with more prompts to find a suitable message tone and style for your brand. Browse the sample prompts by industry:

<Cards columns={3}>
  <Card title="E-Commerce" href="#e-commerce" icon="fa-shopping-cart">
    Personalization & Offers
  </Card>

  <Card title="OTT" href="#ott" icon="fa-tv">
    Content & Engagement
  </Card>

  <Card title="Fintech" href="#fintech" icon="fa-wallet">
    Credit & Lending
  </Card>

  <Card title="Food Delivery" href="#food-delivery" icon="fa-utensils">
    Menu & Recommendations
  </Card>

  <Card title="Gaming" href="#gaming" icon="fa-gamepad">
    Player Engagement & Rewards
  </Card>
</Cards>

## E-Commerce

**Prompt**

> Create a push notification for users who left items in their shopping cart. The tone should be helpful but slightly cheeky. Remind them that their items are feeling lonely and offer a 10% discount to sweeten the deal. Use a heart emoji and a CTA that says "Take Me Home."

**Result**

<Image align="center" border={true} width="80% " src="https://files.readme.io/a6fa6f100bda606949f751aeadbed5bb82ac11df004db19a62aaa9f1cf7d9ef3-image.png" className="border" />

## OTT

**Prompt**

> Write a notification for the premiere of a new Sci-Fi thriller series called "Dark Orbit." The tone should be mysterious and gripping. Create a sense of intrigue. Focus on the show's "cliffhanger" nature. End with a CTA to "Start Watching."

**Result**

<Image align="center" border={true} width="80% " src="https://files.readme.io/1e24abe9ada32a25164793c562d56e163606595890d84b0bab3ced2ff587ddb0-image.png" className="border" />

## Fintech

**Prompt**

> Draft a security-focused push notification reminding users to enable Two-Factor Authentication (2FA). The tone must be professional, trustworthy, and urgent without being alarmist. Explain that it takes only 30 seconds to secure their account.

**Result**

<Image align="center" border={true} width="80% " src="https://files.readme.io/b4c4e5f74a19aea0e44edfb4ca66dbb563a72c079829994077210281bf1b0e03-image.png" className="border" />

## Food Delivery

**Prompt**

> Write a hunger-inducing push notification for the 12 PM lunch window. Target office workers. Use a playful tone with food puns. Mention "Free Delivery" on orders over $20. Include a burger and fries emoji.

**Result**

<Image align="center" border={true} width="80% " src="https://files.readme.io/de8b111d2e47bfe0c5c9a4616022c2ced9196955330e312ef5111ffd962555df-image.png" className="border" />

## Gaming

**Prompt**

> Create high-converting push copy to notify existing users about a limited-time offer for the game 'BattleStar'. Deliver a title and a clear message explaining the value of the offer: '2 free silver coins and new levels unlocked, limited time offer only'. Keep the tone helpful and persuasive, and include a gentle CTA.

**Result**

<Image align="center" border={true} width="80% " src="https://files.readme.io/37971334273982724d22c9e816bfd8b5f54ac8117dd3dec047160de9e8c465e1-image.png" className="border" />

<Callout icon="📘" theme="info">
  **How Brand Kit and Prompts Work Together**

  If your prompt conflicts with your Brand Kit, the Brand Kit always takes priority to maintain brand consistency. The system applies settings in this order: _Brand Kit -> Prompt -> Filters_

  This ensures every generated copy stays brand-compliant and visually consistent with your defined design standards.
</Callout>

For more information on generating copy using the Copywriter Agent, along with step-by-step instructions, refer to [Copywriter Agent](https://staging.docs.user.clevertap.net/update/docs/copywriter-agent).
