---
title: Set up Journey
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
You must set up the Journey before you can start creating it and targeting users. 

To set up a Journey, click *Journeys* from the dashboard and click the **+Journey** button. A new Journey canvas displays. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4f63f9a-Journeys_setup_begin.png",
        "Journeys_setup_begin.png",
        1348,
        624,
        "#f9fafc"
      ]
    }
  ]
}
[/block]
Click **Setup**.
The *Setup* window displays.  Enter the **Journey Name**. 


## Define the Journey Entry Criteria

Select the *Journey entry criteria*. It can be a specific time or an event trigger. 

When you start building your Journey, you must define your *entry criteria*. This is a condition that decides if the users will be included in the Journey. The entry criteria of a Journey is essentially the segment of users you want to target.

The various types of segments you can use are:
  * Live User segments: These segments qualify people as soon as they meet your specified criteria
  * Past Behavior segments: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty-four hours.

Live user segments are further classified as follows: 
  * Action: In this type of *entry criteria*, users will enter your Journey, as soon as they perform an event. For example: Enter people into your Journey, as soon as they install your application.
  * Inaction: Users enter your Journey, as soon as they don’t do something in the future. For example: If someone adds an item to their cart, but doesn’t transact within 15 mins.
  * Property Date-time segments: Qualify a user relative to a specific date and time in a property.
  * Page visit: Users will qualify as soon as they reach a web page that matches your specifications.
  * Refer entry: When users come to your website from a certain referrer, for example, Facebook, or Twitter, they will be qualified for your Journey.
  * Page count: As soon as the user sees the specified number of pages, they will be a part of your Journey.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ada99a2-Journeys_setup_entry_criteria.png",
        "Journeys_setup_entry_criteria.png",
        766,
        433,
        "#faf9fb"
      ]
    }
  ]
}
[/block]
## Define the Journey Entry Timelines

We support one-time, multiple dates, and recurring Journeys.
For example, for monthly payment reminders, you can schedule a Journey to start on the 1st of every month

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/de68ca2-Journeys_setup_entry_timelines.png",
        "Journeys_setup_entry_timelines.png",
        726,
        476,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]

### Allow Users to Re-Enter a Journey
By default, a user will qualify for a Journey only once. However, you can optionally allow users who have exited from a Journey to re-enter it, should they meet the entry criteria at a later date.

After a user is a part of a Journey, they can only re-qualify if they exit the Journey, either by matching one of the specified goals or by being forced out of the Journey and subsequently meeting the specifications of the entry criteria.

 Following is an example:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3b04e68-Journeys_setup_reenter_user.png",
        "Journeys_setup_reenter_user.png",
        698,
        146,
        "#e1e5dd"
      ]
    }
  ]
}
[/block]
When a user makes a purchase they enter into the Journey. After a 20 minute wait time, qualifying users will receive a Push Notification with a discount promotion code.

If the Journey was set up with the default behavior (users cannot re-enter the Journey) then after they purchase and receive the push notification they exit from the Journey. If a user makes another purchase subsequent to the initial purchase they will not receive another promotional Push Notification since this Journey does not allow for re-entry.

If however, your intent is to allow users to receive a new promotional discount after each subsequent purchase, you’d select the option to allow a user to re-enter as follows.

## DND and Timezone

CleverTap provides an option for setting the *Do Not Disturb* hours for notification delivery while creating a journey. The DND feature manages message delivery via engagement nodes in Journeys so that campaigns are only sent after the DND period or discarded.  If users send time-specific messages via Journeys where they send notifications to registered users who requested a specific active time and a specific inactive time, notifications will only be sent during the active time. 

To set DND for Push, SMS, Email & Web Push journeys, perform the following steps:

Select the days and enter the time period during which you do not want to send campaign notifications. If you want to use the same time inactive period for each day, click the **ApplyTo All **link.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a226d97-Journeys_setup_DND_timezone.png",
        "Journeys_setup_DND_timezone.png",
        697,
        730,
        "#f8f9fb"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "DND Conflict Hours",
  "body": "If you schedule a message node to send out delivery during the scheduled DND hours, you will receive an error message. This error message appears at the publishing of the journey."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7ff47d7-2020-08-17_16-14-20_DND_hours_Conflict.png",
        "2020-08-17_16-14-20_DND hours Conflict.png",
        1206,
        643,
        "#838385"
      ]
    }
  ]
}
[/block]

## Define the Control Group

Define the required control groups. For more information on control groups, see [Control Groups](doc:control-groups) .
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7092b2a-Journeys_setup_control_group.png",
        "Journeys_setup_control_group.png",
        725,
        329,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
## Select a Journey Timeout

Journeys are sequences of campaigns. At each stage of a Journey, you can choose to further segment your audience as well as deliver campaigns across multiple channels.

While creating Journeys, you can choose to specify a Journey Timeout, this will be the maximum amount of time a user will spend in a Journey. Once this window is completed for a user, they exit the Journey, no matter their stage in the Journey.
[block:callout]
{
  "type": "warning",
  "body": "Once a user has exited the Journey, the user is free to re-qualify, if you have allowed re-entry in your setup."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e182621-Journeys_setup_timeout.png",
        "Journeys_setup_timeout.png",
        724,
        327,
        "#fbfbfc"
      ],
      "border": true
    }
  ]
}
[/block]
## Add Goals 

Goals are behaviors that you want users to perform. On completing a goal, users are removed from the Journey. You can drag and drop any segment from the left-hand side palette and add it as a goal for your Journey. A Journey can support up to 3 goals, if a user completes any one of the goals, they will be exited from the Journey.

**Common Examples of Goals**
  * Action-based goals: In this goal, users will exit your Journey as soon as they perform a goal, in real-time. For example, exit people as soon as they perform the *Charged* event, where *item* is *Red Nike Shoes*.
  * Past behavior goals: Past behavior goals, like segments, are evaluated once every twenty-four hours, at 12:00 am. Once the goal is evaluated, users who meet this goal will not be a part of the Journey from that day onwards. For example, exit people if they have spent at least $300 in the last week. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/49a8f33-journey8.png",
        "journey8.png",
        746,
        201,
        "#dbedfa"
      ],
      "border": true
    }
  ]
}
[/block]