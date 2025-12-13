---
title: Journeys_Profile_property_update_WIP
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
Journeys is a visual campaign builder that lets you create omnichannel messaging experiences for your users.

# Overview

Journeys are ideal for engaging users across the lifecycle of your app. 

To list a few sample use cases:
  * Build User Onboarding Journeys that engage users over several days or weeks and on different channels as you educate them about your service.
  * Build Promotional Journeys to entice your users to transact at different points of time.
  * Long-running re-engagement campaigns to pull users back into your service if they begin to slip away.

You can access Journeys under the “Engage” section of your CleverTap Dashboard. Click on the “Journeys” link in the left nav bar in your CleverTap Dashboard. Once on the page, you can click on the “create” icon to create your first journey.

# Journey Components

A Journey is a combination of Segment nodes and Engagement nodes. You can connect Segment nodes and engagement nodes to each other to create powerful automation.

There are three types of nodes:
* Segment
* Engagement
* Controllers

##Segment Nodes
[block:parameters]
{
  "data": {
    "h-0": "Segment Node",
    "h-1": "What it does",
    "h-2": "Description",
    "0-0": "Action",
    "0-1": "As soon as the user performs an action, the user enters this node.",
    "0-2": "Qualification to this node occurs as soon as the user performs the said event.",
    "1-0": "Inaction",
    "2-0": "Past Behavior",
    "3-0": "Date Time",
    "4-0": "Journey Trigger",
    "4-1": "You can use this node in the entry criteria only.\nA user is qualified on this node when the same user is qualified for the corresponding node in another Journey, from where the current Journey is triggered.",
    "4-2": "E.g. Journey 1 has a Push message node. You want to move all users who were sent the push into another Journey. Journey trigger allows you to do this.",
    "5-0": "Page Visit",
    "6-0": "Referrer Entry",
    "7-0": "Page Count",
    "1-1": "Segment users who did the 1st event, but did not do the 2nd event within a specified time interval.",
    "1-2": "For example,  Qualify users who added to cart, but did not purchase within 5 mins.",
    "2-1": "Segment users who performed and did not perform a set of events in the past n days.",
    "2-2": "E.g. Users who did Video Watched AND did not do Subscription Paid in the Last 30 days.",
    "3-1": "Segment users based on a date time property value like flight time, etc.",
    "3-2": "E.g. Users who have their flight after 2 hours.",
    "5-1": "Segment users as soon as they visit a specific page.",
    "6-1": "Segment users based on a referring website or campaign.",
    "7-1": "Segment users based on the number of pages visited by them.",
    "5-2": "Web based segment.",
    "6-2": "Web based segment.",
    "7-2": "Web based segment.",
    "8-0": "Custom list",
    "8-2": "Custom segment. For example, users from your Retail Point of Sale (POS).",
    "8-1": "You can use this node in the entry criteria only.  You can upload custom lists of users for engage in the Journey."
  },
  "cols": 3,
  "rows": 9
}
[/block]




# Building Your First Journey

## Step 1: Define the Entry Criteria

When you start building your Journey, you need to define your “entry criteria”, this is the condition, which when met, users will enter and be a part of the Journey. The entry criteria of a Journey is essentially the segment of users you want to target.

The various types of segments you can use are:
  * Live User segments: These segments qualify people as soon as they meet your specified criteria
  * Past Behavior segments: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty-four hours.

Live user segments are further bifurcated as follows: 
  * Action: In this type of Entry Criteria, users will enter your Journey, as soon as they perform an event. Example: Enter people into your Journey, as soon as they install your application.
  * Inaction: Users enter your Journey, as soon as they don’t do something in the future. Example: If someone adds an item to their cart, but don’t transact within 15 mins.
  * Property Date-time segments: Qualify a user relative to a specific date and time in a property.
  * Page visit: Users will qualify as soon as they reach a web page that matches your specifications.
  * Refer entry: When users come to your website from a certain referrer, example: Facebook, or Twitter, they will be qualified for your Journey.
  * Page count: As soon as the user sees the specified number of pages, they will be a part of your Journey.
