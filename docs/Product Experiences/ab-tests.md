---
title: Product Experiences
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
Our Product Experiences suite helps you to enrich the experience for your app users right from the CleverTap dashboard using AB testing as a tool.

CleverTap A/B Test allows Application Developers, Product Managers, and Marketers to run A/B tests for their mobile Apps. This feature provides a web-based interface for managing experiments.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ddb823d-Product_Exp_View.png",
        "Product_Exp_View.png",
        704,
        540,
        "#e5e1e9"
      ],
      "border": true
    }
  ]
}
[/block]
Let’s learn more about A/B tests and managing them from the CleverTap dashboard.

## Getting Started
Install the latest versions of CleverTap SDK for Android (3.6.0 and above) and iOS (3.7.0 and above). If you have already installed CleverTap SDK, check that you have the latest version.

## Types of A/B Tests
CleverTap supports two types of A/B Tests that you can use to optimize and manage the end-user experience in your app: [Visual Editor](doc:visual-editor)  and [Dynamic Variables](doc:dynamic-variables). 

You can use A/B Tests to estimate the impact of any changes on your app before making it live to your entire user-base. An A/B test consists of a default control variant and one or more variants. For each variant, CleverTap enables you to quantify the impact on important metrics such as conversion events, engagement, retention, and revenue.

## Setting goals for your experiment
Click "+A/B Tests" from the left navigation menu and click the "A/B Test" button to start a new A/B experiment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1b1d8b9-Screenshot_2019-10-30_at_4.01.34_PM.png",
        "Screenshot 2019-10-30 at 4.01.34 PM.png",
        1224,
        287,
        "#f6f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
Select the operating system, that is, Android or iOS. 
[block:callout]
{
  "type": "warning",
  "body": "If your app is on Android and iOS operating systems, create separate experiments for them.",
  "title": "Note"
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/687f9bd-Screenshot_2019-10-30_at_4.06.02_PM.png",
        "Screenshot 2019-10-30 at 4.06.02 PM.png",
        835,
        467,
        "#8b8c8d"
      ],
      "caption": ""
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Tip for apps built in React Native",
  "body": "If you are using a hybrid platform such as React Native, you will be able to use only [Dynamic Variables](doc:dynamic-variables) experiments. In this case, you will have to create a bridge for transferring variables to your React Native app."
}
[/block]

Name your experiment to identify it. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b7eeea-Screenshot_2019-10-30_at_5.30.22_PM.png",
        "Screenshot 2019-10-30 at 5.30.22 PM.png",
        1263,
        594,
        "#f3f4f5"
      ],
      "caption": ""
    }
  ]
}
[/block]
You will see three action items to create an experiment:

1. Goals - Set goals for your experiment
2. Variants - Create variants that you wish to test
3. Segment - Select sample users from a segment for your experiment

## Step 1: Define goals
A goal is equivalent to a hypothesis that you define to run an A/B Test. A goal can be interpreted as a success criterion that helps you measure and compare the impact of different variants of your app on user experience.

After you click the "Add" button in the goals section, you can create the required goal. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/749e632-Screenshot_2019-10-30_at_5.52.19_PM.png",
        "Screenshot 2019-10-30 at 5.52.19 PM.png",
        906,
        597,
        "#f9f9fb"
      ],
      "caption": "Define goals for the experiment"
    }
  ]
}
[/block]
On the goals page, you can specify the user actions on the app that will define success for this experiment. 

For example, you may want to track the checkout flow from the 'added to cart' to 'purchase' funnel. You may also want to track the total ticket size of the purchases made and repeat purchases within a timeframe of 4 -7 days. 

The results page shows all events and funnels that were added on the goals page.

CleverTap allows you to define several goals of these types: User behaviors (events), Conversions (multi-event funnels), Retentions, and Value per user.
[block:parameters]
{
  "data": {
    "h-0": "Goal type",
    "h-1": "Definition",
    "h-2": "Use case",
    "0-0": "Behaviour (Single event)",
    "0-1": "Percentage of total users in the experiment who have performed a particular event.\n\nExample: 25% users made a purchase",
    "0-2": "Purchase conversion measurement: Did a new variant convert more users to pay?",
    "1-0": "Conversion (Multi-step funnel)",
    "1-1": "Percentage of total users who have completed the steps that were defined in the funnel, in the defined sequence, and  within the defined period.\n\nExample: If 100 users complete the first step of the funnel, 50 out of the 100 users complete the second step and 25 out of the 50 users complete the final step of the funnel, then the conversion rate is 25/100 = 25%\nUsers must to go through the funnel steps in sequence, and that too within the defined time period, to be counted as success. However, the users can perform arbitrary events in between the flow.",
    "1-2": "User flow measurement: Did the new app flow work better to send the users from product list page to the checkout page?",
    "2-0": "Retention (Returning users)",
    "2-1": "Percentage of the total users who have come back and performed an event within a timeframe.\n\nExample: 65% of users in New York ordered food from the same restaurant within 4 -7 days.",
    "2-2": "Retention: Did the new app copy make more users return to the app and purchase items within x number of days?",
    "3-0": "Value",
    "3-1": "Total event value per user.\n\nExample: $35 revenue per user or 12 hour of music listens per user per month.",
    "3-2": "Value generated per user: Did the new variant result in getting more purchases from users?"
  },
  "cols": 3,
  "rows": 4
}
[/block]
## Step 2: Define Variants

