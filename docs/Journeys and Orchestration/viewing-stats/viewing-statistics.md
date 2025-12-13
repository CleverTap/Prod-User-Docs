---
title: Viewing Journey Stats
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
# Concepts

You will need to know some key terms to understand the Journey stats.

* **Goal Met:** If a goal is set in the Journey builder, these are all users who met the goal. 
* **Journey Timeout:** If a Journey timeout is set in the Journey builder (entry criteria), these are all the users who timed out.
* **Node Timeout:**  The qualifying window that is set for the node, after which the users will move on to the next node via Node timeout connector.
* **Completed:** If a goal is not set in the Journey builder, these are all the users who successfully reached the last node of the Journey.

# Overview

Click *Engage* > *Journeys* from the left side menu. The *Journey List* page appears. Search for a journey and then click to open a Journey.  The *Journey Canvas* has three tabs:

1. Build - Shows your Journey components and connections

<Image title="Journeys_tab_build.png" alt={1376} border={true} src="https://files.readme.io/03a1fad-Journeys_tab_build.png">
  Build Journey
</Image>

2. Node Stats - Shows stats for each node

<Image title="Journeys_Tab_Node_Stats.png" alt={1378} border={true} src="https://files.readme.io/c175c06-Journeys_Tab_Node_Stats.png">
  Node stats
</Image>

3. Journey Stats - Shows stats for the Journey

<Image title="Journeys_Tab_Journey_Stats.png" alt={1379} border={true} src="https://files.readme.io/6141b6b-Journeys_Tab_Journey_Stats.png">
  Journey Stats
</Image>

# Node Stats

The Node Stats tab shows you the stats for each node. You can account for all users who entered the Journey and their current state.

Click the **Node Stats** tab. Select the *date range* from the calendar. The following shows how to check the statistics for each of the node types:

## Entry Node

This is the first node in the Journey. There can be only one *Entry* node.  An *Entry* node can only be a *Segment* node. 

<Image title="Journeys_node_Entry.png" alt={317} width="smart" src="https://files.readme.io/f7aca14-Journeys_node_Entry.png">
  Entry node
</Image>

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Stat
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Qualified
      </td>

      <td>
        The total number of users who qualified for the journey. This stat is available only on the entry node.
      </td>
    </tr>

    <tr>
      <td>
        Entered Journey
      </td>

      <td>
        The users who have entered a Journey via node connectors, such as Yes or No.
      </td>
    </tr>

    <tr>
      <td>
        Control Group
      </td>

      <td>
        The number of users who were marked for the control group. 

        A control group is a set of users who do not receive any marketing campaigns. You can measure the effectiveness of your initiatives by comparing this group with the target group of users who received your campaigns.
      </td>
    </tr>
  </tbody>
</Table>

## Segment Nodes

<Image title="Journeys_node_Segment.png" alt={316} src="https://files.readme.io/5a1ed63-Journeys_node_Segment.png">
  Segment node
</Image>

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Stat
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Entered Node
      </td>

      <td>
        The total number of users who entered the node. It includes the sum of all the users from Moved forward, Waiting users, Goal Met, and Journey timeout.
      </td>
    </tr>

    <tr>
      <td>
        Moved forward
      </td>

      <td>
        The users who have moved forward via node connectors, such as Yes, No, or Node Timeout.
      </td>
    </tr>

    <tr>
      <td>
        Waiting users
      </td>

      <td>
        The users waiting at a node to qualify. The users may wait for either of the 2 reasons: 

        1. Delay from a previous node
        2. Waiting to perform an action
      </td>
    </tr>

    <tr>
      <td>
        Goal Met
      </td>

      <td>
        These are the users who have performed the intended goal, such as viewing a movie or purchasing a product.
      </td>
    </tr>

    <tr>
      <td>
        Journey timeout exits
      </td>

      <td>
        These are the users who exited the Journey after the time duration set for the Journey, that is, Journey Timeout is complete.
      </td>
    </tr>
  </tbody>
</Table>

## Engage Nodes

Simply put, *Engage* nodes are campaigns. You can see the stats of each campaign from the *Node Stats* tab. Click the **Engage** node from the *Nodes Stats* tab to see the campaign statistics. 

<Image title="Journeys_nodes_Engage.png" alt={315} src="https://files.readme.io/e443e68-Journeys_nodes_Engage.png">
  Engage node
</Image>

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Stat
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Entered Node
      </td>

      <td>
        The total number of users who entered the node. It includes the sum of all the users from Moved forward, Waiting users, Goal Met, and Journey timeout.
      </td>
    </tr>

    <tr>
      <td>
        Moved Forward
      </td>

      <td>
        The users who have moved forward via node connectors, such as Sent, Viewed, Clicked, Failed, and Unreachable.
      </td>
    </tr>

    <tr>
      <td>
        Waiting users
      </td>

      <td>
        These users may wait for either of the 2 reasons: 

        1. Before Node: Delay from a previous node
        2. At Node: The outcome for these users is not defined. For example, if the 'Failed' connector is not connected, the users in this state will be counted in ‘At node.’
      </td>
    </tr>

    <tr>
      <td>
        Goal Met
      </td>

      <td>
        These are the users who have performed the intended goal, such as viewing a movie or purchasing a product.
      </td>
    </tr>

    <tr>
      <td>
        Journey timeout exits
      </td>

      <td>
        These are the users who exited the Journey after the time duration set for the Journey, that is, Journey Timeout is complete.
      </td>
    </tr>
  </tbody>
