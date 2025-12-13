---
title: Setup
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
# Overview

CleverTap uses API endpoints from [Nexmo](https://www.nexmo.com/products/messages/whatsapp) or [Gushup](https://enterprise.smsgupshup.com/whatsapp) to connect with WhatsApp. To get started, send an email to [sales@clevertap.com](mailto:sales@clevertap.com) to get a WhatsApp business account for your organization.

CleverTap's customer success team then creates a business account that will enable you to use WhatsApp as an engagement channel.

Alternatively, if you already have a Nexmo or Gupshup account, you can plug in the details by navigating to *Account* > *Settings* > *Engage* > *Channels* > *WhatsApp*.

For adding Gupshup as a provider, refer to [Adding Gupshup](https://docs.clevertap.com/docs/gupshup).\
For adding Nexmo as a provider, refer to [Adding Nexmo](https://docs.clevertap.com/docs/nexmo-provider).

## Opt-in Users into WhatsApp

Most people do not like receiving unsolicited messages on WhatsApp. Therefore, it is important for you to explicitly request permission before sending messages to your users on their WhatsApp account. 

By default, CleverTap keeps all the profiles opted out of WhatsApp. To opt-in profiles, update the profile using the following code:

```json
"MSG-whatsapp":true
```

You have the following two ways to opt-in users for WhatsApp:

* [Opt-in via updating the user's profile property](https://developer.clevertap.com/docs/concepts-user-profiles#section-updating-the-user-profile). 
* [Opt-in via the API profile update](https://developer.clevertap.com/docs/upload-user-profiles-api). 

## Message Templates in WhatsApp

WhatsApp restricts brand-initiated messages (the messages that you send via campaigns) to pre-approved templates. You can fill in the variables in the templates to personalize a message. 

For example:

*Hello \{\{1}}, Congratulations on your ticket booking. Here is your ticket number: \{\{2}}. Please ensure you visit us on \{\{3}}. Enjoy your experience.*

The variables *\{\{1}}* or *\{\{2}}* or *\{\{3}}* can be replaced by a text of your choice. You can use CleverTap's event and profile personalization to personalize the message for your audience.

To set up a message template, follow the steps listed under [Sending Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/creation) documentation on Facebook.

## Configure Message Templates

All your message templates must be approved by WhatsApp. At CleverTap, we help you with the verification. For more information on how to create message templates, refer to the [Creating Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/creation/) documentation by Facebook. 

The media message templates allow you to expand the content you can send to the recipients beyond the standard messages. The template is organized primarily into four sections - *Header*, *Body*, *Footer*, and *Buttons*.

Using this template, one can attach media files (image, video, document, location) within the **Header** along with the message body. 

Additionally, WhatsApp also allows marketers to include **CTAs** or **Quick Reply** buttons in the text or media message templates for making the conversations more interactive. 

* Call-to-Action (CTAs) — Enables the customer to make a phone call or visit a website.
* Quick Reply — Allows your customer to respond with a simple text message.

Once your interactive message templates have been created and approved, you can use them in notification messages as well as customer service/care messages.

The images below represent different templates that marketers can create for engaging with their customers effectively.

<Image title="Templates.png" alt={2318} className="border" border={true} src="https://files.readme.io/fa88774-Templates.png" />

After your templates are verified, you can add them in the WhatsApp settings under the *Templates* tab.

To use WhatsApp with CleverTap, it is important to copy the templates accurately in the settings by performing the following steps:

1. From the dashboard, navigate to *Account > Settings > Engage > Channels > WhatsApp*. 
2. Click on one of the Provider names.

![1894](https://files.readme.io/c423fd6-image.png "image.png")

3. Navigate to the **Templates** tab.
4. Click **+ Template** .

<Image title="Screenshot 2021-09-21 at 8.37.29 PM.png" alt={2346} className="border" border={true} src="https://files.readme.io/af37717-Screenshot_2021-09-21_at_8.37.29_PM.png" />

5. Now, enter the *Namespace* for your template.

> 🚧 Namespace Format
>
> When copying the message templates from the WABA dashboard, use the following format for the namespace: \<template\_namespace>:\<template\_name>. One can find the *Namespace* value from the *Message templates* section on the WABA dashboard as shown in the image below:

<Image title="namespace.png" alt={2879} className="border" border={true} src="https://files.readme.io/f755093-namespace.png" />

Refer to the image below to get a sense of a sample *Namespace* format.

<Image title="Screenshot 2021-09-23 at 1.01.12 PM.png" alt={1354} className="border" border={true} src="https://files.readme.io/d7f6250-Screenshot_2021-09-23_at_1.01.12_PM.png" />

6. Copy and save the approved message templates from your WhatsApp Business Account (WABA) dashboard.

<Image title="Screenshot 2021-09-20 at 11.27.52 AM.png" alt={1764} className="border" border={true} src="https://files.readme.io/7787955-Screenshot_2021-09-20_at_11.27.52_AM.png" />

5. Click **Save Template** to save the message template.  

> 📘 Language Support
>
> * For Vonage (Nexmo), if you don't find the required language support on the CleverTap dashboard, contact our support team to enable the required language for your account.
> * Gupshup supports and handles all languages automatically, hence you do not need to add them on the CleverTap dashboard.