You can define the variations of a screen or UI flow that you want to test against a base variant. The base variant here is called the **control variant**. The control variant is not modified so that it can provide a benchmark to compare the results.


[block:callout]
{
  "type": "warning",
  "title": "Check that the device is connected",
  "body": "You can define a variant only if your device or an emulator is connected."
}
[/block]
You can define multiple variants with some modifications to each of them. You can then check over time if one of the variants provides a higher incremental impact over the control variant. 

Variants can be defined in 2 ways:
1. [Visual Editor](doc:visual-editor) 
2. [Dynamic Variables](doc:dynamic-variables) 

## Step 3: Select sample users
An experiment must have a test population to analyze the impact of different variants. Select one of the segment types that you see in the segment selection screen.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d18451d-Screenshot_2019-11-04_at_11.43.24_AM.png",
        "Screenshot 2019-11-04 at 11.43.24 AM.png",
        1255,
        519,
        "#f4f5f8"
      ],
      "caption": "Select segment for sample users"
    }
  ]
}
[/block]
You can choose from 2 types of segments:
**1. Saved segments:** Select from already saved segments. For example, your saved segment can be "Users who did sign up in the last 30 days."
**2. Ad-hoc segment:** Define a segment on the go. If you do not have a pre-defined segment, you can create one. 
You can also select **All users**. Select a sample set of users from all your user bases. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5803013-Screenshot_2019-11-04_at_1.03.12_PM.png",
        "Screenshot 2019-11-04 at 1.03.12 PM.png",
        1232,
        542,
        "#f1f1f4"
      ],
      "caption": "Specify a percentage of the user base to conduct the experiment on"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "body": "It is advisable to perform experiments only on a part of the user base. That way, if some variant does is not acceptable to your audience, you can limit its undesirable effects.",
  "title": "Important"
}
[/block]
After you have completed all the 3 steps, you are ready to publish your experiment. You can either publish the experiment immediately or schedule it for a later time.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/196954f-Screenshot_2019-11-04_at_1.17.30_PM.png",
        "Screenshot 2019-11-04 at 1.17.30 PM.png",
        383,
        174,
        "#ebeffa"
      ],
      "caption": "Run your A/B Test now or schedule it for later"
    }
  ]
}
[/block]
You will now be able to see your experiment on the list page. You can click the name of the experiment and see the overview and results page.

## Experiment overview 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81a848d-Screenshot_2019-11-08_at_6.28.21_PM.png",
        "Screenshot 2019-11-08 at 6.28.21 PM.png",
        1197,
        532,
        "#f9fafb"
      ]
    }
  ]
}
[/block]
The experiment overview page shows you a summary of your experiments. You can view the goals, variants, and segments.

##Experiment results

You can analyze the results of a running experiment from the results page. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7b2b7d7-Product_Experience_Stats_Sales_Deck.png",
        "Product Experience_Stats_Sales Deck.png",
        2560,
        2852,
        "#f1f2f3"
      ],
      "caption": "Experiments results page"
    }
  ]
}
[/block]
Let's start understanding the different sections of the results page.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b3ad65f-Screenshot_2019-11-07_at_3.02.01_PM.png",
        "Screenshot 2019-11-07 at 3.02.01 PM.png",
        856,
        202,
        "#f7f7f8"
      ]
    }
  ]
}
[/block]
The top section has the following information/call to actions:
1. The name of the experiment
2. Date of start of the experiment
3. Current status of the experiment stating whether it is scheduled, running, reverted or completed
4. If the experiment was completed, the date when the experiment was completed
5. Action button to clone or edit a running experiment

