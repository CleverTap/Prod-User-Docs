---
title: Product A/B Tests
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
Our Product Experiences suite helps you to enrich the experience for your app users right from the CleverTap dashboard using AB testing as a tool.

CleverTap A/B Test allows Application Developers, Product Managers, and Marketers to run A/B tests for their mobile Apps. This feature provides a web-based interface for managing tests.

For example, test your app for a better click-through rate. There are many ways in which you can present the CTA button. In our example, let us assume that the button on one variant of the app says "Buy Now", and the same button in another variant says "Hurry!". You can run this test for 4-5 weeks and determine which CTA delivers a higher click-through rate. You can roll out these changes partially to say 10 percent of the segment. When you are satisfied with the results, you can declare a variant that generates the highest click-through rate as a winner, and then roll out this variant to all the users. 

## Getting Started

An A/B test has three components. 
  * Segment - The set of users that will see the different variants. For creating segments, see [Create Segments](https://docs.clevertap.com/docs/product-experiences-setup#section-create-segments).

  * Keys - These are the keys that you have defined in your app code. You can map these keys from the CleverTap dashboard and control the configuration of your app. Keys allow you to define the variable and default value to be used in the test. Keys can be shared across multiple A/B tests. For more information about creating keys, see [Create Keys](https://docs.clevertap.com/docs/product-experiences-setup#section-create-keys). 

  * Goals - This is the desired outcome of your test. They help evaluate the performance of an A/B test. It is an event and when a user performs this event, it is considered as a conversion. For more information on creating goals, see [Creating Goals](https://docs.clevertap.com/docs/product-experiences-setup#section-create-goals)

An A/B test consists of a default control variant and one or more test variants. For each variant, CleverTap enables you to quantify the impact on important metrics such as a conversion event or goal.

#Define A/B Test

1. Click Product Experiences > A/B Tests.
2. Click the +A/B Tests button. The Create New page appears. 
3. Add a name and meaningful description for the test. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a88005e-AB_Test_Create.png",
        "AB_Test_Create.png",
        801,
        441,
        "#f6f7f9"
      ],
      "border": true
    }
  ]
}
[/block]
# Select Segment and Goals
1. Select a Segment or a test group from the Segment. If you want to roll out the test partially, select the percent of users in segment that can see the test, using test group %.
2. Select the goals. In our example, we select a single goal. It is a purchase event. For creating a goal, see [Set up Goals](https://docs.clevertap.com/docs/product-experiences-setup#section-goals). You can select a maximum of 5 goals.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0ccaec-AB_Segment_Segments_Goals.png",
        "AB_Segment_Segments_Goals.png",
        916,
        587,
        "#fafafa"
      ],
      "border": true
    }
  ]
}
[/block]
3. Make users exclusive for this test. From a qualifying segment, only unique users that are not part of any other test are selected. Also, such users are not included in any other test until the current test is stopped, rolled out, or the user is disqualified for some reason.  For more information, see [Setting mutually exclusive users](https://docs.clevertap.com/docs/product-experiences-setup#section-mutually-exclusive-a-b-tests)

4. Check the box to keep qualified users in the segment. It means that the user will remain in the test unless it is stopped or rolled out, even if they disqualify from the test after some time.

##Create Variations 

1. Create different variations of the test. Select [Keys](https://docs.clevertap.com/docs/product-experiences-setup#section-create-keys) and enter values for the Test Variant. The Control Variant displays the default value defined for the key in the setup and this value cannot be edited. 
You can have a maximum of 7 variants. 
2. Click Next.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a8b1529-AB_Variant_Create.png",
        "AB_Variant_Create.png",
        842,
        626,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "All identified users will always get the same variant across all devices. If some users choose not to identify, then they may see different variants on different devices."
}
[/block]

#Schedule AB Test

Schedule the start and end time of your test. You can choose to start immediately or at a later date and time. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a31d8ed-AB_Test_Schedule.png",
        "AB_Test_Schedule.png",
        633,
        390,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]
#Publish AB Test
Publish the test to start receiving results. 

1. Save the test and review all the test information.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a5716f3-AB_Test_Publish_Summary.png",
        "AB_Test_Publish_Summary.png",
        864,
        1191,
        "#f7f8f9"
      ]
    }
  ]
}
[/block]
2. Publish the test. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b378cf2-AB_Experiment_Publish.png",
        "AB_Experiment_Publish.png",
        881,
        713,
        "#b4b4b6"
      ]
    }
  ]
}
[/block]
#Manage Test

1. Navigate to Product Experiences > A/B Tests. The A/B Tests page lists all the tests. 
2. Click the required test from the list. The Stats page appears by default. 

##Edit Test

You can edit a published test. Following fields can be edited in a test - 
- Change the description 
- Change the test group % of the chosen segment
- Add or delete goals 
- Add or delete keys 
- Change values of the keys 

1. Navigate to Product Experiences > A/B Tests. The A/B Tests page lists all the tests. 
2. Click the required test from the list. 
3. Click Setup.
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "For a Scheduled AB test, all components including segment can be edited."
}
[/block]
###Version Control

A new version is created every time a published test is edited. The stats for each version are tracked separately. You can revert to an older version of the test. To view versions, follow the steps:

1. Open Product Experiences > A/B Tests. The A/B Tests page lists all the tests. 
2. Click the required test from the list.
3. Click the View Version History link. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55ef7bb-AB_Test_version_link.png",
        "AB_Test_version_link.png",
        873,
        639,
        "#f8f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
4. The Version History page appears. Click the required version to see the stats.

