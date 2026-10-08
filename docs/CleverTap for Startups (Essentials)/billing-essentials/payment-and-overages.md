---
title: Payments and Overages
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Payment Methods

Under the CleverTap Essential plan, CleverTap accepts all major credit or debit cards (for example, Visa, Mastercard, Discover, and JCB).\
We also allow eNACH (eMandate via Net Banking) for Indian customers paying in INR. For more information about how it works, refer to the [eMandate via NetBanking](https://docs.clevertap.com/docs/emandate-via-netbanking?utm_source=C4S\&utm_medium=doc\&utm_id=KB).

## Managing Payment Method

CleverTap provides the flexibility of having more than one payment method. One of the payment methods is always marked as Default. You can update any one of the saved methods as the default payment method. In this case, all future transactions will be made through the default method.

## Update Billing Information and Card Details

If you are an organization member with billing permissions (Admins), you can update the billing and payment information by clicking **Organization** on the left navigation menu of the dashboard. Then, click **Payment Methods** to update the required details.

> 📘 Billing Currency
>
> You cannot change the currency for billing.

## Payment Failure

In case your payment fails, we notify you right away. You must complete your payment within a grace period of 10 days. You can choose to retry with the existing default payment method or use a new payment method. We automatically make the payment method you choose to pay with a default method post successful transaction.

During the grace period, the incoming data, data exports, and dashboard access are not affected. If the payment details are not updated within the grace period, your account access is locked. If you do not clear all outstanding payments within 14 days of the account lock, your account is canceled. After the account is canceled, you can no longer retrieve your account, and all the data is deleted permanently.

> 📘 New RBI eMandate Regulations
>
> For Indian Customers, with new Reserve Bank of India (RBI) e-mandate regulations coming into effect, there are high chances your payment may fail. This is because the processing of e-mandate on cards for recurring transactions requires an Additional Factor of Authentication (AFA). For more information, refer to [Compliance with RBI eMandate Regulations](https://docs.clevertap.com/docs/compliance-with-rbi-emandate-regulations?utm_source=C4S\&utm_medium=doc\&utm_id=KB).

## Exceeding Plan Limits

If you exceed your plan limits, you can upgrade to a higher MAU tier before the end of the billing period to avoid overage charges.

## Overage Calculation

When your MAU usage exceeds the plan's MAU limit, you will be charged extra for each additional MAU. For the Essential Plan, the following rates apply for overages:

* **Base Price**: $1.25 per 100 MAUs in USD and ₹100 in INR.
* **Overage Rate**: Overage charges are calculated at 1.2 times the base price for each additional 100 MAU.
* **Add-On Surcharge**: An additional 10% surcharge applies to the calculated overage for each add-on.

The following example helps us understand the calculation of overage charges for a USD subscription with an MAU tier of 20,000, including add-ons:

<Table align={["left","left","left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        MAU Limit
      </th>

      <th>
        Monthly Billable Users
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
        Billable Amount
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
        $250
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
        $250
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
        $250
      </td>

      <td>
        $25
      </td>

      <td>
        $0
      </td>

      <td>
        $0
      </td>

      <td>
        $275
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
        $250
      </td>

      <td>
        $0
      </td>

      <td>
        Overage [(2,000/100)x$1.25x1.2] = $30
      </td>

      <td>
        $0
      </td>

      <td>
        $280
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
        $250
      </td>

      <td>
        $25
      </td>

      <td>
        Overage [(2,000/100)x$1.25x1.2] = $30
      </td>

      <td>
        Overage\
        $30x10/100 = $3
      </td>

      <td>
        $308
      </td>
    </tr>
  </tbody>
</Table>

\*Excluding applicable taxes.

### Monitor and Manage Overages

You can monitor your plan’s estimated MAU usage and overages by navigating to *Organization* > *My Plan >* *Usage Summary*. Overage charges are calculated pro-rata from the start of the billing period for the month in which the overage occurred.

To avoid overage charges, consider upgrading your subscription to a higher MAU tier.

> 📘 MBU Usage over 300%
>
> You may lose access to your account for any MBU usage over 300%. There are no overage charges levied during the trial period.

> 📘 Softlock for Annual Payments
>
> The softlock for annual payment happens at 120%. If your **Annual Billable Users** exceed 120% of the annual data point limit, then your account gets softlocked.

## Alert for Overages

All account admins will receive alert emails when their account exceeds their MAU tier limit cap by the following percentages: 80%, 100%, 125%, 150%, 200%, 250%, 300%, and 600%. Account admins are also notified to upgrade to a higher MAU tier through a popup if the account exceeds the MAU tier limit.

## Account Lock and Suspension

### Account Lock Due to Overages

If your MAU overages exceed 300%, your account may be locked. During this time, you will no longer be able to access the dashboard. To restore account access and avoid overages, you must upgrade your subscription to a higher MAU tier limit. Data ingestion and any scheduled or recurring campaigns will not be affected during this time. All data exports via API, SFTP, and third-party partners will be disabled.

If you do not upgrade by the next billing date (the 1st of each month), your account access will be locked, and overage charges will be applicable.

# Invoices, GST, and Sales Tax

## View & Manage Invoices

Whenever you purchase a CleverTap Essentials subscription, you can find your invoices under the Billing tab of your admin section. The invoice is sent on the first of every month only to the email added under the billing details section. For more details on changing the invoice recipient, refer to the [Change Invoice Recipients and Billing Details](https://docs.clevertap.com/docs/billing#section-change-invoice-recipients-and-billing-details?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB) section.

To find your invoices:

1. Click **Organization** on the left navigation menu of the dashboard. 
2. Click **Billing details** > **Invoices**. From there, you will be able to view all invoices. 
3. To view the entire invoice, click on an invoice number.

> 📘 Invoice Access
>
> Only account admins can access and update invoices.

# Tax Invoicing

* **VAT (Value-Added Tax)**: A field is provided to USD customers for entering tax numbers, which is shown in the invoice for USD accounts.
* **GST (Goods and Services Tax)**: CleverTap supports GST invoicing for customers in India. GST (Goods and Services Tax) is a mandatory levy for all Indian Rupee (INR) invoices as per regulatory requirements in India. Businesses registered in India can input their GSTIN (GST Identification Number) during the signup process.
* **TDS (Tax Deducted at Source)**: Compliance with regards to the TDS or withholding taxes is required to be taken by the customer. To comply with the requirement, you must gross up the amount paid to CleverTap and accordingly calculate the TDS on the same.\
  For example, If INR 14000 + GST is the monthly invoice and you need to withhold 2% TDS, then 2% of Rs.14000 or INR 280 becomes the withholding tax, and you have to expense it out at your end. Please check the terms and conditions mentioned on the online page related to TDS or withholding taxes. Please refer to [section 6.2](https://clevertap.com/terms-service?utm_source=C4Sdoc\&utm_medium=doc\&utm_campaign=KB) of the terms and conditions.

# Change Invoice Recipients and Billing Details

To change the invoice recipient or update invoice details:

1. Go to *Organization* > *Billing* > *Billing details* > on the CleverTap dashboard.
2. Make the required changes and click **Save** to apply your changes.

Any changes made to these settings will be reflected on the next invoice. For more information on the billing details page, refer to [Add Billing Details](doc:project-setup#add-billing-details).

For additional information on commonly encountered queries, refer to the [FAQs](doc:clevertap-for-startups-billing-faqs).
