---
title: Lifecycle Optimizer
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
#Overview
Mobile marketing platforms often focus on the campaign and journey-level engagement. CleverTap developed the Lifecycle Optimizer to create a view of the entire user base. As the name suggests, CleverTap Lifecycle Optimizer provides you with a guided and end-to-end solution for your retention flow. 

Why Lifecycle Optimizer? 
Lifecycle optimizer enables you to effectively define lifecycle stages to understand users. After the stages are defined, you can connect with users to influence them to move into the next stage. To best move users forward, you can run engagement experiments, measure their impact, and apply the winning variation to all users in a stage to optimize the lifecycle.

Lifecycle Optimizer comprises the following:

1. Map users to lifecycle stages based on qualifying actions to understand the entire user base
2. Experiment and iterate with different approaches and rollout the winning Journey.
3. Engage users with relevant, timely messages to move them to the next stage

You can choose from two frameworks to achieve your retention goals, that is, AIC or AARRR.

#Lifecycle Optimizer Steps
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c88a2f0-LCO_Retention_Main_Steps.png",
        "LCO_Retention_Main_Steps.png",
        1200,
        577,
        "#9295ae"
      ],
      "sizing": "full",
      "border": true,
      "caption": ""
    }
  ]
}
[/block]
You can optimize the Lifecycle in four easy steps:
1. Select Lifecycle Framework
2. Define Lifecycle Stages
3. Create Engagements
4. Test, Iterate, and Rollout to All Users in a Stage


#Current Retention
Let us begin by viewing our current retention. This is a good starting point because it shows the current state of your retention. We can benchmark all our improvements against these statistics. 

Click Lifecycle Optimizer from the main dashboard. The key metrics overview displays the current retention state. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a3bd720-LCO_Current_Retention.png",
        "LCO_Current_Retention.png",
        1347,
        569,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]
You will see the following trends with some presets. You can modify these presets by clicking the edit <img src="https://files.readme.io/d0f481d-icon_edit.png"height=“8px” width=“8px” > icon. 
[block:parameters]
{
  "data": {
    "h-0": "Trend Name",
    "h-1": "Events mapped",
    "h-2": "Description",
    "0-0": "Usage Rate",
    "1-0": "Current Conversion Rate",
    "2-0": "Repeat Conversion Rate",
    "0-1": "App Launched to App Launched",
    "1-1": "App Launched to Charged",
    "2-1": "Charged to Charged",
    "0-2": "This indicates the app usage rate. It shows the percentage of active returning users.",
    "1-2": "This is your current conversion rate. It shows the percentage of active users who converted.",
    "2-2": "This is your repeat conversion rate. It is the percentage of active users who converted again."
  },
  "cols": 3,
  "rows": 3
}
[/block]
# Setup 

Let us begin setting up your model. 

##System Control Group

A system control group is a group of people who do not receive any engagement from CleverTap. A comparison of results against the system control group will enable you to measure the effectiveness of your engagement. You can build the Lifecycle Optimizer framework only if you have already enabled a system control group. 

##Select Framework

You can choose from either AIC or AARRR.

Select a framework and click Next. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f1756a-LCO_Setup_Framework_Select.png",
        "LCO_Setup_Framework_Select.png",
        1345,
        429,
        "#f5f6f9"
      ],
      "border": true
    }
  ]
}
[/block]
##AIC Framework

This is a 3-stage customer lifecycle framework.
[block:parameters]
{
  "data": {
    "h-0": "Sequence",
    "0-0": "1",
    "h-1": "Stage",
    "h-2": "Indicative User Events",
    "0-2": "App open",
    "0-1": "Acknowledge",
    "1-1": "Interest",
    "1-2": "Search, add to cart, share app, and so on.",
    "2-1": "Convert",
    "2-2": "Book ride, post message, create board, and so on.",
    "1-0": "2",
    "2-0": "3",
    "h-3": "User Insight",
    "0-3": "Action, low intent",
    "1-3": "Investment in the app experience",
    "2-3": "Complete core action"
  },
  "cols": 4,
  "rows": 3
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "This table is indicative. You can edit this stage with data points within the framework to suit your business needs."
}
[/block]
###Why Select AIC 

Brands that choose the AIC framework tend to focus on the type of user actions.

The core action or conversion event represents the most desirable user action. 

It is generally used by Social Networking or Ad-based apps.

##AARRR Framework

The acronym AARRR stands for Acquisition, Activation, Retention, Referral, and Revenue. This is a 5-stage customer lifecycle framework. 
[block:parameters]
{
  "data": {
    "h-0": "Sequence",
    "h-1": "Stage",
    "h-2": "Indicative User Events",
    "h-3": "User Insight",
    "0-0": "1",
    "1-0": "2",
    "2-0": "3",
    "3-0": "4",
    "4-0": "5",
    "0-1": "Acquisition",
    "1-1": "Activation",
    "2-1": "Retention",
    "3-1": "Revenue",
    "4-1": "Referral",
    "0-2": "App open",
    "0-3": "Trackable acquisition event in CleverTap",
    "1-2": "Register, likes, board created",
    "1-3": "Action that indicated likely continued app use",
    "2-2": "Pin, wishlist, add to cart, view product",
    "2-3": "Core app activity, inherent to the app’s purpose",
    "3-2": "Purchase, subscribe",
    "3-3": "Revenue metrics",
    "4-2": "Share content, invite to app, add rating",
    "4-3": "Indicates advocacy"
  },
  "cols": 4,
  "rows": 5
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "This table is indicative. You can edit any stage within the framework to suit your business needs.",
  "title": "Note"
}
[/block]

###Why Select AARRR

The AARRR framework is based on customer lifecycle stages. 

