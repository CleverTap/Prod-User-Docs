---
title: 'Journey: Troubleshooting and FAQs'
excerpt: Frequently asked Questions related to Journeys
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Frequently asked questions

### Q. Why do my users not qualify for journey entry and a goal completion?

CleverTap checks the freshness of every event once, before it reaches any journey processing.

An event qualifies only if the timestamp falls within 60 minutes in the past and 2 minutes in the future, relative to when CleverTap processes it. This check depends only on how old the event timestamp is, not on how or when the event was sent. A real-time API call carrying a delayed timestamp is checked the same way as a backfilled or historical event.

Events outside this window are discarded before entry or goal evaluation runs. So the restriction applies to both Action entry nodes and Goal completion.

### Q. What are the last nodes?

A. These are the nodes that do not have an output path. These nodes are present in Journeys without goals.

### Q. What happens to my users if my Journey does not have a goal?

A. If you do not set a goal, the users from the last node exit the Journey. Their Journey is considered complete when they reach the last node.

### Q. Where can I see the waiting users because of delay or sleep defined between two nodes?

A. You will see them on the following node under 'Waiting users.'

### Q. Why is the number of users on nodes not matching or adding up?

A. The count of the users depends on the selected date range. If the original date range of the Journey does not match the date range in your search, then the numbers will differ from the original.

### Q. How do I verify the number of users entering a specific node?

A. The number of users moving forward from a node will always match the number of users who are entering the following nodes.

### Q. Why are there discrepancies between the users who qualified for a Journey and those who entered a Journey?

A. There can be discrepancies between the users who qualified for a Journey and those who entered a Journey due to the Control Group.

### Q. Why my stats at the last node are not matching?

A. In the journeys created before Dec 27, 2019, You might see a mismatch of user counts or a drop in users. This is because earlier, we used a dummy wait step to post the last node, where users will move and wait for the goal to be met. In the new journeys (created post-Dec 27, 2019), the dummy step no longer exists, and this mismatch should not happen.

### Q. What are 'Non-Targetable' profiles?

A. 'Non-Targetable' profiles are profiles on a device other than a mobile device that do not possess any identity, email, phone, or token (web/ push).

### Q. What happens to Non-Targetable profiles if they reach the last engagement node?

A. If Journey Goal is set up, Non-Targetable profiles will accumulate under 'Waiting users' → 'Before Node' stats.<br />If the Journey Goal is not set up, Non-Targetable profiles will exit the journey.

### Q. What is this intermediate stat on node stat?

A. If you draw the same connector, such as 'Yes' multiple times from a node and connect it to multiple Segment nodes, the users will move after the first action.  The stats for these Waiting users are displayed as an intermediate node on the connector.


<Image src="https://files.readme.io/e0d470f-Journeys_multiple_Yes_Build.png" alt="785" align="center" border={true} />



<Image src="https://files.readme.io/960c1b8-Journeys_Multile_Yes_Node_stats.png" alt="1080" align="center" border={true} />


### Q. How will I see the stats for the Phantom node?