## Understanding the states of the experiment 
1. **Running:** The experiment is currently active. The experiment data is reaching your users' devices and experiments are rendered on their devices. You can edit the variant design or variables in a running experiment. 
2. **Completed:** When you select a winning variant in your experiment, it is marked as completed. After an experiment is completed, the experiment is no longer sent out to new users.
3. **Reverted:** If you decide that you no longer want to continue with a running experiment,  you can click the revert button (appears alongside Clone and Edit). All the devices that have the experiment data are reverted to their original state. After the revert, your users stop getting the experiment and see your default app experience.

## Cloning an experiment 
You can clone an experiment if it's in the running, completed, or reverted state. 

## Editing an experiment 
An experiment can be edited only if it's scheduled for a later run or if it is already running. 

You can edit the following for scheduled experiments:
[block:parameters]
{
  "data": {
    "h-0": "Element",
    "h-1": "Operations",
    "0-0": "Goals",
    "0-1": "Add, remove, modify",
    "1-0": "Variants",
    "1-1": "Add, remove, modify",
    "2-0": "Segments",
    "2-1": "Modify the segment definition"
  },
  "cols": 2,
  "rows": 3
}
[/block]
For running experiments, however, you can only make limited edits to the variants.  You cannot add or delete variants since it will lead to faulty results. 

However, you can edit variables(for dynamic variables) and the look and feel of the screens (visual editor).

## Exclusion of users in multiple experiments
It's important to prevent cross-attribution of goal conversion from different experiments. Otherwise, the results may be inaccurate. CleverTap doesn't send more than one experiment to a user. If you are running two or more experiments simultaneously on the same segment of users, the system randomly runs the experiment on a different subset of users.

## User distribution in an experiment
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f46ee8-Screenshot_2019-11-08_at_3.33.27_PM.png",
        "Screenshot 2019-11-08 at 3.33.27 PM.png",
        1121,
        173,
        "#f9f9fa"
      ],
      "caption": "User distribution on the results page"
    }
  ]
}
[/block]
The user distribution section shows the number of variants for which the experiment has been rendered. An experiment is rendered when your app user launches the app for the first time. This is also when the event **Experiment Rendered** is raised. 
[block:callout]
{
  "type": "info",
  "title": "Experiment rendered event",
  "body": "If you are using CleverTap's A/B tests you are subscribed to an additional event called Experiment rendered. The Experiment rendered event is raised for users who launch their apps for the first time after they have been selected for an experiment.\n\nThis event has 2 custom properties:\n1. **Experiment ID:** the unique identifier for the experiment\n2. **Variant:** The control variant received by the user, or the experiment variant such as A, B, C, and so on."
}
[/block]
The second sub-section titled 'Users exposed to test variants so far' gives you the absolute number of users who have **seen**  the experiment. You also see the percentage of users who have received each variant. 

[block:callout]
{
  "type": "info",
  "body": "The control variant is considered as 'rest of the users' who do not receive any variant.",
  "title": "Note"
}
[/block]
## Experiment stats 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ca778e6-Screenshot_2019-11-08_at_5.22.37_PM.png",
        "Screenshot 2019-11-08 at 5.22.37 PM.png",
        1139,
        421,
        "#f6faf6"
      ],
      "caption": "Stats section: Showing conversions for different goals"
    }
  ]
}
[/block]
Your experiment tracks conversions on each of the goals separately. This allows you to make visual comparisons between different variants within one screen. 

## Winner declaration
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ba6d550-Screenshot_2019-11-08_at_5.53.27_PM.png",
        "Screenshot 2019-11-08 at 5.53.27 PM.png",
        1201,
        67,
        "#f0f4f9"
      ],
      "caption": "Declare winner in a running experiment",
      "sizing": "original"
    }
  ]
}
[/block]
In a running experiment, you can see buttons below each variant column. You have to manually click one of the buttons to declare a winner. 



[block:callout]
{
  "type": "info",
  "body": "Declaring a winner will not stop the experiment. You can change the winner any number of times during the experiment. The experiment is marked as complete only after you roll out the winner."
}
[/block]
## Rolling out a variant 
When you roll out a winning variant, that variant becomes the new default for all users. 
[block:callout]
{
  "type": "success",
  "title": "Experiment rollout best practices",
  "body": "After you have decided that a certain variant is giving you the best results (goal conversions), you can release that variant of your app. This will ensure you do not have to run multiple experiments."
}
[/block]
## Goal conversion trend 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19d20e8-Screenshot_2019-11-08_at_6.18.30_PM.png",
        "Screenshot 2019-11-08 at 6.18.30 PM.png",
        1201,
        556,
        "#f6f7f8"
      ],
      "caption": "Line charts showing day-on-day goal conversion"
    }
  ]
}
[/block]