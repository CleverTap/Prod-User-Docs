---
title: Journeys
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
Journeys is a visual campaign builder that lets you create omnichannel messaging experiences for your users.

# Overview

Journeys are ideal for engaging users across the lifecycle of your app. 

To list a few sample use cases:

* Build User Onboarding Journeys that engage users over several days or weeks and on different channels as you educate them about your service.
* Build Promotional Journeys to entice your users to transact at different points of time.
* Long-running re-engagement campaigns to pull users back into your service if they begin to slip away.

You can access Journeys under the “Engage” section of your CleverTap Dashboard. Click on the “Journeys” link in the left nav bar in your CleverTap Dashboard. Once on the page, you can click on the “create” icon to create your first journey.

> 👍
>
> Journeys are only available to customers who are on the [Essentials plan](https://clevertap.com/pricing/).

# Journey Components

A Journey is a combination of Segment blocks and Engagement blocks. You can connect segment blocks and engagement blocks to each other to crate powerful automations

Types of Segment Blocks

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Segment Block
      </th>

      <th>
        What it does
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Action
      </td>

      <td>
        As soon as the user performs an action, the user enters this block
      </td>

      <td>
        Qualification to this block occurs as soon as the user performs the said event
      </td>
    </tr>

    <tr>
      <td>
        Inaction
      </td>

      <td>
        Segment users who did the 1st event, but did not do the 2nd event within a specified time interval
      </td>

      <td>
        E.g. Qualify users who added to cart, but did not purchase within 5 mins
      </td>
    </tr>

    <tr>
      <td>
        Past Behaviour
      </td>

      <td>
        Segment users who performed and did not perform a set of events in the past n days
      </td>

      <td>
        E.g. Users who did Video Watched AND did not do Subscription Paid in the Last 30 days
      </td>
    </tr>

    <tr>
      <td>
        Date Time
      </td>

      <td>
        Segment users based on a date time property value like flight time, etc.
      </td>

      <td>
        E.g. Users who have their flight after 2 hours
      </td>
    </tr>

    <tr>
      <td>
        Journey Trigger
      </td>

      <td>
        You can use this block in the entry criteria only.\
        A user is qualified on this block when the same user is qualified for the corresponding block in another Journey, from where the current Journey is triggered
      </td>

      <td>
        E.g. Journey 1 has a Push message block. You want to move all users who were sent the push into another Journey. Journey trigger allows you to do this
      </td>
    </tr>

    <tr>
      <td>
        Page Visit
      </td>

      <td>
        Segment users as soon as they visit a specific page
      </td>

      <td>
        Web based segment
      </td>
    </tr>

    <tr>
      <td>
        Referrer Entry
      </td>

      <td>
        Segment users based on a referring website or campaign
      </td>

      <td>
        Web based segment
      </td>
    </tr>

    <tr>
      <td>
        Page Count
      </td>

      <td>
        Segment users based on the number of pages visited by them
      </td>

      <td>
        Web based segment
      </td>
    </tr>
  </tbody>
</Table>

# Building Your First Journey

## Step 1: Define the Entry Criteria

When you start building your Journey, you need to define your “entry criteria”, this is the condition, which when met, users will enter and be a part of the Journey. The entry criteria of a Journey is essentially the segment of users you want to target.

The various types of segments you can use are:

* Live User segments: These segments qualify people as soon as they meet your specified criteria
* Past Behavior segments: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty four hours.

Live user segments are further bifurcated as follows:

* Action: In this type of Entry Criteria, users will enter your Journey, as soon as they perform an event. Example: Enter people into your Journey, as soon as they install your application.
* Inaction: Users enter your Journey, as soon as they don’t do something in the future. Example: If someone adds an item to their cart, but don’t transact within 15 mins.
* Property Date-time segments: Qualify a user relative to a specific date and time in a property.
* Page visit: Users will qualify as soon as they reach a web page that matches your specifications.
* Refer entry: When users come to your website from a certain referrer, example: Facebook, or Twitter, they will be qualified for your Journey.
* Page count: As soon as the user sees the specified number of pages, they will be a part of your Journey.

## Step 2: Select a Journey Conversion Time

Journeys are sequences of campaigns. At each stage of a Journey you can choose to further segment your audience as well as deliver campaigns across multiple channels.

While creating Journeys, you can choose to specify a Journey conversion time, this will be the maximum amount of time a user will spend in a Journey. Once this window is completed for a user, they will be exited from the Journey, no matter which stage they are at.

> 🚧 Once a user has exited the Journey, she is free to re-qualify, if you have allowed re-entry in your setup.

<Image title="journey1.png" alt={390} className="border" border={true} src="https://files.readme.io/6574eed-journey1.png" />

**Allow Users to Re-Enter a Journey**\
By default a user will qualify for a Journey only once. However, you can optionally allow users who have exited from a Journey to re-enter it should they meet the entry criteria at a later date.

Once a user is a part of a journey, the only way they can re-qualify is if they exit the journey, either by matching one of the specified goals, or by being forced out of the journey and subsequently meeting the specifications of the entry criteria.

Take the following simple example.

<Image title="journey2.png" alt={841} className="border" border={true} src="https://files.readme.io/5ac9276-journey2.png" />

When a user makes a purchase they enter into the Journey. After a 20 minute wait time qualifying users will receive a Push Notification with a discount promotion code.

If the Journey was set-up with the default behavior (users cannot re-enter the Journey) then after they purchase and receive the push notification they exit from the Journey. If a user makes another purchase subsequent to the initial purchase they will not receive another promotional Push Notification since this Journey does not allow for re-entry.

If however, your intent is to allow users to receive a new promotional discount after each subsequent purchase, you’d select the option to allow a user to re-enter as follows.

<Image title="journey3.png" alt={386} className="border" border={true} src="https://files.readme.io/05c039b-journey3.png" />

## Step 3: Define the Journey

**Connect Segment & Engage Blocks**\
Once you have defined a segment of users, you can choose to communicate with the segment by dragging and dropping a channel of communication from the palette on the right hand side. This communication could go to users who match the segment criteria specified by you, or to the rest of the users i.e. the users who don’t match your segment criteria.

<Image title="journey4.png" alt={668} className="border" border={true} src="https://files.readme.io/5592499-journey4.png" />

**Connect Engage & Segment Blocks**\
After a user receives a message, you can add a segment after that to ensure that only users who meet the criteria specified by you are taken further in the journey. 

Example: After users receive a push notification, wait for 1 day, check if users have transacted, for the people that have transacted, send them down path A, and for those who haven’t send them down path B.

<Image title="journey5.png" alt={935} className="border" border={true} src="https://files.readme.io/ede4aad-journey5.png" />

**Connect Engage & Engage Blocks**\
After a user receives a message, you can follow it up immediately, or with a delay with another message on a channel of communication of your choosing. 

Example: After a user receives a push notification, you can wait for 3 days, and send another push notification.

<Image title="journey6.png" alt={700} className="border" border={true} src="https://files.readme.io/90c3af7-journey6.png" />

**Connect Segment & Segment Blocks**\
After a user has been segmented, you can follow it up with with another segment to further refine your journey. 

Example: If someone has not transacted in the last 30 days, send users who qualify for this segment down path A and if one of these users adds and item to their cart, and doesn’t buy within 15 mins, send them down a specific path.

<Image title="journey7.png" alt={736} className="border" border={true} src="https://files.readme.io/ecdbdbe-journey7.png" />

## Step 4: Add Goals to Your Journey

Goals are behaviors that you want users to perform. On completing a goal, users are exited from the journey. You can drag and drop any segment from the right hand side palette and add it as a goal for your journey. A journey can support up to 3 goals, if a user completes any one of the goals, they will be exited from the journey.

**Common Examples of Goals**

* Action based goals: In this goal, users will exit your journey as soon as they perform a goal, in real time. Example: Exit people as soon as they perform the “Charged” event, where “item” is “Red Nike Shoes”
* Past behavior goals: Past behavior goals, like segments, are evaluated once every twenty four hours, at 12:00 am. Once the goal is evaluated, users who meet this goal will not be a part of the journey from that day onwards. Example: Exit people if they have spent at least $300 in the last week. 

<Image title="journey8.png" alt={746} className="border" border={true} src="https://files.readme.io/49a8f33-journey8.png" />

# Viewing Statistics for Your Journey

You can see stats for your journey in 2 modes:

* Real Time View
* Stats View

The stats are shown as an overlay on top of your canvas. If you click on a segment block, it will take you to the segment details page. If you click on a campaign block, it will take you to the campaign details page, so you can carry out further analysis.

**Real Time Stats View**\
In this view, you will see a snapshot of how many people are currently in your journey, and at what stage of the journey are these people at. You can use this view to figure out if a vast majority of people are stuck at a certain level, which you might want to make edits to upcoming journeys.

**Historical Stats View**\
This view will show you comprehensive details of your journey for whatever time frame you select. In this view, you will see how many people have qualified for a particular segment or campaign. You will also see how many people have exited at each stage.

# Performance Attribution

The stats and user exit criteria for a Journey will be different depending on if you set a Journey goal and/or a conversion time.

## Concepts

* **Entry:** All users who have entered the Journey (first node).
* **Goal Met:** If a goal is set in the Journey builder, these are all users who met the goal.
* **Time Out:** If a conversion time is set in the Journey builder (entry criteria), these are all the users who timed out before meeting the Journey goal.
* **Completed:** If a goal is not set in the Journey builder, these are all the users who successfully reached the last node of the Journey.

## How Enabling a Goal and/or Conversion Time Impact Journey's Exit Criteria & Reporting

The table below describes the different options for enabling a goal and/or conversion time, and their impact on how users exit a Journey and how stats are reported for a Journey. 

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>

      </th>

      <th>
        Stats Page
      </th>

      <th>
        List Page
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Goal Set AND Conversion Time Set
      </td>

      <td>
        * Every node will have Goal Met stats. All users who met the goal will move into the Goal node.
        * Every node will have a Time Out. All users who timed out will move into the Time Out node.
      </td>

      <td>
        * Entry
        * Goal Met
        * Time Out
        * Conversion % = (Goal Met/Entry)\*100\ <br />
      </td>
    </tr>

    <tr>
      <td>
        Goal Set BUT Conversion Time Not Set
      </td>

      <td>
        * Every node will have Goal Met stats. All users who met the goal will move into the Goal node.
        * Users will NOT time out from the Journey.
      </td>

      <td>
        * Entry
        * Goal Met
        * Conversion % = (Goal met/Entry)\*100\ <br />
      </td>
    </tr>

    <tr>
      <td>
        Goal Not Set BUT Conversion Time Set
      </td>

      <td>
        * Goal met stats will NOT be available.
        * Users who reach the last node of the Journey will be said to be Completed the Journey and will be counted under the Completed stats.
      </td>

      <td>
        * Entry
        * Completed
        * Time Out
        * Conversion = (Completed/Entry)\*100\ <br />
      </td>
    </tr>

    <tr>
      <td>
        Goal Not Set AND Conversion Time Not Set
      </td>

      <td>
        * Goal met stats will NOT be available.
        * Users will NOT time out from the Journey.
      </td>

      <td>
        * Entry
        * Completed
        * Conversion = (Completed/Entry)\*100\ <br />
      </td>
    </tr>
  </tbody>
</Table>

# Advanced Topics

## Past Behavior Segments & Journey Qualification

* If your entry criteria is a Past Behavior segment, users will be qualified for your journey at the start time specified.
* If you have added a Past Behavior segment along your journey that segment will be evaluated once a day at 12:00 am (in the timezone of your account).
* If you have added a Past Behavior segment as a goal that segment will be evaluated once a day at 12:00 am (in the timezone of your account).