[block:callout]
{
  "type": "info",
  "title": "Journey Scheduler",
  "body": "We support One time, Multiple date and recurring Journeys.\nE.g. For monthly payment reminders, you can schedule a Journey to start on the 1st of every month"
}
[/block]
## Step 2: Select a Journey Timeout

Journeys are sequences of campaigns. At each stage of a Journey, you can choose to further segment your audience as well as deliver campaigns across multiple channels.

While creating Journeys, you can choose to specify a Journey Timeout, this will be the maximum amount of time a user will spend in a Journey. Once this window is completed for a user, they will be exited from the Journey, no matter which stage they are at.
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
        "https://files.readme.io/0dfbbd2-Journeys_Timeout.png",
        "Journeys_Timeout.png",
        715,
        387,
        "#fafbfb"
      ],
      "border": true
    }
  ]
}
[/block]
**Allow Users to Re-Enter a Journey**
By default, a user will qualify for a Journey only once. However, you can optionally allow users who have exited from a Journey to re-enter it should they meet the entry criteria at a later date.

Once a user is a part of a Journey, the only way they can re-qualify is if they exit the Journey, either by matching one of the specified goals, or by being forced out of the Journey and subsequently meeting the specifications of the entry criteria.

Take the following simple example.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d00fca9-Journeys_Allow_users_reentery.png",
        "Journeys_Allow_users_reentery.png",
        1052,
        270,
        "#c0eaf7"
      ]
    }
  ]
}
[/block]
When a user makes a purchase they enter into the Journey. After a 20 minute wait time qualifying users will receive a Push Notification with a discount promotion code.

If the Journey was set-up with the default behavior (users cannot re-enter the Journey) then after they purchase and receive the push notification they exit from the Journey. If a user makes another purchase subsequent to the initial purchase they will not receive another promotional Push Notification since this Journey does not allow for re-entry.

If however, your intent is to allow users to receive a new promotional discount after each subsequent purchase, you’d select the option to allow a user to re-enter as follows.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bd74cac-Journeys_Re-enter_Users.png",
        "Journeys_Re-enter_Users.png",
        656,
        444,
        "#e8e8eb"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 3: Define the Journey

**Connect Segment & Engage Blocks**
Once you have defined a segment of users, you can choose to communicate with the segment by dragging and dropping a channel of communication from the palette on the right hand side. This communication could go to users who match the segment criteria specified by you, or to the rest of the users i.e. the users who don’t match your segment criteria.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7a32f70-Journeys_Connect_Segment_Engage_Blocks.png",
        "Journeys_Connect_Segment_Engage_Blocks.png",
        1051,
        248,
        "#edf2ee"
      ],
      "border": true
    }
  ]
}
[/block]
**Connect Engage & Segment Blocks**
After a user receives a message, you can add a segment after that to ensure that only users who meet the criteria specified by you are taken further in the Journey. 

Example: After users receive a push notification, wait for 1 day, check if users have transacted, for the people that have transacted, send them down path A, and for those who haven’t send them down path B.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/37b12e3-Journey_Connect_Engage_Segment_Blocks.png",
        "Journey_Connect_Engage_Segment_Blocks.png",
        973,
        388,
        "#ecf4f3"
      ],
      "border": true
    }
  ]
}
[/block]
**Connect Engage & Engage Blocks**
After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

Example: After a user receives a push notification, you can wait for 3 days, and send another push notification.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ee6bb98-Journeys_Connect_Engage_Engage_Blocks.png",
        "Journeys_Connect_Engage_Engage_Blocks.png",
        905,
        312,
        "#e2f8f8"
      ],
      "border": true
    }
  ]
}
[/block]
**Connect Segment & Segment Blocks**
After a user has been segmented, you can follow it up with with another segment to further refine your Journey. 

Example: If someone has not transacted in the last 30 days, send users who qualify for this segment down path A and if one of these users adds and item to their cart, and doesn’t buy within 15 mins, send them down a specific path.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/430bb85-Journeys_Connect_Segment_Segment_Blocks.png",
        "Journeys_Connect_Segment_Segment_Blocks.png",
        999,
        431,
        "#f9f7f4"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "Note",
  "body": "You can apply campaign limits in a Journey. However, global throttling is not supported in Journeys."
}
[/block]

###User Flow Management

