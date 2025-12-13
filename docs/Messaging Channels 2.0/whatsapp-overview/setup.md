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

CleverTap uses API endpoints from [Nexmo](https://www.nexmo.com/products/messages/whatsapp) or [Gushup](https://enterprise.smsgupshup.com/whatsapp) to connect with WhatsApp. To get started, perform the following steps:

1. Contact CleverTap's sales team to get a WhatsApp business account for your organization by emailing sales@clevertap.com.
2. CleverTap's customer success team will then create the business account which will enable you to use WhatsApp as an engagement channel.

Alternatively, if you already have a Nexmo or Gupshup account, you can plug in the details by navigating to *Account* > *Settings* > *Engage* > *Channels* > *WhatsApp*.

For adding Gupshup as a provider, see [Adding Gupshup](https://docs.clevertap.com/docs/gupshup).
For adding Nexmo as a provider, see [Adding Nexmo](https://docs.clevertap.com/docs/nexmo-provider).
[block:api-header]
{
  "title": "Opt-in Users into WhatsApp"
}
[/block]
Most people do not like receiving unsolicited messages on WhatsApp. Therefore, it is important for you to explicitly request permission before sending messages to users on their WhatsApp account. 

By default, CleverTap keeps all the profiles opted out of WhatsApp. To opt-in profiles, update the profile using the following code:
[block:code]
{
  "codes": [
    {
      "code": "\"MSG-whatsapp\":true",
      "language": "json"
    }
  ]
}
[/block]
You have two ways to opt-in users for WhatsApp:
1. [Opt-in via updating the user's profile property](https://developer.clevertap.com/docs/concepts-user-profiles#section-updating-the-user-profile). 
2. [Opt-in via the API profile update](https://developer.clevertap.com/docs/upload-user-profiles-api). 
[block:api-header]
{
  "title": "Understand Message Templates in WhatsApp"
}
[/block]
WhatsApp restricts brand initiated messages (the messages that you send via campaigns) to pre-approved templates. You can fill in the variables in the templates to personalize a message. 

For example:

*Hello {{1}}, Congratulations on your ticket booking. Here is your ticket number: {{2}}. Please ensure you visit us on {{3}}. Enjoy your experience.*

The variables *{{1}}* or *{{2}}* or *{{3}}* can be replaced by a text of your choice. You can use CleverTap's event and profile personalization to personalize the message for your audience.

To set up a message template, follow the [Sending Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/) documentation on Facebook.
[block:api-header]
{
  "title": "Configure Message Templates"
}
[/block]
All your message templates must be approved by WhatsApp. At CleverTap, we help you with the verification. For more information on how to create message templates, refer to the [Creating Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/creation/) documentation on Facebook. After your templates are verified, you can enter them on the WhatsApp settings under the *Templates* tab.

To use WhatsApp with CleverTap, it is important to copy the templates accurately in the settings by performing the following steps:

1. From the dashboard, navigate to *Account* > *Settings* > *Engage* > *Channels* > *WhatsApp*. 
2. Click on one of the provider names.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6aeaef1-1_Settings_WhatsApp_dashboard.png",
        "1 Settings WhatsApp dashboard.png",
        1091,
        459,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
3. Click on the **Templates** tab.
3. Click on the **+ Template** button.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19532c1-2_Plus_WhatsApp_template.png",
        "2 Plus WhatsApp template.png",
        1090,
        559,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
4. Once the window below displays, add the namespace and message template text from your Facebook pages.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7787955-Screenshot_2021-09-20_at_11.27.52_AM.png",
        "Screenshot 2021-09-20 at 11.27.52 AM.png",
        1764,
        1470,
        "#f4f5f9"
      ]
    }
  ]
}
[/block]
5. Click **Save** to save the message template.  
[block:callout]
{
  "type": "info",
  "title": "Language Support",
  "body": "Please note the following for language support:\n  * As of now, Nexmo supports the Arabic language. For other languages, contact our support team to enable a different language.\n  * Since Gupshup supports and handles all languages automatically, you do not need to add them on the CleverTap dashboard."
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Namespace Format",
  "body": "While copying message templates from the Facebook business dashboard, be sure to use the following format for the namespace, so your templates get added to the CleverTap dashboard properly: <template_namespace>:<template_name>"
}
[/block]