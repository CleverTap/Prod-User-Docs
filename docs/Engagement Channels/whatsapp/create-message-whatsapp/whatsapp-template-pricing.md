---
title: WhatsApp Template Pricing
excerpt: Learn how to set a max price for your WhatsApp marketing templates.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Max pricing lets you control the amount Meta can charge for each delivered marketing message. When you create a Marketing template, the _Pricing_ step displays the rate-determining details for the template and lets you set a maximum price per delivered message. The max price you set is an upper limit, that is, Meta charges this amount or lower for each delivered message. If you do not set a max price, Meta charges its published rate, that is, Meta's standard rate for delivered messages.

Setting a max price also affects delivery. A higher max price may improve delivery rates when Meta is experiencing high message traffic in the recipient's country. Max pricing is part of Meta's per-message pricing model for marketing messages. For more information, refer to [Pricing on the WhatsApp Business Platform](https://developers.facebook.com/documentation/business-messaging/whatsapp/pricing).

<Callout icon="📘" theme="info">
  ### Before You Set a Max Price

  Max pricing is currently in Private Beta. Contact your Customer Success Manager for access.

  Max pricing applies only to templates in the _Marketing_ category. Meta charges Utility and Authentication templates at its standard per-message rates. The max price affects how Meta prioritizes delivery.&#x20;
</Callout>

This document covers the following:

- [Set the Max Price for a Template](#set-the-max-price-for-a-template)
- [Analyze Prices with Price Trend](#analyze-prices-with-price-trend)
  - [View the Price Trend Chart](#view-the-price-trend-chart)
- [Adjust the Max Price in a Campaign or Journey](#adjust-the-max-price-in-a-campaign-or-journey)
- [FAQs](#faqs)
- [Next Steps](#next-steps)

## Set the Max Price for a Template

The _Pricing_ step appears after you configure the template content and before you send the template for approval.&#x20;

<Callout icon="📘" theme="info">
  ### New Templates Only

  Max pricing can only be set during template creation. It cannot be added to existing templates.
</Callout>


<Image src="https://files.readme.io/5881db8f9bec6d5f8c86355093a74fc922b0f346b4adce7793830b3d66ce2138-MAX_PRICE_.png" align="center" caption="Max price - WhatsApp Template" border={true} />


<br />

To set the max price for a template, follow these steps:

1. Go to _Content Manager > Templates > WhatsApp_ and create a Marketing template as described in [WhatsApp Templates](doc:whatsapp-templates). After you configure the content, the _Pricing_ step displays.

2. Review the following details. These fields are read-only on the _Pricing_ step and reflect the values you configured during template creation:

   | Field      | Description                                                                              |
   | :--------- | :--------------------------------------------------------------------------------------- |
   | _Category_ | The template category. Max pricing applies only to the _Marketing_ category.             |
   | _WABA_     | The WhatsApp Business Account under which the template is created.                       |
   | _Currency_ | The currency associated with your WhatsApp Business Account, selected during onboarding. |

3. (Optional) Select the **Max pricing** checkbox.

4. Enter the max price per delivered message in the _Max price_ field.

5. (Optional) Click **View Price Trend** to compare estimated delivery rates at different max prices for your target countries. For more information, refer to [Analyze Prices with Price Trend](#analyze-prices-with-price-trend).

6. Click **Send for Approval**.

<Callout icon="📘" theme="info">
  ### Delivery Is Not Guaranteed

  A higher max price may improve delivery rates when Meta is experiencing high message traffic. It does not guarantee delivery at any price.
</Callout>

## Analyze Prices with Price Trend

Price Trend gives you an estimate of how delivery rates may vary at different max prices for each of your target countries. Published rates and message traffic differ by country, so a max price that performs well in one country may not perform the same way in another. These estimates are based on historical delivery data and are meant for planning purposes only. It means actual delivery outcomes can differ due to changing platform conditions and other factors. Use Price Trend to compare estimated delivery rates at different price points and choose a max price that supports your delivery goals across your target countries.


<Image src="https://files.readme.io/f3c8b4be5189d007108a5378811f485d166877a2d61c89f3e5b3af435c6ff205-proce_trend.png" align="center" caption="Price Trend" border={true} />


### View the Price Trend Chart

The chart plots estimated delivery rate against max price for each country you select.

1. On the _Pricing_ step, click **View Price Trend**.

2. Select your target countries from the _Select countries_ dropdown. Select every country your campaigns using this template are likely to target, because the same max price produces a different delivery rate in each country.

3. Select a time period, such as _7 days_. Estimates are based on Meta's historic delivery data for the selected period. A shorter period reflects more recent platform conditions, and a longer period smooths out short-term spikes.

4. Review the chart. The horizontal axis shows the max price per 1,000 messages, and the vertical axis shows the estimated delivery rate. Each line represents one selected country.

5. Hover over any point on a line to view the max price, the estimated delivery rate, and the effective multiplier for that country at that point.

6. (Optional) Click the download icon to export the chart.

## Adjust the Max Price in a Campaign or Journey

The max price you set on a template acts as the default for every campaign and journey that uses the template. To raise or lower it for a single campaign or journey node without editing the template, use the _Max Price Multiplier_ in the builder. The value you enter is multiplied by the template's max price to get that campaign's or journey node's max price. For example, if the template's max price is 0.015 USD and you enter a multiplier of 2, the campaign's max price is 0.030 USD. To reduce spend on a lower-priority campaign using the same template, you can enter 0.5, which sets the campaign's max price at 0.008 USD. For more information, refer to [Create a WhatsApp Message](doc:create-message-whatsapp).

## FAQs

### Q. Why was I charged less than my max price?

The max price you set is only a ceiling, not a fixed charge. Meta determines the actual price for each delivered message through its own delivery-optimization process. This price is not tied to Meta's published rate, and it isn't something CleverTap controls or can see into, that is, you can be charged well below your max price, and the price can vary from one message to the next even within the same country.

### Q. Is the max price my contract price?

No. The max price affects how Meta prioritizes delivery and caps what Meta can charge per delivered message. Your invoices are calculated according to your contract terms.

### Q. What happens if I do not set a max price?

Meta charges its published rate for each delivered message, with no upper limit.

### Q. Can I set a different max price for each campaign or journey?

Yes. Use the _Max Price Multiplier_ in the builder to adjust the template's max price for a single campaign or journey node. For more information, refer to [Adjust the Max Price in a Campaign or Journey](#adjust-the-max-price-in-a-campaign-or-journey).

### Q. Does max pricing apply to Utility or Authentication templates?

No. Max pricing applies only to templates in the _Marketing_ category. Utility and Authentication templates are charged at Meta's standard per-message rates.

## Next Steps

<Cards columns="2">
  <Card title="Create a WhatsApp Message" href="doc:create-message-whatsapp">
    Use the template in a campaign and adjust its max price with a multiplier.
  </Card>

  <Card title="Template Approval and Operations" href="doc:whatsapp-template-approval-and-operations">
    Submit the template for Meta approval and manage it throughout its lifecycle.
  </Card>
</Cards>