Your users perform one action in a Journey and then move on to the next action. However, there may be instances when they do not move forward in the Journey. 

####**Users Waiting at Segment node**
There may be users waiting at the Segment node. For example, there may be users who added a product to the cart and did not buy it. They may have changed their decision or maybe they simply forgot about it. These users are waiting in the Journey until they perform the next action. You must be able to nudge them to perform the next action and continue the Journey. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/662237f-Journeys_Segment_Waiting_Users_Blink.png",
        "Journeys_Segment_Waiting_Users_Blink.png",
        456,
        200,
        "#fae6dc"
      ],
      "border": true,
      "caption": "Segment node"
    }
  ]
}
[/block]

You can send these users on a different path or exit them from the Journey completely. 

To send them on a different path, set the qualifying period and then send them to the following node to continue their Journey. 

 #####**Step 1 - Set the qualifying window**
Click the hexagon on the Segment node to set the qualifying window for the users. 

[block:callout]
{
  "type": "warning",
  "body": "The qualifying window must be set up in combination with the drawing of the Node Timeout connector. The users will not move if the Node Timeout is not connected to another node."
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6ae12e0-Journeys_Segment_timeout.gif",
        "Journeys_Segment_timeout.gif",
        1226,
        618,
        "#4b4b4b"
      ],
      "border": true,
      "caption": "Node timeout"
    }
  ]
}
[/block]
#####**Step 2 - Connect to another node** 
Connect the Node Timeout connector to another node. After the qualifying window is complete, the user automatically moves on to the next node through this timeout connector. For understanding node timeout evaluation schedule, please refer to advance section below. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6e3878f-Journey_Connect_Node_timeout.gif",
        "Journey_Connect_Node_timeout.gif",
        1238,
        654,
        "#fcfbfa"
      ],
      "border": true,
      "caption": "Connect Node"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "body": "The yellow indicator on your segment node is a reminder that you may need to plan for Waiting users on this node in the Journey.",
  "title": "Note"
}
[/block]
####**Users waiting at Engage node**
There may be another instance where the users have received a message but they may still wait for action. If the users do not click the message, then they are waiting for the next action.  It means that when you created the Journey, the node following the Engage node is connected with a 'Viewed' or 'Clicked' connector.  However, we have you covered! When you draw a  'Viewed' or 'Clicked' connector, a Phantom node with a node timeout will appear automatically. You can set the qualifying window from this Phantom node. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7d174d7-Journeys_pseudo_node.gif",
        "Journeys_pseudo_node.gif",
        1238,
        654,
        "#f9faf9"
      ],
      "border": true,
      "caption": "Phantom Node"
    }
  ]
}
[/block]
####**Force exit users**

You can use the Force exit operator node to create an exit for users in the Journey. For example,  if you want the users to exit and re-enter the current Journey you can set up this node.  Drag the Force exit node from the Operator Node pane and connect it to the Segment node.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2335591-Journey_Segment_timeout_Force_exit.gif",
        "Journey_Segment_timeout_Force_exit.gif",
        1240,
        616,
        "#fcfbfa"
      ],
      "border": true,
      "caption": "Force exit"
    }
  ]
}
[/block]

####**Update Profile Property** 

You may need to update your user's profiles based on some milestones. These milestones can be based on actions such as money spent, or time spent such as 6 months of active use, or a combination of both. For example, a ride-hailing app can update a user to platinum after 10 rides. 

To update a profile property within a Journey, drag a controller node called User profile update in the Journey. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/31d6eef-Journeys_profile_property_node.png",
        "Journeys_profile_property_node.png",
        1191,
        423,
        "#f2eef2"
      ]
    }
  ]
}
[/block]
Update the profile property with the required values. You can perform the following actions:

* Set to - You can set a property value. For example, set the customer type property to Platinum. 
* Add to array - Add a value to a list. For example, if a user marks a Gotham as a favorite, add it as a profile property to the  'Favourite Shows' array. 
* Remove from array - Remove a value from a list. For example, remove a profile property called Gotham from the  'Favourite Shows' array.
* Increment - Increment an integer value. For example, increment the 'Ride count' profile property whenever a user takes a ride. You can use it to track the number of rides taken by the user, in real-time. 
* Decrement - Reduce an integer value. For example, you can decrement the 'Free Trials Count' property every time a user takes a trial. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1fdf9da-Journeys_profile_property.png",
        "Journeys_profile_property.png",
        1007,
        477,
        "#f4f5f7"
      ],
      "border": true
    }
  ]
}
[/block]

