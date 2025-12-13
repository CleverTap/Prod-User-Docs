---
title: Control Groups
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "What is a Control Group"
}
[/block]
Marketing teams typically run a variety of campaigns to onboard, convert and retain their users. However, it is hard to measure the efficacy of these campaigns independently. For e.g. - Was the increase in purchases today due to the reminder email we sent last night, or it could it have been that those users would have bought anyways without the reminder. 

A control group is a set of users marked to be not touched by any marketing campaigns. You can measure the effectiveness of your initiatives by comparing this group with the target group of users who received your campaigns.
[block:api-header]
{
  "title": "Introduction"
}
[/block]
CleverTap allows you to measure and track the performance of your engagement efforts comparing it the  Control Group

You can create 2 different types of Control Groups:-
1. System Control Group
  * System Control Group is created on your entire user base
  * You can create 1 System Control per account
  * You can create a system control group of size between 2% to 5%

2. Custom Control Group
  * Custom Control Group is created on your entire user base
  * You can create up to 10 Custom Control Groups per account
  * You can create a custom control group of size between 2% to 5%
  * Custom Control Groups are generally created for short duration strategies
 E.g. Determining Engagement impact for the Christmas campaigns
[block:api-header]
{
  "title": "Control Group Qualification"
}
[/block]
* When a Control Group is created, it is created from all the users who are a part of the application at the given time
E.g. If a 5% Control Group is created, every 1 in 20 users will be a part of the Control Group.
* This selection of users who are a part of the Control Group is completely random. We do not introduce any bias for qualification
* For all new users coming to the application after creating the control group, qualification to the Control Group will be based on the size of the control group. 
E.g. If a 5% Control Group is created, every 1 in 20 new users will be a part of the Control Group
[block:api-header]
{
  "title": "Creating a System Control Group"
}
[/block]
**Step 1**
You can create a system control group from Engage → Control Group
Here, you can create a System Control Group
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c22b4d9-Screenshot_2018-12-28_at_3.54.17_PM.png",
        "Screenshot 2018-12-28 at 3.54.17 PM.png",
        1440,
        706,
        "#e1e2e7"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 2**
You can choose to apply the Control Group to existing running campaigns and journeys by checking the box to 'Apply to all current campaign and journeys

[block:callout]
{
  "type": "warning",
  "title": "Important Note",
  "body": "Once you make this selection, you cannot change it"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8338049-Screenshot_2018-12-28_at_3.57.08_PM.png",
        "Screenshot 2018-12-28 at 3.57.08 PM.png",
        567,
        323,
        "#a5a6a8"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 3**
Now, you will be able to see the details of the system control group you created
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7fc7693-Screenshot_2018-12-28_at_4.01.09_PM.png",
        "Screenshot 2018-12-28 at 4.01.09 PM.png",
        763,
        426,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Creating a Custom Control Group"
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "Custom Control Group can be created only after you have a created System Control Group"
}
[/block]
**Step 1** 
When you move to 'Custom Control Group' and create a new custom control group, a new group will be created for you
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/250f7ef-Screenshot_2018-12-28_at_4.06.58_PM.png",
        "Screenshot 2018-12-28 at 4.06.58 PM.png",
        1440,
        667,
        "#e0e2e7"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 2**
Once you click on '+ Create New', you asked to provide a name, purpose and control group size
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3243bbf-Screenshot_2018-12-28_at_4.13.51_PM.png",
        "Screenshot 2018-12-28 at 4.13.51 PM.png",
        458,
        474,
        "#d4d4d6"
      ],
      "border": true
    }
  ]
}
[/block]
**Step 3** 
Now, you will be able to see the details of the custom control group(s) you created
You can create up to 10 Custom control groups
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d18233f-Screenshot_2018-12-28_at_4.10.44_PM.png",
        "Screenshot 2018-12-28 at 4.10.44 PM.png",
        1247,
        537,
        "#f4f7f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "API and Clever Campaigns",
  "body": "Control Groups are not applicable to campaigns created via APIs\nControl Groups are not applied to Clever Campaigns"
}
[/block]

[block:api-header]
{
  "title": "Campaign and Journey Creation"
}
[/block]

[block:callout]
{
  "type": "danger",
  "title": "Removing System Control Group",
  "body": "Although CleverTap provides the option to remove the System Control Group, we recommend to only use this option for transactional messages. Removing the System Control Group will impact the campaign reports"
}
[/block]
## Campaign Creation
Once you have created a System and/or Custom control group, you can now use this control group in your Campaigns
In the campaign creation workflow, when in the '**Setup**' section, you are given the option to add/remove the Control Group

* The system control group is applied by default for every campaign.
* You can choose to add a Custom control group to the campaign
* Optionally you can also add a Campaign control group. This control group will be applicable only to the said campaign
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bb533d2-Screenshot_2018-12-31_at_11.20.29_AM.png",
        "Screenshot 2018-12-31 at 11.20.29 AM.png",
        1371,
        638,
        "#f8f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
## Journey Creation
Once you have created a System and/or Custom control group, you can now use this control group in your Journeys
In the entry node of the Journey, you are given the option to add/remove the Control Group

* The system control group is applied by default for every campaign.
* You can choose to add a Custom control group to the campaign
* Optionally you can also add a Campaign control group. This control group will be applicable only to the said campaign
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/72b3281-Screenshot_2018-12-31_at_11.26.46_AM.png",
        "Screenshot 2018-12-31 at 11.26.46 AM.png",
        1440,
        789,
        "#f3f4f7"
      ],
      "border": true
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Reporting Stats"
}
[/block]
# Nomenclature
1. Campaign Qualification
  * All users who have qualified for the campaign based on the 'who' section picked by you
  * This will include users who are a part of the Control Group qualification
2. Control Group Qualification
  * All users who have qualified for the system or custom control group
3. Control Group Qualification for the campaign
  * All users who have qualified for the campaign AND were qualified to be a part of the Control Group
  * There may be users who are a part of the Control Group, but do not qualify for the campaign. These users will not be a part of the Control Group for the campaign in question

**Note**: If the campaign qualifies a very small user base, there may be a condition, that no user from the qualified based is a part of the Control Group. In that case, we will not showcase the Control Group stats for that campaign
[block:callout]
{
  "type": "warning",
  "title": "Deleting Control Group",
  "body": "If a Control Group is deleted when campaigns are running with a Control Group, the campaign report will be impacted"
}
[/block]
Once a campaign is created with a Control Group, the stats for the same can be viewed in the campaign report
Here you can see -
1. Number of users in the Control Group
2. Conversions of Target Group w.r.t. Control Group
3. Revenue of Target Group w.r.t. Control Group
* Revenue is calculated as ARPU (Average Revenue Per User)
** where ARPU = Total Revenue / number of users
[block:image]
{
  "images": [
    {
      "image": [],
      "caption": "Campaign Report"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [],
      "caption": "Journey Report"
    }
  ]
}
[/block]