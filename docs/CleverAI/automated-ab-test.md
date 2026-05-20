---
title: Automated A/B Test
excerpt: >-
  Learn how to configure AI-powered A/B Test for Push campaigns that
  continuously learns and shifts traffic toward your best-performing message in
  real time.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Automated A/B Test is CleverTap's AI-powered experimentation layer built on top of A/B testing. It enables marketers to test up to 10 message variants simultaneously within a Push campaign and uses a Multi-Armed Bandit (MAB) algorithm to continuously learn which variants drive the most engagement, automatically shifting traffic toward better-performing variants in real time.

Manual A/B testing works well with a small number of variants but becomes inefficient as experimentation scales. When too many variants split your traffic equally, most users see weaker messages, and results only tell you who won and not why a particular variant won. Automated A/B Test solves this by turning experimentation into a continuous, self-optimizing system.

For example, you are running a flash sale. You create 4 push notification variants with different CTAs, tones, and offer framing.

**With Manual A/B Test**, you split traffic evenly (25% each) and wait 7 days for a winner. By the time you act on results, the sale is over. Users who saw the weaker variants never converted.

**With Automated A/B Test**, by day 2, the bandit has already identified that Variant C is getting 3x the clicks and automatically routes 60% of traffic there, while the sale is still live. And it never stops learning. If Variant D starts outperforming C on day 5, traffic shifts again, automatically.

<Image align="center" border={true} caption="Manual A/B Test vs. Automated A/B Test" src="https://files.readme.io/c4c50593602055322b5ec762b9fb9ae38fff8243540da2e96e1bd20b66d2128b-Automated_AB_Test.png" />

# Manual A/B Test vs. Automated A/B Test

The following table shows how the Automated A/B Test differs from the manual A/B Test:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Feature
      </th>

      <th>
        Manual A/B Test
      </th>

      <th>
        Automated A/B Test
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Traffic Allocation
      </td>

      <td>
        Fixed % split across all variants throughout the campaign.
      </td>

      <td>
        Dynamic in nature; continuously shifts traffic toward better-performing variants.
      </td>
    </tr>

    <tr>
      <td>
        Learning
      </td>

      <td>
        Static learning; traffic split remains fixed for the duration of the campaign, regardless of variant performance.
      </td>

      <td>
        Real-time learning; bandit model updates reward distributions with every event.
      </td>
    </tr>

    <tr>
      <td>
        Exploration
      </td>

      <td>
        Not applicable.
      </td>

      <td>
        Stays uniformly random.
      </td>
    </tr>

    <tr>
      <td>
        Winner Selection
      </td>

      <td>
        Marketer can declare the winner after reviewing engagement results; typically determined by which variant shows the highest click or impression rate over the test period.
      </td>

      <td>
        Automatic or manual. The marketer can declare when ready; the system signals when the data is reliable.
      </td>
    </tr>

    <tr>
      <td>
        Wasted Impressions
      </td>

      <td>
        High; equal traffic to weak variants throughout.
      </td>

      <td>
        Lower; weaker variants receive progressively less traffic.
      </td>
    </tr>

    <tr>
      <td>
        Max Variants
      </td>

      <td>
        2–10.
      </td>

      <td>
        2–10.

        **Note**: Avoid adding variants just to fill the limit. More variants require more data per variant, which means more campaign runs before the system converges on a winner.
      </td>
    </tr>

    <tr>
      <td>
        Best For
      </td>

      <td>
        Controlled hypothesis testing with statistical significance.
      </td>

      <td>
        Fast experimentation at scale, messaging optimization, and continuous learning.
      </td>
    </tr>
  </tbody>
</Table>

# Key Concepts

* **Exploration**: A configurable percentage of your audience that always receives all variants equally, regardless of which variant is currently winning. This ensures that every variant continues to accumulate data, preventing the system from prematurely locking onto an early leader.
* **Exploitation**: The remaining traffic is dynamically allocated to the variants the AI model currently believes perform best.
* **Arms**: Each message variant is an "arm" of the bandit. CleverTap supports up to 10 arms (variants) per campaign.
* **Reward Signal**: The event you define as success. When a user achieves this event after receiving a variant (for example, clicking the notification), that variant receives a "reward" that improves its standing in the model.

# Automated A/B Test Workflow

## Algorithm

Automated A/B Test uses a goal-based MAB algorithm to dynamically allocate traffic across variants. For each variant, CleverTap maintains two counters:

* Total messages sent
* Total goal events achieved (rewards)

These feed a statistical model (Beta distribution) per variant. As more data accumulates, each variant's model becomes more precise, allowing the algorithm to distinguish genuine winners from early flukes.

The algorithm balances two competing objectives simultaneously:

* **Exploration**: A configured percentage of traffic is always distributed equally across all variants, regardless of which is currently winning. This ensures that every variant continues to receive data throughout the campaign.
* **Exploitation**: The remaining traffic is allocated by the AI model, which routes users toward the variant most likely to achieve the configured goal based on current performance data.

