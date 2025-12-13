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
# Overview

Mobile marketing platforms often focus on the campaign and journey-level engagement. CleverTap developed the Lifecycle Optimizer to create a view of the entire user base. As the name suggests, CleverTap Lifecycle Optimizer provides you with a guided and end-to-end solution for your retention flow. 

Why Lifecycle Optimizer?\
Lifecycle optimizer enables you to effectively define lifecycle stages to understand users. After the stages are defined, you can connect with users to influence them to move into the next stage. To best move users forward, you can run engagement experiments, measure their impact, and apply the winning variation to all users in a stage to optimize the lifecycle.

Lifecycle Optimizer comprises the following:

1. Map users to lifecycle stages based on qualifying actions to understand the entire user base
2. Experiment and iterate with different approaches and rollout the winning Journey.
3. Engage users with relevant, timely messages to move them to the next stage

You can choose from two frameworks to achieve your retention goals, that is, AIC or AARRR.

# Lifecycle Optimizer Steps

<Image title="LCO_Retention_Main_Steps.png" alt={1200} className="border" width="100%" border={true} src="https://files.readme.io/c88a2f0-LCO_Retention_Main_Steps.png" />

You can optimize the Lifecycle in four easy steps:

1. Select Lifecycle Framework
2. Define Lifecycle Stages
3. Create Engagements
4. Test, Iterate, and Rollout to All Users in a Stage

# Current Retention

Let us begin by viewing our current retention. This is a good starting point because it shows the current state of your retention. We can benchmark all our improvements against these statistics. 

Click Lifecycle Optimizer from the main dashboard. The key metrics overview displays the current retention state. 

<Image title="LCO_Current_Retention.png" alt={1347} className="border" border={true} src="https://files.readme.io/a3bd720-LCO_Current_Retention.png" />

