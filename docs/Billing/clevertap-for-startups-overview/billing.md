---
title: Billing
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

This section provides various information about billing questions for CleverTap for Startups.

## **Billing for Monthly Active Users**

This section covers various CleverTap for Startups billing information regarding monthly active users (MAUs).

### What is a billable MAU?

A MAU is an end-user who has recorded one or more events in a calendar month. When tracking mobile apps and websites, a user who is active on both devices with the same identity token will be counted as one MAU. An organization is charged based on the total number of MAUs across all projects which means that if a user performs a qualifying event in multiple projects, they are counted once per project. Events excluded under the MAU calculation are Notification Sent, Push Impression, and Webhook Delivered.

Billable MAU is a combination of MAUs and data points. A data point is an event, event property, or profile property update; a usage measure associated with MAU. A total of 2,000 data points are allowed per MAU.

### How do you calculate billable MAU?

The total bill amount per month is based on whichever is highest, such as: 

* MAU tier limit as defined on your plan.
* Actual MAU usage.
* Processed MAU which is the total data points used divided by allowed data points per MAU (2,000 data points). In most cases, users perform fewer than 2,000 data points per month.

### Data Upload Charges

If data is uploaded to amend a user profile or user activity history, the number of data points uploaded counts toward the total number of data points allocated for the month. The number of data points allocated for each calendar month is equal to the MAU tier in your pricing agreement times 2,000.

### Data Retention Policy

The default data retention policy for the CleverTap for Startups plan is one year and this cannot be changed.

## **Plan Changes and Cancelation**

As a paid subscriber, you can make changes to your plan.

### MAU Tier Upgrade

You can upgrade to a higher MAU tier. To upgrade:

1. Navigate to *Organization* > *My Plan* > *Change Plan*. 
2. Choose the new MAU tier. 
3. Click **Save Changes** to confirm the upgrade.

The upgrade will be effective right away and a prorated charge for the current month will occur, including charges for any paid add-ons. A confirmation with the payment details and invoice will be sent to your registered billing address. 

> 📘 Upgrade Change
>
> The upgrade is effective only upon successful payment. All paid add-ons will also be recalculated as per the new base rate when upgrading the MAU tier.

To upgrade to a MAU tier of more than 100,000 users, we recommend upgrading to the CleverTap Enterprise plan to better suit your organization’s growing scale and needs. For more information on the plan and pricing, please reach out to our team from the CleverTap dashboard.

### MAU Tier Downgrade 

To downgrade to a lower MAU tier, request a plan update from the My Plan section of your account. Your request will be reviewed by our team and we will notify you with a confirmation of the downgrade in a timely manner. 

> 📘 Billing Cycle
>
> MAU tier downgrades are effective starting from the next billing cycle date.

### Add-ons Inclusion

Free add-ons are additional features that are available without any extra charge. Paid add-ons are additional features that are available to an account at an extra charge. To include an add-on in your plan, navigate to *Organization* > *Billing* > *My Plan* > *Change Plan*, then choose the required features you want to add. If you have included a paid add-in in your plan, your card on file will be charged right away and an invoice will be generated for this transaction.

### Add-ons Removal

To remove an add-on, navigate to *Organization* > *Billing* > *My Plan* > *Change Plan*, then choose the add-ons you want to remove. All add-on removals take effect from the next billing cycle, and you can continue using the add-on until then. If you change your mind, you can cancel the removal before the given billing date and continue to access the add-on.

### Subscription Cancelation

To cancel your subscription, submit a cancelation request from the dashboard by navigating to *Organization* > *Billing* > *My Plan* > *Cancel Plan*. Once the request is received, our billing team will initiate the cancelation process. You will receive an email once the cancelation is processed. 

## **Payments and Overages**

