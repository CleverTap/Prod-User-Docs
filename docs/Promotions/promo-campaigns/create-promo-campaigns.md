---
title: Create Promo Campaigns
excerpt: >-
  Learn how to create and configure a Promo Campaign from scratch using the
  step-by-step campaign builder.
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

This document provides detailed instructions on creating and configuring a Promo Campaign using the Campaign Builder. It guides you through the key steps to set up your campaign, including defining your campaign goals, selecting the right target audience, choosing the campaign type, and customizing your settings.

# Create Promo Campaign

Go to _Promotions_ > _Promo Campaigns_ and click **Create Campaign**. The _New Promotion Campaign_ page opens. To create a Promo Campaign, perform the following five key steps:

1. [Define Qualification Criteria](doc:create-promo-campaigns#define-qualification-criteria)
2. [Select Target Segment](doc:create-promo-campaigns#select-target-segment)
3. [Set Up Reward](doc:create-promo-campaigns#set-up-reward)
4. [Set Up Delivery Preference](doc:create-promo-campaigns#set-up-delivery-preferences)
5. [Publish Campaign](doc:create-promo-campaigns#publish-campaign)

## Define Qualification Criteria

The _Start Here_ section is where you choose how users will qualify for the reward. The qualification criteria provide the following options:

* **Past behavior/Custom list**: Target users based on actions performed in the past or a custom list uploaded to the CleverTap dashboard. For example, you can target users who have not done a transaction in the last 6 months, and offer them a 20% discount coupon.
* **Live behavior**: Trigger rewards in real-time when a user performs or does not perform an event. For example, you can trigger a reward when a user adds items to their cart but does not complete the checkout process within a set timeframe.

<Image align="center" border={true} caption="Define Qualification Criteria" src="https://files.readme.io/db8874c06fae7a9f98884e2d01a593742b44a052dc5bd6030f63527b1d42b607-image.png" />

## Select Target Segment

The _Who_ section allows you to define who should receive the reward using the rule builder. The _Target Segment_ rule builder lets you select users from an existing saved segment or create a new segment using event and property-based rules as follows:

* **Find users from segment**: Select users from a saved segment or define a new one.
* **Create rules based on events**: Build custom logic using event and property-based conditions
  * Users who **have done** specific events
  * Users who **have not done** certain events
  * Users who **have common user properties**, such as device type and location, are part of a particular segment, and so on.
  * Users who **have common interests** or share common behavioral traits or usage patterns, such as frequent shoppers or high-engagement users.
* Option to enable **Constant event property**, which keeps event property values fixed during evaluation. It is useful when comparing multiple events with shared attributes. For example, you can lock the Product ID property across both events to find users who viewed and purchased the same product.

<Image align="center" border={true} caption="Select Target Segment" src="https://files.readme.io/c0f72135336ae3b88597f99adb1a424fad8b23e8c8d814927a28548d3ef4853c-image.png" />

### Set Control Group and Target Segment Cap

After defining your target segment, expand the _Control group and target segment cap_ panel to configure two optional controls:

* A control group for measuring campaign impact, and
* A cap on how many users receive the reward

#### Set Control Group

The control group is a subset of qualified users who do not receive the reward. Their behavior can be compared with users who receive it, giving you a true measure of campaign impact.

<Image align="center" border={true} caption="Set Control Group" src="https://files.readme.io/aa8aa9fa114809458e4da9c92a1fcd3d0ec35c8d94830d3f3a854dfd8a43280c-image.png" width="75% " />

The following control group options are available:

* **System Control Group**: Selected by default. Randomly excludes a system-defined percentage of qualified users (for example, 4%) from receiving the reward.
* **Other Control Groups**: (Optional) Select a custom control group from the dropdown if additional control groups are configured at the account level.

<Callout icon="📘" theme="info">
  #### Note

  The System control group percentage is set at the account level and cannot be changed from within the campaign builder. To modify it, go to _Settings_ > _Control Groups_. For more information, refer to [Control Groups](doc:control-groups).
</Callout>

#### Set Target Segment Cap

The target segment cap controls how many users from the qualified segment actually receive the reward.

<Image align="center" border={true} caption="Set Target Segment Cap" src="https://files.readme.io/51efb2f3f7466132a338b975e7f41857b25800ba5976992f440d795327c1c4a7-image.png" width="75% " />

The available options and their behavior vary depending on the campaign type (Past Behavior/Custom List or Live Behavior) selected in the [Select Target Segment](doc:create-promo-campaign#select-target-segment) section. The following segment cap options are available based on the selected campaign type:

**Option 1: Send campaign to all qualified target segment users**

Distributes the reward to every user who qualifies based on the segment rules defined in the [Select Target Segment](doc:create-promo-campaign#select-target-segment) section.

For Past Behavior and Custom List campaigns, you can also select the _Don't send the campaign if target segment exceeds [X] users_ option to set an upper threshold. If the qualified segment size exceeds the specified limit, CleverTap does not send the campaign. This protects reward budgets on limited-inventory campaigns such as bulk coupon codes.

**Option 2: Send campaign to at most [X] qualified users**

Limits the total rewards distribution to X users across the entire campaign run. For example, if your qualified segment has 50,000 users and you enter 5,000, only 5,000 randomly selected users will receive the reward when the campaign runs.

**Option 3: Send campaign to at most X qualified users per day (available only for live campaign types)**

Limits the total rewards distribution to X users per day, with qualification in real time.

Additionally, you can also select _And cap to [X] over all_ to cap the cumulative upper limit. This sets the total number of users who can receive the reward over the campaign's lifetime. Once this overall cap is reached, the campaign stops distributing rewards, even if the daily cap has not been met that day.

For example, if you set the daily cap to 500 users and the overall cap to 2,000 users, the campaign rewards up to 500 users each day. Once 2,000 total users have been rewarded across all days, the campaign stops distributing rewards regardless of how many days remain.

<Image align="center" border={true} caption="Set Per Day Capping" src="https://files.readme.io/8f9c34dcd8afd08a80f06c76e0e0746ad8577ce47eecd31d1381aa6a07a37ead-image.png" />

<Callout icon="📘" theme="info">
  Note

  If you only set the daily cap without enabling _And cap to [X] over all_, rewards continue distributing at the daily rate until the campaign's end date is reached.
</Callout>

## Set Up Reward

The **What** section allows you to define the **reward type** for your Promo Campaign. Depending on your selection, the configuration options vary. CleverTap supports the following reward types:

* [Loyalty Points](doc:create-promo-campaigns#loyalty-points)
* [Coupons](doc:create-promo-campaigns#coupons)
* [Partner Vouchers](doc:create-promo-campaigns#partner-vouchers)
* [Custom Rewards](doc:create-promo-campaigns#custom-rewards)

## Set Up Delivery Preferences

The _When_ section defines when the campaign starts and ends, and the controls available vary based on whether you select a _Past Behavior Segment (PBS)_ or a _Live Behavior Segment_.

### For Past Behavior Segments or Custom List (PBS)

When you select Past Behavior or Custom List Segment, the _When_ section shows the following options:

| Option                 | Description                                                                                                                       | Example / Use Case                                                                  |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Send Now**           | Launches the campaign immediately using the current timestamp and the **account timezone** (for example, GMT+05:30 Asia/Kolkata). | Run a flash-sale promotion as soon as it is configured.                             |
| **Schedule for Later** | Let's you choose a **future start date and time**. You can also adjust the timezone if required.                                  | Schedule a promo to start at 6:00 PM on a Friday evening to capture higher traffic. |

<Image align="center" border={true} caption="Set Delivery Preferences in Past Behavior/Custom List Segments" src="https://files.readme.io/f64c9ea54de2ed6ec5e1f42297e4005d60be73e4dd7e6e07dd3364c20127b795-image.png" />

### For Live Behavior Segments

When you select Live Behavior Segment, the _When_ section shows the following options:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>

      <th>
        Example / Use Case
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Start Date and Time**
      </td>

      <td>
        Choose when the campaign should start.

        * **Now**: Launches the campaign immediately after publishing.
        * **On a Date/Time**: Launches the campaign at a scheduled date and time.
      </td>

      <td>
        Start the live campaign immediately to capture ongoing cart abandonment events, or schedule it to go live on the morning of a sale day.
      </td>
    </tr>

    <tr>
      <td>
        **End Date and Time**
      </td>

      <td>
        Choose when the campaign should stop.

        **Never**: Campaign keeps running until manually stopped.

        * **On a Date/Time**: Campaign automatically ends at a chosen date/time.
      </td>

      <td>
        End the campaign automatically at midnight on the final day of a seasonal sale.
      </td>
    </tr>
  </tbody>
</Table>

<Image align="center" border={true} caption="Set Deliver Preference in Live Behavior Campaigns" src="https://files.readme.io/ac5f953cd43599b7d06b8532535fe1ae8871b5e900f4559687d0b0fa8bba8dfb-image.png" />

## Publish Campaign

Once you define all the above sections, click **Publish Campaign** to activate or schedule the campaign.

<Image align="center" border={true} caption="Publish Campaign" src="https://files.readme.io/208d31fed015df3703b4e35c6741ded52ecf1b99c62bfef9f5c085323a193ad1-image.png" />

# Reward Types

Each reward type includes different configuration settings, described in the sections below:

## Loyalty Points

Use Loyalty Points to incentivize users with loyalty points that can be accumulated and redeemed within your app or platform. This option requires that wallets be pre-created in your CleverTap account.

The following configuration options are available when Loyalty Points is selected:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>

      <th>
        Example / Use Case
      </th>

      <th>
        Available In
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Loyalty wallet**
      </td>

      <td>
        Select the wallet from the dropdown. Ensures that points are distributed to the correct wallet.
      </td>

      <td>
        You can reward users based on context if you have multiple wallets (for example, Grocery vs. Food).
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Points earning scheme**
      </td>

      <td>
        Define how points are calculated when users qualify. Options include:

        * **Flat**: A fixed number of points for each qualifying user.
        * **Percentage**: Points calculated as a percentage of an event property (for example, order amount).
        * **Proportional**: Points awarded per defined unit of an event property.
        * **Random**: Points assigned from a defined range; exposes Value Range + Distribution Bias controls.
      </td>

      <td>
        * **Flat**: Every eligible user earns 100 points regardless of order amount.
        * **Percentage**: If set to 10% of the amount, a ₹500 purchase earns 50 points.
        * **Proportional**: For every ₹100 spent, the user gets 10 points.
        * **Random**: Users earn between 10 and 50 points, with distribution bias favoring the average.
      </td>

      <td>
        * **Flat** and **Random**: Available in both Past Behavior/Custom List and Live Behavior segments.
        * **Percentage** and **Proportional**: Available only in Live Behavior segments
      </td>
    </tr>

    <tr>
      <td>
        **Points value**
      </td>

      <td>
        The input control for Points value changes based on the selected Points Earning Scheme:

        * **Flat**: Enter a single fixed value of points/credits awarded to each qualifying user.
        * **Percentage**: Define a percentage of a selected event property (for example, order amount) from the qualifying event (typically a Charged event).
        * **Proportional**: Define "points per unit" of a selected event property (for example, for every X units of the property, award Y points).
        * **Random**: Set a min–max range of points/credits; the system randomly selects a value within this range for each qualifying user (also supports Distribution Bias).
      </td>

      <td>
        * **Flat**: Set to 100 means every qualifying user gets 100 credits.
        * **Percentage**: Set to 10% means a purchase of ₹500 (as per selected event property) gives 50 credits.
        * **Proportional**: Set to 10 credits for every Rs. 100 (per selected event property).
        * **Random**: Set to a range of 10–100 means each qualifying user gets a random value between 10 and 100.
      </td>

      <td>
        * **Flat** and **Random**: Available in both Past Behavior/Custom List and Live Behavior Segment.
        * **Percentage** and **Proportional**: Available only in Live Behavior campaigns.
      </td>
    </tr>

    <tr>
      <td>
        **Distribution bias** (For Random scheme only)
      </td>

      <td>
        Control distribution pattern that allows you to select the following options:

        * **Favor Min**: Skews distribution toward the lower end of the range.
        * **Favor Avg**: Skews distribution toward the midpoint of the range.
        * **Favor Max**: Skews distribution toward the higher end of the range.
      </td>

      <td>
        * **Favor Min**: For a range of 10–100 points, most users receive lower values (for example, 10–30), while fewer receive higher values.
        * **Favor Avg**: For a range of 10–100 points, most users receive values around the midpoint (for example, ~55), with fewer at the extremes.
        * **Favor Max**: For a range of 10–100 points, most users receive higher values (for example, 70–100), while fewer receive lower values.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Max points per reward**
      </td>

      <td>
        Define the maximum number of points that can be awarded in a single transaction or instance. Applicable only when using **Percentage** or **Proportional** earning schemes in Live Behavior campaigns. Not available for **Flat** or **Random** schemes.
      </td>

      <td>
        Cap points at 500 per purchase, even if the % calculation exceeds this value.
      </td>

      <td>
        Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Maximum recurrence per user**
      </td>

      <td>
        Control how many times a single user can receive the reward. Multiple limits can be combined (for example, total + per day/week/month).
      </td>

      <td>
        If the total limit is 5 and the per-day limit is 2, the user can receive the reward up to two times per day until they reach a total of 5 rewards.
      </td>

      <td>
        Live Behavior Segments only
      </td>
    </tr>

    <tr>
      <td>
        **Custom points validity**
      </td>

      <td>
        Define the activation and expiry lifecycle of awarded points.
      </td>

      <td>
        * **Activation**: Immediate (points instantly usable) OR Custom delay (for example, activate after 7 days).

        * **Expiry**: Specifies how the expiry of points is determined. You can choose one of the following options:
          * **Never**: Points do not expire.
          * **Fixed date**: Points expire on a specific date.
          * **Custom duration**:  Points expire after a defined duration from when they are awarded (for example, 30 days after activation). When a custom duration is set to Calendar years, points earned in the same calendar year expire at the end of the selected year. For example, if validity is set to 3 calendar years, points earned anytime in 2025 expire on December 31, 2027
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Budget**
      </td>

      <td>
        Define the budget to control how rewards are distributed. Budget can be set at two levels:

        * **Per Campaign Budget**: Caps the total rewards that the campaign can distribute.
        * **Per User Budget**: Caps the maximum rewards a single user can receive during the campaign.  
          Once the defined limit is reached (per user or for the entire campaign), no further rewards are issued.
      </td>

      <td>
        If the Per Campaign Budget is 5,000 points, rewards stop once the campaign collectively distributes 5,000 points, even if more users qualify.  
        If the Per User Budget is 500 points, each user can only receive up to 500 points during the campaign, even if they continue qualifying.
      </td>

      <td>
        Live Behavior Segments only
      </td>
    </tr>

    <tr>
      <td>
        **Custom metadata**
      </td>

      <td>
        Add dynamic key–value pairs to pass additional data into the wallet points payload. Each row has two modes:

        * **System Key**: Select from predefined system keys.
        * **Custom Key**: Define your own key.

        Duplicate keys are not allowed.
      </td>

      <td>
        Add `{'{'}' "orderId": "12345", "promoType": "festival" {'}'}` as custom metadata to track order-related rewards.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  **Points to Consider**

  * Custom Activation does not check user behavior. It delays redemption so businesses can increase net profit on orders.
  * Wallet must be pre-configured in your account.
</Callout>

<Image align="center" border={true} caption="Set Up Loyalty Points in Rewards" src="https://files.readme.io/4d437eec9f1f394b546d51406d53ff000e37dfdcf458a6ec637b06d8f1ced0fb-image.png" />

## Coupons

Use Coupons to provide users with discount codes or special offers. Coupons must be pre-created in CleverTap and active.

The following configuration options are available when Coupons is selected:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>

      <th>
        Example / Use Case
      </th>

      <th>
        Available In
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Coupon Type**
      </td>

      <td>
        Choose Single Code (shared) or Bulk Codes (unique).
      </td>

      <td>
        * **Single Code:** A fixed 20% off coupon shared with all users.
        * **Bulk Codes:** Each user gets a unique 10% off coupon.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Coupon code**
      </td>

      <td>
        Select from available coupons that match the type. Coupon must be active and not fully redeemed.
      </td>

      <td>
        Dropdown lists valid Single or Bulk codes.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Max coupons per user**
      </td>

      <td>
        Defines how many times the coupon can be rewarded to the same user. This does not control redemption. If a user-level redemption limit is 2 and the same coupon is rewarded twice, user can redeem 4 times total.
      </td>

      <td>
        Selecting _Limit = 1_ means each user can only be rewarded the coupon once.
      </td>

      <td>
        Live Behavior Segments only
      </td>
    </tr>

    <tr>
      <td>
        **Max coupons per campaign**
      </td>

      <td>
        Defines the total number of coupon codes that the campaign can distribute.
      </td>

      <td>
        Selecting _Limit = 1000_ means the campaign stops distributing coupons after 1000 coupons are issued.
      </td>

      <td>
        Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Coupon redemption activation**
      </td>

      <td>
        Define when coupons can be redeemed, immediately or after a custom delay.
      </td>

      <td>
        * **Immediate:** Flash sale means redeem instantly.
        * **Custom:** Redeemable 48 hours after reward assignment.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>
  </tbody>
</Table>

<Image align="center" alt="Set Up Coupons in Rewards" border={true} caption="Set Up Coupons in Rewards" src="https://files.readme.io/362ace8d3ea7a677c7c9a93f885bd75dbd8db80a5f74fc2fda32e1de4b2c66ca-image.png" />

## Partner Vouchers

Use Partner Vouchers to distribute unique codes provided by third-party providers integrated with your account.

The following configuration options are available when Partner Vouchers is selected:

| Option                     | Description                                                                                                                                                                                                         | Example / Use Case                                                                                      | Available In                                       |
| :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------ | :------------------------------------------------- |
| **Partner**                | Select from integrated and active voucher providers.                                                                                                                                                                | Pick Amazon Gift Cards provider.                                                                        | Past Behavior/Custom List + Live Behavior Segments |
| **List tag**               | Select the voucher batch (list tag) for distribution. Codes are auto-assigned uniquely to users.                                                                                                                    | Batch _Holiday2025_ with 10,000 gift codes.                                                             | Past Behavior/Custom List + Live Behavior Segments |
| **Max codes per user**     | Defines how many times the voucher can be rewarded to the same user. This does not control redemption. If a user-level redemption limit is 2 and the same voucher is rewarded twice, user can redeem 4 times total. | Selecting _Limit = 1_ means each user can only be rewarded the voucher once.                            | Live Behavior Segments only                        |
| **Max codes per campaign** | Defines the total number of voucher codes that the campaign can distribute.                                                                                                                                         | Selecting _Limit = 1000_ means the campaign stops distributing vouchers after 1000 vouchers are issued. | Live Behavior Segments                             |

<Image align="center" border={true} caption="Set Up Partner Vouchers in Rewards" src="https://files.readme.io/5ede864217cd7dc80e936bad3e1ea62efb4de25939eca23a041f1d8f2aa1126e-image.png" />

<Callout icon="📘" theme="info">
  **Note**

  * Only active, unexpired voucher lists are displayed.
  * No preview of voucher details is available.
  * System ensures each user receives a unique, unused code.
</Callout>

## Custom Rewards

Use Custom Rewards to integrate external reward systems. When a user qualifies, CleverTap triggers a webhook call to your configured endpoint, enabling you to issue rewards such as third-party gift cards, credits, or custom incentives.

The following configuration options are available when Custom Rewards is selected:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Option
      </th>

      <th>
        Description
      </th>

      <th>
        Example / Use Case
      </th>

      <th>
        Available In
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Webhook endpoint (mandatory)**
      </td>

      <td>
        Select a pre-configured webhook endpoint from the dropdown. If none exist, click the link provided to add a new configuration.
      </td>

      <td>
        Connect to an external gift card provider API endpoint.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Custom reward type**
      </td>

      <td>
        Select whether to issue Physical & digital rewards (tangible gifts) or Self-managed wallet credits (monetary/credit-based).
      </td>

      <td>
        Physical & digital: Send a Bluetooth speaker as a gift.  
        Self-managed: Credit ₹200 to a user's wallet.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Physical & digital rewards**
      </td>

      <td>
        Choose a reward that must be pre-created in your account.
      </td>

      <td>
        Select "Amazon Voucher" or "Smartwatch".
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Max recurrence per user**
      </td>

      <td>
        Allows you to control how many rewards can be granted per user on a daily, weekly, or monthly basis.
      </td>

      <td>
        Max per user = 1 reward in a week
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Self-managed wallet credits**
      </td>

      <td>
        Choose a wallet from the dropdown (must be pre-created).
      </td>

      <td>
        Select a wallet to reward credits or money.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Credits earning scheme** (only for Self-managed wallet credits)
      </td>

      <td>
        Choose how to define wallet credits. Options include:

        * **Flat**: a fixed number of credits for each qualifying user.
        * **Percentage**: credits calculated as a percentage of an event property (for example, order amount).
        * **Proportional**: credits awarded per defined unit of an event property (for example, 10 credits per ₹100 spent).
        * **Random**: credits assigned from a defined range; exposes Value Range + Distribution Bias controls.
      </td>

      <td>
        * **Flat**: All qualifying users get 100 credits.
        * **Percentage**: 10% of ₹500 purchase, i.e., 50 credits.
        * **Proportional**: 10 credits for every ₹100 spent.
        * **Random**: Users get between 10–100 credits.
      </td>

      <td>
        * **Flat** and **Random**: Available in both Past Behavior/Custom List and Live Behavior segments.
        * **Percentage** and **Proportional**: Only available in Live Behavior campaigns (not supported in PBS).
      </td>
    </tr>

    <tr>
      <td>
        **Value**
      </td>

      <td>
        The input control for the credits value changes based on the selected credits Earning Scheme:

        * **Flat**: Enter a single fixed value of credits awarded to each qualifying user.
        * **Percentage**: Define a percentage of a selected event property (for example, order amount) from the qualifying event (typically a Charged event).
        * **Proportional**: Define "credits per unit" of a selected event property (for example, for every X units of the property, award Y credits).
        * **Random**: Set a min–max range of credits; the system randomly selects a value within this range for each qualifying user (also supports Distribution Bias).
      </td>

      <td>
        * **Flat**: Set to 100 means every qualifying user gets 100 credits.
        * **Percentage**: Set to 10% means a purchase of ₹500 (as per selected event property) gives 50 credits.
        * **Proportional**: Set to 10 credits for every ₹100 (as per selected event property).
        * **Random**: Set to a range of 10–100 means each qualifying user gets a random value between 10 and 100.
      </td>

      <td>
        * **Flat** and **Random**: Available in both Past Behavior/Custom List and Live Behavior Segment.
        * **Percentage** and **Proportional**: Available only in Live Behavior campaigns.
      </td>
    </tr>

    <tr>
      <td>
        **Distribution bias** (For Random scheme only)
      </td>

      <td>
        Control distribution pattern that allows you to select the following options:

        * **Favor Min**: skews distribution toward the lower end of the range.
        * **Favor Avg**: skews distribution toward the midpoint of the range.
        * **Favor Max**: skews distribution toward the higher end of the range.
      </td>

      <td>
        * **Favor Min**: For a range of 10–100 credits, most users receive lower values (for example, 10–30), while fewer receive higher values.
        * **Favor Avg**: For a range of 10–100 credits, most users receive values around the midpoint (for example, ~55), with fewer at the extremes.
        * **Favor Max**: For a range of 10–100 credits, most users receive higher values (for example, 70–100), while fewer receive lower values.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Max credits per rewards** (only for Percentage and Proportional schemes)
      </td>

      <td>
        Enter the maximum credits per reward.
      </td>

      <td>
        Setting 100 means each user can get a maximum of 100 credits per reward.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Max recurrence per user**
      </td>

      <td>
        Allows you to control how many rewards can be granted per user on a daily, weekly, or monthly basis.
      </td>

      <td>
        Max per user = 1 reward in a day
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Budget**
      </td>

      <td>
        Defines how many rewards can be distributed.

        * **Physical & digital rewards**: Supports campaign-level and time-based limits.
        * **Self-managed wallet credits**: Supports per-campaign and per-user limits (varies by scheme).
        * **Flat**: Supports Per Campaign budget only.
        * **Percentage**: Supports both Per Campaign and Per User budgets.
        * **Proportional**: Supports both Per Campaign and Per User budgets.
        * **Random**: Supports both Per Campaign and Per User budgets.
      </td>

      <td>
        * **Physical & digital rewards**:  
          Campaign limit = 5,000 vouchers; additionally, set 1,000 vouchers per month.
        * **Self-managed  wallet credits**:
        * **Flat Credits**: Campaign limit = 10,000 credits.
        * **Percentage Credits**: Campaign limit = 10,000 credits and per-user cap = 500 credits.
        * **Proportional Credits**: Campaign limit = 10,000 credits and per-user cap = 500 credits.
        * **Random Credits**: Campaign limit = 10,000 credits and per-user cap = 500 credits.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **User identifiers key mapping**
      </td>

      <td>
        Map CleverTap's default user identity fields (User ID, Email address, Phone number) to your webhook payload keys. Each field supports the following modes: System key (CleverTap's default field names) or Custom key (specify your own key names).
      </td>

      <td>
        Map CleverTap's identity field to your external system's customerId or use default mapping for email and phone.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>

    <tr>
      <td>
        **Custom metadata**
      </td>

      <td>
        Add dynamic key-value pairs to include contextual data in the reward payload. Duplicate keys are not allowed.
      </td>

      <td>
        Add `{'{'}' "orderType": "electronics", "promoType": "festival" {'}'}` as custom metadata to track order-related rewards.
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segments
      </td>
    </tr>

    <tr>
      <td>
        **Preview JSON Payload**
      </td>

      <td>
        Displays a live JSON preview that includes reward metadata and configured key-value parameters.
      </td>

      <td>
        For example, refer to [JSON Payload](doc:create-promo-campaigns#json-payload)
      </td>

      <td>
        Past Behavior/Custom List + Live Behavior Segment
      </td>
    </tr>
  </tbody>
</Table>

<Image align="center" border={true} caption="Set Up Reward in Custom Rewards" src="https://files.readme.io/539ebea5210050327666ff4ed929383317200eb806d0ab85a7d1fa1ccd95f621-image.png" />

<Callout icon="📘" theme="info">
  **Points to Consider**

  Before you begin:

  * Ensure you configure the webhook endpoint before creating the campaign.
  * Verify that the endpoint can handle campaign volume, retries, and logging.

  During setup:

  * Physical & Digital Rewards and Self-managed Wallet Credits have separate configuration options; choose the appropriate type based on your use case.
  * The reward payload is fully customizable and scales automatically with campaign volume.
  * Custom Rewards give maximum flexibility but require your external system to handle issuance and redemption.
</Callout>

### JSON Payload for Custom Rewards

```json
{
  "user": {
    "userId": "12345",
    "email": "user@example.com",
    "phone": "+1234567890"
  },
  "reward": {
    "type": "custom",
    "value": 100,
    "metadata": {
      "orderType": "electronics",
      "promoType": "festival"
    }
  }
}
```

# Best Practices

Maximize campaign effectiveness and avoid common pitfalls with the following best practices for setup, execution, and management:

* **Use Segments Wisely**: Tailor rewards with meaningful segmentation.
* **Test Before Scaling**: Start small to validate campaign performance.
* **Set Limits**: Always define per-user and per-campaign limits.
* **Reward Inventory**: Ensure sufficient reward stock throughout the campaign.
