---
title: Compliance with RBI eMandate Regulations
excerpt: >-
  Understand how CleverTap complies with new Reserve Bank of India (RBI)
  eMandate regulations on recurring card payments
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

With the new regulations from RBI coming into effect, payment processing for India-issued cards will get affected. This section provides information about changes done to CleverTap Essentials payment workflows to comply with the new regulations.

# RBI eMandate Regulations

With RBI eMandate regulations coming into effect from October 1, 2021, the processing of card payments for recurring transactions requires an Additional Factor of Authentication (AFA). This mandate aims to protect customers from fraudulent transactions. To enhance customer convenience and ensure customer safety when using recurring payment options, the new guidelines mandate the use of AFA during registration and the first transaction, with relaxation for subsequent transactions of up to ₹15,000.

The card issuer sends a pre-transaction notification to the customer at least 24 hours before the actual debit. At this point, if the amount is higher than Rs. 15000, it would require an additional AFA to pass through. The pre-transaction notification also provides the flexibility to withdraw the mandate. To know more about the new RBI guidelines, refer to the following press releases:

* [Processing of e-mandate on cards for recurring transactions](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=11668\&Mode=0)
* [Reserve Bank of India extends timeline for processing of recurring online transactions](https://www.rbi.org.in/Scripts/BS_PressReleaseDisplay.aspx?prid=51353)

# How does it affect you?

The RBI framework requires that all the existing subscriptions must be re-registered via a one-time process of AFA. We are working with our payment partners to ensure that this transition is as seamless as possible. During this period, we are also ensuring that the services remain unaffected.

If the payment does not go through, we recommend you pay for the pending invoices from the dashboard. For any one-time payments, such as MAU upgrade or Add-on purchase that requires AFA, we immediately take you to the payment partner page.

After successful re-registration, we would request you to approve any future recurring payments through the pre-transaction notification that you receive if the transaction amount is higher than Rs. 15000. This payment may take some time to go through, while the subscribed services remain unaffected.

We have also added a new payment method *eMandate via NetBanking* if you want to switch from card payment. For more information, refer to the [eMandate via NetBanking](https://docs.clevertap.com/docs/emandate-via-netbanking) section.

# Saving Cards

Starting June 30, 2022, per the new RBI guidelines for Indian-issued cards, only card issuers and networks can store credit/debit card details on their servers for transactions processed through payment service providers licensed by RBI. To comply with this regulation, payment aggregators must use network tokens to process payments instead of their actual card details.\
To know more about the new RBI guidelines, refer to [Restriction on storage of actual card data \[i.e. Card-on-File (CoF)\]](https://www.rbi.org.in/Scripts/NotificationUser.aspx?Id=12211).

## How does it affect you?

If you are an existing CleverTap Essentials user and trying to add a new card, you are prompted to provide your consent for saving card details. And, if you are a new user, you are prompted to save card details at the time of registration. This allows the payment aggregators to securely save the card information as a unique token in line with regulations.