For the CleverTap for Startups plan, CleverTap accepts all major credit cards (e.g., Visa, Mastercard, American Express, Discover, Diner's Club, and JCB). 

### Update Billing Information and Card Details

If you are an organization member with billing permissions (Admins), you can update the billing and payment information by clicking on Organization on the left navigation menu of the dashboard. Then, click on Card details to update the required details.

> 📘 Payment Method Change
>
> You cannot change the payment method or currency for billing.

### Payment Failure

In case your payment has failed, we will notify you right away. You will be required to update your payment details within a grace period of 10 days. Incoming data, data exports, and dashboard access will not be affected during this period. In case the payment details are not updated within the grace period, your account access will be locked.

If you do not clear all outstanding payments within 10 days of the account lock, your account will be suspended. After account suspension, you will no longer be able to retrieve your account and all data will be deleted.

### Exceeding Plan Limits

If you exceed your plan limits, you can upgrade to a higher MAU tier before the end of the billing period to avoid overage charges. For more information on how overages are calculated, refer to [overage calculations](https://docs.clevertap.com/docs/billing#section-overages-calculations).

### Overages Calculations

An overage is charged for each additional billable MAU over the plan’s MAU tier limit. A total of 2,000 data points are allowed per MAU. Any excess data points over the specified limit will be counted as an additional MAU. 

For every additional 100 MAUs, an overage is charged at 1.2x of the plan’s base price (view calculation below). All paid add-ons are charged overages at 1.2x of the plan price.

Example\
Below is an example of overage charges for a subscription with a MAU tier limit up to 20,000, including with add-ons:

<Table align={["left","left","left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        MAU Limit
      </th>

      <th>
        Billable MAU
      </th>

      <th>
        Base Price
      </th>

      <th>
        Add-on Price
      </th>

      <th>
        Overage for MAU
      </th>

      <th>
        Overage for Add-on
      </th>

      <th>
        Billable Amount*
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Up to 20,000
      </td>

      <td>
        \<20,000 without add-ons
      </td>

      <td>
        $200
      </td>

      <td>
        $0
      </td>

      <td>
        $0
      </td>

      <td>
        $0
      </td>

      <td>
        $200
      </td>
    </tr>

    <tr>
      <td>
        Up to 20,000
      </td>

      <td>
        \<20,000 with add-ons
      </td>

      <td>
        $200
      </td>

      <td>
        $20
      </td>

      <td>
        $0
      </td>

      <td>
        $0
      </td>

      <td>
        $200
      </td>
    </tr>

    <tr>
      <td>
        Up to 20,000
      </td>

      <td>
        22,000 (2,000 MAUs overage) without add-ons
      </td>

      <td>
        $200
      </td>

      <td>
        $0
      </td>

      <td>
        Overage (2,000/100\*1.2)\
        $24
      </td>

      <td>
        $0
      </td>

      <td>
        $224
      </td>
    </tr>

    <tr>
      <td>
        Up to 20,000
      </td>

      <td>
        22,000 (2,000 MAUs overage) with add-ons
      </td>

      <td>
        $200
      </td>

      <td>
        $20
      </td>

      <td>
        Overage (2,000/100\*1.2)\
        $24
      </td>

      <td>
        $24\
        ($20\*1.2)
      </td>

      <td>
        $268
      </td>
    </tr>
  </tbody>
</Table>

\*Not inclusive of taxes, if applicable 

You can view the estimated billable MAU and overages for your plan under *Organization* > *My Plan* > *Usage Summary*. To avoid overages charges, you will need to upgrade your subscription to a higher MAU tier limit. 

> 📘 Billable MAU Usage over 300%
>
> You may lose access to your account for any billable MAU usage over 300%. There are no overage charges levied during the trial period.

### Alerts for Overages

All account admins will receive alert emails when their account exceeds their MAU tier limit cap by the following percentages: 80%, 100%, 125%, 150%, 200%, 250%, 300%, and 600%. Account admins are also notified to upgrade to a higher MAU tier through a popup if the account exceeds the MAU tier limit.

### Account Lock and Suspension

#### Account Lock Due to Overages

If your MAU overages exceed 300%, your account may be locked. During this time, you will no longer be able to access the dashboard. To restore account access and avoid overages, you will be required to upgrade your subscription to a higher MAU tier limit. During this time, data ingestion and any scheduled or recurring campaigns will not be affected. All data exports via API, SFTP, and third-party partners will be disabled.

If you do not upgrade by the next billing date (the 1st of each month), your account access will be locked and overages charges will be applicable.

## **Invoices, GST, and Sales Tax**

### View and Manage Invoices

Whenever you purchase a CleverTap subscription, you can find your invoices under the billing tab of your admin section. The invoice is sent on the first of every month only to the email added under the billing details section. For more details on changing the invoice recipient, refer to the [Change Invoice Recipients and Billing Details](https://docs.clevertap.com/docs/billing#section-change-invoice-recipients-and-billing-details) section. 

To find your invoices:

1. Click **Organization** on the left navigation menu of the dashboard. Click **Billing details** > **Invoices**. From there, you will be able to view all invoices. 
2. To view the full invoice, click on an invoice number.

> 📘 Invoice Access
>
> Only account admins can access and update invoices.

## **Change Invoice Recipients and Billing Details**

To change the invoice recipient or update invoice details:

1. Click on the **Billing Details** section under *Organization* on the CleverTap dashboard. 
2. Click **Save** to apply your changes. 

Any changes made to these settings will reflect on the next invoice. 

## **GST Invoicing (India Only)**

CleverTap supports GST invoicing for customers in India. GST (Goods and Services Tax) is a mandatory levy for all Indian Rupee (INR) invoices in accordance with regulatory requirements in India. Businesses registered in India can input their GSTIN (GST Identification Number) during the signup process.