The degree of exploration vs. exploitation is controlled by the Exploration % setting configured before publishing the campaign. A higher exploration % means traffic is more evenly distributed across all variants; a lower % means a larger share of traffic is routed by the AI model toward the leading variant.

## Traffic Allocation

For every user who qualifies for the campaign, the system makes a real-time routing decision:

* Exploration bucket (your configured Exploration %)

  The user is assigned uniformly at random to any variant, regardless of current performance. This is the always-testing portion that keeps all variants alive.
* Exploitation bucket (remaining % of traffic) The system samples from each variant's probability model and routes the user to whichever variant it predicts is best at that moment. Variants with consistently higher goal rates get selected here more often.

<Callout icon="📘" theme="info">
  #### Recurring Campaigns

  On the first run of a recurring campaign, all traffic is distributed equally across all variants, no exploitation happens yet. This serves as the initial data the model needs to learn from.

  **Exploration + Exploitation begins from the second run onward.**
</Callout>

### What Counts as Reward?

The reward signal is the goal metric the marketer selects during experiment configuration. The  following are the supported goal metrics:

* Notification Clicked
* Push Impressions

Every time a user who received a specific variant triggers your chosen goal event, the variant reward count increases. This improves the model score and share of exploitation traffic.

### How Variant Weights Update Over Time?

After each campaign run (recurring) or on an ongoing basis (live/trigger), the system:

1. Reads the latest Sent + Goal-Met counts for all variants.
2. Rebuilds each variant's probability model from the updated data.
3. Uses the updated model for all subsequent user routing decisions.

Better-performing variants (higher goal rate per send) progressively capture a larger share of the exploitation traffic. The gap widens as data accumulates.

### When Does Automated A/B Test Declare Winner?

The campaign runs continuously, optimizing in real time; there is no fixed time window or sample size that triggers an automatic stop.

You declare a winner manually from the stats page when you are satisfied. CleverTap supports this decision by indicating the variant with a _Statistically significant_ badge when its probability of being the best performer is 90% or higher. This indicates that the data is reliable enough to act on.

Once you declare a winner, 100% of traffic goes to that variant for the remainder of the campaign.

<Callout icon="📘" theme="info">
  #### Supported Channels

  Currently, Automated A/B Test in campaigns is supported only for Push Notifications.
</Callout>

# Set Up Automated A/B Test Campaign

The setup involved the following six significant steps:

1. Create A/B Test Push Campaign.
2. Define Variants.
3. Configure Experiment Mode and Goal.
4. Set Exploration Rate.
5. Configure Delivery Preferences.
6. Publish Campaign.

## Create A/B Test Push Campaign

To create a Push campaign that uses an automated A/B test mechanism, perform the following steps:

1. Go to _Campaigns_ and click + Campaign.
2. In the What step, select _A/B Test_ as your message type.

## Define Variants

You can create your campaign message manually or use the Fill with AI option. AI fills the title and message of the current variant. For more information about creating a message using AI, refer to [Copywriter Agent](doc:copywriter-agent).

<Image align="center" border={true} caption="Fill with AI" src="https://files.readme.io/0b94fa3aa2f8963ca0345a4f14faee8fd6467815c37e4d71423236eb1ce70884-Fill_with_AI.png" />

