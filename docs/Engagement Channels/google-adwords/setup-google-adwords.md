---
title: Setup
excerpt: >-
  Understand how to integrate Google Ads with CleverTap to be able to run
  marketing campaigns
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Refer to the pages listed below to learn more about the following Google Ads
    sections:
---
# Overview

Connect and manage multiple Google Ads accounts within CleverTap for remarketing. Once integrated, you can sync segments, configure a default account, and take administrative actions such as reconnecting or removing accounts. Remarketing with Google Ads lets you re-engage users outside your app or website by showing ads to specific user segments across the Google Search Network, YouTube, and Gmail.

## Prerequisites

Before connecting a Google Ads account, check that the following requirements are met:&#x20;

- **Google Ads Account ID**<br />The Customer ID of the Google Ads account to be connected should be available to identify the account in the picker during setup. The ID is available at the top right of the Google Ads dashboard. For more information, refer to [Google Support](https://support.google.com/ads/express/answer/6083253).
- **Admin Access**<br />The connecting user must have administrative permission on the Google Ads account. Only a user with Admin rights on the Google Ads platform can integrate Google Ads and CleverTap accounts. Any admin-authorized account can be connected; it does not need to belong to the same Manager account as CleverTap.
- **Customer Match Eligibility**<br />The Google Ads account must be eligible to use Customer Match, with a good history of policy compliance. If your account is not eligible, audience uploads fail with an _Advertiser not Whitelisted_ error. Eligibility is controlled by Google, not CleverTap. For the criteria your account must meet, refer to the [Customer Match policy](https://support.google.com/adspolicy/answer/6299717).
- **Manager Account (Optional)**<br />If your Google Ads account is managed through a [Manager Account](https://ads.google.com/intl/en_in/home/tools/manager-accounts/), you can provide the Manager account ID to link it during setup.

## Connect a Google Ads Account

To run Google Ads remarketing campaigns directly from CleverTap, you must first grant CleverTap access to your Google Ads account. This enables audience sync and campaign delivery from within the dashboard. You can connect more than one Google Ads account, and each connected account appears on the listing page.

To link a new account:

1. Go to _Settings > Channels > Remarketing > Google_.
2. Click **Connect Ad Account**.
3. In the Google sign-in window, sign in and grant CleverTap access to your Google Ads accounts.

\[Image: @jithendra]

4. After authorization, CleverTap displays the Google Ads accounts you have access to. Use the search box to find an account by name or ID if needed.
5. Select the accounts you want to connect, and then click **Connect**.
6. The connected accounts appear on the listing page.

<Callout icon="🚧" theme="warn">
  ### Verify Credentials

  If you have multiple CleverTap accounts, check that you are using the correct account. Similarly, when selecting accounts in the picker, verify you are connecting the correct Google Ads accounts.
</Callout>

## Map Properties

After you connect your Google Ads account, configure the mapping between Google's export attributes and your CleverTap user properties. Mapping ensures that the correct profile data is exported to Google when creating a remarketing audience. If an attribute is not mapped to a CleverTap user property, its column is blank in the exported audience file, and the option appears disabled in the campaign setup flow.

<Callout icon="📘" theme="info">
  ### Note

  If the _CleverTap user properties_ are not mapped in _Settings > Channels > Remarketing > Google > Map Properties_, these options appear disabled and their columns are blank in the exported audience file.
</Callout>

### Assign User Properties

This section assigns CleverTap user properties to Google's export attributes so that the correct data is included when creating audiences.

1. Click **Map Properties**.
2. For each export attribute, open the drop-down in the **Mapped User Property** column and select the CleverTap user property that contains the relevant data. You can choose from system properties or any custom properties already available in your CleverTap account.
3. Click **Save**.

System properties are used by default for Email and Phone unless you assign a different custom property to them. Mapped properties are available for selection during campaign creation. Unmapped properties appear disabled in the campaign setup flow.

<Callout icon="📘" theme="info">
  ### Note

  The Map Properties panel lists export attributes for both Facebook and Google Ads audiences. Google Ads supports only the attributes listed in the following table. Attributes that Google Ads does not support are not exported, even if they are mapped.
</Callout>

### Supported Attributes for Google

The following table lists the export attributes supported by Google and their descriptions. Use it as a reference when selecting which CleverTap user properties to map.

| Export Attribute           | Description                                                                 |
| -------------------------- | --------------------------------------------------------------------------- |
| Email                      | User's email address                                                        |
| Phone                      | User's phone number                                                         |
| First Name                 | User's first name                                                           |
| Last Name                  | User's last name                                                            |
| Country                    | User's country (ISO 3166-1 alpha-2 code)                                    |
| ZIP                        | User's postal or ZIP code                                                   |
| Google Advertising ID      | Unique, resettable identifier assigned to a device for advertising purposes |
| Identifier for Advertisers | Unique identifier assigned to a device for advertising purposes             |

## Reconnecting an Account

Authentication tokens expire periodically for security reasons. When this happens, the account's **Status** displays as _Disconnected_.

To restore the connection, click the **Reconnect** icon on the disconnected account's row and complete the authorization flow again to re-establish access. Reconnecting uses the same authorization flow as connecting a new account. This maintains a secure, uninterrupted integration.

\[Image: google reconnect icon on a disconnected account]

## Disconnecting an Account

To remove a linked Google Ads account:

1. Navigate to _Settings > Channels > Remarketing > Google_.
2. Click the **Disconnect** icon next to the account.
3. In the **Disconnect Google Account** dialog, click **Disconnect** to confirm.

<Callout icon="🚧" theme="warn">
  ### Note

  Disconnecting an account makes it unavailable for future engagements. Any current engagements using this account are stopped or paused.
</Callout>

\[Image: google disconnect confirmation dialog]

## Setting a Default Account

Only one Google Ads account can be set as the default for campaign delivery. To set the default account:

1. On the listing page, locate the account you want to set as the default.
2. Click **Set as Default**.

This account is pre-selected as the Export destination during campaign creation, unless you select a different one for the campaign.

The **Set as Default** option appears only for connected accounts that are not currently the default.

\[Image: google set as default]
