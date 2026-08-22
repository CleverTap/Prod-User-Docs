---
title: Create Message
excerpt: Understand how to create a campaign for Facebook Audiences.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

CleverTap’s Facebook Remarketing integration enables you to run personalized ad campaigns on Facebook by exporting user segments directly to your connected Facebook Ads account. This guide walks you through the process of creating a remarketing campaign—from selecting a channel to defining your target audience and exporting it to Facebook. You can configure qualification criteria, apply user-level filters, define control groups, and set targeting caps to optimize campaign performance and reach.

## Create a Campaign

Follow these steps to create a new remarketing campaign on Facebook:

1. From the dashboard, navigate to _Campaigns_.
2. Click the **+ Campaign** button.

   <Image align="center" alt="Create Facebook Campaign" border={true} caption="Create Facebook Campaign" src="https://files.readme.io/f72801e97a4bfe63e6df5bde8b84c7230b7b6d4feaa9ac7215460ee50ba92860-image_62.png" />
3. From the _Messaging Channels_ list, select _Facebook_.

The campaign page will load.

<Image align="center" alt="Campaign Page" border={true} caption="Campaign Page" src="https://files.readme.io/3925573545ce2dd8160bf3cd54ae3406df236c24953ee196c799825ac20fa33d-screencapture-localhost-8083-WWW-WWW-WWRZ-campaigns-campaign-new-audiences-2025-06-02-15_59_03.png" width="65% " />

## Start Campaign Setup

The _Start here_ section displays the setup information.

**Qualification criteria**: Define the criteria for your target audience. You can deliver the Facebook ad based on the user's past or real-time behavior.

**Ad Account**: From the Ad Account drop-down, select the linked Facebook Ads account to which you want to export the audience.

**Set a Goal**: You can track campaign performance by defining a conversion goal. This helps measure how effectively the campaign achieves the intended outcome. For example, you may choose to track users who made a purchase within five days of the campaign launch. This step is optional.

<Image align="center" alt="Start Campaign Setup" border={true} caption="Start Campaign Setup" src="https://files.readme.io/01c0b107b24085715cf44f0e59dbd89f53adf6ce2b28607879cc3ac83cc9d48a-image_63.png" />

## Define the Target Audience

Under the **Who** section, define the target audience for your campaign. You can create a [new segment](doc:setup-segment) or use an existing saved segment. For instance, you may want to re-target users who added a product to their cart but did not complete a purchase in the last 30 days.

### Filter by User Properties

Use the _With user properties_ filter in the _Who_ section to refine your audience based on specific characteristics.

For example, you can choose to show Facebook Ads only to users based in a specific country and within a certain age group.

<Image align="center" alt={2202} border={true} caption="Filter by User Properties" title="Add Multiple User Properties" src="https://files.readme.io/bfc0fd496126aa45270c77e26cf6ce8d711288322277e428f2e03ddf0e46d40a-Segment.jpg" />

The following table describes the available property types:

| Property Type       | Description                                                                                                                                            | Example                                                                       |
| :------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------- |
| **User Properties** | Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap. | Customer Type = Platinum                                                      |
| **Demographics**    | Demographics filters include _Age_ and _Gender_.                                                                                                       | Age = 25 to 40 years  <br /> Gender = Female                                  |
| **Geography**       | User's coarse location. Filters include _Country_, _Region_, and _City_. CleverTap's SDK can detect this from the user's IP address.                   | Country = United States <br /> State = California <br /> City = San Francisco |
| **Reachability**    | Filters include _Has email address_, _Has phone number_, _Unsubscribed email_, and _Unsubscribed SMS_.                                                 | Unsubscribed email = No                                                       |
| **App Fields**      | Includes _App Version_, _Device Make_, _Device Model_, _OS Version_, and CleverTap _SDK Version_. Sent automatically from the SDK per device.          | OS Version = 10                                                               |

### Control Group and Target Cap

You can define a control group to compare campaign performance against a non-targeted audience. For more details, refer to [Control Groups](doc:control-groups). Additionally, you can set a target cap to limit how many users will receive the Facebook ad.

<Image align="center" alt="Control Group and Target Cap." border={true} caption="Control Group and Target Cap." src="https://files.readme.io/475e7c73530164dc22d679d881f098cf001ad3c80a34854f937a1fed704109d4-control_group_and_target_cap.jpg" />

