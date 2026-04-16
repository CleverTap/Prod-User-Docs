---
title: Wallet Overview
excerpt: >-
  Learn how to monitor and analyze your loyalty wallet’s performance and
  transaction details.
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

The _Overview_ tab provides a comprehensive summary of a wallet’s points distribution and configuration details. It allows you to track issued, redeemed, expired, and removed points and make necessary adjustments, such as adjusting the points for a specific user, filtering the points balance for a duration, and editing a loyalty wallet or points names.

To view the _Overview_ of a wallet:

1. Go to _Promotions_ from the CleverTap dashboard.
2. Click **Rewards** and select **Loyalty Wallets** from the dropdown menu.
3. Click the desired wallet and view the following details:

<Image border={true} src="https://files.readme.io/4702391dd54c7c81f6de0c46ca93e2bc5189b7541327ed9f2ef7012ab29d5b27-Wallet_Overview.png" className="border" /> Wallet Overview

## Summary

The _Summary_ section provides the current status of all the loyalty wallet points in the following way:

### Key Metrics

Track the real-time status of the loyalty points available for users and those scheduled for future credit with the following key metrics:

* **Active Points:** Total points currently available for use.
* **Promised Points:** Points earned by customers but are yet to be credited to the active points bucket based on the points activation date.

### Points Breakdown

Analyze the distribution of loyalty points, including issued, expired, redeemed, and manually adjusted points in the following ways:

* **Issued Points:** Total points awarded to users within the selected date range through various sources, such as:
  * **Cashback Coupon**: Points credited when a cashback coupon is redeemed. For example, a user redeems a coupon called _SAVE50_ and earns 50 points.
  * **Promo Campaigns**: Points credited via marketing promotions. For example, a festival sale campaign credits 100 points.
  * **Wallet Credit API**: Points credited via the Credit Wallet API. For example, an automated credit of 30 points triggered by a system workflow or a manual credit of 50 points by an admin using the API for customer support resolution.
  * **Manual Credit**: Points credited manually via the CleverTap dashboard. For example, an Admin credits 20 points to an irate customer through the CleverTap dashboard.
* **Expired Points:** Total points that were unused within their validity period.
* **Redeemed Points:** Total points debited via the Debit API.
* **Removed Points:** Points deducted or revoked due to manual adjustments made through the CleverTap Wallet dashboard.

> 📘 Ledger Balance Calculation
>
> The ledger balance is calculated with the following formula:  
> **Active Points** = Issued Points – (Redeemed Points + Removed Points + Expired Points)
>
> Where,  
> **Issued Points** = Points Rewarded via Campaign + Points Rewarded via API + Points Rewarded Manually via Dashboard

## Setup Details Section

This section provides the following information about the wallet configuration:

* **Created On:** Date when the loyalty wallet was created.
* **Created By:** Email of the user who created the wallet.
* **Loyalty Wallet Name:** The name of the wallet.
* **Loyalty Points Name:** The name of the points used in the wallet.
* **Wallet ID:** Unique identifier for the loyalty wallet.
* **Rounding Rules:** Displays the rounding rule applied to points.
* **Points Expiry:** Indicates whether points expire and the applicable expiry policy.

<Image border={true} src="https://files.readme.io/1b39c2a0341e367aa00857137f05467ee93a0c95fc12516b0f1bc5b36ca5f746-Setup_Details.png" className="border" />  Setup Details

### Date Filter

You can adjust the date range using the date picker to analyze the distribution of points within a specific period.

<Image border={true} src="https://files.readme.io/c4b6551f0a2665e0e3aec60ca9c181641b3cd105b12ac9c902fe174a2d876753-Calendar_Widget.png" className="border" />  Calendar Widget

### Edit

Clicking _Edit_ allows you to modify wallet names and points.

<Image border={true} src="https://files.readme.io/7cfe24d02f41493079a13b689e05654d42fcb03c5de41e2802798260c77cec4f-Edit_Loyalty_Wallet.gif" className="border" />  Edit Loyalty Wallet and Points Name

# Transactions

The _Transactions_ page allows you to view and filter loyalty wallet transactions based on different parameters, such as transaction type, source, and points range.

To view the list of all recorded transactions:

1. Go to _Loyalty Wallets_ and select the desired wallet.
2. Click the **Transactions** tab. The following parameters of the transactions appear:

<Image border={true} src="https://files.readme.io/7ca194070e2bb934aca1e64c92678dfb76bb9734aa5697dc71acdff97d18f0fb-image.png" className="border" />  View Wallet Transactions

> 📘 Transaction Display Limit
>
> The dashboard displays only the latest 500 transactions. However, if you are looking for a specific transaction beyond this limit, you can use the [Search](doc:wallet-operations#search) feature.

## Transactions Table

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Identity
      </td>

      <td>
        A unique identifier representing the user associated with the transaction. The identity value is clickable and redirects to the user details page in a new window, allowing quick access to user-specific information.
      </td>
    </tr>

    <tr>
      <td>
        Timestamp
      </td>

      <td>
        The date and time when the transaction was recorded.
      </td>
    </tr>

    <tr>
      <td>
        Source
      </td>

      <td>
        <p>The origin of the transaction. The following are valid sources:</p>

        <ul>
          <li>API</li>
          <li>Promo Campaigns</li>
          <li>Manual</li>
          <li>Cashback Coupon</li>
          <li>System</li>
        </ul>

        For more information, refer to [Source](doc:wallet-operations#source).
      </td>
    </tr>

    <tr>
      <td>
        Txn ID
      </td>

      <td>
        A unique transaction identifier for the wallet transaction.
      </td>
    </tr>

    <tr>
      <td>
        Description
      </td>

      <td>
        <p>A brief note about the transaction. The transaction descriptions are determined based on the following transaction types:</p>

        <ul>
          <li>**API Transactions (Credit/Debit)**: The description is determined by user input in the API payload.</li>
          <li>**Manual Adjustments (Dashboard)**: The description is set by the user while adjusting points.</li>
          <li>**System-Generated Transactions**: The following standard descriptions are automatically applied based on the transaction types:</li>

          <ul>
            <li>*Points earned from campaign*: Applied to credit transactions originating from promotional campaigns.</li>
            <li>*Points earned for redeeming \{Coupon Code} coupon*: Applied when users redeem cashback coupons.</li>
            <li>*Expired points*: Applied when loyalty points have expired.</li>
          </ul>
        </ul>
      </td>
    </tr>

    <tr>
      <td>
        Txn Type
      </td>

      <td>
        The transaction type, such as Credit, Debit, Scheduled, or Expired.
      </td>
    </tr>

    <tr>
      <td>
        Points
      </td>

      <td>
        The value credited, debited, or expired in the transaction.
      </td>
    </tr>
  </tbody>
</Table>

<br />
