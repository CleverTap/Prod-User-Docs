---
title: Setup
excerpt: Understand how to set up SMS as a channel for your marketing campaigns.
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

This document outlines the steps to configure and manage SMS providers within CleverTap. Depending on whether your SMS provider is pre-integrated with CleverTap, you can choose between SMS Direct and SMS Connect for seamless setup.

**SMS Direct**: This option is for users with SMS providers already integrated with CleverTap. To configure with pre-integrated providers, navigate to *Settings > Channels > SMS > SMS Direct*.

**SMS Connect**: This option enables users with SMS providers that are not integrated with CleverTap to connect and configure external providers manually. To get started, navigate to *Settings > Channels > SMS > SMS Connect*.

# Configure a New Provider

To add a new SMS provider, perform the following steps:

1. From the dashboard, navigate to _Settings_ > _Channels_ > _SMS_ and Select either SMS Connect or SMS Direct based on the Provider status.
2. Click **+ Add Provider**.&#x20;

   <Image src="https://files.readme.io/2718d5aeb030ec845749eda6d3a54c7001195fe26ca93ed6c84f9d7465bb5795-sms_teams.png" align="center" caption="Add Provider" border={true} />


3) Enter all the required information.
4) If Teams is enabled for your account, click the _Teams_ field, select one or more teams, and then click **Apply**. The _Teams_ field is required. For details, refer to [Teams for SMS Providers](#teams-for-sms-providers).
5) Click **Save**.

Once the phone number is validated by the SMS service provider, you can send a test SMS to test the integration before you start creating SMS campaigns and journeys.


<Image src="https://files.readme.io/30118cb-sms_provider.png" alt="1088" align="center" caption="Provider Configuration" border={true} />

To learn more about integrating specific SMS service providers with CleverTap, refer to this [document](https://docs.clevertap.com/docs/sms-partners). 

# Edit Provider Details

To edit a *Provider*, perform the following steps:

1. Click the ellipsis next to the required provider from the _Providers_ tab.
2. Click **Edit settings** to update the provider details.
3. If Teams is enabled for your account, click the _Teams_ field, select or clear teams, and then click **Apply**. For the rules, refer to [Teams for SMS Providers](#teams-for-sms-providers).
4. Click **Save**.
   <Callout icon="🚧" theme="warn">
     ### Warning

     Removing a team from a provider stops the running and scheduled campaigns and the live journeys that belong to that team and use the provider. CleverTap lists the affected campaigns and journeys, and asks you to confirm before it saves the change. You cannot resume a stopped campaign or journey, but you can clone it.
   </Callout>

You can also mark a provider as default by selecting *Mark as Default* option available in the ellipsis next to a particular provider.

# Add a Provider Group

The failure of an SMS provider may affect your SMS campaigns, so it is always better to have another SMS provider. By grouping providers, you can provide your users with a seamless experience.

You can assign a preferred provider to send a message. A provider group is used based on its assigned priority for each message. If provider 1 is unavailable, then we attempt the message with provider 2, and so on. In the end, this ensures higher message deliverability for your campaigns.

> 📘 Provider Group Maximum
>
> Each provider group can have a maximum of 10 providers.

To create a provider group, perform the following steps:

1. From the dashboard, navigate to _Settings_ > _SMS_ > _Provider Groups_ tab.
2. Click **+Provider Group**.&#x20;

   <Image src="https://files.readme.io/c28a74189beadf28b92c3c48f7640682795a37379fbab749ed8dc5ec88b6fcce-sms_teams_provider_group.png" align="center" caption="Add Provider Group" border={true} />


3) Enter a _Group Name_.
4) If Teams is enabled for your account, click the _Teams_ field, select one or more teams, and then click **Apply**. The _Teams_ field is required. For details, refer to [Teams for SMS Providers](#teams-for-sms-providers).
5) Select the providers by priority.
6) Click **Save Provider Group**.&#x20;

   <Image src="https://files.readme.io/aca55ea243ea228cd381e89932320d004cd6e7b56cabe82d176510d1e3e2a972-save_provider_group.png" align="center" caption="Provider Group Details" border={true} />

