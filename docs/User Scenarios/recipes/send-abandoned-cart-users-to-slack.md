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

<Image title="s1.png" alt={1437} className="border" border={true} src="https://files.readme.io/a2ba51d-s1.png" />

# Step 2: Create a CleverTap Webhook Campaign

In your CleverTap Dashboard, under the "Engage" section you will find "Webhooks" as an option, create a new "Live User Segment" webhook, which targets inaction within time. Launch that campaign.

<Image title="s2.png" alt={1237} className="border" border={true} src="https://files.readme.io/c505ca4-s2.png" />

<Image title="s3.png" alt={330} className="border" border={true} src="https://files.readme.io/bc6569e-s3.png" />

# Step 3: Open Slack

In the Slack channel that you have specified, you will see messages pop-up with details on users who are abandoning high value transactions in your app.

<Image title="s4.png" alt={1219} className="border" border={true} src="https://files.readme.io/3ccdfae-s4.png" />
