---
title: Loyalty Wallets
excerpt: >-
  Learn how to implement personalized, credit-based loyalty programs and track
  customer rewards, ensuring seamless engagement across your system.
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

The Loyalty Wallet is a digital system that allows businesses to store and reward loyalty points earned by customers for actions such as purchases, referrals, reviews, and so on. Customers can later redeem these points for discounts or exclusive benefits.

CleverTap’s Loyalty Wallets feature provides a flexible, credit-based engagement strategy that allows businesses to seamlessly manage points ledger and distribute wallet points. By leveraging this feature, businesses can enhance user interactions, drive repeat purchases, and build stronger customer relationships.

This document explains how to configure, manage, and utilize the Loyalty Wallet across various websites and mobile platforms.

# Use Cases

The following table highlights key use cases, real-world examples, and the impact of the Loyalty Wallet on both customers and businesses:

| Category                                             | Use Case                                | Example                                                                                                            | Customer Value                                                                      | Business Impact                                                                                          |
| ---------------------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Driving Higher Customer Spending and Retention**   | Awarding Points for Purchases           | A retail brand gives 100 points for every $100 spent or 10% of cashback points when a cashback coupon is redeemed. | Customers feel incentivized to increase order value to earn more points.            | Encourages repeat purchases, boosts customer retention, and increases customer lifetime value (CLV).     |
|                                                      | Bonus Points on First Purchase          | A food delivery app offers 200 bonus points on the first order.                                                    | New users are encouraged to place their first order, reducing acquisition friction. | Lowers cost-per-acquisition (CPA) and improves conversion rates.                                         |
|                                                      | Double Points on Special Occasions      | A fashion e-commerce store gives double points in a Christmas week.                                                | Personalized rewards increase emotional connection with the brand.                  | Drives engagement and encourages seasonal or Christmas-related purchases.                                |
| **Creating a Premium Customer Experience**           | Tiered Rewards System                   | Customers who earn 1,000 points in a year get VIP perks such as free shipping and exclusive discounts.             | Customers aim for a higher status by shopping more frequently.                      | Encourages loyalty program participation, increases purchase frequency, and enhances customer retention. |
|                                                      | Redeeming Points for Exclusive Products | A cosmetics brand allows customers to use 500 points to access limited-edition products.                           | Creates exclusivity and perceived value for loyalty members.                        | Strengthens brand rapport, increases customer engagement with limited products, and reduces churn rates. |
| **Leveraging Social Proof and Community Engagement** | Points for Writing Reviews              | A tech gadget store offers 20 points per product review.                                                           | Encourages customers to share feedback, which enhances brand credibility.           | Generates user-generated content (UGC), boosts SEO rankings, and influences purchase decisions.          |
|                                                      | Referral Bonuses                        | Both the referrer and the new customer earn 100 points on the first successful transaction.                        | Encourages word-of-mouth marketing and attracts new users organically.              | Reduces marketing costs, expands customer base, and increases trust through referrals.                   |
| **Boosting Seasonal and Behavioral Conversions**     | Seasonal Point Multipliers              | A sportswear brand offers triple points during the holiday season.                                                 | Encourages time-sensitive purchases during peak seasons.                            | Increases holiday sales volume, enhances customer engagement, and improves campaign ROI.                 |
|                                                      | Points for Abandoned Cart Recovery      | A grocery delivery service awards 50 points to users who complete their abandoned cart checkout.                   | Provides a low-cost incentive for customers to return and complete transactions.    | Reduces cart abandonment rates, increases conversion rates, and improves revenue per visitor.            |

# Prerequisites

Before using the Wallet feature, check the following:

- You have enabled the Loyalty Wallets feature on your CleverTap account.
- You have the necessary permissions to configure and manage wallet points.
- You have a Wallet already created for your account to integrate the [Wallet APIs](https://developer.clevertap.com/docs/wallet-apis).

# Key Features

The following are the key features of the Loyalty Wallets:

- **Wallet Points**: Loyalty points assigned to customers that can be redeemed for discounts, offers, or in-app purchases. Points can be credited through various sources, such as promotional campaigns, cashback coupons, APIs, and the CleverTap dashboard. Different reward types are supported, such as fixed points, percentage-based points, proportional points, and random points based on their probability factors.
- **Wallet Transactions**: Tracks all wallet-related transactions for a user, including point credits, debits, promises, and expiry. Loyalty points can be credited via promo campaigns, the Wallet Credit API, cashback coupons, or the CleverTap dashboard. Debits occur through the [Wallet Debit API](https://developer.clevertap.com/docs/debitcredit-wallet) when users redeem points or the points expire.
- **Points Expiration**: Wallets can be set up with a point expiration duration, specifying the number of days, months, years, or calendar years after which rewarded points will automatically expire. This approach encourages timely usage and increases engagement.
- **Point Redemption Strategy**: Wallets support the following two redemption strategies:
  - **Expiry FIFO**: Points closest to expiry are redeemed first.
  - **Issuance FIFO**: Points issued earliest are redeemed first. These points redemption strategies control the order in which points are drawn from a user's wallet during redemption.

# Access Loyalty Wallets

The Loyalty Wallets page shows all the wallets created for your account. To view all the created wallets:

1. Go to _Promotions_ from the CleverTap dashboard.
2. Click **Rewards** and select **Loyalty Wallets** from the list.


<Image src="https://files.readme.io/52fa28d7380c4ac8e5ef1c7bd9612edf0d5f33e5d5b866315252917b151752a9-Loyalty_Wallets_Page.png" alt="Access All Wallets" align="center" caption="Access All Wallets" border={true} />


Each wallet has its unique Wallet ID and some predefined values such as Loyalty Points Name, Creation Date, Created by, and so on. For more information, refer to [Create Wallet](doc:create-loyalty-wallet#create-wallet).

# Resources

Refer to the following documents to understand CleverTap's Loyalty Wallet feature:

<div class="two-col-container">
  <div class="link-content">
    <ul>
      <li><a class="links" href="https://docs.clevertap.com/docs/wallet-overview" target="_blank" rel="noopener noreferrer">Wallet Overview</a></li>
      <li><a class="links" href="https://docs.clevertap.com/docs/wallet-operations" target="_blank" rel="noopener noreferrer">Wallet Operations</a></li>
    </ul>
  </div>

  <div class="link-content">
    <ul>
      <li><a class="links" href="https://docs.clevertap.com/docs/create-loyalty-wallet" target="_blank" rel="noopener noreferrer">Create Loyalty Wallet</a></li>
      <li><a class="links" href="https://docs.clevertap.com/docs/use-loyalty-wallets-in-campaigns" target="_blank" rel="noopener noreferrer">Use Loyalty wallets in Campaigns</a></li>
    </ul>
  </div>
</div>

<br />
