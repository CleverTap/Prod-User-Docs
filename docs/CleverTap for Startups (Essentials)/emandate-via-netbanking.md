---
title: eMandate via NetBanking
excerpt: Learn about CleverTap's eMandate via Netbanking (eNACH) payment method.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

eMandate via NetBanking (eNACH) helps schedule automatic transfers from your bank account for recurring payments, providing flexibility for INR payments. You must complete a one-time authentication with your NetBanking, Debit Card, or Aadhaar details. After the eMandate is set up, all future payments are processed automatically without intervention.

You can select *eMandate via NetBanking* as your payment method when setting up a CleverTap Essentials account or at a later stage. This document provides the steps to set up and manage an eMandate using Netbanking from the CleverTap dashboard.

# Prerequisites

Before setting up an eMandate, ensure you have the following:

* A registered CleverTap account with Admin access.
* A valid bank account with the following details:
  * Account holder name
  * Phone number
  * Bank account number
  * Bank name
  * Account type
  * Branch IFSC code

# Set Up eMandate via Netbanking

> 📘 Important
>
> Before completing the eMandate setup, please take note of the following key details to ensure a smooth registration and payment process:
>
> * The authorization process varies by bank and may take up to 1-2 banking days.
> * Some banks may charge a nominal amount of ₹1 or ₹2, which will be refunded within 5-7 banking days.
> * CleverTap does not charge for eMandate registrations or transactions. However, banks may charge penalties, in case a transaction fails due to insufficient funds.

You can set up the eMandate from the Dashboard. The setup process involves the following steps:

1. Log in to your CleverTap dashboard.
2. Navigate to *Organization* > *Billing* > *Payment Methods*.
3. Click **+ Payment Method**.
4. Enter the required bank details and click **Add**.

<Image alt="Add eMandate via Netbanking" align="center" border={true} src="https://files.readme.io/157cdb9aa60b065ae7b8e53c1a050eeac8122d73576630e7d72f021220e63f3a-2024-10-04_15-25-59_1.gif">
  Add eMandate via Netbanking
</Image>

5. Click **Proceed** and complete the one-time authorization via OTP, Secure PIN, or other methods provided by your bank.

<Image alt="Authenticate for Netbanking" align="center" border={true} src="https://files.readme.io/32d7d9465a445fbae4fc825f5c4d99f71efbf81437b95a5c0aeb387155789d53-NPCI_Mandate_Authorization.png">
  Authenticate for Netbanking
</Image>

After successful verification, your eMandate is set up, and the issuing bank will confirm via email.

# Manage eMandate

You can easily manage your eMandates through the CleverTap dashboard. You can remove eMandates or set a default payment method.

## Remove eMandate

You can remove an eMandate from the CleverTap dashboard. To remove an eMandate from the CleverTap dashboard, click the **Remove** button next to the eMandate and confirm the removal.

<Image alt="Remove an eMandate" align="center" border={true} src="https://files.readme.io/5c4f3cbda31a2bbbc1e6c0edbcabbd50413720d672818e173300c32f41896177-2024-10-04_13-10-56_1.gif">
  Remove an eMandate
</Image>

## Make Default

You can make an eMandate default from the CleverTap dashboard. To make an eMandate the default payment method, click **Make Default** and confirm your selection.

<Image alt="Make an eMandate as Default" align="center" border={true} src="https://files.readme.io/6632861f5238d2286ffef71e55e7fefb206cc04ba5ad08ee919fe2a10044403b-2024-10-04_13-11-21_1.gif">
  Make an eMandate as Default
</Image>

## Bank Authorization Time

The following table lists the Turn Around Time (TAT) for authorization of different banks:

| Bank Name                    | Turn Around Time for Authorization |
| :--------------------------- | :--------------------------------- |
| All Banks via NPCI           | Real-time                          |
| ICICI and Axis               | Real-time                          |
| HDFC and State Bank of India | T + 1 working days                 |

## Bank Payment Processing Time

Once registration is complete, CleverTap automatically debits the billing amount from the registered bank account.

The following table provides information about the Turn-around-time (TAT) for different banks:

| Bank Name           | Turn Around Time for Payment Processing |
| :------------------ | :-------------------------------------- |
| ICICI               | Real-time                               |
| State Bank of India | T + 1 working days                      |
| Other Banks         | Same day                                |

# Troubleshooting

While setting up or managing eMandates, if you encounter issues, use the following solutions: 

## Authorization Failure

If the eMandate registration fails:

* Verify that the bank details are correct.
* Retry the registration process or opt for an alternative payment method, such as a Credit or Debit Card.

## Payment Failure

If a payment fails due to insufficient funds or technical issues, CleverTap notifies you immediately. To resolve the payment failure issue:

* Ensure there are sufficient funds in the account for transactions.
* Re-enter the bank account details or use a different payment method, such as a Credit or Debit Card.

# Frequently Asked Questions

### Q. What happens if my eMandate setup fails?

A. You will be notified via email. Retry the setup process using the same or a different payment method, such as a Credit or Debit card.

### Q. How long does it take to set up an eMandate?

A. While the authorization is typically instant, in some cases, it can take up to 1-2 banking days, depending on your bank.

### Q. Is there a charge for setting up eMandate?

A. No, CleverTap does not charge for setting up eMandate. However, banks may apply nominal charges for failed transactions.
