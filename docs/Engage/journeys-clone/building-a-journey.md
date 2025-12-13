---
title: Building a Journey
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
# Building Your First Journey

Let us build a simple journey.  Assume that some users add a pair of shoes to the cart but do not buy within 5 minutes. We will create a Journey where the users will receive reminders and offers through mobile push and an email. The Journey ends after the user makes a purchase. Let's start!

You can access Journeys under the “Engage” section of your CleverTap Dashboard. Click “Journeys” from in the left navigation bar in your CleverTap Dashboard. Click the "+Journey" button to create your first journey.  


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/598f235-Journeys_Main_List_Create.png",
        "Journeys_Main_List_Create.png",
        1437,
        690,
        "#dbdde1"
      ],
      "border": true
    }
  ]
}
[/block]

## Step 1: Define the Entry Criteria

When you start building your Journey, you must define the “entry criteria”. When these criteria are met, the users can enter a Journey.  All the users who fulfill the entry criteria become the target segment. 

The various types of segments you can use are:
  * Live User segments: These segments qualify people as soon as they meet your specified criteria. 
  * Past Behavior segments: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty-four hours. 


For more information on segments, see [Segments](doc:segments-2)

In our example, we want to identify all users who abandoned the cart after adding shoes. 

###**Set the entry criteria**

You can select or create a user segment that qualifies your requirements.  In our example, we select users based on user inaction. These are the users who have made a decision to purchase but did not complete it. Drag the Inaction node into the Journey.




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0118ba3-Journeys_Entry_Segment_Drag.png",
        "Journeys_Entry_Segment_Drag.png",
        1213,
        652,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
You can drag and drop any of the segment nodes. 

[block:callout]
{
  "type": "info",
  "body": "The entry criteria is always a segment node."
}
[/block]

###**Select the start and end time for Journeys**

After you drag and drop the Entry node, you can edit it to define the start and end time for the Journey. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1af7794-Journeys_Entry_Node.png",
        "Journeys_Entry_Node.png",
        438,
        205,
        "#f0ebed"
      ],
      "border": true
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/39e425c-Journey_Entry_When.png",
        "Journey_Entry_When.png",
        1440,
        900,
        "#f0f1f5"
      ],
      "border": true
    }
  ]
}
[/block]
### **Define Journey timeouts**

Journeys are sequences of campaigns. At each stage of a Journey, you can choose to filter your target audience as well as deliver campaigns over multiple channels.

While creating Journeys, you can choose to specify a Journey timeout. This is the maximum amount of time a user will spend in a Journey. After the Journey timeout is complete for users, they exit the Journey, irrespective of the stage of their journey.  The default Journey timeout is 6 months.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34a9ebe-Journeys_Re-enter_Users.png",
        "Journeys_Re-enter_Users.png",
        376,
        390,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Journey Scheduler",
  "body": "We support One time, Multiple date and recurring Journeys.\nFor example, for monthly payment reminders, you can schedule a Journey to start on the first day of every month."
}
[/block]
###**Re-enter users**
A user can qualify for a Journey only once. However, you can allow users who have exited from a Journey to re-enter it, if they pass the entry criteria on a later date.

The users who are a part of an existing Journey can only qualify after they exit the Journey, either by meeting the goal or by being forced out and then matching the journey criteria again. 

Let's see it in our example.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2bcad63-Journeys_Reenter_Users.png",
        "Journeys_Reenter_Users.png",
        683,
        98,
        "#80d7ee"
      ]
    }
  ]
}
[/block]
When users add a product to the cart they enter a Journey. If they do not purchase the product within 5 minutes, they are sent a Push Notification with a discount promotion code.

If the Journey was set-up with the default behavior (users cannot re-enter the Journey) they exit from the Journey after they receive the push notification. If a user adds another product to cart they will not receive another promotional Push Notification because this Journey does not allow for re-entry.

