---
title: Generate Message Copy with Scribe
excerpt: >-
  Learn how to write effective Scribe prompts, with best practices and
  ready-to-use templates for common campaigns across industries.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# Overview

You can optimize the message content that [Scribe](https://docs.clevertap.com/docs/scribe) generated with effective text prompts. A prompt is a short sentence, phrase, or keyword instructing Scribe to generate copywriting ideas. Scribe uses AI to help you generate relevant and engaging message suggestions.

Key capabilities of Scribe's AI:

* Speeds up production: Turns a short prompt into multiple copy options in seconds.
* Optimizes emotion and tone: Ask for humour, urgency, celebratory, reassuring emotion, and so on, based on your specific use case.
* Adapts to context: Scribe already knows the channel (such as WhatsApp, Email, Web Push, and so on) from CleverTap. However, you can further customize the prompt by adding brand, product, offer, festival, language, font, or audience details to guide the message style and tone. The more specifics you provide, the better the output.
* Follows constraints: Scribe considers title and body word limits, must-include or avoid words, and bilingual output, if mentioned.

# Best Practices

Following are some best practices you must follow while writing prompts for Scribe:

* **Use clear keywords**: Clearly mention the product, brand, or offer to focus the message generation.
  * _Example_: `Brand: FitFuel | Offer: 25% off on protein bars` — This helps generate message options that highlight the brand and deal.
* **Provide details**: Keep prompts detailed. Lead with a one-line goal, then add brief details for Brand, Product/Offer, Tone/Emotion, Language/Font, Include/Exclude words, Title/Body limits.
  * _Example_: `Goal: Promote a flash sale for a new launch. Brand: LuxeWear | Tone: Urgent | Style: Clickbait | Include Words: today, sale | Format: Title (5 words max), Body (20 words max)`
* **Provide context and numbers**: Include campaign type (e.g., festival offer, back-to-school), emotion, or urgency markers. Add offer values, product names, coupon codes, deadlines, or locations to help generate sharper copy.
  * _Example_: `Festival: Diwali | Product: LED Strip Lights | Discount: ₹500 off | Expires: Nov 12 | Emotion: Joy`
* **Guide the emotion**: Mention the feeling required for your campaign, such as playful, FOMO, trust-building, premium, friendly, and so on.
  * _Example_: `Tone: Playful | Emotion: Surprise | Style: Bollywood jingle`
* **Avoid sensitive words**: Avoid using profanity or sensitive words.
  * _Example_: Instead of "bet big on Diwali," use "grab the best Diwali deal."

You can combine multiple fields (topic, language, style, and so on) in one prompt to get a more specific output.

## Prompt Fields

Refer to the table below to understand prompt fields:

| Field             | Example                                           | Sample line                                        |
| ----------------- | ------------------------------------------------- | -------------------------------------------------- |
| **Topic**         | "Air Conditioner 20% off", "New theatre opening"  | `Topic: Air Conditioner with 20% off`              |
| **Brand Name**    | "Basketball Blitz", "GamePlay Central"            | `Brand: Cricket Dazzler`                           |
| **Language**      | English, Hindi (mix), Spanish                     | `Language: Mix of Hindi and English`               |
| **Font**          | Devanagari, English, Helvetica                    | `Font: Devanagari`                                 |
| **Style**         | Bollywood jingles, Weather report, Rap, Clickbait | `Style: Rap Song`                                  |
| **Include Words** | "delivery", "cashback", "finals"                  | `Include Words: cashback, weekend`                 |
| **Exclude Words** | "offer", "gambling", "betting"                    | `Exclude Words: offer, betting`                    |
| **Format**        | Title 5 words, Body 20 words                      | `Format: Title (5 words max), Body (20 words max)` |

# Sample Syntaxes to Write Prompts

The following sample prompts can help you get started with Scribe quickly. You can experiment with more prompts to find a more suitable message tone and style. Browse the sample prompts by industry:

<Cards columns={5}>
  <Card title="E-Commerce" href="#e-commerce" icon="fa-shopping-cart">
    Personalization & Offers
  </Card>

  <Card title="OTT" href="#ott" icon="fa-tv">
    Content & Engagement
  </Card>

  <Card title="Fintech" href="#fintech" icon="fa-wallet">
    Finance & Portfolios
  </Card>

  <Card title="Food Delivery" href="#food-delivery" icon="fa-utensils">
    Menu & Recommendations
  </Card>

  <Card title="Gaming" href="#gaming" icon="fa-gamepad">
    Rewards & Items
  </Card>
</Cards>

## E-Commerce

Refer to the below sample prompts for retail offers, festive sales, and multilingual copy.

#### Brand related offers

```text
Topic: Assorted Dessert Box — 10% off (Diwali)
Brand: <Your brand>
Tone/Emotion: Festive, indulgent, gift-ready
Language: English
Include Words: Diwali, sweets, 10% off, order now
Format: Title (5 words), Body (25 words)
```

<Image align="center" border={true} width="100% " src="https://files.readme.io/0900b2dd053298faa3afe59f1bf16abc850b36e8eeb7db8b320e28ff4dbc6059-Scribe_message.png" className="border" />

<details>
  <summary style={{ fontSize: "20px" }}><strong>More E-Commerce examples</strong></summary>

  <p />

  <p><strong>Language Target</strong> — Give me a message for sports goods in Spanish.</p>

  <img src="https://files.readme.io/d422635-S3EP1.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Discount Campaign</strong> — Topic: Air Conditioner with 20% off · Language: Hindi · Font: Devanagari · Style: Humour</p>

  <img src="https://files.readme.io/6ac0b15-S1EP1.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Word Swap</strong> — Replace the word savings with something else: 🐰🌸 Hop into Easter savings with our sale! 🌸🐰 Don't miss out on our limited time deals.</p>

  <img src="https://files.readme.io/a9abc32-S5EP1.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Title Limit</strong> — Give a 5-word Title message for: Hop into Easter with our exclusive offers!</p>

  <img src="https://files.readme.io/80817cb-S6EP1.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />
</details>

## OTT

Refer to the below sample prompts for new releases, subscriptions, and bilingual campaigns.

#### Brand related offers

```
Topic: Channel subscription—1 month free (New Year)
Tone: Excited, celebratory
Include Words: free month, New Year
Format: Title (7 words), Body (25 words)
```

<Image align="center" border={true} width="100%" src="https://files.readme.io/52878c2d7c23ad5e2f33a892b3685c263ae24526527427e2246818e6d0e24ccd-subscription.png" className="border" />

<details>
  <summary style={{ fontSize: "20px" }}><strong>More OTT examples</strong></summary>
  <p><strong>Bilingual Mix</strong> — Give me a message in a mix of Hindi and English for the latest music releases.</p>

  <img src="https://files.readme.io/b47d566-S4EP3.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Language Target</strong> — Give me a message for movie releases in French.</p>

  <img src="https://files.readme.io/6e08cca-S3EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Word Swap</strong> — Replace the word rib-tickling with something else: Check out our rib-tickling movie collection now.</p>

  <img src="https://files.readme.io/3ae9c2a-S5EP3.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Title Limit</strong> — Give a 10-word Title message for: Get unstoppable streaming power! Ready to try out our channel? Enjoy a FREE trial now!</p>

  <img src="https://files.readme.io/5d60c53-S6EP3.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Title + Body</strong> — Give me a message for a new theatre opening near your area with a title in 5 words and a body in 25 words or less.</p>

  <img src="https://files.readme.io/91b8ebf-S7EP3.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />
</details>

## Fintech

Refer to the below sample prompts for cards, loans, and savings in single or mixed languages.

#### Brand related offers

```
Topic: Credit card—birthday cashback
Audience: Existing cardholders
Tone: Warm, appreciative
Exclude Words: limited time
Format: Title (6 words), Body (20 words)
```

<Image align="center" border={false} src="https://files.readme.io/870ae0a865dfa22b61bfaa961b1dfd8350f27e42d974431ce1f56e801272d128-Fintech.png" />

<details>
  <summary style={{ fontSize: "20px" }}><strong>More Fintech examples</strong></summary>
  <p><strong>Bilingual Mix</strong> — Give me a message in a mix of Hindi and English for a new bank account opening.</p>

  <img src="https://files.readme.io/3481a50-S4EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Language Target</strong> — Give me a message for a house loan offer in Hindi.</p>

  <img src="https://files.readme.io/8393545-S3EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Word Swap</strong> — Replace the word reliable with something else: Need extra cash? Get a loan from our reliable bank today!</p>

  <img src="https://files.readme.io/8a068ba-S5EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Title Limit</strong> — Give a 6-word Title message for: Unlock exclusive savings! Lower interest rates for Senior Citizens. Don't miss out; act now.</p>

  <img src="https://files.readme.io/b62fcef-S6EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <br />

  <p><strong>Title + Body</strong> — Give me a message to open a fixed deposit easily using the mobile app with a title in 5 words and a body in 25 words or less.</p>

  <img src="https://files.readme.io/91d02a9-S7EP4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />
</details>

## Food Delivery

Refer to the below sample prompts for menus, offers, and delivery promos across languages.

#### Brand related offers

```
Topic: Weekend pizza offer—buy 2 get 1 free
Brand: PizzaExpress
Tone: Fun, casual, mouth-watering
Include Words: weekend, free pizza
Format: Title (6 words), Body (25 words)
```

<Image align="center" border={true} width="100%" src="https://files.readme.io/4d7ee7d7897fd3828c674ec623c15023dfbd4441c4416148f6a091d3a9f7b6be-scribe.png" className="border" />

<details>
  <summary style={{ fontSize: "20px" }}><strong>More Food Delivery examples</strong></summary>
  <p><strong>Bilingual Mix</strong> — Give me a message for free delivery charge in a mix of Hindi and English.</p>

  <img src="https://files.readme.io/9a3a82d-S4EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Language Target</strong> — Give me a message for Pizza in Italian.</p>

  <img src="https://files.readme.io/380a4d5-S3EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Word Swap</strong> — Replace the word hoggers with something else: Our latest menu will leave even the biggest food enthusiasts satisfied.</p>

  <img src="https://files.readme.io/db4ff84-S5EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Title Limit</strong> — Give a 5-word Title message for: Cheers to Happy Hour! Get 50% off on all drinks now!</p>

  <img src="https://files.readme.io/3e0ad62-S6EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Short Title + Body</strong> — Give me a message for corporate offers at a restaurant with a title in 5 words and a body in 15 words or less.</p>

  <img src="https://files.readme.io/0eceea0-S7EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />
</details>

## Gaming

Refer to the below sample prompts for gaming and fantasy sports using styles and emojis.

#### Emoji Prompt

```
Topic: Ab firse chadega fantasy ka bukhar. Make your team now.
Brand: Cricket Dazzler
Emoji: Yes
```

<Image align="center" border={true} width="100%" src="https://files.readme.io/8a36682-image.png" className="border" />

<details>
  <summary style={{ fontSize: "20px" }}><strong>More Gaming examples</strong></summary>
  <p><strong>Field Builder (Include/Exclude)</strong> — Topic: Create a promotional Campaign for football enthusiasts. · Include: Betting, Gambling · Exclude: Offer, Adrenaline</p>

  <img src="https://files.readme.io/509a261-S1EP2.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Style (Bollywood) + Hinglish</strong> — Topic: 58 runs from 39 Balls! … · Style: Bollywood songs · Language: Mix of Hindi and English</p>

  <img src="https://files.readme.io/4bfb776-S1EP3A.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Style (Rap)</strong> — Topic: Make your cricket team now with India's leading gaming app and win big prizes · Style: Rap Song</p>

  <img src="https://files.readme.io/c7267c0-S1EP3B.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />

  <p />

  <p><strong>Response Length</strong> — Topic: Cricket Dhamaka, Try your luck and win amazing prizes. · Brand: Cricket Funda · Response Length: 15 Words</p>

  <img src="https://files.readme.io/8b798f7-S1Ep4.jpg" style={{ maxWidth: "100%", border: "1px solid #eee", borderRadius: "8px" }} />
</details>