For example, you can segment users based on their email engagement.  For maintaining an email reputation it is important to use multiple sending domains. You can leverage different domains for customers who open your email in the last 0-90 days via domain 1 and 91-180 days via domain 2.
You can do this for triggered campaigns and do not require a daily download or upload of users. This can also help maintain the reputation of an email domain by [sunsetting](https://docs.clevertap.com/docs/glossary#section-email-sunsetting), that is,  opting out users from receiving emails if they have not opened emails, such as emails in the last 90 days or the last 11 emails.

####**Auto Align & Space**
An elaborate Journey may contain multiple overlapping nodes and connections. The Auto Align & Space button will help you add clarity to the Journey canvas. 
Click the Auto Align & Space button on the upper right corner of the Journey canvas. 
The Auto Align & Space button automatically rearranges and spaces your nodes so that all the stats are visible clearly. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/73d6fc1-Journeys_rearrange.gif",
        "Journeys_rearrange.gif",
        1228,
        674,
        "#f4f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "warning",
  "title": "",
  "body": "The nodes on the Nodes Stats tab are arranged automatically so that all the stats are visible clearly."
}
[/block]


## Step 4: Add Goals to Your Journey

Goals are behaviors that you want users to perform. On completing a goal, users are exited from the Journey. You can drag and drop any segment from the right hand side palette and add it as a goal for your Journey. A Journey can support up to 3 goals, if a user completes any one of the goals, they will be exited from the Journey.

**Common Examples of Goals**
  * Action based goals: In this goal, users will exit your Journey as soon as they perform a goal, in real time. Example: Exit people as soon as they perform the “Charged” event, where “item” is “Red Nike Shoes”
  * Past behavior goals: Past behavior goals, like segments, are evaluated once every twenty four hours, at 12:00 am. Once the goal is evaluated, users who meet this goal will not be a part of the Journey from that day onwards. Example: Exit people if they have spent at least $300 in the last week. 


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
## Step 5: Save Journey 

We have now successfully built a Journey!

Now that we have built a Journey, save it. You can save a Journey in draft mode so that you can make more changes at a later date or time.  All edits are possible to the Journey at this stage. 

Click the Save button. 


## Step 6: Publish Journeys

When you are ready to publish your Journey and all the edits are complete, your Journey can go live. Open the Journey and click Publish.  You can view the [Journey Statistics](doc:viewing-statistics) page to check the status of your Journey.


[block:callout]
{
  "type": "warning",
  "title": "Editing a Journey",
  "body": "You can edit only the 'What' section in an engagement node after you publish a Journey."
}
[/block]
# Advanced Topics

##Stop/Pause Journeys

You can Stop or Pause a published journey either from within the journey (top right corner) or from the Journey listing page.
  * Pause will temporarily halt the qualification of new users in the Journey. You can use the same button to resume. Users already in journey will continue travelling through the journey or receiving messages. You can bulk pause or bulk resume paused journeys from the Journey listing page.
  * Stop will completely halt the journey. A stopped journey cannot be restarted. It will stop the qualification of new users, any user movement within the journey, and sending out any campaigns. You can bulk stop journeys from the Journey listing page.

##Archive Journeys

Generally, Journeys are created with the same name with the suffix being the only difference. 
With an increasing number of Journeys over time, it becomes difficult to manage these Journeys. 
Archiving Journeys can help you to keep only relevant and latest journeys for your reference on the main Journey listing page.

To archive Journeys, follow these steps:

1. Click Journeys. The Journeys page appears and lists all the available journeys. 
2. Select the required Journeys and click the Archive icon <img src= "https://files.readme.io/fe9ec79-Journeys_archive_icon.png" height=“30px” width=“30px” >on the top. 
[block:callout]
{
  "type": "info",
  "body": "Scheduled or running journeys cannot be archived.",
  "title": "Note"
}
[/block]
To unarchive a journey, follow the steps below:
1. Click Journeys. The Journeys page appears and lists all the available journeys. 
2. Select the **Show archived Journeys only** box at the bottom. All the archived Journeys are listed. 
3. Select the required Journeys and click the Unarchive icon <img src= "https://files.readme.io/0b500cd-Journeys_unarchive_icon.png" height=“30px” width=“30px” >.

