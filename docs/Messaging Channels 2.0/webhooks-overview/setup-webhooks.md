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
To set up your first CleverTap webhook, perform the following steps:

1. Navigate to *Settings* > *Engage* > *Channels* > *Webhooks*.
2. Click **+ Add Webhook**. 
3. Update the webhook template.
4. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c5ed2e7-Campaign_Webhooks_add_webhook_param.png",
        "Campaign_Webhooks_add_webhook_param.png",
        606,
        875,
        "#f6f7f9"
      ],
      "sizing": "smart",
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Add a webhook name and destination URL. If you currently do not have an endpoint created on your server to receive the webhook, you can use www.Requestbin.com to create an endpoint for testing purposes.",
  "title": "Testing Considerations"
}
[/block]
# Codeless Integration 

Another option besides setting up an endpoint on your server to listen for CleverTap webhooks is using a workflow automation tool, such as Tray.io or Zapier. These tools can help integrate a CleverTap webhook without any code and then send these notifications to other systems such as Slack. If you are interested in learning more, we have [a guide](https://docs.clevertap.com/docs/send-abandoned-cart-users-to-slack) that walks through sending a CleverTap webhook to Slack via Tray.io.