You will see the following trends with some presets. You can modify these presets by clicking the edit \<img src="[https://files.readme.io/d0f481d-icon\_edit.png"height=“8px”](https://files.readme.io/d0f481d-icon_edit.png"height=“8px”) width=“8px” > icon. 

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Trend Name
      </th>

      <th>
        Events mapped
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Usage Rate
      </td>

      <td>
        App Launched to App Launched
      </td>

      <td>
        This indicates the app usage rate. It shows the percentage of active returning users.
      </td>
    </tr>

    <tr>
      <td>
        Current Conversion Rate
      </td>

      <td>
        App Launched to Charged
      </td>

      <td>
        This is your current conversion rate. It shows the percentage of active users who converted.
      </td>
    </tr>

    <tr>
      <td>
        Repeat Conversion Rate
      </td>

      <td>
        Charged to Charged
      </td>

      <td>
        This is your repeat conversion rate. It is the percentage of active users who converted again.
      </td>
    </tr>
  </tbody>
</Table>

# Setup

Let us begin setting up your model. 

## System Control Group

A system control group is a group of people who do not receive any engagement from CleverTap. A comparison of results against the system control group will enable you to measure the effectiveness of your engagement. You can build the Lifecycle Optimizer framework only if you have already enabled a system control group. 

## Select Framework

You can choose from either AIC or AARRR.

Select a framework and click Next. 

<Image title="LCO_Setup_Framework_Select.png" alt={1345} className="border" border={true} src="https://files.readme.io/6f1756a-LCO_Setup_Framework_Select.png" />

## AIC Framework

This is a 3-stage customer lifecycle framework.

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Sequence
      </th>

      <th>
        Stage
      </th>

      <th>
        Indicative User Events
      </th>

      <th>
        User Insight
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>

      <td>
        Acknowledge
      </td>

      <td>
        App open
      </td>

      <td>
        Action, low intent
      </td>
    </tr>

    <tr>
      <td>
        2
      </td>

      <td>
        Interest
      </td>

      <td>
        Search, add to cart, share app, and so on.
      </td>

      <td>
        Investment in the app experience
      </td>
    </tr>

    <tr>
      <td>
        3
      </td>

      <td>
        Convert
      </td>

      <td>
        Book ride, post message, create board, and so on.
      </td>

      <td>
        Complete core action
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Note
>
> This table is indicative. You can edit this stage with data points within the framework to suit your business needs.

### Why Select AIC 

Brands that choose the AIC framework tend to focus on the type of user actions.

The core action or conversion event represents the most desirable user action. 

It is generally used by Social Networking or Ad-based apps.

## AARRR Framework

The acronym AARRR stands for Acquisition, Activation, Retention, Referral, and Revenue. This is a 5-stage customer lifecycle framework. 

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Sequence
      </th>

      <th>
        Stage
      </th>

      <th>
        Indicative User Events
      </th>

      <th>
        User Insight
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>

      <td>
        Acquisition
      </td>

      <td>
        App open
      </td>

      <td>
        Trackable acquisition event in CleverTap
      </td>
    </tr>

    <tr>
      <td>
        2
      </td>

      <td>
        Activation
      </td>

      <td>
        Register, likes, board created
      </td>

      <td>
        Action that indicated likely continued app use
      </td>
    </tr>

    <tr>
      <td>
        3
      </td>

      <td>
        Retention
      </td>

      <td>
        Pin, wishlist, add to cart, view product
      </td>

      <td>
        Core app activity, inherent to the app’s purpose
      </td>
    </tr>

    <tr>
      <td>
        4
      </td>

      <td>
        Revenue
      </td>

      <td>
        Purchase, subscribe
      </td>

      <td>
        Revenue metrics
      </td>
    </tr>

    <tr>
      <td>
        5
      </td>

      <td>
        Referral
      </td>

      <td>
        Share content, invite to app, add rating
      </td>

      <td>
        Indicates advocacy
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Note
>
> This table is indicative. You can edit any stage within the framework to suit your business needs.

### Why Select AARRR

The AARRR framework is based on customer lifecycle stages. 

You choose this framework if you look at users and their progression through defined stages. There will be clear revenue conversion events.

This framework is generally used by eCommerce and Travel apps.

## Lifecycle Stages

Here you choose events that qualify users into each stage of the lifecycle. You can choose multiple events. Events are considered from the latest step. 

### AIC Events

![1337](https://files.readme.io/360d773-LCO_select_events_AIC.png "LCO_select_events_AIC.png")

### AARRR Events

![1342](https://files.readme.io/9b58a11-LCO_select_events_AARRR.png "LCO_select_events_AARRR.png")

## Preferred Value

The preferred value is the time period on which your model is based. The default value is 12 weeks.  This period can be edited. However, changing this default value will also change the model accordingly. 

![909](https://files.readme.io/fee15f4-LCO_choose_preferred_values.png "LCO_choose_preferred values.png")

Select "Qualify users for different stages of customer lifecycle based on these preferred values"  and save the setup. 

You can save the model as a draft or click Publish to publish the model. 

<Image title="LCO_Dashboard_Main.png" alt={1342} className="border" border={true} src="https://files.readme.io/780b17b-LCO_Dashboard_Main.png" />

# Create Engagement

You can create engagement tailored to each stage. Click Lifecycle Optimizer > Engagement Snapshot > View Engagements from the dashboard. The Engagements page appears. You can create engagement for your model from this page. 

![1349](https://files.readme.io/3003dba-LCO_Enagement_Create.png "LCO_Enagement_Create.png")

## Define Engagement

Define your engagement and roll it out to the selected percentage of users.

![1358](https://files.readme.io/db869fe-LCO_Engagment_Define.gif "LCO_Engagment_Define.gif")

> 📘 Tip
>
> Roll out this engagement to all users if you are confident that your engagement does not need improvement. However, if you wish to experiment first, you can experiment with a selected percent of users and then view the results. Rollout the engagement to all users if the results are satisfactory. Else, repeat the experiment.

## Define Engagement modes

Create a Journey to engage your users in the selected stage. For example, create a Journey to onboard all your new users. To learn more about creating a Journey, see [Journeys](doc:journeys).

After you create your Journey, you can save it as a draft or publish it. 

![1369](https://files.readme.io/57b756c-LCO_Journey.png "LCO_Journey.png")

Following  Journey operations are available:

* Edit - You can edit a current Journey. 
* Stop - You can stop a Journey. However, a stopped Journey cannot be restarted. 
* Rollout to all users - If you are experimenting with a Journey and the results are good, then you can roll out the Journey to all of your users.

# Journey Considerations

* Entry node - It will be pre-populated with the % of users in the stage. For example,  20% of users in the acquisition stage.
* Goals - They are pre-filled with the membership to higher stages. For example, if you're creating engagement in the acknowledgment stage and the users move to the next stage, that is Interest or Conversion, then these users.
* System Control Group - To benchmark results correctly, the system control group cannot be removed.  Also, a custom control group cannot be set. 

# Stats

You can view the stats for all users from the "Distribution Across Lifecycle Stages" section.\
Click View Stats to view the engagement statistics.

* Distribution Across Lifecycle Stages

Shows the current percentage of users across the Lifecycle Stages. 

![669](https://files.readme.io/c7dfdb7-lifecycle_distribution_stages.png "lifecycle_distribution_stages.png")

* Change Over Time

Shows the differential change in each stage.  For example, if the Interest stage shows the user count at 17.41% on June 1st and 18.04 % on June 2nd, then the differential increase in user interest is : **(18.01 - 17.41)  / 17.41 = 3.33%.**

<Image title="LCO_Stats_Change_over_time.png" alt={669} className="border" border={true} src="https://files.readme.io/422bd93-LCO_Stats_Change_over_time.png" />

* Inter Stage Transition

Shows how the users transitioned to a particular stage from each of the Lifecycle stages. 

<Image title="LCO_Stats_Inter_stage_Transitions.png" alt={1348} className="border" border={true} src="https://files.readme.io/59aa509-LCO_Stats_Inter_stage_Transitions.png" />

> 📘 Note
>
> Hover over a stage in the chord diagram to see the user transitions.

* Into a stage trend

Shows the trend of users who transitioned from other stages into the selected stage. 

![1346](https://files.readme.io/f94b25d-LCO_Stats_into_a_stage.png "LCO_Stats_into_a_stage.png")

* From a stage

Shows the trend of users who transitioned to other stages from the selected stage. If the model is set up optimally, the users must transition from a lower stage to a higher stage. 

![1350](https://files.readme.io/e10b9d6-LCO_Stats_from_a_stage.png "LCO_Stats_from_a_stage.png")
