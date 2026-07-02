---
title: Create Coupons
excerpt: >-
  Learn how to create and configure coupon rewards in CleverTap to offer
  discounts, cashback, or partner incentives as part of your promotional
  campaigns.
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

The _Create Coupon_ page allows you to define, configure, and launch coupon-based rewards tailored to your business goals. You can create single or bulk coupon codes, set up reward types, define redemption limits, and control visibility and expiration settings.

Coupons created through this flow can be used in Promo Campaigns, distributed via user actions, or uploaded in bulk for manual assignment.

# Create Coupon

To create a coupon, go to _Promotions_ > _Rewards_ > _Coupons_, and click **Create Coupon**. The entire process is divided into the following three key steps:

1. [Select Coupon Type](doc:create-coupons#select-coupon-type)
2. [Select Reward Effect](create-coupons#select-reward-effect)
3. [Configure Coupon](doc:create-coupons#configure-coupon)

## Select Coupon Type

Select how you want to distribute the coupon codes to your users based on your engagement strategies, then click **Next** to continue.

- **Single code for all users**: A single coupon code that can be used by all users without eligibility criteria. This includes new visitors and existing users. For example, use code `CHRISTMAS20` to get 20% off on your entire order—no sign-up, login, or purchase history required. This type of code is ideal for platform-wide promotions such as festive sales, homepage banners, or email campaigns targeting a broad audience.

- **Single code based on user actions**: A single coupon code that is distributed through Promo campaigns when users meet specific qualifying conditions, such as signing up, completing a purchase, or reactivating after a period of inactivity. For example, use code `WELCOME100` to get $100 cashback on your first order. This type of coupon is best used for milestone-based campaigns such as onboarding, re-engagement, or referral rewards, ensuring the reward is tied to meaningful user actions.

- **Downloadable bulk unique codes**: Unique, one-time-use codes that can be redeemed by any user—no eligibility criteria required. These are generated in bulk using customizable code formats (for example, alphanumeric), with optional prefix, suffix, and length settings. For example, generate 10,000 unique codes such as `SAVE25XYZ`, which are then distributed via any partner platform. This type of coupon is ideal for offline promotions, printed flyers, or third-party channels where you want to restrict each user to a single redemption without needing system-based user segmentation.

- **Bulk unique codes based on user actions**: One-time-use codes that are automatically assigned to users who meet specific conditions defined in a linked Promo campaign. The system selects and assigns a unique code from the coupon pool when the user qualifies. For example, assign a unique code to each user who completes three purchases in a loyalty campaign. The code is automatically issued once the condition is met and can be redeemed only once by that user. This type of coupon is ideal for personalized reward journeys or limited inventory campaigns where you want to control distribution based on behavioral triggers.

The preview panel provides a representative visualization of each selected coupon type, helping you understand how the coupon will appear and function for users.


<Image src="https://files.readme.io/817615e15b51e294723fa2b396f7e1c518b58b0d9497b20d29bd5c210f8e54df-2025-03-24_15-27-29_1.gif" alt="Select Coupon Type from the Available Types" align="center" border={true} />


## Select Reward Effect

Define where the coupon discount will be applied within the order and click **Continue** to configure coupon settings:

- **Entire Order**: Applies the discount to the total order value. For example, a coupon offering 20% off on an order worth $250 results in a $50 discount. The user pays $200.

- **Specific Products**: Applies the discount only to selected products in the cart. For example, a coupon offering 30% off on jackets, where the cart includes a jacket ($2,000) and shoes ($3,000). The discount applies only to the jacket (30% of $2,000 = $600). The final payable amount is $4,400.

- **Custom Order Property**: Applies the discount to a custom property such as platform fees, convenience fees, or surge charges. For example, a coupon offering 50% off on platform fees. If the order subtotal is $2,000 and the platform fee is $200, the user gets a $100 discount, reducing the total payable amount to $2,100.

The preview panel displays a visual breakdown of how the coupon is applied, including itemized pricing, discount amount, and final total.


<Image src="https://files.readme.io/11375f30bb60e5c64a0263811f8ba5b5a2e7d047bb1ddb1f67e47a0c4ad1fbd8-2025-03-24_15-31-25_1.gif" alt="Select Reward Effect for a Coupon" align="center" border={true} />


## Configure Coupon

### Key Details

Define the core identity and structure of your coupon. The following table outlines each available field, its purpose, and the coupon types it applies to.

| Field                  | Description                                                                             | Single Code | Bulk Unique Codes |
| ---------------------- | --------------------------------------------------------------------------------------- | ----------- | ----------------- |
| **Coupon code**        | A static code users apply at checkout (for example, `FLAT500`).                         | ✅           | –                 |
| **Coupon name**        | Internal name to identify the coupon set (for example, `FLAT_APRIL_2025`).              | –           | ✅                 |
| **Code format**        | Choose the format for generated codes: Numeric, Alphabetic, or Alphanumeric.            | –           | ✅                 |
| **Code length**        | Set the number of characters for each generated code.                                   | –           | ✅                 |
| **Number of codes**    | Total number of unique codes to generate (for downloadable bulk codes).                 | –           | ✅                 |
| **Prefix/Suffix**      | Add optional text before or after the generated code for tracking or branding.          | –           | ✅                 |
| **Coupon description** | A short description of the offer shown to users or used internally.                     | ✅           | ✅                 |
| **Terms & Conditions** | Define restrictions or usage notes such as "One-time use only" or "Cannot be combined." | ✅           | ✅                 |
| **Coupon visibility**  | Toggle ON to make the coupon code visible to users in the coupon tray                   | ✅           | ✅                 |

You can preview how the coupon will appear in the user’s coupon tray.

<Callout icon="📘" theme="info">
  ### Coupon Preview

  The preview panel on the right provides a visual representation of how the coupon will appear in the user’s coupon tray. This is only a sample and may not reflect the exact in-app appearance. To customize the tray layout, refer to [Fetch Coupon API](https://developer.clevertap.com/docs/fetch-coupon).
</Callout>

### Reward

Choose where the reward should be applied within the user’s order. This determines which part of the cart or transaction the discount or cashback will target as follows:


<Image src="https://files.readme.io/a5e9b19718944996b157c361902beab0a55df2d5f72a93e1cbffe29c2bc1d1a9-Configure_Reward_Section_.png" alt="Define Reward Scope" align="center" border={true} />


#### Reward Effect

Each _Reward effect_ provides additional configuration options as follows

<Table>
  <thead>
    <tr>
      <th>
        Reward Effect
      </th>

      <th>
        Description
      </th>

      <th>
        Unique Configuration Options
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Entire Order**
      </td>

      <td>
        Applies the reward to the total value of the order.
      </td>

      <td>
        **Exclude products**

        : Enable this option to exclude certain products from the coupon discount. For example, if you select exclude

        `itemName = iPhone 15`

        and if a cart contains

        `iPhone 15`

        and

        `AirPods`

        , only the

        `AirPods`

        value will be considered for discount calculation.
      </td>
    </tr>

    <tr>
      <td>
        **Specific Products**
      </td>

      <td>
        Applies the reward only to selected products in the cart.
      </td>

      <td>
        <li>**Product Filters**: Define which products are eligible for the reward based on attributes such as `itemName` or `category`. You can apply multiple filters using AND/OR logic. Additionally, you can use custom catalog properties from your product catalog to define business-specific filters.</li><li>**Qualifying rules**: Once eligible products are identified using filters, you can define qualifying rules that determine when the reward should apply. These rules are evaluated only against discount-eligible items and include: <ul><li>`itemsTotalQuantity`: The total number of eligible items in the cart.</li><li>`itemsSaleAmount`: The total sale value of eligible items, calculated as unit price × quantity.</li></ul>You can combine these rules using AND or OR to specify whether all conditions must be met or just any single is sufficient.</li>
      </td>
    </tr>

    <tr>
      <td>
        **Custom Order Property**
      </td>

      <td>
        Applies the reward to a specific order-level property.
      </td>

      <td>
        **Applicable property**

        : Choose a custom field such as platform fee or shipping cost
      </td>
    </tr>
  </tbody>
</Table>

Once you select the reward scope, you can define the reward details such as _Reward type_ and _Discount value_.

#### Reward Type

The following are the options available for the _Reward types_ dropdown on the CleverTap dashboard:

| Reward Type         | Description                                                                                                                                                                                                                                               | Supports Max Cap |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| Fixed discount      | Offers a flat reduction in the order amount. For example, enter 200 to give users $200 off on their purchases.                                                                                                                                            | No               |
| Percentage discount | Applies a percentage-based discount to the order. For example, enter 15 to give users a 15% discount on their purchase.                                                                                                                                   | Yes              |
| Fixed cashback      | Gives fixed cashback points to the user wallet or account. For example, enter 100 to credit $100 cashback points to the user after a successful transaction. It also requires selecting the target _Loyalty wallet_, where the cashback will be credited. | No               |
| Percentage cashback | Credits cashback points based on a percentage of the order total. For example, enter 10 to provide 10% of the order value as cashback points. It also requires selecting the target _Loyalty wallet_ where the cashback will be credited.                 | Yes              |

<Callout icon="📘" theme="info">
  ### Max Cap for Percentage Rewards

  For percentage-based rewards, you can optionally set a maximum cap by clearing the Unlimited discount per order or Unlimited cashback per order checkbox.

  For example, 10% discount with a cap of $100 means if the order total is $1500, the discount applied will be $100 max.
</Callout>

#### Discount Value

Enter either the fixed amount or the percentage to be applied based on the selected reward type. For cashback rewards, ensure a loyalty wallet is selected.

#### Example

Consider an example to understand how the Reward configuration works. You want to offer a 20% discount on T-shirts, but only when a user buys at least two items from that category.<br />In this case,

- **Product filters**: Set category = T-shirts to limit the reward to T-shirt purchases.
- **Qualifying rule**: Define itemsTotalQuantity ≥ 2 to ensure the discount applies only when the user adds two or more T-shirts to their cart.
- **Reward type**: Choose Percentage discount.
- **Discount value**: Enter 20% and optionally set a maximum cap (for example, $50) by disabling the Unlimited discount per order checkbox.

### Qualifying Rules

Define the conditions under which a coupon becomes applicable. You can apply rules based on cart properties, product-level attributes, or user profile traits. Multiple conditions can be combined using AND/OR logic to build flexible eligibility criteria.


<Image src="https://files.readme.io/20e60f8c37a5a452b8fc4c750b0315194c4799c1b29893e0d0ef5280f8d296cf-Qualifying_Rules.png" alt="Define Qualifying Rules for the Coupon" align="center" border={true} />


#### Cart

Define eligibility based on cart-level attributes such as total sale amount or item count. You can add multiple cart properties with different operators, such as `equals`, `greater than`, `less than`, `between` and. You can combine multiple conditions using AND to enforce all rules, or OR to allow any rule to trigger coupon eligibility.

For example, if a user adds 2 T-shirts priced at ₹150 each and a cap priced at ₹250 (total ₹550), the coupon is applicable.


<Image src="https://files.readme.io/5ce6807d47d34f47e1b15cfa6acec5678120832d93c9f667e2babb2bdfcc79af-image.png" alt="Add Qualifying Rules for Cart" align="center" border={true} />


#### Product

Apply the coupon on product properties with two available modes. You can add multiple product property rules and combine them with **AND/OR** conditions as needed.

Let us consider an example to understand this better. A fashion retailer wants to offer 15% OFF on winter wear items such as jackets, sweaters, and hoodies, all from the brand ArcticEdge. The product filters are:

- `productCategory = Jackets OR Sweaters OR Hoodies`
- `brand = ArcticEdge`

It supports the following two modes:

- **Any of**: The coupon applies if at least one item in the cart meets the filters above. In this case, if the cart contains 1 ArcticEdge sweater + 1 regular t-shirt, the coupon applies (sweater qualifies)\`.

- **Each of**: The coupon applies only if all items in the cart match the filters. In this case, if the cart contains 2 ArcticEdge jackets + 1 ArcticEdge hoodie, the coupon applies (all items match).


<Image src="https://files.readme.io/ad4990fd2d3aac2bbc28a5085015587940e2deeb555061b88b5aabe28537f088-image.png" alt="Add Qualifying Rules for Product" align="center" border={true} />


#### User Property

Restrict coupon applicability to users who match specific profile attributes. You can configure multiple user properties combined using **AND/OR** conditions to target the right audience precisely. These conditions ensure that the coupon is visible and redeemable only for eligible users based on attributes available in their user profile.

For example, A food delivery app wants to offer a $50 OFF coupon exclusively to users located in India.


<Image src="https://files.readme.io/8c6474ada9e3b2a4020fdd8d1b9f34cf3fe90c270fc52e3b78ab6aed30b1e567-image.png" alt="Add Qualifying Rules for User Property" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  The User Property rule is available only for All Users coupons.
</Callout>

### Validity

Configure when the coupon will become active and remain available to users. Validity settings vary based on the coupon type.

#### For All Users Coupons

These include the following coupon types: Single code for all users or Downloadable bulk unique codes. Set the following parameters to define the active window for the coupon:

- **Timezone**: The system uses your default account timezone, for example, GMT +05:30 Asia/Kolkata.
- Time Period:
  - **Start date and time**: Define when the coupon becomes active. For example, if the start time is 1st July 2025 at 10:00 AM, users will only be able to view and redeem the coupon from that moment onward. The start date is derived from promo campaigns based on when the coupon is being rewarded to the user.
  - **End date and time**: Choose when the coupon expires. Set a specific time, for example, 31st July 2025 at 11:59 PM) or select _Never ends_ for ongoing availability.


<Image src="https://files.readme.io/a09819937eef7baa1ba00961f658fd2df33702417a9370b40dfb2e8fae454467-image.png" alt="Set Validity for All User Coupons" align="center" border={true} />


#### For User Actions-Based Coupons

These include the following coupon types: Single code based on user actions or Bulk unique codes based on user actions.

These coupons become active when assigned through a Promo Campaign and support only relative expiry settings:

- **Coupon expiry**: Define how long the coupon remains valid after it is assigned. For example, 7 days after the coupon was rewarded. You can select from minutes, hours, days, or weeks. Select Never for coupons with no expiry.


<Image src="https://files.readme.io/18f4b64212939afced1f33c6ef9571c4864501c88755ea11575a8b30d5956ffc-image.png" alt="Set Validity of User Action Based Coupons" align="center" border={true} />


#### Custom Schedule

Use this option to restrict when a coupon can be redeemed during the day or week, regardless of the overall start or end time. This feature is available for all coupon types. It is especially useful for time-sensitive promotions, for example, Happy hour discounts, Weekend-only deals, Midnight or lunchtime offers and so on.

You can define:

- Specific days of the week (for example, Saturday, Sunday)
- Specific time slots (for example, 12:00 PM – 3:00 PM)

This ensures the coupon is only redeemable during those selected windows, even if it’s otherwise valid.

### Redemption Limits

Configure how many times a coupon can be redeemed globally and per user. These settings help prevent overuse and ensure budget control.

<Callout icon="📘" theme="info">
  ### Redemption Limits Rules

  - Redemption limits can be configured only for single code coupons (both all user and user action based).
  - For bulk code coupons (both downloadable and user action based codes), the code-level and user-level redemption limits are fixed to one. This is because each bulk coupon code is unique and designed for one-time use by a single user, ensuring exclusivity and preventing misuse.
</Callout>

#### Code Level Limits

Set the total number of times a coupon code can be redeemed globally across all users. The default is _unlimited_ but you can also change the total limit to X times.

- **Daily limit**: Maximum number of redemptions allowed per day. For example, 100 redemptions per day.
- **Weekly limit**: Maximum number of redemptions allowed per week. For example, 500 redemptions per week.
- **Monthly limit**: Maximum number of redemptions allowed per month. For example, 2000 redemptions per month.


<Image src="https://files.readme.io/2b89e8e77a4f6a603141b34f9987bbc60f4239884678bbe7bbc0d1ef5d30e9de-image.png" alt="Set Code Level Limits" align="center" border={true} />


#### User Level Limits

Set the number of times each user can redeem the coupon. The default total limit is set to one use per user, but you can change it to unlimited or click **Add Limit** to customize:

- **Daily limit**: Redemptions allowed per user per day. For example, 1 redemption per user per day.
- **Weekly limit**: Redemptions allowed per user per week. For example, 2 redemptions per user per week.
- **Monthly limit**: Redemptions allowed per user per month. For example, 4 redemptions per user per month.


<Image src="https://files.readme.io/d14a64172c2f68ddf06a08b5e98708e93c527c5bb12ea2aa241c7e52222aa755-image.png" alt="Set User Level Limits" align="center" border={true} />


#### Redemption Logic

When a user attempts to redeem a coupon, the system validates:

- Whether the coupon is active and within the validity period
- Whether the coupon meets all qualifying rules (cart, product, user property)
- If Single Code Coupon:
  - Ensure the global code-level limit has not been exceeded
  - Ensure the user has not exceeded their redemption quota
- If Bulk Code Coupon:
  - Ensure the unique code hasn’t been used before

If all checks pass, the coupon is successfully applied.

# Best Practices

The following are the best practices when creating coupons:

- Use percentage discounts for small purchases and flat discounts for high-value items.
- Set expiry dates to create urgency.
- Use cart-based conditions to increase order value.
- Track coupon performance regularly and adjust campaigns accordingly.
- Avoid excessive stacking to prevent revenue loss.

<br />
