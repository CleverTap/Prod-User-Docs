---
title: Facebook Audiences Setup
excerpt: >-
  Understand how to integrate Facebook Audiences with CleverTap for runing
  marketing campaigns
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Connect and manage Facebook Ads accounts within CleverTap for remarketing. Once integrated, you can sync segments, configure default accounts, and take administrative actions such as reconnecting or removing accounts.

## Prerequisites

Before connecting a Facebook Ads account, check that the following requirements are met:

* **Facebook Business Manager Account**\
  Recommended for centralized management of assets such as WhatsApp Business Manager, Ads Manager, and Product Catalogs.

* **Active Ads Account**\
  The Facebook Ads account must be active and connected to the Business Manager Account.

* **Admin Access**\
  The connecting user must have administrative permission to access the ad account.

* **Custom Audiences Terms Acceptance**\
  The administrator must have accepted Facebook’s Custom Audiences [Terms of Service](https://business.facebook.com/ads/manage/customaudiences/tos) . If the default link does not load, append your Facebook Ad Account ID to the end of the URL as shown below:

```html
<https://business.facebook.com/ads/manage/customaudiences/tos/?act=>\<your_ad_account_id>
```

## View and Manage Connected Ad Accounts

This section displays all Facebook Ads accounts that have been linked to your CleverTap project. You can view key account details, check connection status, and perform actions such as setting a default account or removing an existing one.

To access this section, go to *Settings > Channels > Remarketing > Facebook*.

* **Account Name**: The display name of the connected Facebook Ads account.
* **Status**: Indicates whether the account is currently *Connected* or *Disconnected*.
* **Added on**: The date the account was linked to CleverTap.
* **Added by**: The email ID of the user who connected the account.

Available actions include:

* **Set as Default**: Designate the account for campaign delivery by default.
* **Delete**: Remove the account from CleverTap.

## Connecting a Facebook Ads Account

To run Facebook remarketing campaigns directly from CleverTap, you must first grant CleverTap access to your Facebook Ads account. This enables seamless audience sync and campaign delivery from within the dashboard.

To link a new account:

1. Go to *Settings > Channels > Remarketing > Facebook*.
2. Click **Connect Ad Account**. 

   <Image alt="Connect Ad Account" align="center" border={true} src="https://files.readme.io/8718919f886da342e7473b6fdc96ad2b98de2231ee8df742d7eb3aa39162ae4f-image_53.png">
     Connect Ad Account
   </Image>
3. Review the prerequisites and select **Continue to Authorize**.
4. Log in to Facebook and grant CleverTap access to your Ads accounts. 

   <Image alt="Connect CleverTap Ad Account on Facebook" align="center" border={true} src="https://files.readme.io/71e314b2a21734a82d48474ec5e63a06f3e5765f95195f780580bb9f04b8d624-image_57.png">
     Connect CleverTap Ad Account on Facebook
   </Image>
5. After authorization, return to the CleverTap dashboard. The connected account will appear on the listing page. 

   <Image alt="Connected Ad Account on CleverTap" align="center" border={true} src="https://files.readme.io/e83e7524184ecabc055cfa8c2b1031cbde505892ad934708456fa6103b1ad1a9-image_58.png">
     Connected Ad Account on CleverTap
   </Image>

## Reconnecting an Account

Authentication tokens expire periodically for security reasons. When this happens, the account’s **Status** will display as *Disconnected*.

To restore the connection, click ![](https://files.readme.io/270abb959e6febec395aefee567f56e73f74aac0f129a5705c276f3db3f513d3-image_60.png) and repeat the authorization flow to re-establish access. This ensures continued security while maintaining seamless integration. 

<Image alt="Reconnecting Ad Account" align="center" border={true} src="https://files.readme.io/9762a5fc6e3b7732a0fdc7ef551afee66f8dca5f648e7a454fa5c8e6f10df969-image_59.png">
  Reconnecting Ad Account
</Image>

## Deleting an Account

To remove a linked Facebook Ads account:

1. Navigate to *Settings > Channels > Remarketing > Facebook*.
2. Click the **Trash** icon next to the account.
3. Confirm by clicking **Delete** in the dialog box. 

   <Image alt="Delete Ad Account" align="center" border={true} src="https://files.readme.io/de654fcae39d2336700df74896bb99aa5cdf08c48ff318d7513ead7f61c8eece-image_61.png">
     Delete Ad Account
   </Image>

## Setting a Default Account

Only one Facebook Ad account can be set as the default for campaign delivery. To set the ad account:

1. On the listing page, locate the desired account.
2. Click **Set as Default**.

This account will be used automatically during campaign creation unless a different one is manually selected. 

<Image alt="Set as Default" align="center" border={true} src="https://files.readme.io/1437e3f9248e90f1016668deb26b8d70fb8193eb54e650a3e23581d6f95eeee6-image_61.png">
  Set as Default
</Image>