You choose this framework if you look at users and their progression through defined stages. There will be clear revenue conversion events.

This framework is generally used by eCommerce and Travel apps.

##Lifecycle Stages

Here you choose events that qualify users into each stage of the lifecycle. You can choose multiple events. Events are considered from the latest step. 

###AIC Events

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/360d773-LCO_select_events_AIC.png",
        "LCO_select_events_AIC.png",
        1337,
        855,
        "#f9f9f9"
      ]
    }
  ]
}
[/block]
###AARRR Events
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b58a11-LCO_select_events_AARRR.png",
        "LCO_select_events_AARRR.png",
        1342,
        1197,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
##Preferred Value

The preferred value is the time period on which your model is based. The default value is 12 weeks.  This period can be edited. However, changing this default value will also change the model accordingly. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/fee15f4-LCO_choose_preferred_values.png",
        "LCO_choose_preferred values.png",
        909,
        576,
        "#fafaf9"
      ]
    }
  ]
}
[/block]
Select "Qualify users for different stages of customer lifecycle based on these preferred values"  and save the setup. 

You can save the model as a draft or click Publish to publish the model. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/780b17b-LCO_Dashboard_Main.png",
        "LCO_Dashboard_Main.png",
        1342,
        1449,
        "#f8f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
#Create Engagement

You can create engagement tailored to each stage. Click Lifecycle Optimizer > Engagement Snapshot > View Engagements from the dashboard. The Engagements page appears. You can create engagement for your model from this page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3003dba-LCO_Enagement_Create.png",
        "LCO_Enagement_Create.png",
        1349,
        718,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
##Define Engagement
Define your engagement and roll it out to the selected percentage of users.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db869fe-LCO_Engagment_Define.gif",
        "LCO_Engagment_Define.gif",
        1358,
        640,
        "#f8f9f8"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "Roll out this engagement to all users if you are confident that your engagement does not need improvement. However, if you wish to experiment first, you can experiment with a selected percent of users and then view the results. Rollout the engagement to all users if the results are satisfactory. Else, repeat the experiment."
}
[/block]
## Define Engagement modes
Create a Journey to engage your users in the selected stage. For example, create a Journey to onboard all your new users. To learn more about creating a Journey, see [Journeys](doc:journeys).

After you create your Journey, you can save it as a draft or publish it. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/57b756c-LCO_Journey.png",
        "LCO_Journey.png",
        1369,
        766,
        "#e9f3f3"
      ]
    }
  ]
}
[/block]
Following  Journey operations are available:

  * Edit - You can edit a current Journey. 
  * Stop - You can stop a Journey. However, a stopped Journey cannot be restarted. 
  * Rollout to all users - If you are experimenting with a Journey and the results are good, then you can roll out the Journey to all of your users.

#Journey Considerations
  * Entry node - It will be pre-populated with the % of users in the stage. For example,  20% of users in the acquisition stage.
  * Goals - They are pre-filled with the membership to higher stages. For example, if you're creating engagement in the acknowledgment stage and the users move to the next stage, that is Interest or Conversion, then these users.
  * System Control Group - To benchmark results correctly, the system control group cannot be removed.  Also, a custom control group cannot be set. 


# Stats

You can view the stats for all users from the "Distribution Across Lifecycle Stages" section. 
Click View Stats to view the engagement statistics.


  * Distribution Across Lifecycle Stages

Shows the current percentage of users across the Lifecycle Stages. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c7dfdb7-lifecycle_distribution_stages.png",
        "lifecycle_distribution_stages.png",
        669,
        469,
        "#f7f8fc"
      ]
    }
  ]
}
[/block]
  * Change Over Time

Shows the differential change in each stage.  For example, if the Interest stage shows the user count at 17.41% on June 1st and 18.04 % on June 2nd, then the differential increase in user interest is : **(18.01 - 17.41)  / 17.41 = 3.33%.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/422bd93-LCO_Stats_Change_over_time.png",
        "LCO_Stats_Change_over_time.png",
        669,
        479,
        "#f7f7f9"
      ],
      "border": true
    }
  ]
}
[/block]

  * Inter Stage Transition

Shows how the users transitioned to a particular stage from each of the Lifecycle stages. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/59aa509-LCO_Stats_Inter_stage_Transitions.png",
        "LCO_Stats_Inter_stage_Transitions.png",
        1348,
        600,
        "#f5f6f7"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Hover over a stage in the chord diagram to see the user transitions."
}
[/block]
  

* Into a stage trend

Shows the trend of users who transitioned from other stages into the selected stage. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f94b25d-LCO_Stats_into_a_stage.png",
        "LCO_Stats_into_a_stage.png",
        1346,
        652,
        "#f5f5f6"
      ]
    }
  ]
}
[/block]
  * From a stage

Shows the trend of users who transitioned to other stages from the selected stage. If the model is set up optimally, the users must transition from a lower stage to a higher stage. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e10b9d6-LCO_Stats_from_a_stage.png",
        "LCO_Stats_from_a_stage.png",
        1350,
        649,
        "#fcfbfc"
      ]
    }
  ]
}
[/block]

# Video Tutorial
For further information, you can watch the following video on lifecycle optimizer:
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2F1YZuGQkxUtM&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D1YZuGQkxUtM&image=http%3A%2F%2Fi.ytimg.com%2Fvi%2F1YZuGQkxUtM%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=1YZuGQkxUtM&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=7",
  "title": "Product Demo: Lifecycle Optimizer",
  "favicon": "https://www.youtube.com/s/desktop/404f9720/img/favicon.ico",
  "image": "http://i.ytimg.com/vi/1YZuGQkxUtM/hqdefault.jpg"
}
[/block]