You can revert to an earlier version anytime. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/64d3297-AB_Test_version_history.png",
        "AB_Test_version_history.png",
        897,
        692,
        "#b3b3b6"
      ]
    }
  ]
}
[/block]
##View Stats

You can view the test stats to determine the performance of the test. In our example, we need the CTA with the highest conversion. 
1. Navigate to Product Experiences > A/B Tests. The A/B Tests page lists all the tests. 
2. Click the required test from the list. The Stats page appears by default. 
3. Scroll down to see all the stats.

###Statistical significance

Statistical significance provides a measurable impact for your winning variant by eliminating any possibility of a chance winner. We use Welch's t-test to measure statistical significance. The formula for calculating the necessary confidence level for a variant to be declared as statistically significant is `100 - (5 / number of variants - 1)`. For more information on A/B testing, see [How to Identify and Mitigate Risk in A/B Testing](https://clevertap.com/blog/how-to-identify-and-mitigate-risk-in-a-b-testing/).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/29d2015-AB_Exposure_event_Stats.png",
        "AB_Exposure_event_Stats.png",
        2336,
        590,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
##Exposure Event

An exposure event can help to determine the exact order of events that lead to a goal. You can assign an event as an exposure event to further test the effectiveness of your campaign.  For example, you can check if the number if the user immediately performs a purchase after viewing a product. You can set the product viewed event as an exposure event. 

Another aspect of using an exposure event is it allows you to measure more focused conversions. Once it is toggled on, you can see the conversions of only those users who actually saw the experiment or who were actually exposed to the experiment as per the event defined. 

To set exposure events follow these steps:

1. Navigate to Product Experiences > A/B Tests. The A/B Tests page lists all the tests. 
2. Click the required test from the list. The Stats page appears by default. 
3. Toggle the Test exposure event button. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2fe5828-AB_Exposure_event_toggle.png",
        "AB_Exposure_event_toggle.png",
        2366,
        796,
        "#f9f9fa"
      ]
    }
  ]
}
[/block]
4. Select and save the exposure event

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8c40e29-AB_Exposure_event_set.png",
        "AB_Exposure_event_set.png",
        908,
        296,
        "#f6f7fb"
      ]
    }
  ]
}
[/block]
5. View Conversion Stats.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9b5c0b4-AB_Exposure_event_Stats.png",
        "AB_Exposure_event_Stats.png",
        2336,
        590,
        "#f8f8f9"
      ]
    }
  ]
}
[/block]
###Edit Exposure Event


##Declare Winner

The best performing variant can be declared as a winner. 

1. Click the Declare Winner button to declare a variant as the winner. The Declare Winner window appears.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/28beebf-AB_Test_Declare_Winner.png",
        "AB_Test_Declare_Winner.png",
        386,
        364,
        "#eff1fa"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
2. Select the Variant and click Declare to declare it as the winner. The stats page will now display the stats of the winning variant. 

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "The test is still active after declaring the winner. Declaring a winner does not affect the test. You can always change the winning variant later."
}
[/block]
##Rollout Variant
After you are satisfied with the performance of a variant, you can roll it out to all users. This cannot be reversed. However, you can stop the test to stop rolling out the variant to the target segment. 

1. Click the Roll Out button from the test. The Roll out variant window appears.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3034673-AB_Test_Rollout_Variant.png",
        "AB_Test_Rollout_Variant.png",
        392,
        387,
        "#edeef9"
      ],
      "border": true,
      "sizing": "80"
    }
  ]
}
[/block]
2. Select the variant
3. Select the segment. 
4. Click Roll Out. 

This variant is rolled out to all the users in the segment and the test is marked as 'Rolled out'. 

#Set Test Priority

A user may belong to multiple tests with the same key. In that case, you can assign a higher priority to the required test. This is only applicable to new users. 

In our example, say user A qualified for the variant 'Buy now'. Now another test is created for the same key. This newly created test has a higher priority. There is no change for user A. This user continues to see the variant from the first test. However, for a new user who qualifies for both the test after the new test is prioritized, the priority will be respected. This new user will get a variant from the new test because it has a higher priority.  

To set priority follow the steps:

1. Navigate to Product Experiences > AB Tests. 
2. Click the Priority Order Tab. The priority list appears.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be865df-AB_Test_Priority.png",
        "AB_Test_Priority.png",
        861,
        618,
        "#f7f7f9"
      ]
    }
  ]
}
[/block]
3. Drag and drop the test to prioritize the test.

#Video Tutorial
For further information, you can watch the following video on product A/B tests:
[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fwww.youtube.com%2Fembed%2FlPCvSJzqTps%3Flist%3DPLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&display_name=YouTube&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DlPCvSJzqTps&image=https%3A%2F%2Fi.ytimg.com%2Fvi%2FlPCvSJzqTps%2Fhqdefault.jpg&key=f2aa6fc3595946d0afc3d76cbbd25dc3&type=text%2Fhtml&schema=youtube\" width=\"854\" height=\"480\" scrolling=\"no\" title=\"YouTube embed\" frameborder=\"0\" allow=\"autoplay; fullscreen\" allowfullscreen=\"true\"></iframe>",
  "url": "https://www.youtube.com/watch?v=lPCvSJzqTps&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=13",
  "title": "Product Demo: New Product A/B Tests",
  "favicon": "https://www.youtube.com/s/desktop/006e516c/img/favicon.ico",
  "image": "https://i.ytimg.com/vi/lPCvSJzqTps/hqdefault.jpg"
}
[/block]