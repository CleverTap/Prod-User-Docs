---
title: Gupshup
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
# Overview

CleverTap supports customers sending and receiving WhatsApp messages using Gupshup as their provider. Once a provider is selected the user needs to create a template before creating a WhatsApp campaign.

## Select Gupshup Provider

Perform the following steps to select Gupshup as the messaging provider for WhatsApp.

1. From the CleverTap dashboard, navigate to *Settings* and click on **Channels**.
2. Select *WhatsApp*.

![647](https://files.readme.io/496ab50-2020-06-25_09-04-14_Add_provider.png "2020-06-25_09-04-14_Add provider.png")

3. Click **+Providers** then select *Gushup* from the dropdown menu. Nexmo is the provider default.

<Image title="2020-06-25_09-12-35_Provider credentials.png" alt={429} width="80%" src="https://files.readme.io/14ce97c-2020-06-25_09-12-35_Provider_credentials.png" />

4. Enter the following credentials:

* Nickname: Enter the nickname for these set of credentials.
* Inbound message callback URL: This is a non-editable field.
* Delivery reports callback URL: This is a non-editable field.
* Notification account user ID: Enter the notification account user ID.
* Notification account password: Enter the notification account password.
* Two-way account user ID: Enter the two-way account user ID.
* Two-way account password: Enter the two-way account password.
* App name:  Enter the App name from the Gupshup dashboard.
* Mobile Number: Enter either a Gupshup phone number or a shortcode. You can enter phone numbers or shortcodes listed under the Gupshup dashboard > Numbers > Your Numbers.
* Facebook URL: Enter the Facebook URL from the Gupshup dashboard.

> 📘 Non-Editable Fields
>
> The inbound message callback URL and delivery reports callback URL are non-editable fields. These values must be set up in your Gupshup account to allow CleverTap to receive inbound messages from end-users and delivery reports for messages sent through Gupshup.

<Image title="2020-06-25_09-12-35_Provider credentials1.png" alt={704} width="80%" src="https://files.readme.io/cf55c41-2020-06-25_09-12-35_Provider_credentials1.png" />

> 📘 Auto Reply Checkbox
>
> Select the checkbox if you want to set auto-replies for users who are not tracked in CleverTap.

5. Click **Save**.

![729](https://files.readme.io/4fbb7a9-2020-06-26_16-05-32_Saving_credentials.png "2020-06-26_16-05-32_Saving credentials.png")

## Select Template

Once you have selected Gupshup as the provider, create a template for the campaign.

1. Select the *Templates* option, and click **+Template**.

![934](https://files.readme.io/4e41af4-2020-06-25_10-21-57_Select_Templates.png "2020-06-25_10-21-57_Select Templates.png")

2. Enter the template namespace.
3. Enter the template massage.
4. Select an attachment type from the dropdown menu.

![972](https://files.readme.io/a26d185-2020-06-25_10-25-38_Name_and_save_template.png "2020-06-25_10-25-38_Name and save template.png")

> 📘 Namespace format
>
> Namespace is combination of your Account name in capital and template name on Gupshup dashboard. for example if you account is ABC and the template name for a verified template on Gupshup is welcome\_message, then namespace would be **ABC:welcome\_message**

5. Click **Save**.

## Create Campaign

To create a WhatsApp campaign using Gupshup as the provider, refer to [Creating a WhatsApp Campaign](https://docs.clevertap.com/docs/whatsapp#section-creating-a-whatsapp-campaign) for detailed instructions.

## Troubleshooting

Errors during integration\
Restricted IPs can cause errors during integration. Check that there are no IP restrictions enabled on the Gupshup account. To check the IPs from the CleverTap dashboard, go to *Settings > Channels > Mobile push*. The *FCM credentials* section lists the IPs that are used to send Whatsapp requests.  These IPs must be whitelisted on both the *one-way* and *two-way* account IDs of Gupshup.

![810](https://files.readme.io/e24891a-Gupshup_Whitelist_IPs.png "Gupshup_Whitelist_IPs.png")
