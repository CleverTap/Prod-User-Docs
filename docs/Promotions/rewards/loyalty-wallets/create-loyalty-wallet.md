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

The loyalty wallet tracks all reward points that can be used for discounts, offers, and in-app purchases. This document provides an overview of wallet creation and explains each configurable field with examples to help you set up your wallet accurately.

# Create Wallet

To create a wallet:

1. Go to _Promotions_ from the CleverTap dashboard.
2. Click **Rewards** and select **Loyalty Wallets** from the list.
3. Click the **Create Loyalty Wallet**.
4. Enter a unique name for the loyalty wallet. For example, _CleverTap Coins_. Once created, the wallet name cannot be changed.
5. Enter the applicable currency or points system of the loyalty points associated with the wallet. For example, _Coins_.
6. Define the points expiry rule for points issued through the wallet. You can select the expiry type from the following options:

   1. **Never**: Points will never expire.
   2. **After**: Points expire after a specific duration. You can specify the number of _days_, _months_, or _years_, after which points must expire.
   3. **After X Calendar Years**: Points expire at the end of the Xth calendar year following issuance. For more information on how points expiry is calculated, refer to [Points Expiry Calculation](doc:create-loyalty-wallet#points-expiry-calculations).

   <Callout icon="📘" theme="info">
     #### Expiry Rule Setting

     The expiry rule can only be set once at the time of wallet creation and cannot be changed later. If no expiry rule is set, points never expire.
   </Callout>
7. **Point Consumption Strategy**: Select how points are consumed from a user's wallet when they redeem. This setting applies to all future redemption events for this wallet. Select from the following two strategies:

   1. **Points with earliest expiry are consumed first**: Select this expiry option when you want the points with the earliest expiry date to be consumed first during redemption, regardless of when the points were issued.
   2. **Points with earliest issuance are consumed first**: Select this expiry option when you want the points with the earliest issuance date to be consumed first during redemption, regardless of expiry date.

   For a detailed explanation of how each strategy works across different redemption scenarios, refer to [Point Consumption Strategies](doc:create-loyalty-wallet#points-consumption-strategies).
8. **Rounding Rules**: Determine how point values are rounded when calculated. You can round point values to 0, 1, 2, or 3 decimal places. Select from the following rounding types:
   1. **Round up**: Rounds the value up to the nearest specified decimal place when the next digit is 5 or greater. For example, if the calculated points are 30.2789 and rounding is set to 2 decimal places, the third decimal digit (8) is greater than 5, so the points credited will be 30.28.
   2. **Round down**: Rounds the value down to the nearest specified decimal place, discarding any digits beyond the specified limit. For example, if the calculated points are 12.783 and rounding is set to 2 decimal places, the points credited will be 12.78.
9. Click **Create**. The wallet configuration is saved, and the wallet is activated immediately.

<Image align="center" border={true} caption="Create a Wallet" src="https://files.readme.io/a40274fb59e8f2439ab132c6fa48eaf92b5bbfd6e8575e89dd169b5cb358d8c3-image.png" />

<Callout icon="📘" theme="info">
  #### Updating Points Consmption Strategy

  The points consumption strategy can only be configured when creating a new wallet. It cannot be changed after the wallet is created.

  For example, if you create a wallet with the issuance FIFO strategy, all points issued to that wallet will be consumed in the order they were issued. If you later want to switch to Expiry FIFO, you cannot update the existing wallet. To update this, you need to create a new wallet with the desired strategy. Points already issued to the original wallet are unaffected and continue to follow the strategy set at the time that wallet was created.
</Callout>

# Points Expiry Calculations

The following table explains how points expiry is calculated for each expiry unit:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Expiry Unit
      </th>

      <th>
        How Expiry is Calculated
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Days
      </td>

      <td>
        Points expire exactly X days after the timestamp of the credit transaction.
      </td>

      <td>
        Points issued on January 10, 2026, at 12:59 PM with a 30-day expiry will expire on February 9, 2026, at 12:59 PM.
      </td>
    </tr>

    <tr>
      <td>
        Months
      </td>

      <td>
        Points expire X calendar months after the credit transaction timestamp. The system adds X to the month value and preserves the same day-of-month. If the resulting date does not exist in the target month, the last valid day of that month is used instead.
      </td>

      <td>
        **When the target date exists**: Points issued on January 10, 2026, at 12:59 PM with a 1-month expiry, expire on February 10, 2026, at 12:59 PM.  
        **When the target date does not exist**: Points issued on January 31, 2026, at 11:45 AM with a 1-month expiry and February 31 does not exist, the points expire on February 28, 2026, at 11:45 AM (last valid day of February).
      </td>
    </tr>

    <tr>
      <td>
        Years
      </td>

      <td>
        Points expire X calendar years after the credit transaction timestamp. The system adds X to the year value and preserves the same month and day. If the resulting date does not exist (e.g., February 29 in a non-leap year), the last valid day of that month is used instead.
      </td>

      <td>
        **Standard case**: Points issued on March 10, 2025, at 10:00 AM with a 2-year expiry, expire on March 10, 2027, at 10:00 AM.  
        **Leap year edge case**: Points issued on February 29, 2024, at 09:00 AM with a 1-year expiry, and February 29, 2025, do not exist; the points expire on February 28, 2025, at 09:00 AM.
      </td>
    </tr>

    <tr>
      <td>
        Calendar Years
      </td>

      <td>
        Points expire at the end of the Xth calendar year following the credit transaction date, regardless of when the points were credited.
      </td>

      <td>
        Points credited on May 15, 2025, with a 1-calendar-year expiry expire on December 31, 2025, and not on May 14, 2025.
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  #### Timestamp and Expiry Behavior

  * For all expiry units, the exact issuance timestamp (HH:MM:SS) is preserved when calculating the expiry date. For example, points issued at 12:59 PM expire at 12:59 PM on the expiry date not at midnight (12:00 AM).
  * All timestamps are stored and evaluated in UTC. Ensure your credit transactions are timestamped in UTC to avoid expiry calculation discrepancies.
  * Existing wallets and previously issued points are not affected. All previously issued points continue to follow the expiry rule that was active at the time they were credited.
</Callout>

# Point Consumption Strategies

When a user redeems points from their wallet, CleverTap consumes points sequentially across eligible credit records until the requested redemption amount is fulfilled. Only credit records with a remaining balance greater than zero and an expiry date in the future are considered. If a credit record has insufficient points to cover the full redemption, its entire remaining balance is consumed, and the system moves to the next eligible record.

The order in which credit records are consumed depends on the following two configured strategies for the wallet:

## Points with Earliest Expiry are Consumed First (Expiry FIFO)

Points closest to their expiry date are redeemed first, regardless of when they were issued. This minimizes expiry liability by consuming the most at-risk points before they lapse.

For example, a user has three credit records in their wallet:

* **Record A**: 100 points, expires March 31, 2026
* **Record B**: 200 points, expires January 31, 2026
* **Record C**: 150 points, expires May 31, 2026

The user redeems 250 points. With Expiry FIFO, the system consumes Record B first (the earliest expiry of 200 points), then takes the remaining 50 points from Record A (the next earliest expiry). Record C is untouched.

### Tie-breaking with Same Expiry Date

If two credit records share the same expiry date, the record with the earlier issuance timestamp is consumed first.

For example, a user has two credit records in their wallet:

* **Record A**: 100 points, expires June 25, issued January 10, 2026
* **Record B**: 50 points, expires June 25, issued January 12, 2026

Both records expire on the same date. In this case, the system consumes Record A first because it has the earlier issuance timestamp.

## Points with Earliest Issuance are Consumed First (Issuance FIFO)

Points earned earliest are redeemed first, regardless of their expiry date. This follows a chronological first-in, first-out order based on when the points were credited.

For example, a user has three credit records in their wallet:

* **Record A**: 100 points, issued January 5, expires December 31
* **Record B**: 200 points, issued January 10, expires March 31
* **Record C**: 150 points, issued January 20, expires June 30

The user redeems 250 points. With Issuance FIFO, the system consumes Record A first (the earliest issuance of 100 points), then consumes the remaining 150 points from Record B (the next earliest issuance). Record C is untouched, even though Record B expires sooner than Record C.

### Tie-breaking with Same Issuance Timestamp

If two credit records share the same issuance timestamp, the record with the earlier expiry date is consumed first.

For example, a user has two credit records in their wallet:

* **Record A**: 100 points, issued January 10, expires June 20
* **Record B**: 50 points, issued January 10, expires June 25

Both records were issued on the same date. In this case, the system consumes Record A first because it has the earlier expiry date.

<Callout icon="📘" theme="info">
  #### Identical Timestamps

  If two transactions share the same expiry date or issuance timestamp, the system resolves the tie using the order in which the transactions were recorded in the database, ensuring consistent and predictable redemption behavior.
</Callout>