## Edit a Provider Group

To edit a provider group, perform the following steps:

1. Click the ellipsis next to the required provider from the _Provider Groups_ tab.
2. Click **Edit settings** to add or remove providers or change the priority for any providers.
3. If Teams is enabled for your account, click the _Teams_ field, select or clear teams, and then click **Apply**. For the rules, refer to [Teams for SMS Providers](#teams-for-sms-providers).
4. Save your changes.

You can also mark a provider group as default by selecting the *Mark as Default* option available in the ellipsis next to a particular provider group.

## Teams for SMS Providers

With [Teams](https://docs.clevertap.com/docs/teams-setup#overview) enabled, you assign each SMS provider and provider group to one or more teams, and only the members of those teams can view and edit them.

Teams control access only. Message delivery and provider credentials remain unchanged.

<Callout icon="📘" theme="info">
  ### Note

  Teams for SMS providers is available through a gradual rollout. To enable this feature for your account, contact your Customer Success Manager or raise a support ticket.
</Callout>

For information on how teams scope what you see across the dashboard, refer to [Working across Teams](https://docs.clevertap.com/docs/teams-setup#working-across-teams) and [Impact of Teams Across Dashboard](https://docs.clevertap.com/docs/teams-setup#impact-of-teams-across-dashboard). For how teams apply to campaigns and journeys, refer to [Using Teams in Engagements](https://docs.clevertap.com/docs/using-teams-in-engagements).

### Provider Access with Teams

Teams decide which providers you see on the SMS provider configuration page and in the rest of the dashboard, based on the teams to which you belong.

Consider the following example:

- Provider 1 is assigned to Team A.
- Provider 2 is assigned to Team B.
- Provider 3 is assigned to both Team A and Team B.
- The admin, User 1, and User 2 open _Settings > Channels > SMS_. User 1 belongs to Team A, and User 2 belongs to Team B.

| User   | Teams                    | Providers on the provider configuration page |
| ------ | ------------------------ | -------------------------------------------- |
| Admin  | Not restricted to a team | Provider 1, Provider 2, and Provider 3       |
| User 1 | Team A                   | Provider 1 and Provider 3                    |
| User 2 | Team B                   | Provider 2 and Provider 3                    |

User 1 does not see Provider 2, and User 2 does not see Provider 1, because neither user belongs to a team assigned to the provider. The admin sees all the providers.

The same scope applies wherever a provider appears. User 1 can select only Provider 1 and Provider 3 in the provider dropdown of a campaign or journey. When User 1 edits Provider 3, the _Teams_ field lets User 1 add or remove only Team A. Team B appears greyed out, and it stays assigned. The same rules apply to provider groups.

### Rules for the Teams Field

The _Teams_ field follows these rules when you add or edit a provider or a provider group.

- You must select at least one team.
- You can select more than one team.
- You can add or remove only the teams to which you belong. Other teams appear greyed out, and you cannot change them.

### Select Providers in Campaigns and Journeys

Campaigns and journeys list only the providers that you can access through your teams, in addition to the [team-based scoping of engagements](https://docs.clevertap.com/docs/using-teams-in-engagements#access-and-roles).

- The provider dropdown in the campaign and journey builders shows only the providers that belong to your teams.
- CleverTap does not let you save a campaign or journey with a provider that you cannot access.
- The public Campaign API does not enforce team-based provider selection.

# FAQs

### Why can I not see an SMS provider?

You see only the providers assigned to a team to which you belong. To get access, ask an admin to [assign you to the team](https://docs.clevertap.com/docs/teams-setup#assign-teams-to-existing-users), or ask a team member to assign the provider to one of your teams.