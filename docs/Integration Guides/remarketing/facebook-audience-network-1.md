---
title: Facebook Audience Network
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: Create Campaign with Facebook Audience
  pages:
    - type: basic
      slug: facebook-audience
      title: Facebook Audience
---
# Overview

The benefit of integrating your Facebook Ads account with CleverTap is getting per-campaign, per-user cost data and the average revenue for users acquired via that campaign. This will help you understand the cost of a campaign versus the revenue earned with it.

# Step 1: Get Your Facebook Ads Account ID
  * Log in to your [Facebook Ads account](https://www.facebook.com/ads/manage/home/).
  * Go to “Settings”, and copy the Account ID visible under Account Information.


# Step 2: CleverTap Dashboard Steps
  * Log into your CleverTap Dashboard, and go to Settings -> Ad campaigns. If you have multiple CleverTap accounts, make sure that you’re using the correct one.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2d330c4-Facebook_remarketing_integration.png",
        "Facebook_remarketing_integration.png",
        1434,
        764,
        "#f5f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
  * Now paste the Account ID that you had copied in step #2, and hit “Connect”.

  * Press “Okay” when prompted by Facebook to give access to CleverTap.

Once the connect is successful, you should see the “Account connected successfully” message. The initial campaign data will start showing up in 2 hours, and is subsequently updated every 2 hours.

# Additional Notes

Please ensure that your Facebook Ad campaign links are tagged with the parameters below for them to show up in the Campaign dashboard:
  * wzrk_source=facebook
  * wzrk_campaign=<campaign_name>