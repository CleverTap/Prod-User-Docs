---
title: VTEX
excerpt: Learn how to integrate your VTEX store with CleverTap.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
## Overview

The CleverTap VTEX Pixel app provides an easy, no-code way to integrate your VTEX store within minutes. All you require is a CleverTap account, and you can have a seamless flow of events and user data from your VTEX store. You can also send personalized messages to your users through channels such as Web Push, Web Pop-up, Web Inbox, and Web Native Display.

## Integrate VTEX

After you install the CleverTap app, log in to the VTEX Admin and follow the steps below to complete the integration.

The integration includes the following steps:

* Install and Connect App
* Configure App Settings
* Customize Events

## Install and Connect App

Contact your CleverTap Success Manager to install the app.  Once installed, the app appears on the My Apps page under the **Installed** tab.

To verify the installation, navigate to **Apps > My Apps** from the VTEX Admin. The CleverTap app will be listed under the **Installed** tab.


<Image src="https://files.readme.io/40ef06579972af98967fb3dc6b1ddd610c236028f578e709fa9e120292b90d3b-image.png" alt="Check installed CleverTap app" align="center" caption="Check for the installed CleverTap app" border={true} />


<br />

## Configure App Settings

After installing the app, you must configure it with your CleverTap account credentials.

1. Navigate to **Apps > My Apps** from the VTEX Admin.
2. Locate the **CleverTap** app tile on the **Installed** tab.
3. Click **Settings** on the app tile. The app settings page opens.
4. Enter the following details:

* **CleverTap Project ID**: Enter the [Project ID ](https://developer.clevertap.com/docs/api-quickstart-guide#get-clevertap-account-credentials-to-authenticate-api-requests)of your CleverTap account. You can find this in your CleverTap dashboard under _Settings > Project_.
* **CleverTap Account Passcode**: Provide the authentication passcode for your CleverTap account. This is available in your CleverTap dashboard under _Settings > Project_.
* **CleverTap Region**: Specify the data center region of your CleverTap account (for example: `us1`, `in1`, `sg1`, `sk1`). You can find this in your CleverTap dashboard. For more information, refer to [Region Codes](https://developer.clevertap.com/docs/web-quickstart-guide#add-region-code).

5. Click **Save** once all credentials have been entered.

## Customize Events

After configuring your credentials, you can select which VTEX store events to track and send to CleverTap.

1. On the CleverTap app Settings page, scroll down to view the available VTEX events.


<Image src="https://files.readme.io/93b58d6c1a2a4bbf941f5c408f711e8e470adee262d04c79b5d3923139673e83-image.png" alt="Select VTEX events" align="center" caption="Select VTEX events" border={true} />


2. Select the events you want to track. Common VTEX events include product views, add to cart, checkout started, and order placed.
3. Click **Save** to apply your configuration.

Your VTEX store is now connected to your CleverTap account and will begin sending the selected events and profile data. For more information about VTEX events, refer to [VTEX events](/docs/vtex-advanced-customization#events).

## Create Web Campaigns

The CleverTap VTEX Pixel app provides support for web channels such as Web Push, Web Pop-up, and Web Exit Intent without the need for any manual code integration.

To create a Web campaign:

1. From the CleverTap dashboard, navigate to _Campaigns_.
2. Click _+ Campaign_.
3. Create a _Web Push_\*, _Web Pop-up_, _Web Native Display_, or _Web Inbox_ campaign to engage your users.