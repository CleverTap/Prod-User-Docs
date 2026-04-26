---
title: Loyalty Tiers
excerpt: >-
  Learn how to set up loyalty tiers that automatically group users by activity,
  reward them at each level, and regularly re-evaluate eligibility using
  configurable expiry and downgrade rules.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Loyalty Tiers allow you to segment users into hierarchical levels, also known as tiers (Silver, Gold, Platinum), based on their engagement, spend, or custom-defined criteria. As users progress through tiers, they can unblock differentiated benefits, rewards, and experiences, driving higher retention, frequency, and lifetime value for your business.

Common examples of tiers include airline loyalty tiers (Silver, Gold, Platinum), e-commerce membership levels (Bronze, Silver, Gold), and so on. Loyalty Tiers work seamlessly with Rewards such as [Loyalty Wallets](doc:loyalty-wallets), [Coupons](doc:coupons), [Partner Vouchers](doc:partner-vouchers), and [Custom Rewards](doc:custom-rewards) within CleverTap Promotions.

# Key Capabilities

Loyalty Tiers help you build long-term user relationships by recognizing users who engage consistently, through purchases, app activity, or points earned, and rewarding them with better benefits as they progress. By organizing users into tiers and managing their progression, Loyalty Tiers enable you to create structured incentives that encourage continued engagement and loyalty.

Loyalty Tiers manage the full lifecycle of user progression, including how users upgrade to higher tiers, how tiers are renewed or re-evaluated over time, how users are downgraded when they no longer qualify, what rewards or benefits apply at each tier, and when tiers expire.

With Loyalty Tiers, you can:

* Enable users to progress through tier levels based on engagement, transactions, or points earned
* Define clear rules for tier upgrades, renewals, and downgrades
* Reward users differently at each tier to encourage continued engagement
* Control how long tiers remain valid using flexible expiry and re-evaluation rules
* Periodically re-evaluate user eligibility to ensure tiers reflect recent activity

<Callout icon="📘" theme="info">
  #### Note

  A Loyalty Tier system must include, at least one tier upgrade parameter and at least one higher tier (beyond the base tier).
</Callout>

# How Tiers Work After Publishing?

Once published, CleverTap automatically manages all the following tier transitions based on your configuration:

* **Upgrades**: Users are upgraded in real time as soon as they meet the qualification criteria for a higher tier. CleverTap evaluates every qualifying event as it occurs and upgrades the user immediately when the threshold is reached.
* **Renewals and Downgrades**: At the end of each tier's validity period, CleverTap runs a scheduled evaluation. If the user meets the criteria for their current tier, the tier is renewed. If not, the [Downgrade Outcome](doc:create-loyalty-tiers#downgrade-outcome) policy is applied.
* **User Property Update**: CleverTap automatically updates a user property with the user's current tier name and tier ID whenever the user's tier status changes. You can use this property in campaign segmentation to target users based on their current tier without manual updates.
* **Tier System Events**: CleverTap raises the following non-billed system events on every tier status change. You can use these events in Campaigns, Journeys, and Segments to trigger follow-up engagement.