## Past Behavior Segments & Journey Qualification
  * If your entry criteria is a Past Behavior segment, users will be qualified for your Journey at the start time specified.
  * If you have added a Past Behavior segment along your Journey that segment will be evaluated once a day at 12:00 AM (in the timezone of your account).
  * If you have added a Past Behavior segment as a goal that segment will be evaluated once a day at 12:00 AM (in the timezone of your account).
  * Node timeout Evaluation - Node timeout evaluation happens every 1 hour at 1 PM, 2 PM, 3 PM and so on, where start time depends on the account. Here is an example - 
- User A reaches a node 4 at 2:30 PM with node time out of 1 hour. Her window will get over at 3:30 PM after which even if the user performs the action, she will not move via ‘Yes’ path as the user is marked for node timeout. At 4 PM, user A will timeout. 
- User B reaches a node 4 at 3:30 PM with node timeout of 1 hour. Her window will get over at 4:30 PM after which even if the user performs the action, she will not move via ‘Yes’ path as user is marked for node timeout. At 4 PM, user B will NOT move out. At 5 PM (i.e. next evaluation run), the user will move via node timeout.
  * If you have added a Past Behaviour segment in middle of the journey and have drawn Node timeout path with qualifying window set less than 24hours value, all users might move via node timeout path as PBS is only evaluated every 24 hours.

##Set Do Not Disturb (DND) for Journeys

CleverTap provides an option for setting the “Do Not Disturb” hours for notification delivery while creating a journey. The DND feature manages message delivery via engaging nodes in journeys so that campaigns are only sent after the DND period or discarded.  If users send time-specific messages via journeys where they send notifications to registered users who requested a specific active time and a specific inactive time, notifications will only be sent during the active time. 

To set DND for Push, SMS, Email & Web Push journeys, perform the following steps:

1. On the entry node of a journey, you will see the checkbox for DND.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dc6ec56-2020-08-17_16-06-04_Edit_Journey_Criteria.png",
        "2020-08-17_16-06-04_Edit Journey Criteria.png",
        1105,
        603,
        "#fafafb"
      ]
    }
  ]
}
[/block]
2. Click the **Do Not Disturb (DND)** checkbox.
3. Select the days and input the times you do not want to send campaign notifications. If you want to use the same time inactive period for each day, click the Copy Time To All link.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3506690-2020-08-17_16-10-55_Select_DND.png",
        "2020-08-17_16-10-55_Select DND.png",
        1113,
        719,
        "#fafafc"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "DND Conflict Hours",
  "body": "If you schedule a message node to send out delivery during the scheduled DND hours, you will receive an error message. This error message appears at the publish of the journey."
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

##Set Campaign Frequency for Journeys

Campaign frequency provides the ability to define when the messages should be delivered. If a user qualifies outside this window, the message is discarded.

To set campaign frequency for In-app, Web pop-up, or Exit intent nodes in journeys, perform the following steps: 

1. Select *In-app* and click on the node to edit it.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0c61f4c-2020-08-17_16-22-32_Online_Journeys.png",
        "2020-08-17_16-22-32_Online Journeys.png",
        1090,
        644,
        "#f5f8fb"
      ]
    }
  ]
}
[/block]
2. Click the **Set frequency** checkbox.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ec08b02-2020-08-17_16-25-56_Journey_set_frequency.png",
        "2020-08-17_16-25-56_Journey_set frequency.png",
        1120,
        301,
        "#f6f7fa"
      ]
    }
  ]
}
[/block]
3. Select the days and input the times you do not want to send campaign notifications. If you want to use the same time inactive period for each day, click the **Copy Time To All** link.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6d4ba30-2020-08-17_16-30-44_Set_DND_Dates.png",
        "2020-08-17_16-30-44_Set DND Dates.png",
        1108,
        605,
        "#f7f9fc"
      ]
    }
  ]
}
[/block]
4. Click **Continue**.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]