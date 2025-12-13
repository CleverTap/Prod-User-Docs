---
title: Nexmo_integration_WIP
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

CleverTap supports sending and receiving messages. The primary vendor CleverTap uses in the backend is Nexmo WhatsApp API. Contact our sales team at [sales@clevertap.com](mailto:sales@clevertap.com) to enable WhatsApp for your organization. Follow these steps after you have created an account on Nexmo:

# Add Nexmo

1. Navigate to *Settings> Channels > WhatsApp* to add Nexmo as the Provider from the CleverTap dashboard.
2. Click **+Providers**.  Nexmo is the default provider.

<Image title="Whatsapp_Nexmo_Setup.png" alt={596} className="border" border={true} src="https://files.readme.io/e3455eb-Whatsapp_Nexmo_Setup.png" />

3. Enter the required credentials:

* Nickname: Enter the nickname for this set of credentials.
* API Key: {user["Need info"]}
* Secret Key: {user["Need info"]}
* App name:  Enter the App name from the Nexmo dashboard.
* Mobile Number: Enter either a Nexmo phone number or a shortcode. You can enter phone numbers or shortcodes listed under the *Nexmo dashboard > Numbers > Your Numbers*.
* App ID:  Enter the App name from the Nexmo dashboard.
* Facebook URL: Enter the Facebook URL from the Gupshup dashboard.
* Private key:

> 📘 Auto Reply Checkbox
>
> Select the checkbox if you want to set auto-replies for users who are not tracked in CleverTap.

4. Click **Save**.

## Select Template

The *WhatsApp Business Manager* account must approve all your messaging templates. You can then add the whitelisted templates for your messages from the CleverTap dashboard.

1. From the *Templates* tab, and click **+Template**.

![883](https://files.readme.io/55f6bda-Whatsapp_Nexmo_Template_main.png "Whatsapp_Nexmo_Template_main.png")

The Add message template window displays. 

<Image title="Whatsapp_Nexmo_Template.png" alt={386} className="border" border={true} src="https://files.readme.io/622f441-Whatsapp_Nexmo_Template.png" />

2. Enter the template namespace.
3. Enter the template massage.
4. Select the language. 
5. Select an *Image, Video, Document,* or *Location* from the *Attachment type* list.  
6. Click Save. 

# Manage Users

1. Allow user Opt-Ins via consent. \<\<Need more info here. How do we do that ?>>
2. For existing users, change the *Opt-In* flags for your end-users after they subscribe to WhatsApp alerts. Updating via API profile update helps, with `msg-whatsapp=true`. Do this at an Object ID level, and not at an Identity Level. \<\<Is this applicable for new users too ? >>
3. You can ensure that all new users that log in or sign up for WhatsApp alerts are marked as *Subscribed*.   Pass `MSG-whatsapp: TRUE` when calling the `Profile.Push` function during the Sign in/Sign-Up process. Check that you select the consent of the users. 
4. Perform WhatsApp warm up. Tiers have to be crossed, and it is called Initial Warm-Up by the Facebook team. {user["Need to clarify this sentence"]}
5. For any concerns specific to Nexmo that need redressal, contact Nexmo support at [support@nexmo.com](mailto:support@nexmo.com).
