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

The benefit of integrating your Facebook Ads account with CleverTap is getting per-campaign, per-user cost data and the average revenue for users acquired via that campaign. This helps you understand the cost of a campaign versus the revenue earned with it.

# Integrate Facebook Ads account

## Get Your Facebook Ads Account ID

1. Log in to your [Facebook Ads account](https://www.facebook.com/ads/manage/home/).
2. Navigate to *Settings*, and copy the *Account ID* visible under *Account Information*.

## CleverTap Dashboard Steps

1. Log into your CleverTap Dashboard, and navigate to *Settings* > *Channel* > *Remarketing*. 

> 📘 Users with Multiple CleverTap Accounts
>
> If you have multiple CleverTap accounts, check that you are using the correct account.

<Image title="2d330c4-Facebook_remarketing_integration.png" alt={1151} className="border" border={true} src="https://files.readme.io/3849a5b-2d330c4-Facebook_remarketing_integration.png" />

2. Paste the *Account ID* you copied in Step #1, and click **Connect**.
3. Click **Okay** when prompted by Facebook to give access to CleverTap.

Once the connection is successful, the *Account connected successfully* message displays. The initial campaign data will display in two hours and is subsequently updated every two hours.

# Additional Notes

Check that your Facebook Ad campaign links are tagged with the following parameters for them to show up in the *Campaign* dashboard:

* wzrk\_source=facebook
* wzrk\_campaign=\<campaign\_name>