A.  A Phantom node appears only when a _Viewed_ or _Clicked_ connector is drawn from an Engage node. The originating node will display the Sent count and the Phantom node will display the Clicked or Viewed count. For more information on Phantom nodes, see [Users waiting at Engage nodes](https://docs.clevertap.com/docs/journeys#section-users-waiting-at-segment-node).


<Image src="https://files.readme.io/af5a2ea-Journeys_Pseudo_Node.png" alt="1162" align="center" border={true} />



<Image src="https://files.readme.io/8fac40f-Journeys_Pseudo_Node_Stats.png" alt="839" align="center" border={true} />


### Q. What are the different journey types in the past behavior segment?

A. One Time Journey is the type of journey that runs only for one time at the start time of the journey. Here there is no option to re-enter for the users who have exited the journey through journey timeout, force exit, or Goal completed. New users will not be added after the journey ran its course on the start time.

Multiple Dates Journey is the type of journey that will run on the multiple dates selected by you. You get to select the journey end time as per your use case for the journey. In this type of journey, the users can re-enter if the option of Allow users to re-enter the journey is selected.

The recurring journey is the type of journey that will repeatedly run and allow entry to new users on the criteria selected by you under the Repeat section. The first run would be as soon as you publish the Journey. The next runs will be according to the selected criteria. Once exited, users can re-enter the journey if the option of Allow users to re-enter the journey is selected.

### Q. How Does a Past Behavior Segment Journey Work?

A. In a PBS Journey, there is a processing time between when users qualify and when the message is sent. The following is a sample recurring PBS Journey.


<Image src="https://files.readme.io/d5c50e9-image.png" alt="Recurring Past Behaviour Segment Journey" align="center" border={true} />


Consider an example where you [publish](https://docs.clevertap.com/docs/journey-concepts#journey-procedures-and-outcomes) a weekly recurring PBS Journey. You schedule the _Journey entry timelines_ to _Now_ and _every Tuesday_. Assume you also publish it at 5 p.m. on a Tuesday, and the push notification must be sent at 8 p.m. Let us now understand how a Journey works, how users qualify, and when the users receive the message.

- The **[initial run](https://docs.clevertap.com/docs/journey-concepts#journey-procedures-and-outcomes)** of the Journey occurs right after you publish it at 5 p.m. on Tuesday. Only users who meet the criteria up to 5:00 p.m. enter the journey at this time and receive the message at 8:00 p.m. on the same day, i.e., Tuesday.
- The **second run** of the Journey happens on Wednesday at midnight. Any users who perform the event between 5:00 p.m. and 11:59 p.m. on Tuesday will only qualify at 12:00 a.m. on Wednesday. The message for this set of users is delivered at 8:00 p.m. on Wednesday.
- The **[third run](https://docs.clevertap.com/docs/journey-concepts#journey-procedures-and-outcomes)** of the Journey happens next Wednesday at 12:00 a.m., and this cycle continues. Any users who perform the event from this Wednesday to next week's Tuesday until 11:59 p.m. qualify at 12:00 a.m. next Wednesday.


<Image src="https://files.readme.io/d4645b5-PBSJourney_5.png" alt="User Qualification in a PBS Journey" align="center" width="90% " border={true} />


### Q: Why Do Users Who Failed To Meet the Inaction Criteria Move via the Node Timeout Path Instead of the No Path in a Journey?

A: Consider the inaction criteria defined as follows: Users performed action A but not action B within 2 minutes, with the node timeout set at 60 minutes.


<Image src="https://files.readme.io/005adfb-image.png" align="center" border={true} />


The user flow is outlined as follows:

- **Yes Path**: Users who completed A but not B within 2 minutes.
- **No Path**: Users who completed both A and B or users who completed A but not B for more than 2 minutes.
- **Node Timeout Path**: Users who did not complete A within the specified timeout.

Think of the node timeout as a security check at the entrance to the airport (segment), and consider the Yes and No paths as the second security check inside the airport.

### When multiple segments are connected to an action node, through which path does the user qualify?

A. Let's consider a journey where the entry segment is an Action node connected to action segments that are defined in a mutually exclusive manner, as shown in the following image. In this case, when the user completes the action, they enter the respective segments.


<Image src="https://files.readme.io/48eece1-image.png" alt="Journey with Multiple Segments " align="center" border={true} />


If the user fails to qualify for any connected segments, the path they should follow is determined by the node timeout connector associated with each segment. However, if multiple segments are connected simultaneously, creating competing paths, CleverTap does not support multiple node timeout connectors extending from parallel segments. Using only one node timeout connector is recommended for parallel segments because only one node timeout will apply to all parallel segments.

### Why is there a discrepancy between Via Sent count (Node Stats) and Sent count (Campaign Stats)?

A. Let's clarify:

- A represents the **Via Sent** count in Node Stats.
- B represents the **Sent** count in Campaign Stats.
- C represents the **Inbox TTL Expired Error** count in Campaign Stats.
- D represents all other errors on the Campaign Stats page, such as Unreachable, Failed, or Sent errors.


<Image src="https://files.readme.io/36dce32ee171111185e0f33944127da6660dcd6a2eff68fc51e87e92b0c7174b-Node_Stats_for_Inbox.png" alt="Node Stats for Inbox" align="center" width="75% " border={true} />


where, Via Sent count (A) = Sent count (B) +  Inbox TTL Expired Error count (C)

The **Via Sent** count (A) in Node Stats is calculated as the sum of the **Sent** count (B) and the **Inbox TTL Expired Error** count (C) in Campaign Stats. Therefore, it is expected to see a difference between these counts.

Other errors (D), like Unreachable, Failed, or Sent errors, are accounted for in **Waiting users - At Node**. These errors affect the total count of users waiting at a node.

### Why are the Waiting users - At Node numbers so high?

A. High numbers in this category occur when users are stuck at a node. This happens because the path (Unreachable, Failed, or Sent path) is not defined for users to move to the next node. These users then wait at the node until a defined action occurs, such as a goal event or timeout.

### What happens when the scheduled message time in PBS and Action Journeys conflicts with the dwell time?

If a user is scheduled to receive a push message in a PBS or Action journey at a specific time, for example, 12:00 PM. However, you have also set a dwell time for push messages that conflicts with this delivery time. Such users are marked as **Waiting users**, and the message delivery is attempted again in the next run.
