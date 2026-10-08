---
title: Email Add-on
excerpt: >-
  Learn how the Email Add-on for CleverTap Essentials Plan empowers you to
  streamline customer engagement with built-in email capabilities.
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

The Email Add-on for the CleverTap Essentials Plan offers a built-in Email Service Provider (ESP) designed to simplify email communication. With this add-on, businesses can send emails directly from CleverTap without relying on third-party integrations. 

With features such as AMP for Email, Email on Acid API support, and detailed consumption tracking, the add-on empowers startups with advanced tools to enhance email campaigns and drive customer engagement efficiently.

## Features of the Email Add-on

When you purchase the CleverTap Email Add-on, you gain access to the following features:

| Feature                  | Description                                                                                                   |
| :----------------------- | :------------------------------------------------------------------------------------------------------------ |
| **Monthly Email Quota**  | 1,00,000 emails per month.                                                                                    |
| **SendGrid Integration** | A SendGrid account, including one dedicated IP.                                                               |
| **AMP for Email**        | Create engaging, interactive email content with [AMP for Email](doc:ampforemail).                             |
| **Email on Acid**        | Test your email design and deliverability with up to 5 monthly API calls.                                     |
| **Rich Content Support** | Leverage [Linked Content](doc:linked-content) and [Liquid Tags](doc:liquid-tags) for dynamic personalization. |

# Pricing and Billing

The Email Add-on comes with a fixed cost and a variable component based on overages for emails sent beyond the allotted quota. The following is the pricing structure for the Email Add-on:

| Component        | Details                                              |
| :--------------- | :--------------------------------------------------- |
| **Add-on Price** | $50 per month + 10% of your CleverTap base plan cost |
| **Overages**     | $0.0005 per email sent beyond the allotted quota     |

## Example Calculation

Suppose you are a CleverTap Essential customer with a base plan of $200 per month, and you have added the Email Add-on to enhance your email communication capabilities. If you send 10,000 emails over your allocated quota, your total monthly cost will be calculated as follows:

| Calculation Step             | Details                                                  | Amount          |
| :--------------------------- | :------------------------------------------------------- | :-------------- |
| **Base Plan Cost**           | Monthly base plan cost                                   | $200            |
| **Add-on Price (A)**         | $50 (fixed) + 10% of base plan ($200 x 10%)              | $50 + $20 = $70 |
| **Overage Cost (B)**         | Additional 10,000 emails beyond allotted quota x $0.0005 | $5              |
| **Total Monthly Cost (A+B)** | Add-on Price + Overage Cost                              | $70 + $5 = $75  |

# Enabling Add-on

The following are the key steps to enable the Email Add-on feature in your project:

1. [Purchase the Email Add-on](doc:email-add-on-for-clevertap-essentials-plan#purchase-the-email-add-on) 
2. [Configure Email Settings](doc:email-add-on-for-clevertap-essentials-plan#configure-email-settings)
3. [Warm Up Your IP](doc:email-add-on-for-clevertap-essentials-plan#warm-up-your-ip)

## Purchase the Email Add-on

1. Log in to your CleverTap dashboard.
2. Navigate to *Organization >  Billing > My Plan > Manage Add-ons*.
3. Locate the *CleverTap Email Add-on* and click **Select**.
4. Click **Pay & Update Plan** to confirm the purchase.

<Image alt="Purchase Email Add-on" align="center" border={true} src="https://files.readme.io/2410a02faf35ed8ad0b30971700e13d87ea5cbdfe1a986e7a6cb19a45982136f-2024-12-11_13-23-51_1.gif">
  Purchase Email Add-on
</Image>

5. Submit the form and then wait for 72 hours. You will receive the API Key from CleverTap's onboarding team for the email configuration.

> 📘 Email Configuration Process
>
> Currently, the configuration process is manual and will be completed within a 72-hour standard licensed agreement (SLA) after filling the form.

## Configure Email Settings

After you receive the API Key from CleverTap's onboarding team:

1. Navigate to *Settings > Email > Provider*.
2. Select *CleverTap Email* from the dropdown menu.
3. Enter the provider details shared by CleverTap's onboarding team and click **Save**.

<Image alt="Configure CleverTap Email Provider" align="center" border={true} src="https://files.readme.io/bebe0bcff039e7f691edfd81ec278b7b61da3275a79539c41d44e0c8e479e961-Provider_Credentials.png">
  Configure CleverTap Email Provider
</Image>

For more information, refer to [Setup Provider](doc:sendgrid).

## Warm Up Your IP

Gradually increasing email volume is crucial to maintaining optimal email deliverability. This process, known as IP Warm-up, helps establish a strong IP reputation and avoids potential deliverability issues. To warm up your IP, follow the IP warm-up guide sent via email post-purchase or refer to [IP Warm-up](doc:ip-warmup). The IP warm-up is a self-service process, requiring you to follow the provided documentation independently.

After the IP warm-up, you can start creating Email campaigns. For more information, refer to [Create Message](doc:create-message-email).

# FAQs

### Q. What happens if I exceed my email quota?

A. You will be charged $0.0005 per email for overages.

### Q. How long does it take to activate the add-on?

A. The activation process, including SendGrid account setup, is completed within 72 hours of filling out the form.  

### Q. Can I use multiple email providers in CleverTap?

A. Yes, you can configure and use other providers simultaneously.
