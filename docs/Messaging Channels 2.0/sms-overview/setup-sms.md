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
# Add a New Provider

To add a new SMS provider, perform the following steps:
1. From the dashboard, navigate to *Settings* > *Channels* > *SMS*.
2. Click **+ Add Provider**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ea1f1a5-1_Add_Provider_dashbboard.png",
        "1 Add Provider dashbboard.png",
        1074,
        423,
        "#f7f8fb"
      ]
    }
  ]
}
[/block]
3. Enter all the required information.
4. Click **Save**. 

Once the phone number is validated by the SMS service provider, you can send a test SMS to test the integration before you start creating SMS campaigns and journeys.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9bdfd5b-2_Add_a_new_provider.png",
        "2 Add a new provider.png",
        814,
        739,
        "#f9fafb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Twilio SMS Integration",
  "body": "For Twilio integration, CleverTap also supports the capability to add a CoPilot id instead of a phone number in the *From* section.\n\nTwilio CoPilot improves the SMS delivery by letting you add multiple phone numbers to send the same campaign. For more information, refer to the [Twilio CoPilot](https://www.twilio.com/copilot) page."
}
[/block]
# Add a Provider Group

The failure of an SMS provider may affect your SMS campaigns, so it is always better to have another SMS provider. By grouping providers, you can provide your users a seamless experience. 

For example, if you have a subscriber base across different countries, it helps to have a provider group for each country. You can assign a preferred provider to send a message. A provider group is used based on its assigned priority for each message. If provider 1 is unavailable, then we attempt the message with provider 2, and so on. In the end, this ensures higher message deliverability for your campaigns.
[block:callout]
{
  "type": "info",
  "body": "Each provider group can have a maximum of 10 providers.",
  "title": "Provider Group Maximum"
}
[/block]
To create a provider group, perform the following steps:
1. From the dashboard, navigate to *Settings* > *SMS* > *Provider Groups* tab. 
2. Click **+ Add Provider Group**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a9f0479-3_Provider_Group_dashboard.png",
        "3 Provider Group dashboard.png",
        1064,
        415,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
2. Enter a group name.
3. Select the providers by priority.
4. Click **Save Provider Group**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/663186b-SMS_provider_group_create.png",
        "SMS_provider_group_create.png",
        576,
        714,
        "#f7f8fc"
      ],
      "border": true
    }
  ]
}
[/block]
## Edit a Provider Group

To edit a provider group, perform the following steps:

1. Click the ellipsis next to the required provider from the *Provider Groups* tab. 
2. Click **Edit settings** to add or remove providers or change the priority for any providers. 

You can also mark a provider group as a default by clicking on **Mark as Default**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72b25cf-4_Edit_Provider_Group.png",
        "4 Edit Provider Group.png",
        1062,
        509,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]