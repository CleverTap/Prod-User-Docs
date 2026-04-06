---
title: Facebook Audiences Create Message
excerpt: Understand how to create a campaign for Facebook Audiences
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

CleverTap’s Facebook Remarketing integration enables you to run personalized ad campaigns on Facebook by exporting user segments directly to your connected Facebook Ads account. This guide walks you through the process of creating a remarketing campaign—from selecting a channel to defining your target audience and exporting it to Facebook. You can configure qualification criteria, apply user-level filters, define control groups, and set targeting caps to optimize campaign performance and reach.

## Create a Campaign

Follow these steps to create a new remarketing campaign on Facebook:

1. From the dashboard, navigate to *Campaigns*.
2. Click the **+ Campaign** button. 

   <Image alt="Create Facebook Campaign" align="center" border={true} src="https://files.readme.io/f72801e97a4bfe63e6df5bde8b84c7230b7b6d4feaa9ac7215460ee50ba92860-image_62.png">
     Create Facebook Campaign
   </Image>
3. From the *Messaging Channels* list, select *Facebook*.

The campaign page will load. 

<Image alt="Campaign Page" align="center" width="65% " border={true} src="https://files.readme.io/3925573545ce2dd8160bf3cd54ae3406df236c24953ee196c799825ac20fa33d-screencapture-localhost-8083-WWW-WWW-WWRZ-campaigns-campaign-new-audiences-2025-06-02-15_59_03.png">
  Campaign Page
</Image>

## Start Campaign Setup

The *Start here* section displays the setup information.

**Qualification criteria**: Define the criteria for your target audience. You can deliver the Facebook ad based on the user's past or real-time behavior.

**Ad Account**: From the Ad Account drop-down, select the linked Facebook Ads account to which you want to export the audience.

**Set a Goal**: You can track campaign performance by defining a conversion goal. This helps measure how effectively the campaign achieves the intended outcome. For example, you may choose to track users who made a purchase within five days of the campaign launch. This step is optional. 

<Image alt="Start Campaign Setup" align="center" border={true} src="https://files.readme.io/01c0b107b24085715cf44f0e59dbd89f53adf6ce2b28607879cc3ac83cc9d48a-image_63.png">
  Start Campaign Setup
</Image>

## Define the Target Audience

Under the **Who** section, define the target audience for your campaign. You can create a [new segment](doc:setup-segment) or use an existing saved segment. For instance, you may want to re-target users who added a product to their cart but did not complete a purchase in the last 30 days.

### Filter by User Properties

Use the *With user properties* filter in the *Who* section to refine your audience based on specific characteristics.

For example, you can choose to show Facebook Ads only to users based in a specific country and within a certain age group.

<Image title="Add Multiple User Properties" alt={2202} align="center" border={true} src="https://files.readme.io/bfc0fd496126aa45270c77e26cf6ce8d711288322277e428f2e03ddf0e46d40a-Segment.jpg">
  Filter by User Properties
</Image>

The following table describes the available property types:

<Table>
  <thead>
    <tr>
      <th>
        Property Type
      </th>

      <th>
        Description
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **User Properties**
      </td>

      <td>
        Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.
      </td>

      <td>
        Customer Type = Platinum
      </td>
    </tr>

    <tr>
      <td>
        **Demographics**
      </td>

      <td>
        Demographics filters include *Age* and *Gender*.
      </td>

      <td>
        Age = 25 to 40 years  <br /> Gender = Female
      </td>
    </tr>

    <tr>
      <td>
        **Geography**
      </td>

      <td>
        User's coarse location. Filters include *Country*, *Region*, and *City*. CleverTap's SDK can detect this from the user's IP address.
      </td>

      <td>
        Country = United States <br /> State = California <br /> City = San Francisco
      </td>
    </tr>

    <tr>
      <td>
        **Reachability**
      </td>

      <td>
        Filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*.
      </td>

      <td>
        Unsubscribed email = No
      </td>
    </tr>

    <tr>
      <td>
        **App Fields**
      </td>

      <td>
        Includes *App Version*, *Device Make*, *Device Model*, *OS Version*, and CleverTap *SDK Version*. Sent automatically from the SDK per device.
      </td>

      <td>
        OS Version = 10
      </td>
    </tr>
  </tbody>
