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
  description: ''
---
# Overview

The benefit of integrating your Facebook Ads account with CleverTap is getting per-campaign, per-user cost data and the average revenue for users acquired via that campaign. This will help you understand the cost of a campaign versus the revenue earned with it.

# Step 1: Get Your Facebook Ads Account ID

* Log in to your [Facebook Ads account](https://www.facebook.com/ads/manage/home/).
* Go to “Settings”, and copy the Account ID visible under Account Information.

<Image title="Screen Shot 2019-07-23 at 3.38.46 PM.png" alt={800} className="border" border={true} src="https://files.readme.io/7a75b2d-Screen_Shot_2019-07-23_at_3.38.46_PM.png" />

# Step 2: CleverTap Dashboard Steps

* Log into your CleverTap Dashboard, and go to Settings -> Ad campaigns. If you have multiple CleverTap accounts, make sure that you’re using the correct one.

<Image title="fb-ads-1.png" alt={1406} className="border" border={true} src="https://files.readme.io/30143f2-fb-ads-1.png" />

<Image title="fb-ads-2.png" alt={1401} className="border" border={true} src="https://files.readme.io/94d8d5e-fb-ads-2.png" />

* Now paste the Account ID that you had copied in step #2, and hit “Connect”.

<Image title="fb-ads-3.png" alt={1405} className="border" border={true} src="https://files.readme.io/409dcc5-fb-ads-3.png" />

* Press “Okay” when prompted by Facebook to give access to CleverTap.

Once the connect is successful, you should see the “Account connected successfully” message. The initial campaign data will start showing up in 2 hours, and is subsequently updated every 2 hours.

# Additional Notes

Please ensure that your Facebook Ad campaign links are tagged with the parameters below for them to show up in the Campaign dashboard:

* wzrk\_source=facebook
* wzrk\_campaign=\<campaign\_name>
