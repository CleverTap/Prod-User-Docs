---
title: Setup
excerpt: Understand how to set up WhatsApp as a channel for your marketing campaigns
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: >-
    Refer to the pages listed below to learn more about the following WhatsApp
    sections:
---
# Overview

CleverTap offers WhatsApp as a paid add-on, allowing businesses to communicate with their customers effectively and efficiently.

To enable WhatsApp as a communication channel for your organization, you need to raise a request on [sales@clevertap.com](mailto:sales@clevertap.com).

# Getting Started

To use WhatsApp as a channel for your marketing campaigns and customer journeys, you need access to the WhatsApp Business API.\
CleverTap currently supports no-code integration with the following partners:

* Gupshup
* Nexmo
* ValueFirst
* Exotel

If you have access to the WhatsApp Business API through a service provider that is not currently supported by CleverTap, you can use CleverTap's [Generic WhatsApp APIs](https://docs.clevertap.com/docs/generic-whatsapp) to integrate your service provider with CleverTap. 

Alternatively, you can request your service provider to become a supported WhatsApp partner by integrating CleverTap's generic API with their native messaging APIs using middleware.

By enabling your service provider with CleverTap, you'll be able to utilize all the features and benefits offered by our platform.

> 📘 Note
>
> To access the WhatsApp Business API directly through CleverTap, refer to the detailed [integration document](https://docs.clevertap.com/docs/clevertap-bsp).

# Set Up WhatsApp Service Provider

To set up a WhatsApp service provider, perform the following steps:&#x20;

1. From the dashboard, navigate to _Settings_ > _Channels_ > _WhatsApp_.
2. Click **+ Provider** to add a provider.&#x20;

   <Image src="https://files.readme.io/4952483712112f0330a3895e5ea372d73fab32e1fe325b73a2801f49d35047c7-teams.png" align="center" caption="Add Provider" border={true} />


3) Add the WhatsApp service provider's information.
4) If Teams is enabled for your account, select one or more teams in the _Teams_ field. The _Teams_ field is required. For WhatsApp Direct, the field appears on the _CleverTap BSP Setup_ screen, and you complete onboarding as described in [CleverTap BSP](https://docs.clevertap.com/docs/clevertap-bsp). For details, refer to [Teams for WhatsApp Providers](#teams-for-whatsapp-providers).
5) Click **Send Test WhatsApp** to check if the provider has been set up correctly and can send WhatsApp messages.

<Image title="Save Provider Details" alt="Click the Save button to save the WhatsApp provider details." align="center" border={true} src="https://files.readme.io/043a64e-Save_Provider_Details.png">
  Save Provider Details
</Image>

6. Click **Save.**

Refer to the following integration guides for more details:

* [Adding Gupshup as a provider](https://docs.clevertap.com/docs/gupshup).
* [Adding Nexmo as a provider](https://docs.clevertap.com/docs/nexmo-whatsapp).
* [Adding ValueFirst as a provider](https://docs.clevertap.com/docs/valuefirst-digital-whatsapp).
* [Adding Exotel as a provider](https://docs.clevertap.com/docs/exotel-whatsapp). 

# Provider Operations

This section describes the various user actions available across the available WhatsApp service providers.

<Image title="Service Provider Operations" alt="The image represents the WhatsApp service provider operations available for the end users." align="center" border={true} src="https://files.readme.io/eaa04e2-Service_Provider_Operations.png">
  Service Provider Operations
</Image>

## Edit Settings

You can edit the WhatsApp provider settings to update the provider configurations. Follow the steps to edit provider settings:

1. From the CleverTap dashboard, navigate to _Settings_ > _Channels_ > _WhatsApp_.
2. Open the tab for your integration, and then open the provider settings:
   - **WhatsApp Connect:** On the **WhatsApp Connect** tab, click the ellipsis next to the provider, and then select **Edit settings**. The provider credentials window displays.
   - **WhatsApp Direct:** On the **WhatsApp Direct** tab, click the name of the WABA. On the **Mobile Number** tab, click the ellipsis next to the mobile number, and then select **Edit settings**. The _Configuration Details_ drawer opens.
   - **WhatsApp Direct with MNS:** On the **WhatsApp Direct** tab, click the ellipsis next to the WABA, and then select **View Details**. The _WhatsApp Business Account Overview_ popup opens.
3. Update the required information.
4. If Teams is enabled for your account, click the _Teams_ field, select or clear teams, and then click **Apply**. For the rules, refer to [Teams for WhatsApp Providers](#teams-for-whatsapp-providers).
5. For WhatsApp Connect, click **Send Test WhatsApp** to check that the provider is working correctly.
6. Click **Save**.


   <Image src="https://files.readme.io/3e4692b785d6fa6bc37658f171e1a994d85e2b535336fe6e33e7f06502a4771f-edit_config.png" align="center" width="60%" caption="Edit Settings" border={true} />


<Callout icon="🚧" theme="warn">
  ### Warning

  Removing a team from a provider stops the running and scheduled campaigns and the live journeys that belong to that team and use the provider. CleverTap lists the affected campaigns and journeys, and asks you to confirm before it saves the change. You cannot resume a stopped campaign or journey, but you can clone it.
</Callout>

## Archive Service Providers

You can archive any of the current WhatsApp service providers from the settings. Archiving the WhatsApp service provider stops any active Campaigns or Journeys for this provider. The archived provider will not be available for use in the future. 

Follow the steps to archive a WhatsApp service provider:

* From the CleverTap dashboard, navigate to _Settings_ > _Channels_ > _WhatsApp_ > Providers tab.
* Click the ellipsis next to the provider.
* Select _Archive_ from the list.

## Delete Service Providers

You can delete any of the current WhatsApp service providers from the settings. Deleting the WhatsApp service provider will remove all existing data from our system and stop any active Campaigns or Journeys. The deleted provider will not be available for use in the future.

Follow the steps to delete a WhatsApp service provider:&#x20;

1. From the CleverTap dashboard, navigate to _Settings_ > _Channels_ >_WhatsApp_ > Providers tab.
2. Click the ellipsis next to the provider.
3. Select _Delete_ from the list.&#x20;

## Teams for WhatsApp Providers

With [Teams](https://docs.clevertap.com/docs/teams-setup#overview) enabled, you assign each WhatsApp provider to one or more teams, and only the members of those teams can view and edit the provider.

- Teams apply to both WhatsApp Connect and WhatsApp Direct.
- Teams control access only. Message delivery and provider credentials remain unchanged.

Teams apply to each mobile number. For a WABA that uses Multiple Number Support (MNS), teams apply to the entire WABA.

<Image src="https://files.readme.io/626b3c132258751a8272bf26d27235b410c0457325a7bb5f6edb69171f703095-TEAMS_DROP_DOWN.png" align="center" caption="Select Teams" border={true} />

<Callout icon="📘" theme="info">
  ### Note

  Teams for WhatsApp providers is available through a gradual rollout. To enable this feature for your account, contact your Customer Success Manager or raise a support ticket.
</Callout>

For information on how teams scope what you see across the dashboard, refer to [Working across Teams](https://docs.clevertap.com/docs/teams-setup#working-across-teams) and [Impact of Teams Across Dashboard](https://docs.clevertap.com/docs/teams-setup#impact-of-teams-across-dashboard). For how teams apply to campaigns and journeys, refer to [Using Teams in Engagements](https://docs.clevertap.com/docs/using-teams-in-engagements).

### Provider Access with Teams

Teams decide which providers you see on the WhatsApp provider configuration page and in the rest of the dashboard, based on the teams to which you belong.

Consider the following example:

- Provider 1 is assigned to Team A.
- Provider 2 is assigned to Team B.
- Provider 3 is assigned to both Team A and Team B.
- The admin, User 1, and User 2 open _Settings > Channels > WhatsApp_. User 1 belongs to Team A, and User 2 belongs to Team B.

| User   | Teams                    | Providers on the provider configuration page |
| ------ | ------------------------ | -------------------------------------------- |
| Admin  | Not restricted to a team | Provider 1, Provider 2, and Provider 3       |
| User 1 | Team A                   | Provider 1 and Provider 3                    |
| User 2 | Team B                   | Provider 2 and Provider 3                    |

User 1 does not see Provider 2, and User 2 does not see Provider 1, because neither user belongs to a team assigned to the provider. The admin sees all the providers.

The same scope applies wherever a provider appears. User 1 can select only Provider 1 and Provider 3 in the provider dropdown of a campaign or journey. When User 1 edits Provider 3, the _Teams_ field lets User 1 add or remove only Team A. Team B appears greyed out, and it stays assigned.

### Rules for the Teams Field

The _Teams_ field follows these rules when you add or edit a provider.

- You must select at least one team.
- You can select more than one team.
- You can add or remove only the teams to which you belong. Other teams appear greyed out, and you cannot change them.

### Manage Teams for Multiple Number Support

When a WABA uses MNS, you manage teams once for the entire WABA instead of for each mobile number.

|                    | MNS Off                                                 | MNS On                                 |
| ------------------ | ------------------------------------------------------- | -------------------------------------- |
| Teams apply to     | Each mobile number                                      | The entire WABA                        |
| Edit teams         | The _Configuration Details_ drawer of the mobile number | The **View Details** popup of the WABA |
| Effect of a change | Applies to that number only                             | Applies to all numbers under the WABA  |

For a WABA that uses MNS, the _Teams_ field in the _Configuration Details_ drawer of a mobile number is read-only, and a new number that you add inherits the teams of the WABA. To enable MNS for a WABA, contact your Customer Success Manager or raise a support ticket.

<Callout icon="🚧" theme="warn">
  ### Warning

  When MNS is enabled for a WABA, CleverTap stops the live campaigns and journeys that use the mobile numbers under that WABA. You cannot resume a stopped campaign or journey, but you can clone it.
</Callout>

### Select Providers in Campaigns and Journeys

Campaigns, templates, and journeys list only the providers that you can access through your teams, in addition to the [team-based scoping of engagements](https://docs.clevertap.com/docs/using-teams-in-engagements#access-and-roles).

- The provider dropdown in the campaign and journey builders shows only the providers that belong to your teams.
- CleverTap does not let you save a campaign or journey with a provider that you cannot access.
- The public Campaign API does not enforce team-based provider selection.

## Opt-in Users into WhatsApp

Most people do not like receiving unsolicited messages on WhatsApp. Therefore, it is important for you to explicitly request permission before sending messages to your users on their WhatsApp account. 

By default, CleverTap keeps all the profiles opted out of WhatsApp. To opt-in profiles, update the profile using the following code:

```json
"MSG-whatsapp":true
```

You have the following two ways to opt-in users for WhatsApp:

* [Opt-in via updating the user's profile property](https://developer.clevertap.com/docs/concepts-user-profiles#section-updating-the-user-profile). 
* [Opt-in via the API profile update](https://developer.clevertap.com/docs/upload-user-profiles-api). 

## Message Templates in WhatsApp

WhatsApp restricts brand-initiated messages (the messages that you send via campaigns) to pre-approved templates. You can fill in the variables in the templates to personalize a message.

For example:

_Hello \{\{1\}\}, Congratulations on your ticket booking. Here is your ticket number: \{\{2\}\}. Please ensure you visit us on \{\{3\}\}. Enjoy your experience._

The variables _\{\{1\}\}_ or _\{\{2\}\}_ or _\{\{3\}\}_ can be replaced by a text of your choice. You can use CleverTap's event and profile personalization to personalize the message for your audience.

To set up a message template, follow the steps listed under [Sending Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/creation) documentation on Facebook.

## Configure Message Templates

All your message templates must be approved by WhatsApp. At CleverTap, we help you with the verification. For more information on how to create message templates, refer to the [Creating Message Templates](https://developers.facebook.com/docs/whatsapp/message-templates/creation/) documentation by Facebook.

The media message templates allow you to expand the content you can send to the recipients beyond the standard messages. The template is organized primarily into four sections - _Header_, _Body_, _Footer_, and _Buttons_.

Using this template, you can attach media files (image, video, document, location) within the **Header** along with the message body.

Additionally, WhatsApp also allows marketers to include **CTAs** or **Quick Reply** buttons in the text or media message templates for making the conversations more interactive.

* Call-to-Action (CTAs) — Enables the customer to make a phone call or visit a website.
* Quick Reply — Allows your customer to respond with a simple text message.

Once your interactive message templates have been created and approved, you can use them in notification messages as well as customer service/care messages.

The images below represent different templates that marketers can create for engaging their customers effectively.


<Image src="https://files.readme.io/fa88774-Templates.png" alt="2318" align="center" border={true} />


After your templates are verified, you can add them in the WhatsApp settings under the _Templates_ tab.

To use WhatsApp with CleverTap, it is important to copy the templates accurately in the settings by performing the following steps:

1. From the dashboard, navigate to _Account > Settings > Engage > Channels > WhatsApp_.
2. Click one of the Provider names.


<Image src="https://files.readme.io/c423fd6-image.png" alt="1894" align="center" border={true} />


3. Navigate to the **Templates** tab.
4. Click **+ Template** .


<Image src="https://files.readme.io/af37717-Screenshot_2021-09-21_at_8.37.29_PM.png" alt="2346" align="center" border={true} />


5. Now, enter the _Namespace_ for your template.

<Callout icon="🚧" theme="warn">
  ### Namespace Format

  When copying the message templates from the WABA dashboard, use the following format for the namespace: \<templat&#x65;_&#x6E;amespace>:\<templatename>. You can find the Namespace_ value from the _Message templates_ section on the WABA dashboard as shown in the image below:
</Callout>


<Image src="https://files.readme.io/f755093-namespace.png" alt="2879" align="center" border={true} />


Following is an example of _Namespace_ format


<Image src="https://files.readme.io/d7f6250-Screenshot_2021-09-23_at_1.01.12_PM.png" alt="1354" align="center" border={true} />


6. Copy and save the approved message templates from your WABA dashboard.


<Image src="https://files.readme.io/5729acc-Whatsapp_interactive.png" alt="1452" align="center" border={true} />


7. Click **Save Template** to save the message template.

<Callout icon="📘" theme="info">
  ### Language Support

  * For Vonage (Nexmo), if you don't find the required language support on the CleverTap dashboard, contact our support team to enable the required language for your account.
  * Gupshup supports and handles all languages automatically, hence you do not need to add them on the CleverTap dashboard.
</Callout>

## Enable Click Tracking for WhatsApp

You can track button clicks from your WhatsApp message. To enable click tracking:

1. From the dashboard, navigate to *Account > Settings > Engage > Channels > WhatsApp*. 
2. Click one of the Provider names.
3. Click **+ Template** .
4. Add a CTA button. 
5. Select the URL type. 
   1. Static : Add a static link.
   2. Dynamic: Add a dynamic link. 
   3. CleverTap Link Tracking : Add the link for tracking user clicks. For example, [www.ct1.io/\{\{1}}](http://www.ct1.io/\{\{1}}). The URL will be automatically displayed for CleverTap BSP.

# FAQs

### Why can I not see a WhatsApp provider?

You see only the providers assigned to a team to which you belong. To get access, ask an admin to [assign you to the team](https://docs.clevertap.com/docs/teams-setup#assign-teams-to-existing-users), or ask a team member to assign the provider to one of your teams.

### Why can I not edit the Teams field for a WhatsApp Direct number?

The WABA of the number uses MNS, so you manage teams at the WABA level. To change the teams, open the **View Details** popup of the WABA on the **WhatsApp Direct** tab.

<br />