</Table>

### Control Group and Target Cap

You can define a control group to compare campaign performance against a non-targeted audience. For more details, refer to [Control Groups](doc:control-groups). Additionally, you can set a target cap to limit how many users will receive the Facebook ad.

<Image alt="Control Group and Target Cap." align="center" border={true} src="https://files.readme.io/475e7c73530164dc22d679d881f098cf001ad3c80a34854f937a1fed704109d4-control_group_and_target_cap.jpg">
  Control Group and Target Cap.
</Image>

**Use Case**: If you are distributing a coupon-based offer with limited codes, a target cap ensures only a defined number of users receive the message.

## What Section

The *What* section allows you to export the audience defined in the *Who* section to your selected Facebook Ads account.

### Export Audience

Once your audience criteria are defined, use the *What* section to export the audience to the connected Facebook account. This audience will then be available for targeting within your Facebook Ads Manager.

In the *What* section of the campaign flow, you can configure how CleverTap exports users to your Facebook Ads account. There are two ways to define this behavior:

#### Update Existing Audience

Select this option if you want to modify an existing audience based on the new qualification criteria. You can choose one of the following actions:

* **Add users to Audience**: Adds newly qualified users to the selected existing audience in your Facebook Ads Manager.
* **Remove users from Audience**: Removes users who no longer meet the qualification criteria from the selected existing audience.

This method is useful when you want to continuously refine an audience over time based on evolving user behavior. 

<Image alt="Update Existing Audience" align="center" border={true} src="https://files.readme.io/e9f6aaf489e40d1fb515d1ebf0093fdc1ac375cf3457743d257a20484f4d03c1-image_64.png">
  Update Existing Audience
</Image>

#### Create New Audience

Choose this option to create a fresh audience based on the qualification and segmentation defined in the *Who* section.

You will be required to provide the following:

* **Audience Name**:\
  Enter a unique and descriptive name for the new audience. Use clear naming conventions that make it easy to recognize the audience's purpose later (e.g., "Abandoned\_Cart\_30\_Days" or "Loyal\_Customers\_Q2").

* **Audience Description**:\
  Add a brief summary (up to 200 characters) describing the characteristics or intent of the audience. This is especially helpful when managing multiple audiences across different campaigns. 

  <Image alt="Create New Audience" align="center" border={true} src="https://files.readme.io/20b7d226409bcd5fc1735b3f0087963aecb8bb50f210e4a3caae1ecd03c529fc-image_65.png">
    Create New Audience
  </Image>

#### Choose User Properties for Export

To sync user profiles with Facebook, at least one of the following user identifiers must be selected:

* **Email**: Exports the user's registered email address to Facebook for matching and targeting.
* **Phone**: Exports the user's phone number for the same purpose.

> 📘 Note:
>
> You must select at least one identifier. You may choose both for higher match rates.

<Image alt="User Properties to export" align="center" border={true} src="https://files.readme.io/ed8d0e73103b15ee54fc03660fe2dd9e739ab953135616a7f0045c40c020ebbe-image_64.png">
  User Properties to export
</Image>

#### Link Audience to Facebook Ad Sets (Optional)

Once the audience is created or updated, you have the option to link it directly to a Facebook Ad Set. This step allows you to immediately associate the exported segment with an ad campaign already configured in your Facebook Ads account. Linking an Ad Set is not mandatory and can be done later in Facebook Ads Manager if preferred. 

<Image alt="Link Audience to Facebook Ad Sets" align="center" border={true} src="https://files.readme.io/11dbe0a13db2730eeef1280c54219363023a124757344c5e83509ef18b449bdd-image_66.png">
  Link Audience to Facebook Ad Sets
</Image>

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

<Image alt="Define the Remarketing Schedule" align="center" border={true} src="https://files.readme.io/3b7485479f9e0354b103297cd4fb617954fb5955ad392d9d116af8b6493e20d9-WHEN.jpg">
  Define the Remarketing Schedule
</Image>

## Publish Campaign

After previewing the overall configuration of your remarketing campaign, finalize your campaign by clicking **Publish Campaign.**

<Image title="Publish Final Campaign" alt={1193} align="center" border={true} src="https://files.readme.io/b521e92-campaign_Publish.png">
  Publish Campaign
</Image>