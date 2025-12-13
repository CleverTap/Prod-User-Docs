---
title: Troubleshooting
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Overview

This section provides some FAQs, troubleshooting help for your email setup, tips to raise your reputation from poor to good, and IP and domain monitoring. 

# FAQs

## Why does linked content not work in the email builder?

Linked content does not work in the email builder because it is in text format. Linked content is only supported in custom HTML.

## Does the recommendation feature work in the email builder?

No.

## What are the IPs that are used to send out the emails?

To get the IPs, perform the following steps:

1. From the dashboard, navigate to *Settings* > *Channels* > *Mobile Push*.

> 📘 Same IPs
>
> The IPs are the same for webhooks, SMS, and emails.

# Raise your Reputation from Poor to Good

Monitoring your domain health is an ongoing process that requires consistent nurturing. Your sending reputation is a decisive factor when it comes to the delivery of your emails. By complying with permission policies and best practices and carefully monitoring your email list performance, you will be well-positioned to develop and maintain a strong sending reputation.

Take the steps below to improve your domain and IP reputation.

## Prime Your IP for Success

The job of ISP filters is to defend against spam emails. How do you tell these filters that your IP is valid and trustworthy? Start any email campaign by sending small batches of emails. Send these messages to email addresses that you know are engaged. As these emails are received and opened by engaged users, your IP will start to build trust with the ISP. Slowly increase the number of emails until you scale to your peak volume.

## Create a New Subdomain 

We do not recommend everyone to create a new subdomain, but if possible, you may wish to create one. Over time, users will come to trust the subdomain which is an added benefit. The purpose is that this subdomain will allow for domain-specific monitoring of your IP reputation and be able to succeed against some domain-based certification filters.

To add new subdomain in SendGrid, perform the following steps:

1. Log in to your SendGrid account and navigate to the *Settings* section.

![182](https://files.readme.io/46f1e01-1_Settings.png "1 Settings.png")

2. Click **Sender Authentication**.

![180](https://files.readme.io/06c6adc-2_Sender_Authentication.png "2 Sender Authentication.png")

3. Click **Authenticate Your Domain** under *Domain Authentication*.

![424](https://files.readme.io/242cfc9-3_Authenticate_Your_Domain.png "3 Authenticate Your Domain.png")

4. Select the name of your DNS host provider.

![873](https://files.readme.io/2ce2a25-4_name_of_your_DNS_host_provider.png "4 name of your DNS host provider.png")

5. In the second option on the same page, choose if you want the link branding or not and click **Next**.
6. Fill in the name of the domain/subdomain from which you wish to send your email campaigns. 
7. Select the *Use automated security* option in the *Advanced Settings* section and click **Next**.

![502](https://files.readme.io/b395e61-5_Next.png "5 Next.png")

8. The next screen will provide you the records which will be required to be updated on the DNS settings page of your domain host name provider.

![1106](https://files.readme.io/3928608-6_records.png "6 records.png")

9. Once the provided records have been updated on the DNS settings page, click on the checkbox in the bottom right corner along with the option *I've added these records* and click **Verify**.

This will verify that the correct records have been added to the said domain DNS and once the verification is complete the added domain will be listed on the *Sender Authentication* page and is ready for use. If the verification fails, then check if the records have been added to the DNS correctly and repeat the previous verification steps.
