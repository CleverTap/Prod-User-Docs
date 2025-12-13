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

## Define the Entry Criteria

When you start building your Journey, you need to define your *entry criteria*, this is the condition, which when met, users will enter and be a part of the Journey. The entry criteria of a Journey is essentially the segment of users you want to target.

The various types of segments you can use are:

* Live User segments: These segments qualify people as soon as they meet your specified criteria
* Past Behavior segments: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty-four hours.

Live user segments are further bifurcated as follows: 

* Action: In this type of *entry criteria*, users will enter your Journey, as soon as they perform an event. For example: Enter people into your Journey, as soon as they install your application.
* Inaction: Users enter your Journey, as soon as they don’t do something in the future. For example: If someone adds an item to their cart, but doesn’t transact within 15 mins.
* Property Date-time segments: Qualify a user relative to a specific date and time in a property.
* Page visit: Users will qualify as soon as they reach a web page that matches your specifications.
* Refer entry: When users come to your website from a certain referrer, for example Facebook, or Twitter, they will be qualified for your Journey.
* Page count: As soon as the user sees the specified number of pages, they will be a part of your Journey.

> 📘 Journey Scheduler
>
> We support one time, multiple dates, and recurring Journeys.\
> For example, for monthly payment reminders, you can schedule a Journey to start on the 1st of every month

## Select a Journey Timeout

Journeys are sequences of campaigns. At each stage of a Journey, you can choose to further segment your audience as well as deliver campaigns across multiple channels.

While creating Journeys, you can choose to specify a Journey Timeout, this will be the maximum amount of time a user will spend in a Journey. Once this window is completed for a user, they will be exited from the Journey, no matter which stage they are at.

> 🚧 Once a user has exited the Journey, the user is free to re-qualify, if you have allowed re-entry in your setup.

<Image title="Journeys_Timeout.png" alt={715} className="border" border={true} src="https://files.readme.io/0dfbbd2-Journeys_Timeout.png" />

**Allow Users to Re-Enter a Journey**\
By default, a user will qualify for a Journey only once. However, you can optionally allow users who have exited from a Journey to re-enter it should they meet the entry criteria at a later date.

Once a user is a part of a Journey, the only way they can re-qualify is if they exit the Journey, either by matching one of the specified goals or by being forced out of the Journey and subsequently meeting the specifications of the entry criteria.

Take the following simple example.

![1052](https://files.readme.io/d00fca9-Journeys_Allow_users_reentery.png "Journeys_Allow_users_reentery.png")

When a user makes a purchase they enter into the Journey. After a 20 minute wait time, qualifying users will receive a Push Notification with a discount promotion code.

If the Journey was set up with the default behavior (users cannot re-enter the Journey) then after they purchase and receive the push notification they exit from the Journey. If a user makes another purchase subsequent to the initial purchase they will not receive another promotional Push Notification since this Journey does not allow for re-entry.

If however, your intent is to allow users to receive a new promotional discount after each subsequent purchase, you’d select the option to allow a user to re-enter as follows.

<Image title="Journeys_Re-enter_Users.png" alt={656} className="border" border={true} src="https://files.readme.io/bd74cac-Journeys_Re-enter_Users.png" />

## Define the Journey

**Connect Segment & Engage Blocks**\
Once you have defined a segment of users, you can choose to communicate with the segment by dragging and dropping a channel of communication from the palette on the right-hand side. This communication could go to users who match the segment criteria specified by you, or to the rest of the users i.e. the users who don’t match your segment criteria.

> 📘 Tip on Duplicating Segments
>
> To duplicate a specific segment, use the copy/paste function by hovering over a segment, then perform the following:
>
> * MacOS: Alt + mouse click 
> * Windows: Ctrl + mouse click

<Image title="Journeys_Connect_Segment_Engage_Blocks.png" alt={1051} className="border" border={true} src="https://files.readme.io/7a32f70-Journeys_Connect_Segment_Engage_Blocks.png" />

**Connect Engage & Segment Blocks**\
After a user receives a message, you can add a segment after that to ensure that only users who meet the criteria specified by you are taken further in the Journey. 

Example: After users receive a push notification, wait for 1 day, check if users have transacted, for the people that have transacted, send them down path A, and for those who haven’t send them down path B.

<Image title="Journey_Connect_Engage_Segment_Blocks.png" alt={973} className="border" border={true} src="https://files.readme.io/37b12e3-Journey_Connect_Engage_Segment_Blocks.png" />

**Connect Engage & Engage Blocks**\
After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

Example: After a user receives a push notification, you can wait for 3 days, and send another push notification.

<Image title="Journeys_Connect_Engage_Engage_Blocks.png" alt={905} className="border" border={true} src="https://files.readme.io/ee6bb98-Journeys_Connect_Engage_Engage_Blocks.png" />

**Connect Segment & Segment Blocks**\
After a user has been segmented, you can follow it up with another segment to further refine your Journey. 

Example: If someone has not transacted in the last 30 days, send users who qualify for this segment down path A and if one of these users adds an item to their cart, and doesn’t buy within 15 mins, send them down a specific path.

<Image title="Journeys_Connect_Segment_Segment_Blocks.png" alt={999} className="border" border={true} src="https://files.readme.io/430bb85-Journeys_Connect_Segment_Segment_Blocks.png" />

> 🚧 Note
>
> You can apply campaign limits in a Journey. However, global throttling is not supported in Journeys.
