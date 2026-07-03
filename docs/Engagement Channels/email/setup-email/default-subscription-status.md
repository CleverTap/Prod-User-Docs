---
title: Subscription Groups
excerpt: >-
  Learn how to manage email subscription groups to let users control which
  message categories they receive, and target campaigns to specific subscriber
  audiences.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

You can group all marketing campaigns and outgoing communications into separate subscription groups. Customers may want to receive messages about a particular category but opt out of others.

# Create Subscription Groups

To create a Subscription Group, perform the following steps.

1. From the CleverTap dashboard, select _Settings_ > _Setup_ > _Subscription Groups_.
2. Enter the group's name, provide a brief description, and select the Email channel.
3. Select _Unsubscribe by default_ to set the default subscription status to unsubscribed for all new and existing users in this group.
   <Callout icon="📘" theme="info">
     #### Note

     You cannot change the _Unsubscribe by default_ setting after you have saved the configuration.
   </Callout>


<Image src="https://files.readme.io/40425df9c592a6a246bd9b1ec2f725f49df3fdf6878d6207eb9de280781bcf89-Create_new_subscription_group.png" alt="1027" align="center" width="smart" caption="Create Subscription Group" border={true} />


4. Click **Save**.

<Callout icon="📘" theme="info">
  #### Active Subscription Groups

  Customers can set up 50 active groups. They can also archive groups to create new ones.
</Callout>

# Manage Subscription Groups

Once the subscription group is created, all the groups are listed under Settings > Setup > Subscription Groups. The list page displays the following information for each subscription group:


<Image src="https://files.readme.io/8fe90939e4f9c36be03184e71beb36907c30f80419b62256deaef0754ae7f801-Default_Subcription_Status.png" align="center" caption="Default Subscription Status" border={true} />


| Column                      | Details                                                                                                                                                                                                                                                                                                                                                       |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Group Name                  | The unique name assigned to the subscription group during creation.                                                                                                                                                                                                                                                                                           |
| Description                 | A brief description of the purpose of the group or the type of messages it covers.                                                                                                                                                                                                                                                                            |
| Channels                    | The communication channel associated with the group, for example, Email.                                                                                                                                                                                                                                                                                      |
| Default Subscription Status | The Default Subscription Status column on the Subscription Group list page shows the default state for each group: Subscribe or Unsubscribe. This indicates whether users are subscribed to the group by default when added to it.<br /><br />**Note**: The default subscription status cannot be modified for groups that have already been created earlier. |
| Last Updated                | The date and time when the subscription group was last modified.                                                                                                                                                                                                                                                                                              |

# Use Subscription Groups in Segments

1. From the CleverTap dashboard, select _Segments_ > _Find People_.
2. From the Display common properties, such as section, click +Properties.
3. Click **+ Properties** and select _Subscription Groups_ from the dropdown menu.


<Image src="https://files.readme.io/fca954f-Email_subscription_group_list.png" alt="929" align="center" caption="Use Subscription Groups in Segments" border={true} />


4. Select the _Exclude_/_Include_ parameter and accept the All default, or select one or multiple options.


<Image src="https://files.readme.io/4412785-Email_subscription_group_include_exclude.png" alt="926" align="center" width="smart" caption="Include/Exclude Subscription Groups" border={true} />


# Use Subscription Groups in Campaigns

Subscription groups allow users to select the content they want to receive, reducing unsubscription rates and fostering strong brand-user relationships. This approach enhances user satisfaction and builds a more personalized connection with your audience.

You can select the subscription group you want to include in your campaign from the Select Subscription Groups list. This allows you to target users who have subscribed to all the groups you selected for the campaign. To do so:

1. From the CleverTap dashboard, select Campaign and create an email campaign. Refer to Create Email Campaign.
2. From the Who > Control group and targeting cap > Send campaign only to users subscribed to all groups selected below.
3. Select the groups you want to include in your campaign from the Select subscription groups list.


<Image src="https://files.readme.io/e0653d9-image.png" align="center" border={true} />


4. Click **Done** and click **Continue**.
5. Complete creating the email campaign.

# Use Subscription Groups in Email Landing Page

To add the Subscription Group configuration to your email landing page, refer to [Handling Unsubscribes](doc:handling-unsubscribes|)

## Track Unsubscribes

Whenever a user unsubscribes, CleverTap raises a system event called _Channel Unsubscribed_, which updates the user property with the subscription status for the group.


<Image src="https://files.readme.io/b1c9872-Unsubscribe_last_step.png" alt="1012" align="center" width="50%" caption="Track Subscription Groups" border={true} />


<br />


<Image src="https://files.readme.io/3b8453c-image_2.png" alt="Track Subscription Groups" align="center" caption="Track Subscription Groups" border={true} />


# Group Unsubscribe

CleverTap offers Group Unsubscribe, which lets customers opt out of specific message groups. With Group Unsubscribe, the customer unsubscribes only from a specific group of messages while continuing to receive messages of interest. CleverTap tracks group unsubscribe if you are using a CleverTap-hosted Unsubscribe page or [CleverTap's unsubscription methods](doc:handling-unsubscribes) in your Custom Unsubscribe page.
