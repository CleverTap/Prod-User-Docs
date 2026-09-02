---
title: System-Triggered Alert Emails
excerpt: Learn about the system-triggered alert emails sent by the CleverTap platform.
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

This document lists all system-triggered alert emails automatically sent by the CleverTap platform. Each email is categorized by the following:

* Email Sender
* Triggering Scenario

# Email Categorization by Sender

System-generated emails from the CleverTap platform are triggered by specific senders, each associated with distinct events or operational contexts:

* [Account Notification Email](doc:system-triggered-alert-emails#account-notification-email)
* [Billing Alert Email](doc:system-triggered-alert-emails#billing-alert-email)
* [Other System Alerts](doc:system-triggered-alert-emails#other-system-alerts)

## Account Notification Email

These are automated alerts triggered by platform events related to account setup, plan updates, or billing configuration.

| Trigger Scenario            | Email Subject (Example)        | Feature |
| --------------------------- | ------------------------------ | ------- |
| Add-Ons Modified            | "Add-Ons Updated Notification" | Add-Ons |
| Payment Information Updated | "Payment Information Updated"  | Billing |
| Primary Plan Updated        | "Primary Plan Updated"         | Billing |
| Billing Information Updated | "Billing Information Updated"  | Billing |
| Converted to Paid Account   | "Converted to Paid Account"    | Billing |

**Feature Mapping**

* **Billing**: Payment Information Updates, Primary Plan Changes, Billing Information Updates, Conversion to Paid Account
* **Add-Ons**: Add-On Activation, Add-On Modifications

## Billing Alert Email

These emails are triggered by consumption-based events, such as Monthly Active User (MAU) threshold alerts and usage overages.

| Trigger Scenario | Email Subject (Example)       | Feature     |
| ---------------- | ----------------------------- | ----------- |
| Overage Report   | "Monthly Overage Report"      | Consumption |
| 80% MAU Usage    | "MAU Usage at 80% Alert"      | Consumption |
| 100% MAU Usage   | "MAU Usage at 100% Alert"     | Consumption |
| > 100% MAU Usage | "MAU Usage Beyond 100% Alert" | Consumption |
| Capacity Breach  | "509 Capacity Usage Alert"    | Consumption |

**Feature Mapping**

* **Consumption**: MAU Usage Alerts (80%, 100%, >100%), Monthly Overage Reports, 509 Usage Alerts

## Other System Alerts

These are non-standard alerts triggered through external partner submissions, internal test alerts, and manually triggered messages.

| Sender Type          | Email Subject (Example)               | Trigger Scenario |
| -------------------- | ------------------------------------- | ---------------- |
| External (Partner)   | "Contact Sales"                       | External Inquiry |
| Internal Test Sender | "\[Test] Subscription Renewal Notice" | QA/Test Email    |
| Internal Test Sender | "\[Test] Critical Action Required"    | QA/Test Email    |