If however, your intent is to allow users to receive the promotional discount after each subsequent add to cart, you can allow the user to re-enter. For example, the user now adds a pair of socks to the cart. You may want to send a different discount code for it. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/34a9ebe-Journeys_Re-enter_Users.png",
        "Journeys_Re-enter_Users.png",
        376,
        390,
        "#f7f8f9"
      ],
      "border": true
    }
  ]
}
[/block]

###**Control Groups**

These are the set of users who are not sent any messages so that they can be used to compare as a base for the conversion rates of engagement campaigns. 
There are 3 types of control groups:
* System Control Group:  It includes 5 percent of the users by default. It is defined at the account level. 
* Campaign Control Group: This group is defined at a campaign level for each campaign. 
* Custom Control Group: This group is defined by CleverTap users according to their requirements. 

For more information on control groups, see [Control Groups](doc:control-groups-2) .

## Step 2: Define the Journey

You can start creating your Journey now. You can connect the Segment and Engagement nodes in different ways to create a Journey. 

###Drag and Drop Nodes
<<Need info>> <<Need to add GIF>>

###Connect and edit Nodes
<<Need info>> <<Need to add GIF>>

###Reuse and duplicate Nodes
<<Need info>> change the connection from one node to another so that the old node can be reused somewhere else. 

<<Need to add GIF>>

### Edit Connectors
<<Need info>> change the timeout

<<Need to add GIF>>


###**Connect Engage and Segment Nodes**
After a user receives a message, you can add a segment node to filter users who meet the criteria. This is the stage where you can talk to them through messages and convince them for a purchase. 

For example, after users receive a push notification:
 1.Wait for 1 day, 
2.Check if users have transacted, 
3.For the people that have transacted, send them down path A, 
4.For those who haven’t transacted send them down path B.

In our example, we select users who have received a push notification and add another segment for users who added the product to the cart again.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1e2f341-Journeys_Node_Connect_Engagment_Segment.png",
        "Journeys_Node_Connect_Engagment_Segment.png",
        1042,
        135,
        "#e1e9eb"
      ],
      "border": true
    }
  ]
}
[/block]

###**Connect Segment and Engage Nodes**
After you have defined a segment of users, you can choose to communicate with the segment using messages. You can drag and drop a channel of communication from the Engagement Nodes on the right-hand side. This communication is sent to the intended users. 

In our example, we have created a segment for users who have purchased the product. We then send them a thank you email. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9d619ef-Journeys_Node_Connect_Segment_Engagment.png",
        "Journeys_Node_Connect_Segment_Engagment.png",
        626,
        569,
        "#e7e8e2"
      ],
      "border": true
    }
  ]
}
[/block]

###**Connect Engage & Engage Nodes**
After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

In our example, after a user receives an email notification, you can wait for a day, and send another email notification to rate the purchase. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/be8a505-Journeys_Node_Connect_Engagment_Engagement.png",
        "Journeys_Node_Connect_Engagment_Engagement.png",
        963,
        140,
        "#86e3e3"
      ],
      "border": true
    }
  ]
}
[/block]
###**Connect Segment & Segment Nodes**
After a user has been segmented, you can follow it up with another segment to further refine your users in the Journey. 


For example, some users made a purchase after adding shoes to their cart but some users abandoned the cart again. If there is no action, then you can force exit them out of the Journey. You can then filter users who have actually purchased the product and send them on the next stage of the Journey.

There may be cases where some users just sit in the Journey and do not perform any action. You can exit these users with a Force Exit operator.  For more information, on force exit, see [Operator Nodes](https://docs.clevertap.com/docs/journey-components#section-operator-nodes)


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a5054fa-Journeys_Node_Connect_Segment_Segment.png",
        "Journeys_Node_Connect_Segment_Segment.png",
        1062,
        447,
        "#f8e7e2"
      ],
      "border": true
    }
  ]
}
[/block]

## Step 4: Add Goals to Your Journey