To create variants, you can do it manually by clicking ![](https://files.readme.io/64f02a1ec8567dcbfb8a34d1b586ec85a57244dddde72e311c71c30e105c3438-Plus.png)or by clicking **Create More Variants**. AI generates a new variant based on the intent of your existing copy. All non-copy fields are auto-cloned from the source.

<Image align="center" border={true} caption="Create More Variants Using AI" src="https://files.readme.io/1b4395a87cc87bb322dbb9bc959b74ec4ab159fdfed3ed83d0b5225c396a2d40-Create_More_Variants.gif" />

Each variant supports Clear, Delete, and Copy controls, the same behavior as standard A/B. Edits to each variant are independent and persist separately.

<Callout icon="🚧" theme="warn">
  #### Error

  Ensure all mandatory fields are filled before proceeding. If you are creating variants using AI, make sure all liquid tag variables are resolved before moving to the next step.
</Callout>

## Configure Experiment Mode and Goal

Once the variants are set, save them, then click **Done**. The campaign Overview page opens. To configure the Experiment Mode and Goal, perform the following steps:

1. Set the _User distribution_ to **Automated**.
2. Under _Win criteria_, select your goal event from the following options:
   * Notification Clicked
   * Push Impressions

     The Win criteria event is used to compare variant performance and determine the winner.

<Image align="center" border={true} caption="Configure Experiment Mode, Goal and Exploration Size" src="https://files.readme.io/3b4455fdadc0d95c8954295992ee53d4291fceb6f897add748edc224e23a73c3-Experiment_Mode_and_Goal.png" />

## Set Exploration Size

Exploration Size is the percentage of your audience that will always receive all variants equally, even as one variant starts winning.

Percentage of users who receive all variants, split evenly, even after a variant is winning. In the first run, variants are split evenly across the segment.

| Exploration % | Trade-off                                                            |
| ------------- | -------------------------------------------------------------------- |
| Higher        | Slower convergence; better adaptability if audience behavior shifts. |
| Lower         | Faster convergence; less adaptable to mid-campaign shifts.           |

## Configure Delivery Preferences

Define the campaign schedule. An automated A/B Test campaign is available only for campaigns that run more than once:

| Campaign type           | Manual A/B Test Availability | Automated A/B Test Availability        |
| ----------------------- | :--------------------------- | -------------------------------------- |
| Live / trigger-based    | Yes                          | Yes                                    |
| PBS Recurring           | Yes                          | Yes                                    |
| PBS One-Time / Send Now | Yes                          | No. Only Manual A/B Test is supported. |

If you switch delivery from recurring/trigger to one-time after configuring Automated mode, the experiment settings reset to Manual A/B Test.

## Publish Campaign

Review all variants, your goal metric, exploration %, and delivery type, and publish the campaign when ready.

The first run distributes traffic evenly across all variants, regardless of your exploration setting, seeding the learning model. Optimization begins from the second run onward.

# Automated A/B Test Campaign Stats

You can view the campaign stats by selecting the campaign on the campaigns list page, then selecting the _Stats_ tab. For Automated A/B Test campaigns, the stats page includes the following:

* Variant-Level Performance Table
* Goal Conversion Trend Chart
* Statistically Significance
* Declare Winner

## Variant-Level Performance Table

The campaign _Stats_ page displays a variant-level performance table. The table includes:

<Image align="center" border={true} caption="Variant Performance Table" src="https://files.readme.io/acb35266939642bfcaa62d9cd900c987f228f92ce870a106c8ff1201a549d9a9-Variant_Performance_Table.png" />

| Metric         | Description                                                                |
| -------------- | -------------------------------------------------------------------------- |
| Variant Name   | The label for each variant (A-J, up to 10).                                |
| Distribution % | Current traffic allocation percentage for the selected variant.            |
| Sent           | Total messages delivered for the selected variant.                         |
| Impressions    | Total number of times the notification was viewed.                         |
| Clicked        | Total number of clicks on the selected variant                             |
| CTR            | Click-through rate for the selected variant. Calculated as: Clicked / Sent |
| Errors         | Number of delivery errors.                                                 |

An _All Variants_ aggregate row is shown at the top of the table. CSV download is supported for all variant data.

## Goal Conversion Trend Chart

A line chart shows each variant's goal conversion % over time. This visualizes the learning progression; you can see how the Automated A/B Test identifies and converges on the better-performing variants.

Time granularity adjusts based on campaign type: Hourly for Live campaigns, Daily/Weekly/Monthly for PBS campaigns.

## Statistical Significance

When a variant reaches 90% or more probability of being the best performer, CleverTap highlights it with a Statistically Significant badge, shown as a green checkmark next to the variant in the stats table.

## Declare Winner

Automated A/B Test campaigns have no fixed test window; the experiment runs continuously for the campaign lifecycle. You do not need to stop the campaign to get value from the Automated A/B Test. However, you may want to manually declare a winner when:

* One variant's goal conversion rate is clearly and consistently higher than other variants.
* The campaign has run long enough that the distribution trend chart shows stable allocation.
* You want to lock in a variant and stop further exploration.

<Callout icon="📘" theme="info">
  #### Note

  Once you declare a winner, 100% of traffic is routed to the winning variant for the remainder of the campaign. However, the Distribution % in the stats table will be a static value.
</Callout>

<Image align="center" border={true} caption="Winner Declaration" src="https://files.readme.io/eccffab1c1e4b5082f1be0bd532ea791282d4a8ac405d239dadfdbb70282dd10-Declare_Winner.png" />

<Callout icon="📘" theme="info">
  #### Winner Declaration

  Declaring a winner freezes traffic allocation immediately. 100% of subsequent sends go to the winning variant. This action cannot be undone.
</Callout>

# Best Practices

### Wait for the statistical significance badge before acting

An automated A/B Test has no fixed sample size requirement; it runs continuously. But results early in the campaign (especially the first run) are unreliable, as all traffic is distributed equally to seed the model. The statistical significance badge is your reliable signal to act.

### Ideal campaign types for Automated A/B Test

Automated A/B Test compounds its advantage across multiple runs. It works best for:

* Recurring push campaigns (weekly/monthly re-engagement, promotional)
* Always-ON trigger campaigns (onboarding, lifecycle nudges)

Avoid using an automated A/B Test for a campaign you will only send once. It will not have enough runs to optimize meaningfully.

### Choosing Right Goal Event

You must pick based on your campaign objective:

| Goal event           | Use when                                                                     |
| -------------------- | ---------------------------------------------------------------------------- |
| Notification Clicked | You want to drive an action, for example, purchase, sign-up, or feature use. |
| Push Impressions     | Awareness or reach is the primary measure of success.                        |

### Setting Exploration %

* Do not go too low: The system can get stuck on an early leader. If that variant's performance later drops (audience shift, seasonal change), you'll have too little data on others to pivot.
* Do not go too high: Exploitation never gets enough traffic to meaningfully reward the best variant.
