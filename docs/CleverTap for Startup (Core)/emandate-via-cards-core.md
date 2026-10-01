---
title: eMandate via Cards (Core)
excerpt: >-
  Understand how to set up eMandate using cards that comply with the RBI
  guidelines for recurring payments.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

**eMandate** allows businesses to automate recurring payments directly from a registered account, eliminating the need for manual intervention. Introduced by the RBI and NPCI, it streamlines transactions while ensuring regulatory compliance.

This document provides the steps to set up an eMandate using cards within CleverTap. By following this guide, you can set up eMandate using cards within CleverTap and enjoy seamless, automated recurring payments that comply with RBI regulations.

## Prerequisites

Before setting up an eMandate using cards, ensure you have the following:

* A registered CleverTap account with _Admin_ access.
* A valid Credit or Debit card with details including Card Number, Expiry Date, and CVV.

## Set Up eMandate Using Cards

CleverTap allows you to set up eMandate using cards from the Dashboard. This involves the following steps:

1. Log in to your CleverTap dashboard.
2. Navigate to _Organization_ > _Billing_ > _Payment Methods_.
3. Click **+ Payment Method**.


<Image src="https://files.readme.io/e963c5720f733ffff8fa2a078db97c803ac8c648cdbbaad39f5547c57ed91ff2-Payment_Method.png" alt="Add Payment Method" align="center" border={true} />


4. Select **Credit or Debit Card** as the payment method.
5. Enter the following card details:
   * _Card Number_
   * _Expiry Date_
   * _CVV (Card Verification Value)_
6. (Optional) Select the _Save card for future payment_ checkbox if you want to retain the card details for future transactions.
7. Click **Add**.


<Image src="https://files.readme.io/bb979bf60591663f203454393909946c803d12ed53a9dfc14e9d188440561e9d-Add_Payment_Method.png" alt="Add Card Details" align="center" width="80% " border={true} />


8. Complete the one-time authorization process. This could be done using:
   * OTP (One-Time Password) sent by your issuing bank.
   * Secure PIN (if applicable).


<Image src="https://files.readme.io/5446c531f157dc323cf6deceba429c6494288a9ebc70ebeece41e2fce85407bf-OTP.png" alt="Authenticate via OTP" align="center" width="80% " border={true} />


Your eMandate is registered upon successful verification, and a confirmation email will be sent from the issuing bank.

<Callout icon="📘" theme="info">
  ### Important

  While adding the card for payment, please note that:

  * The authentication process varies depending on your bank. This process may take up to 1-2 banking days.
  * Some banks may charge a nominal fee (₹1 or ₹2) for eMandate authorization, which will be refunded within 5-7 banking days.
  * CleverTap does not charge for eMandate registrations or transactions. However, banks may charge penalties, in case a transaction fails due to insufficient funds.
  * Ensure that the card is active and not nearing its expiry date.
</Callout>

# Recurring Payment Processing

Once the eMandate is activated, future payments will be processed automatically based on the billing cycle. Depending on your bank's processing time, payments may be deducted in real time or within 1-2 banking days.

# Troubleshooting

While setting up or managing eMandates, if you encounter issues, use the following solutions:

## Authorization Failure

If the card registration fails:

* Verify that the card details are correct.
* Ensure that the OTP or 3D Secure PIN is entered correctly.
* Retry the registration process or use a different card.

## Payment Failure

If a payment fails due to insufficient funds or technical issues:

* Re-enter the card details or use a different payment method.
* Ensure there are sufficient funds in the account for transactions.

<Callout icon="📘" theme="info">
  ### Removing a Card

  If a card is removed, all future payments will require manual intervention, and the service may be paused until a new payment method is added.
</Callout>

# Frequently Asked Questions

### Q. What happens if my eMandate setup fails?

A. You will be notified via email. Retry the setup process using the same or a different card.

### Q. How long does it take to set up an eMandate?

A. While the authorization is typically instant, in some cases, it can take up to 1-2 banking days depending on your bank.

### Q. Is there a charge for setting up eMandate?

A. No, CleverTap does not charge for setting up eMandate. However, banks may apply nominal charges for failed transactions.
