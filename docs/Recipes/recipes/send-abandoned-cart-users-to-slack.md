---
title: Send Abandoned Cart Users to Slack
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
Whenever a user abandons their cart during a high value transaction, you may want to pull that customers data into Slack so that you can call the customer up.

Using the CleverTap Webhook feature, you can pull data from your application into a Slack channel.

# Step 1: Create a Webhook Endpoint

You first have to create a webhook endpoint, and save it in your CleverTap Account. 

You can do this using any public service like tray.io or you can ask your IT Admin for one. You can read [this doc](https://clevertap-developer-docs.readme.io/v1.0/docs/webhooks) to see the things you need to keep in mind while creating the endpoint.

To set up a webhook endpoint with Tray.io, here are the steps
  * Navigate to [Tray.io](https://tray.io/)
  * Click sign up 
  * Click create workflow
  * Pick "webhooks" as the trigger
  * Select "Slack" as the connector 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a2ba51d-s1.png",
        "s1.png",
        1437,
        795,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 2: Create a CleverTap Webhook Campaign

In your CleverTap Dashboard, under the "Engage" section you will find "Webhooks" as an option, create a new "Live User Segment" webhook, which targets inaction within time. Launch that campaign.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c505ca4-s2.png",
        "s2.png",
        1237,
        426,
        "#fafbfb"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bc6569e-s3.png",
        "s3.png",
        330,
        327,
        "#f6f7f8"
      ],
      "border": true
    }
  ]
}
[/block]
# Step 3: Open Slack

In the Slack channel that you have specified, you will see messages pop-up with details on users who are abandoning high value transactions in your app.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3ccdfae-s4.png",
        "s4.png",
        1219,
        268,
        "#f7f7f7"
      ],
      "border": true
    }
  ]
}
[/block]