</Table>

> 📘 Campaign Reports
>
> You can view the [Campaign Reports](doc:campaign-reports) from the Engage node. Click the **Engage** node to open the campaign report.

## Force Exit Node

This node stat shows only the number of force exits.

<Image title="Journeys_node_Force_exit.png" alt={310} src="https://files.readme.io/200599b-Journeys_node_Force_exit.png">
  Force exit node
</Image>

## Frequently asked questions

Q. Why do my users not qualify?\
A. If the entry node is an action node, but the events are coming from an API, then the users associated with these events do not qualify.

Q. What are last nodes?\
A. These are the nodes that do not have an output path. These nodes are present in Journeys without goals. 

Q. What happens to my users if my Journey does not have a goal?\
A. If you do not set a goal, the users from the last node exit the Journey. Their Journey is considered complete when they reach the last node. 

Q. Where can I see the users who are waiting because of delay or sleep defined between two nodes?\
A. You will see them on the following node under 'Waiting users'. 

Q. Why is the number of users on nodes not matching or adding up?\
A. The count of the users depends on the selected date range. If the original date range of the Journey does not match with the date range in your search, then the numbers will differ from the original. 

Q. How do I verify the number of users entering a specific node?\
A. The number of users moving forward from a node will always match the number of users who are entering the following nodes.

Q. Why my stats at last node are not matching?\
A. In the journeys created before Dec 27, 2019, You might see a mismatch of user counts or a drop in users. This is because earlier we used to have a dummy wait step post last node, where users will move and wait for goal to be met. In the new journeys (created post Dec 27, 2019), the dummy step no longer exists and this mismatch should not happen. 

Q. What is this intermediate stat on node stat?\
A. If you draw the same connector, such as 'Yes',  multiple times from a node and connect it to multiple Segment nodes, the users will move after the first action.  The stats for these Waiting users are displayed as an intermediate node on the connector.  

<Image title="Journeys_multiple_Yes_Build.png" alt={785} border={true} src="https://files.readme.io/e0d470f-Journeys_multiple_Yes_Build.png">
  Intermediate node - Build
</Image>

<Image title="Journeys_Multile_Yes_Node_stats.png" alt={1080} border={true} src="https://files.readme.io/960c1b8-Journeys_Multile_Yes_Node_stats.png">
  Intermediate node - Stats
</Image>

Q. How will I see the stats for the Phantom node?\
A.  A Phantom node appears only when a *Viewed* or *Clicked* connector is drawn from an Engage node. The originating node will display the Sent count and the Phantom node will display the Clicked or Viewed count. For more information on Phantom nodes, see [Users waiting at Engage nodes](https://docs.clevertap.com/docs/journeys#section-users-waiting-at-segment-node).

<Image title="Journeys_Pseudo_Node.png" alt={1162} src="https://files.readme.io/af5a2ea-Journeys_Pseudo_Node.png">
  Phantom node - Build
</Image>

<Image title="Journeys_Pseudo_Node_Stats.png" alt={839} src="https://files.readme.io/8fac40f-Journeys_Pseudo_Node_Stats.png">
  Phantom node - Stats
</Image>

# Journey Stats

Click the **Journey Stats** tab. The *Journey Stats* page appears.  Select the *date range* from the calendar to display the Journey stats.

The *Journey Stats* tab shows you the combined statistics for the entire Journey. All data except the user in Journey count that is displayed on the upper right corner of the *Journey Stats* tab, are based on the selected date range.

The main stats are displayed at the top section that relates to the main stages of the users Journey. 

<Image title="Journey_Goal_Hero_stats.png" alt={1345} border={true} src="https://files.readme.io/b68d6bb-Journey_Goal_Hero_stats.png">
  Journey stats - main
</Image>

The *Goal conversion* section displays the performance of the journey. You can see your influenced conversions here.  It also shows a comparison with the control group's performance. 

<Image title="Journeys_Stats_Goal.png" alt={1880} border={true} src="https://files.readme.io/8f1e196-Journeys_Stats_Goal.png">
  Journey stats - goal conversion
</Image>

The trend section provides powerful insights about the Journey, such as:

* The users who entered the Journey
* The users who exited the Journey
* The users who met the specified goal
* The users who were timed out of the Journey on a daily, weekly or monthly basis

<Image title="Journeys_Stats_Trends.png" alt={1348} border={true} src="https://files.readme.io/74da704-Journeys_Stats_Trends.png">
  Journey stats - trends
</Image>