**Use Case**: If you are distributing a coupon-based offer with limited codes, a target cap ensures only a defined number of users receive the message.

## What Section

The _What_ section allows you to export the audience defined in the _Who_ section to your selected Facebook Ads account.

### Export Audience

Once your audience criteria are defined, use the _What_ section to export the audience to the connected Facebook account. This audience will then be available for targeting within your Facebook Ads Manager.

In the _What_ section of the campaign flow, you can configure how CleverTap exports users to your Facebook Ads account. There are two ways to define this behavior:

#### Update Existing Audience

Select this option if you want to modify an existing audience based on the new qualification criteria. You can choose one of the following actions:

* **Add users to Audience**: Adds newly qualified users to the selected existing audience in your Facebook Ads Manager.
* **Remove users from Audience**: Removes users who no longer meet the qualification criteria from the selected existing audience.

This method is useful when you want to continuously refine an audience over time based on evolving user behavior.

<Image align="center" alt="Update Existing Audience" border={true} caption="Update Existing Audience" src="https://files.readme.io/e9f6aaf489e40d1fb515d1ebf0093fdc1ac375cf3457743d257a20484f4d03c1-image_64.png" />

#### Create New Audience

Choose this option to create a fresh audience based on the qualification and segmentation defined in the _Who_ section.

You will be required to provide the following:

* **Audience Name**:  
  Enter a unique and descriptive name for the new audience. Use clear naming conventions that make it easy to recognize the audience's purpose later (e.g., "Abandoned_Cart_30_Days" or "Loyal_Customers_Q2").

* **Audience Description**:  
  Add a brief summary (up to 200 characters) describing the characteristics or intent of the audience. This is especially helpful when managing multiple audiences across different campaigns.

  <Image align="center" alt="Create New Audience" border={true} caption="Create New Audience" src="https://files.readme.io/20b7d226409bcd5fc1735b3f0087963aecb8bb50f210e4a3caae1ecd03c529fc-image_65.png" />

#### Choose User Properties for Export

To sync user profiles with Facebook, at least one of the following user identifiers must be selected:

* **Email**: Exports the user's registered email address to Facebook for matching and targeting.
* **Phone**: Exports the user's phone number for the same purpose.

> 📘 Note:
>
> You must select at least one identifier. You may choose both for higher match rates.

<Image align="center" alt="User Properties to export" border={true} caption="User Properties to export" src="https://files.readme.io/ed8d0e73103b15ee54fc03660fe2dd9e739ab953135616a7f0045c40c020ebbe-image_64.png" />

#### Link Audience to Facebook Ad Sets (Optional)

Once the audience is created or updated, you have the option to link it directly to a Facebook Ad Set. This step allows you to immediately associate the exported segment with an ad campaign already configured in your Facebook Ads account. Linking an Ad Set is not mandatory and can be done later in Facebook Ads Manager if preferred.

<Image align="center" alt="Link Audience to Facebook Ad Sets" border={true} caption="Link Audience to Facebook Ad Sets" src="https://files.readme.io/11dbe0a13db2730eeef1280c54219363023a124757344c5e83509ef18b449bdd-image_66.png" />

## Define the Remarketing Campaign Schedule

Under the When section, you must define the timeframe for your campaign to start and end.

Past behavior campaigns can be scheduled to run:

* On a specific date and time.
* On multiple specified dates and times.
* Recurring at a periodicity you set.

Live campaigns can be set up on a specific event:

* In response to a user event.
* User event/inaction combination (for example, abandoned cart scenario).

You can set specific dates and times to control when your ads will be live. Depending on the campaign's goals, you can also set recurring schedules or specific time windows when the ads will be shown.

<Image align="center" alt="Define the Remarketing Schedule" border={true} caption="Define the Remarketing Schedule" src="https://files.readme.io/3b7485479f9e0354b103297cd4fb617954fb5955ad392d9d116af8b6493e20d9-WHEN.jpg" />

## Publish Campaign

After previewing the overall configuration of your remarketing campaign, finalize your campaign by clicking **Publish Campaign.**

<Image align="center" alt={1193} border={true} caption="Publish Campaign" title="Publish Final Campaign" src="https://files.readme.io/b521e92-campaign_Publish.png" />