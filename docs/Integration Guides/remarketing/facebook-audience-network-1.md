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

The benefit of integrating your Facebook Ads account with CleverTap is getting per-campaign, per-user cost data and the average revenue for users acquired via that campaign. This helps you understand the cost of a campaign versus the revenue earned with it.

To integrate your Facebook Ads account, perform the following steps:

# Step 1: Get Your Facebook Ads Account ID

* Log in to your [Facebook Ads account](https://www.facebook.com/ads/manage/home/).
* Navigate to *Settings*, and copy the *Account ID* visible under *Account Information*.

# Step 2: CleverTap Dashboard Steps

* Log into your CleverTap Dashboard, and navigate to *Settings* > *Channel* > *Remarketing*. 

> 📘 Users with Multiple CleverTap Accounts
>
> If you have multiple CleverTap accounts, make sure that you are using the correct one.

<Image title="2d330c4-Facebook_remarketing_integration.png" alt={1151} className="border" border={true} src="https://files.readme.io/3849a5b-2d330c4-Facebook_remarketing_integration.png" />

* Paste the *Account ID* you copied in Step #1, and click **Connect**.
* Click **Okay** when prompted by Facebook to give access to CleverTap.

Once the connection is successful, the "Account connected successfully” message displays. The initial campaign data will display in two hours and is subsequently updated every two hours.

# Additional Notes

Ensure your Facebook Ad campaign links are tagged with the parameters below for them to show up in the *Campaign* dashboard:

* wzrk\_source=facebook
* wzrk\_campaign=\<campaign\_name>
