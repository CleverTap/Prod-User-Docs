---
title: Journey Performance
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Concepts

Before diving into Journey statistics, it is essential to understand a few key terms. These concepts define how user progress is tracked through the Journey and help you interpret the stats more accurately.

* **Goal Met**: If a goal is set in the Journey builder, these are all users who met the goal. 
* **Journey Timeout** : If a Journey timeout is set in the Journey builder (entry criteria), all the users are timed out.
* **Node Timeout**: The qualifying window set for the node, after which users will proceed to the next node via the Node Timeout connector.
* **Version Exit**: The number of users who exited the journey from this version after reaching the selected node.

# Overview

Click *Engage* > *Journeys* from the left side menu. The *Journey List* page opens. Search for a journey and then click to open a Journey. The *Journey Canvas* displays the following four tabs for each journey version:

* **Overview Tab**: Displays your Journey components and connections.

<Image alt="Journey Overview" align="center" border={true} src="https://files.readme.io/d496b300449c1c3018e442bb1038afc3adce9e291abf24f8f3aaeb3a91e40389-Journey_Overview.png">
  Journey Overview
</Image>

* [Node Stats Tab](doc:node-stats-edit-a-journey): Displays stats for each Node.

<Image title="View node stats" alt={2718} align="center" width="100% " border={true} src="https://files.readme.io/92241da5ad3812b526cc4b34cded38c744dca321e1e81471541fbb3a716024d3-Node_Stats_-_Edit_Journey.png">
  Node Stats
</Image>

* [Engagement Stats Tab](doc:engagement-stats-edit-a-journey): Displays stats for the Engagement.

<Image alt="Engagement Stats" align="center" border={true} src="https://files.readme.io/cf5c0bc1dfed07874ea2f15ae7b145c1e7aa17a4324091632419b31e6fd69f71-Engagement_Stats_-_edit_journey.png">
  Engagement Stats
</Image>

* [Journey Stats Tab](doc:journey-stats-edit-a-journey): Displays stats for the Journey.

<Image title="View Journey stats" alt={2718} align="center" width="100% " border={true} src="https://files.readme.io/d56b82bd9e5a06a3072ddaad7f3955b6aeca835788a2258fc6bebd1ac88b0bf6-Journey_Stats.png">
  Journey Stats
</Image>

If a Journey has been edited after publishing, it may have multiple versions. To view metrics for a different version, select the desired version using the Version Selector at the top.

# Frequently asked questions

### Why do my users not qualify?

Check if your user matches all the entry-level segments in the initial node.\
If it is an action, check if the event is from API. If yes, then check if you are passing the event in real-time or in batches. Passing the event with a backdated timestamp will not qualify users in a live-action.

### What are the last nodes?

These are the nodes without an output path, which are present in Journeys without goals. 

### What happens to my users if my Journey does not have a goal?

If you do not set a goal, the users from the last node exit the Journey. Their Journey is considered complete when they reach the last node. 

### Where can I view the users who are waiting due to a delay or sleep defined between two nodes?

You will see them on the following node under 'Waiting users'. 

### What are *Unreachable* profiles?

*Unreachable* profiles are profiles that lack an identity, email, phone number, or token (web/push).

### What happens to Unreachable profiles if they reach the last engagement node?

If the Journey Goal is set up, *Unreachable* profiles move to *Waiting users* > *Before Node* stats.\
If the Journey Goal is not set up, *Unreachable* profiles exit the journey.

### Why is the number of users on nodes not matching or adding up?

The count of users depends on the selected date range. If the original date range of the Journey does not match the date range in your search, then the numbers will differ from the original. 

### How do I verify the number of users entering a specific node?

The number of users moving forward from a node will always match the number of users who are entering the following nodes.

### What is this intermediate stat on node stat?

If you draw the same connector, such as 'Yes',  multiple times from a node and connect it to multiple Segment nodes, the users will move after the first action.  The stats for these Waiting users are displayed as an intermediate node on the connector.  

<Image title="Journeys stats for multiple Yes build" alt={785} align="center" border={true} src="https://files.readme.io/e0d470f-Journeys_multiple_Yes_Build.png">
  Intermediate Node - Build
</Image>

<Image title="Journeys stats for intermediate node" alt={1080} align="center" border={true} src="https://files.readme.io/960c1b8-Journeys_Multile_Yes_Node_stats.png">
  Intermediate Node - Stats
</Image>

### How will I see the stats for the Phantom node?

A Phantom node appears only when a *Viewed* or *Clicked* connector is drawn from an Engage node. The originating node will display the Sent count, and the Phantom node will display the Clicked or Viewed count. For more information on Phantom nodes, refer to [Users waiting at Engage nodes](https://docs.clevertap.com/docs/journeys#section-users-waiting-at-segment-node).

<Image title="Journeys stats for Phantom node" alt={1162} align="center" border={true} src="https://files.readme.io/af5a2ea-Journeys_Pseudo_Node.png">
  Phantom Node - Build
</Image>

<Image title="Journeys stats for Phantom node" alt={839} align="center" border={true} src="https://files.readme.io/8fac40f-Journeys_Pseudo_Node_Stats.png">
  Phantom Node - Stats
</Image>