Goals are the objectives of your user Journey. A Journey is complete after the users have performed the defined actions in the Journey and fulfilled the objective. The users exit a Journey after achieving the goal. 
You can drag and drop any segment and add it as a goal for your Journey. A Journey can support up to 3 goals, if a user completes any one of the goals, they exit the Journey.

In our example, we set shoe purchase as a goal. The users that have completed their goal exit the Journey. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a39d24d-Journeys_Goal.png",
        "Journeys_Goal.png",
        1235,
        661,
        "#f1f1f4"
      ]
    }
  ]
}
[/block]
###No Goal Added
<<Need info>>

###Goal and Conversion Time
<<Need info>>
**Common Examples of Goals**
  * Action based goals: In this goal, the users will exit your journey as soon as they perform a goal, in real-time. For example, exit people as soon as they perform the “Charged” event, where “item” is “Red Nike Shoes.”
  * Past behavior goals: Past behavior goals, such as segments, are evaluated once every twenty-four hours, at 12:00 am. After the goal is evaluated, users who meet this goal exit the Journey on the same day. For example, exit people if they have spent at least $300 in the last week. 

###User Flow Management <<TBD>>

Your users perform one action in a Journey and then move on to the next action. However, there may be instances when they do not move forward in the Journey. 

**Users waiting at Segment node**
For example, there may be users who added a product to the cart and did not buy it. They may have changed their decision or maybe they simply forgot about it. These users are waiting in the Journey until they perform the next action. You must be able to nudge them to perform the next action and continue the Journey. 

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

To send them on a different path, set the qualifying window and then send them to the following node. 

 **Set the qualifying window**
Click the Segment Node timer to set the maximum time that a user can remain in the segment. 
<<TBD - add qualifying window>>


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
**Connect to another node** 
Connect the node timeout connector to another node. After the set duration, the user moves on to the next node through the timeout path/connector. 

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
  "body": "The yellow blinking circle on your segment node is a reminder that you may need to plan for waiting users in the Journey.",
  "title": "Note"
}
[/block]
**Users waiting at Engage node**
There may be another instance where the users that have received a message but they may still wait for action. If the users do not click the message, then they are waiting for the next action.  It means that when you created the Journey, the node following the Engage node is connected with a 'Viewed' or 'Clicked' connector.  However, we have you covered! When you draw a  'Viewed' or 'Clicked' connector, a pseudo node with a node timeout will appear automatically. You can set the timeout from this pseudo node. 

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
      "caption": "Pseudo Node"
    }
  ]
}
[/block]
**Force exit users**

You can use the Force exit operator node to create an exit for users in the Journey. This can be useful if you want the users to exit and re-enter the current Journey.  Drag the Force exit node from the Operator Node pane and connect it to the Segment node.

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
## Step 5: Save Journey 

We have now successfully created a Journey!

Now that we have created a Journey, save it. You can save a Journey in draft mode so that you can make more changes at a later date or time.  All edits are possible to the Journey at this stage. 

Click the Save button. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2547701-Journey_Example_All_cases.png",
        "Journey_Example_All_cases.png",
        1381,
        840,
        "#f2f5f8"
      ],
      "border": true
    }
  ]
}
[/block]
## Step 6: Publish Journeys

When you are ready to publish your Journey and all the edits are complete, your Journey can go live. Open the Journey and click Publish.  You can view the [Viewing Journey Statistics](doc:viewing-statistics) page to check the status of your Journey.


[block:callout]
{
  "type": "warning",
  "title": "Editing a Journey",
  "body": "You can edit only the 'What' section in an engagement node after you publish a Journey."
}
[/block]
##Frequently Asked Questions

Past Behavior Segments & Journey Qualification
If your entry criteria is a Past Behavior segment, users will be qualified for your journey at the start time specified.
If you have added a Past Behavior segment along your journey that segment will be evaluated once a day at 12:00 am (in the timezone of your account).
If you have added a Past Behavior segment as a goal that segment will be evaluated once a day at 12:00 am (in the timezone of your account).