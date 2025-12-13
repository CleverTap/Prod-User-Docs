---
title: WhatsApp_clone
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
WhatsApp is a popular messaging channel that enables secure and trustworthy communications. The most attractive value WhatsApp provides is that it is advertisement and spam-free. WhatsApp allows businesses to communicate with their users in a more friendly and interactive manner. 

CleverTap provides the capability to use WhatsApp as a channel to engage users in a reliable and secure way. Moreover, you can use CleverTap's [conversations](doc:conversations) to chat with your users on WhatsApp.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2f2d935-Whatsapp_3_new_1.png",
        "Whatsapp_3_new (1).png",
        1251,
        1551,
        "#9ba29c"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "WhatsApp as a Channel"
}
[/block]

WhatsApp messages have high reachability and readability rates due to its security and trustworthiness making it one of the most attractive channels of engagement for businesses. 

A WhatsApp message can be configured and sent like any other campaign on CleverTap. After sending the campaign, you can measure the performance of that campaign. When a user responds to one of your messages, CleverTap gives you the capability to reply to the user directly from the dashboard.

Below are some use case scenarios:
  * Send real-time notifications to customers regarding delivery alerts and booking confirmations.
  * Send personalized recommendations about new products, offers, and services through rich media sharing.
  * Delight your customers with reminders about their upcoming bookings.
  * Enable your customer support team to respond to customer queries instantly.
[block:api-header]
{
  "title": "How to Get Started"
}
[/block]
CleverTap uses API endpoints from [Nexmo](https://www.nexmo.com/products/messages/whatsapp) or [Gushup](https://enterprise.smsgupshup.com/whatsapp) to connect with WhatsApp. To get started, perform the following steps:

1. Contact CleverTap's sales team to get a WhatsApp business account for your organization by emailing sales@clevertap.com.
2. CleverTap's customer success team will then create the business account which will enable you to use WhatsApp as an engagement channel.

Alternatively, if you already have a Nexmo or Gupshup account, you can plug in the details by navigating to *Account* > *Settings* > *Engage* > *Channels* > *WhatsApp*.
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
4. Once the window below displays, add the namespace and message template text from your Facebook page. 
5. Click **Save** to save the message template.  
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/86a23e8-3_WhatsApp_details.png",
        "3 WhatsApp details.png",
        1084,
        602,
        "#aaabad"
      ],
      "border": true
    }
  ]
}
[/block]

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

[block:api-header]
{
  "title": "Create a WhatsApp Campaign"
}
[/block]
This section covers how to create a WhatsApp campaign.

##Create a Campaign
To create a new campaign, perform the following:

1. On the CleverTap dashboard, select *Campaigns*.
2. Click **+ Campaign**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5d68e67-1_Campaign_dashboard.png",
        "1 Campaign dashboard.png",
        1588,
        500,
        "#f7f9f9"
      ],
      "border": true
    }
  ]
}
[/block]
## Select the Engagement Channel

To select the engagement channel, click on **WhatsApp**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/561dc14-2_engagement_channel.png",
        "2 engagement channel.png",
        840,
        828,
        "#f8f8fa"
      ]
    }
  ]
}
[/block]
##Select a Campaign Type

Select one of the campaign types from the list of options as displayed below.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a93c6f2-3_campaign_type.png",
        "3 campaign type.png",
        827,
        511,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]
###Campaign Types
Unlike other channels such as push notifications or SMS, WhatsApp does not support multiple date campaigns or recurring campaigns to prevent misuse and spam.

The four types of campaigns possible are:

  * One time: For past behavior segments. For example, send a WhatsApp message to all users who booked tickets last week.
  * Single action: For live user segments. For example, send a confirmation to all users after buying a movie ticket from an app.
  * Inaction within time: For example, send a reminder to all the users who added an item to cart but did not check out within 30 minutes. 
  * On a date/time: For example, send a message to users one day before the flight departure regarding do's and don'ts. 

## Define the Who

You must indicate the target audience for your WhatsApp campaign. You can target your campaign to a new user segment by clicking on **+ Create an ad-hoc segment** or use a previously saved user segment from the *Saved Segments* list.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/df20b94-4_Define_the_Who.png",
        "4 Define the Who.png",
        1617,
        398,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
## Draft a Message 
To draft a message, perform the following steps:
1. Select a message type.
2. Select a template. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/158982c-5_select_a_template.png",
        "5 select a template.png",
        1615,
        818,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
3. After selecting the message template, you can replace the variable fields with your custom input.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b1254d-6_customize_message.png",
        "6 customize message.png",
        1510,
        677,
        "#f3f2f1"
      ]
    }
  ]
}
[/block]
##Save and Schedule the Campaign

Review your campaign summary, then click **Schedule notification** to save and schedule your campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/068291f-7_save_campaign.png",
        "7 save campaign.png",
        1629,
        843,
        "#fbfcfc"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Campaign Stats in WhatsApp"
}
[/block]
To view the statistics of your campaign, click the campaign from the campaign list page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ffb683e-8_stats.png",
        "8 stats.png",
        1576,
        577,
        "#fafbfc"
      ],
      "caption": ""
    }
  ]
}
[/block]
You can track the status of your messages sent under the following heads:
  * Sent: Messages sent from CleverTap.
  * Delivered: Messages delivered to the user's WhatsApp app.
  * Viewed: Messages that the users have viewed. 
  * Control Group: Users who were excluded from the WhatsApp campaign because they belong to the control group.
  * Replied: Number of replies sent by the user to the business.
  * Errors: Errors occurred while sending the messages to the user.