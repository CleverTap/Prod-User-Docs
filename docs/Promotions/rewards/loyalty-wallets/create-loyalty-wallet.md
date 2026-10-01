---
title: Create Loyalty Wallet
excerpt: Learn how to create a Loyalty Wallet to reward users with virtual points.
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

The loyalty wallet tracks all reward points that can be used for discounts, offers, and in-app purchases. Beyond earning and expiry rules, a wallet can optionally be configured with redemption settings, conditions, conversion rates, and points discount caps that are enforced when points are redeemed through the [Points Validation API](https://developer.clevertap.com/docs/points-validation-api). This document provides an overview of wallet creation and explains each configurable field, including redemption settings, with examples to help you set up your wallet accurately.

# Create Wallet

To create a wallet, perform the following steps:

1. Go to **Promotions** from the CleverTap dashboard.

2. Click **Rewards** and select **Loyalty Wallets** from the list.

3. Click **Create Loyalty Wallet**. Wallet creation has the following parts:
   - [Wallet Basic](doc:create-loyalty-wallet#wallet-basic)
   - [Redemption Settings](doc:create-loyalty-wallet#redemption-settings-optional)

## Wallet Basic

Wallet Basic defines the core rules of your loyalty wallet: its name, the currency or points system it uses, when points expire, the order in which points are redeemed, and how point values are rounded.&#x20;

Enter the following details:


<Image src="https://files.readme.io/8e29d67cbf8ceb4bd6aeaa8880ce37171f6448308734e7618e17681a989aa3f3-Wallet_Basic_Details.png" align="center" caption="Wallet Basic Details" border={true} />


1. Enter a unique name for the loyalty wallet. For example, _CleverTap Coins_. Once created, the wallet name cannot be changed.

2. Enter the applicable currency or points system for the wallet's loyalty points. For example, _Coins_.

3. Define the points expiry rule for points issued through the wallet. You can select the expiry type from the following options:
   - **Never**: Points will never expire.
   - **After**: Points expire after a specific duration. You can specify the number of days, months, or years after which points must expire.
   - **After X Calendar Years**: Points expire at the end of the Xth calendar year following issuance. For more information on how points expiry is calculated, refer to [Points Expiry Calculation](doc:create-loyalty-wallet#points-expiry-calculations).
     <Callout icon="📘" theme="info">
       #### **Expiry Rule Setting**

       The expiry rule can only be set once at the time of wallet creation and cannot be changed later. If no expiry rule is set, points never expire.
     </Callout>

4. **Define Rounding Rules**: Determine how point values are rounded when calculated. You can round point values to 0, 1, 2, or 3 decimal places. Select from the following rounding types:
   - **Round up**: Rounds the value up to the nearest specified decimal place when the next digit is 5 or greater. For example, if the calculated points are 30.2789 and rounding is set to 2 decimal places, the third decimal digit (8) is greater than 5, so the points credited will be 30.28.
   - **Round down**: Rounds the value down to the nearest specified decimal place, discarding any digits beyond the specified limit. For example, if the calculated points are 12.783 and rounding is set to 2 decimal places, the points credited will be 12.78.

5. **Define Point Consumption Strategy**: Select how points are redeemed from the user wallet. This setting applies to all future redemption events for this wallet. Select from the following two strategies:

   - **Points with earliest expiry are consumed first**: Select this expiry option when you want the points with the earliest expiry date to be consumed first during redemption, regardless of when the points were issued.
   - **Points with earliest issuance are consumed first**: Select this expiry option when you want the points with the earliest issuance date to be consumed first during redemption, regardless of expiry date.
     <Callout icon="📘" theme="info">
       #### **Updating Points Consumption Strategy**

       The points consumption strategy can only be configured when creating a new wallet. It cannot be changed after the wallet is created.

       For example, if you create a wallet with the issuance FIFO strategy, all points issued to that wallet will be consumed in the order they were issued. If you later want to switch to Expiry FIFO, you cannot update the existing wallet. To update this, you need to create a new wallet with the desired strategy. Points already issued to the original wallet are unaffected and continue to follow the strategy set at the time that wallet was created.
     </Callout>

   For a detailed explanation of how each strategy works across different redemption scenarios, refer to [Point Consumption Strategies](doc:create-loyalty-wallet#point-consumption-strategies).

6. Click **Next** to continue to _Redemption Settings_.

## Redemption Settings (Optional)

<Callout icon="📘" theme="info">
  #### Private Beta

  Redemption Settings is currently released in Private Beta. To access the feature, contact your  Customer Success Manager.
</Callout>

Redemption Settings define the rules that a customer's points must meet before they can be redeemed, and how those points convert to a currency value. This configuration is **optional;** set it up only if you want CleverTap to validate points redemption before checkout.&#x20;

- **For existing wallets:** No redemption rule is saved by default. You must explicitly edit the wallet to configure and save the settings.
- **For new wallets:** You can save without configuring this step; unedited fields fall back to default values, and no redemption rule is active until you enable it.

If the use case is a direct redemption, such as buying a reward with points, you do not require these settings. Debit the points directly with the [Debit/Credit Wallet API](https://developer.clevertap.com/docs/debitcredit-wallet).

Redemption Settings let you define the points redemption rules in CleverTap instead of building them in your application. When a redemption request is validated, CleverTap checks it against these rules and calculates the points discount. You do not need to build or maintain this calculation.

You can also use Redemption Settings to encourage higher order values. For example, set a minimum order value for redemption, or increase the points to currency rate for high-value orders.

To configure the settings, enter the following details:


<Image src="https://files.readme.io/64ba7c52f1854c126f2c1ec9e928349a935e8aa87c0554009e02cb9179463ae3-Redemption_Settings.png" align="center" caption="Redemption Settings" border={true} />


1. Under Redemption Conditions, set the order requirements, product requirements, and minimum active points. For more information, refer to [Setting Up Redemption Eligibility Criteria](doc:create-loyalty-wallet#redemption-eligibility-criteria)​.
2. Under Points Conversion Ratio, set the _Points to Currency Rate_. For more information, refer to [Points to Currency Rate](doc:create-loyalty-wallet#points-to-currency-rate).
3. Under Points Discount Limit Per Order, choose the Maximum Points Discount Per Order.&#x20;
4. Click **Create**. The wallet configuration is saved, and the wallet is activated immediately. You can also skip this step to save the wallet with default values (no redemption rule configured).

### Redemption Eligibility Criteria

Users must meet all configured conditions below before a redemption request succeeds:

- **Order requirements**: Conditions evaluated against the order/cart as a whole (for example, "minimum order value of $1,000 and payment mode = credit card").
- **Product requirements**: Conditions evaluated against the items in the cart. An item attribute is a property of each item in the cart, such as `category`, `brand`, or a custom attribute. Set an **Any of / Each of** mode independently for each attribute (for example, "only for recharge and bill payments")
- **Minimum active points required**: The customer's active point balance must meet the specified threshold before a redemption attempt is allowed. These checks are performed independently of the order and product requirements above.

#### Setting Up Redemption Eligibility Criteria

This setting is optional. If you do not configure any, no order, product, or minimum-balance restriction applies.

Under **Redemption Eligibility Criteria**, click **Add Order Condition** or **Add Product Condition** to configure criteria.&#x20;

- For **Order Conditions:**
  - Select a cart property. for example, `saleAmount`, `paymentMode`, or a custom property you have created.
  - Choose an operator: `equals`, `not equals`, `>=`, `<=`, `between`, `contains`, `exists`, or `not exists`.
  - Enter the value to match. String comparisons are case-insensitive;&#x20;
  - Add multiple conditions and combine them with **AND** or **OR**.&#x20;
- For **Product Conditions:**
  - Select an item attribute. For example, `category`, `brand`, or a custom attribute.
  - Choose the rule mode for this attribute: **Any of** (at least one item in the cart must match) or **Each of** (every item must match), and enter the value to match.
  - The rule mode is set **independently per item attribute**; that is, one attribute can use "Any of" while another uses "Each of" in the same rule.
  - Add multiple conditions and combine them with **AND** or **OR** between attributes.
- For **Minimum Redeemable Points Balance:**
  - Enter a positive integer representing the minimum balance a customer must hold to redeem.
  - This check is optional; leave it empty if there's no minimum balance floor.

#### Add Custom Properties

If the property you need is not in the list, create a custom property:

1. In the condition property dropdown, click **Add custom property**.
2. Enter a key name. The key cannot contain spaces and must be unique.
3. Select the data type, either _string_ or _number_.
4. Save the property.

The property appears under **Custom properties**, and you can use it in any condition or override. A property, created from an order condition, applies to the cart. A property, created from a product condition, applies to items in the cart. A custom item attribute is saved at the account level, so they are available across wallets. The data type of the property cannot be changed after it is created.

To validate a redemption against a custom property, send the key in the `metadata` object of the [Points Validation API](https://developer.clevertap.com/docs/points-validation-api) request in `order.metadata` for order properties and, `items[].metadata` for item attributes.&#x20;

**Example 1**

You want to allow points redemption only on orders over $500, with the payment method "wallet", and only when the cart contains a mobile recharge item.

1. **Order Condition:** `saleAmount >= 500` AND `paymentMode = wallet`
2. **Product Condition:** `category = mobile recharge` (rule mode: Any of)
3. **Minimum Active Points:** 100 (customer must hold at least 100 points)

When a customer attempts to redeem, the system checks all three. If the order value is $400 (fails the $500 check), the redemption is rejected, and the customer sees: _"Order value must be greater than or equal to 500."_

<Callout icon="📘" theme="info">
  #### Note

  - Both Order and Product requirements are **optional**; a wallet can have neither configured.

  - If more than one condition fails at once, only the first failing check (by priority order) is returned.

  - Missing or mismatched keys in the payload are treated as failures on AND conditions; on OR conditions, evaluation continues to the next key.
</Callout>

### Points to Currency Rate

The points to currency rate determines how many points equal a given currency amount. You can set a **default ratio** that applies universally, plus optional **conditional ratios** that override the default when specific cart or product conditions match.

#### Set Up Default Ratio

To set up the default ratio, perform the following steps:

1. Under **Points Conversion Ratio**, enter the **Default Ratio** as `1 point = X <currency>`.

   For example, `1 point = 0.01 USD`, that is, 100 points = $1.

2. Click the currency dropdown to select or confirm your currency (for example, USD, EUR, INR). The list follows ISO 4217 standards.
   <Callout icon="📘" theme="info">
     #### Important

     CleverTap does not convert currencies. The currency you select is a label that is returned as-is in the `currency` field of the Points Validation API response. All amounts in the redemption settings, including the rates and the points discount limit, are in this currency, and the `saleAmount` you send is used as-is.&#x20;

     Ensure the orders are in the same currency as the wallet. For example, if the orders are in INR, select INR and set the rates in INR.

     A wallet has one currency. Overrides use the same currency as the default ratio.
   </Callout>

#### Add Overrides

Overrides let you apply different points-to-currency rates based on cart properties, product properties, or combinations of both. The first matching override is used; if no override matches, the default ratio applies.

To add the conditional ratios, perform the following steps:

1. Under **Points to Currency Rate**, click **+ Override** to create a new conditional ratio.

2. Enter a **Setting Name**, for example, "Weekend recharge".

3. Enter the **Override Value** as `1 point = X <currency>`. This becomes the conversion ratio if conditions match.

4. Under **Applicable on**, click **Add Condition** to set when this override applies:
   - **Cart Conditions:** Apply to the order as a whole (for example, `saleAmount >= 1000`).
   - **Product Conditions:** Apply per item (for example, `category = electronics`). Set the rule mode (**Any of / Each of**) independently for each attribute.
   - Combine multiple conditions with **AND** or **OR**.
     You can add **multiple overrides**; they are evaluated in rank order. The first override whose conditions fully match is used, and evaluation stops.
     <Callout icon="📘" theme="info">
       ### Validation

       All ratio values (default + overrides) must be unique. CleverTap rejects duplicate ratios with the error.
     </Callout>

After adding overrides, you can manage them as follows:

- **Reorder:** Drag an override to change its rank. Overrides are evaluated from left to right, and the leftmost match is applied. The new order applies to validation requests made after you save.
- **Delete:** Remove an override from the tab.

<Callout icon="📘" theme="info">
  #### Overrides are Matched in Rank Order

  The first override whose conditions match is applied, even if a lower-ranked override is a closer fit. For example, Override 1 applies when `saleAmount >= 1000`, and Override 2 applies when `saleAmount >= 20000`. For a cart of 25000, Override 1 matches first and is applied, although the cart also qualifies for Override 2.&#x20;

  When using open-ended operators such as `>=`, rank the override with the highest threshold first.
</Callout>

#### Example 1

You want to offer a higher redemption rate as the order value increases.

- **Default Ratio:** `1 point = 0.005 USD`&#x20;
- **Override 1** (rank 1): `1 point = 0.02 USD` when `saleAmount >= 1000` (high-value boost)
- **Override 2** (rank 2): `1 point = 0.01 USD` when `saleAmount` is between 500 and 1000,  including both $500 and $1000.

An order of 1,500 uses Override 1, an order of 700 uses Override 2, and an order of 300 uses the default ratio. An order of exactly 1,000 matches both overrides, so Override 1 applies because it is ranked first.

**Example 2**

You want to change the rate based on the product category

- **Default Ratio:** `1 point = 0.005 USD` (all other categories)
- **Override 1:** `1 point = 0.01 USD` when `category = recharge`
- **Override 2:** `1 point = 0.02 USD` when `category = hotel booking`
- **Override 3:** `1 point = 0.03 USD` when `category = airline booking`

Set the rule mode to _Any of_. The rate applies to the whole order. If a cart contains items from more than one of these categories, the highest-ranked matching override applies to all.

### Points Discount Limit Per Order

This setting caps the percentage of an order value that can be covered by redeemed points. It is a **currency cap**, not a points cap, even though it appears alongside points-based settings.

#### Configure Discount Limit

Under **Points Discount Limit Per Order**, choose one of the following:

- **Unlimited**: No cap; points discount is limited only by the order's sale amount. A customer can redeem as many points as the order value allows.
- **Flat**: A fixed currency amount per order, for example, $50 max points discount per order.
- **Percentage**: A percentage of the order value, itself capped at a fixed currency amount. For example, "10% of order value, capped at $100".&#x20;

#### Example: Discount Limit Scenarios

**Scenario 1: Flat Cap**

- Configured: `Flat, $50 max`
- The customer enters the points (600) with a ratio of `1 point = 0.1 USD` ($60 calculated points discount)
- The calculated points discount exceeds the $50 cap, so the Points Validation API rejects the request with an error message.
- The response also returns the maximum points (500) and the maximum points discount ($50), so you know how many points to enter.

**Scenario 2: Percentage Cap**

- Configured: `Percentage, 15% of order value capped at $100`
- Order value: $800
- 15% of $800 = $120, but the cap is $100
- Maximum points discount allowed: $100

**Scenario 3: Unlimited**

- Configured: `Unlimited`
- Order value: $200
- System caps the points discount at $200 (the order value).

# How Loyalty Wallet Works

### Points Expiry Calculations

The following table explains how points expiry is calculated for each expiry unit:

| Expiry Unit        | How Expiry is Calculated                                                                                                                                                                                                                                                        | Example                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Days**           | Points expire exactly X days after the timestamp of the credit transaction.                                                                                                                                                                                                     | Points issued on January 10, 2026, at 12:59 PM with a 30-day expiry will expire on February 9, 2026, at 12:59 PM.                                                                                                                                                                                                                                                                |
| **Months**         | Points expire X calendar months after the credit transaction timestamp. The system adds X to the month value and preserves the same day-of-month. If the resulting date does not exist in the target month, the last valid day of that month is used instead.                   | **When the target date exists:** Points issued on January 10, 2026, at 12:59 PM with a 1-month expiry, expire on February 10, 2026, at 12:59 PM. **When the target date does not exist:** Points issued on January 31, 2026, at 11:45 AM with a 1-month expiry and February 31 does not exist, the points expire on February 28, 2026, at 11:45 AM (last valid day of February). |
| **Years**          | Points expire X calendar years after the credit transaction timestamp. The system adds X to the year value and preserves the same month and day. If the resulting date does not exist (e.g., February 29 in a non-leap year), the last valid day of that month is used instead. | **Standard case:** Points issued on March 10, 2025, at 10:00 AM with a 2-year expiry, expire on March 10, 2027, at 10:00 AM. **Leap year edge case:** Points issued on February 29, 2024, at 09:00 AM with a 1-year expiry, and February 29, 2025, do not exist; the points expire on February 28, 2025, at 09:00 AM.                                                            |
| **Calendar Years** | Points expire at the end of the Xth calendar year following the credit transaction date, regardless of when the points were credited.                                                                                                                                           | Points credited on May 15, 2025, with a 1-calendar-year expiry expire on December 31, 2025, and not on May 14, 2025.                                                                                                                                                                                                                                                             |

<Callout icon="📘" theme="info">
  #### **Timestamp and Expiry Behavior**

  For all expiry units, the exact issuance timestamp (HH:MM:SS) is preserved when calculating the expiry date. For example, points issued at 12:59 PM expire at 12:59 PM on the expiry date, not at midnight (12:00 AM).

  All timestamps are stored and evaluated in UTC. Ensure your credit transactions are timestamped in UTC to avoid expiry calculation discrepancies.

  Existing wallets and previously issued points are not affected. All previously issued points continue to follow the expiry rule that was active at the time they were credited.
</Callout>

### Point Consumption Strategies

When a user redeems points from their wallet, CleverTap consumes points sequentially across eligible credit records until the requested redemption amount is fulfilled. Only credit records with a remaining balance greater than zero and an expiry date in the future are considered. If a credit record has insufficient points to cover the full redemption, its entire remaining balance is consumed, and the system moves to the next eligible record.

The order in which credit records are consumed depends on the following two configured strategies for the wallet:

#### Points with Earliest Expiry are Consumed First (Expiry FIFO)

Points closest to their expiry date are redeemed first, regardless of when they were issued. This minimizes expiry liability by consuming the most at-risk points before they lapse.

For example, a user has three credit records in their wallet:

- Record A: 100 points, expires March 31, 2026
- Record B: 200 points, expires January 31, 2026
- Record C: 150 points, expires May 31, 2026

The user redeems 250 points. With Expiry FIFO, the system consumes Record B first (the earliest expiry of 200 points), then takes the remaining 50 points from Record A (the next earliest expiry). Record C is untouched.

**Tie-breaking with Same Expiry Date**

If two credit records share the same expiry date, the record with the earlier issuance timestamp is consumed first.

For example, a user has two credit records in their wallet:

- Record A: 100 points, expires June 25, issued January 10, 2026
- Record B: 50 points, expires June 25, issued January 12, 2026

Both records expire on the same date. In this case, the system consumes Record A first because it has the earlier issuance timestamp.

#### Points with Earliest Issuance are Consumed First (Issuance FIFO)

Points earned earliest are redeemed first, regardless of their expiry date. This follows a chronological first-in, first-out order based on when the points were credited.

For example, a user has three credit records in their wallet:

- Record A: 100 points, issued January 5, expires December 31
- Record B: 200 points, issued January 10, expires March 31
- Record C: 150 points, issued January 20, expires June 30

The user redeems 250 points. With Issuance FIFO, the system consumes Record A first (the earliest issuance of 100 points), then consumes the remaining 150 points from Record B (the next earliest issuance). Record C is untouched, even though Record B expires sooner than Record C.

**Tie-breaking with Same Issuance Timestamp**

If two credit records share the same issuance timestamp, the record with the earlier expiry date is consumed first.

For example, a user has two credit records in their wallet:

- Record A: 100 points, issued January 10, expires June 20
- Record B: 50 points, issued January 10, expires June 25

Both records were issued on the same date. In this case, the system consumes Record A first because it has the earlier expiry date.

<Callout icon="📘" theme="info">
  #### **Identical Timestamps**

  If two transactions share the same expiry date or issuance timestamp, the system resolves the tie using the order in which the transactions were recorded in the database, ensuring consistent and predictable redemption behavior.
</Callout>

## How Redemption Settings Work

When a redemption request is validated, CleverTap checks it against the Redemption Settings of the wallet and calculates the points discount. Validation does not deduct points. To deduct them, call the [Debit/Credit Wallet API](doc:debitcredit-wallet) with the points to debit returned in the response.

### Validation Sequence

CleverTap checks each request in the following order and stops at the first check that fails:

1. The wallet has Redemption Settings saved.
2. The customer has enough active points.
3. The customer's active points meet the minimum you set.
4. The order meets the order requirements.
5. The items meet the product requirements.
6. The calculated points discount is within the points discount limit.

### Calculation

CleverTap applies the first matching override, or the default ratio if none match, and calculates the following:

| Value                  | Calculation                                                                                           |
| ---------------------- | ----------------------------------------------------------------------------------------------------- |
| Calculated discount    | Points requested × Rate                                                                               |
| Points discount        | Lower of the calculated discount and the order value, rounded to two decimal places                   |
| Points to debit        | Points discount ÷ Rate, rounded down to the wallet's decimal places and limited to the active balance |
| Maximum points allowed | Points discount limit ÷ Rate                                                                          |

The points to debit may differ from the requested points. Always debit the points to debit value from the response.

#### Example

Rate: `1 point = 0.01 USD`. Order value: $10.00. Points requested: 1,200.

- Calculated discount: 1,200 × 0.01 = 12.00
- Points discount: lower of 12.00 and 10.00 = **10.00**
- Points to debit: 10.00 ÷ 0.01 = **1,000**

If the points discount limit is Flat, $5, the calculated discount of 12.00 exceeds the limit, so the request is rejected. The maximum points allowed are 5.00 ÷ 0.01 = **500**.

<br />

<br />
