---
title: Viewing Journey Stats - Compare
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
We have made some improvements to the current Journeys. 

  * Enhanced node stats: The node stats are now more detailed. So you can now account for all your users and view their progress in the Journey. The Live tab is not available anymore. The 'Users right now' count on the Live tab is now displayed as 'Waiting users' count on the node stats. 
  * Journey Stats: This is a new tab to show you the combined stats of your Journey. 


# Concepts
You will need to know some key terms to understand the Journey stats.
 * **Entry:** All users who have entered the Journey (first node).
 * **Goal Met:** If a goal is set in the Journey builder, these are all users who met the goal. 
 * ** Journey Timeout:** If a Journey timeout is set in the Journey builder (entry criteria), these are all the users who timed out.
 * ** Node Timeout:**  This is the time duration set for the node, after which the users will move on to the next node via Node timeout connector.
 * **Completed:** If a goal is not set in the Journey builder, these are all the users who successfully reached the last node of the Journey.

# Overview
Click Engage > Journeys from the left side menu. The Journey List page appears. Search for a Journey and then click to open a Journey.  The Journey Canvas has three tabs:
1. Build - Shows your Journey components and connections
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/054d5be-Journeys_tab_build.png",
        "Journeys_tab_build.png",
        1376,
        664,
        "#f4f6f8"
      ],
      "border": true,
      "caption": "Enhanced Build Journey"
    }
  ]
}
[/block]
2. Node Stats - Shows stats for each node
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c175c06-Journeys_Tab_Node_Stats.png",
        "Journeys_Tab_Node_Stats.png",
        1378,
        666,
        "#f7f8fa"
      ],
      "border": true,
      "caption": "Enhanced Node stats"
    }
  ]
}
[/block]
3. Journey Stats - Shows stats for the Journey
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/60f7b80-Journeys_Tab_Journey_Stats1.png",
        "Journeys_Tab_Journey_Stats1.png",
        1379,
        728,
        "#f7f8f9"
      ],
      "border": true,
      "caption": "New Journey Stats"
    }
  ]
}
[/block]
#Node Stats
The Node Stats tab shows you the stats for each node. You can account for all users that entered the Journey and their current state.

Click the Node Stats tab. Select the date range from the calendar.  Let's see how to check the statistics for each of the node types:

##Entry Node
This is the first node in the Journey. There can be only one Entry node.  An Entry node can only be a Segment node. 









[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c4d4ac9-Journeys_Entry_Node_Old_New.png",
        "Journeys_Entry_Node_Old_New.png",
        774,
        454,
        "#e8e9e9"
      ]
    }
  ]
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Status",
    "h-1": "Description",
    "0-0": "Qualified",
    "0-1": "The total number of users that entered the Journey. This stat is available only on the Entry Node.",
    "1-0": "Moved Forward",
    "1-1": "The users who have moved forward via node connectors, such as Yes, No, Node Timeout.",
    "2-0": "Control Group",
    "2-1": "The number of users who were marked for the control group. \n\nA control group is a set of users that do not receive any marketing campaigns. You can measure the effectiveness of your initiatives by comparing this group with the target group of users who received your campaigns."
  },
  "cols": 2,
  "rows": 3
}
[/block]
##Segment Nodes




[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b1d80f5-Journeys_Segment_Node_Old_New_copy.png",
        "Journeys_Segment_Node_Old_New copy.png",
        711,
        393,
        "#e8e5e3"
      ]
    }
  ]
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Status",
    "h-1": "Description",
    "0-0": "Entered Node",
    "0-1": "The total number of users who entered the node. It includes the sum of all the users from Moved forward, Waiting users, Goal Met, and Journey timeout.",
    "1-0": "Moved forward",
    "2-0": "Waiting users",
    "3-0": "Goal Met",
    "4-0": "Journey timeout exits",
    "2-1": "The users waiting at a node to qualify. The users may wait for either of the 2 reasons: \n1. Delay from a previous node\n2. Waiting to perform an action",
    "1-1": "The users who have moved forward via node connectors, such as Yes, No, or Node Timeout.",
    "4-1": "These are the users who exited the Journey after the time duration set for the Journey, that is, Journey Timeout is complete.",
    "3-1": "These are the users who have performed the intended goal, such as viewing a movie or purchasing a product."
  },
  "cols": 2,
  "rows": 5
}
[/block]
##Engage Nodes
Simply put, Engage nodes are campaigns. You can see the stat of each campaign from the Node Stats tab. Click the Engage node from the Nodes Stats tab to see the campaign statistics. 





[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07642f3-Journeys_Engage_Node_Old_New.png",
        "Journeys_Engage_Node_Old_New.png",
        864,
        517,
        "#e8e9e9"
      ]
    }
  ]
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "Status",
    "h-1": "Description",
    "2-0": "Waiting users",
    "2-1": "These users may wait for either of the 2 reasons: \n1.  Before Node: Delay from a previous node\n2. At Node: The outcome for these users is not defined. For example, if the 'Failed' connector is not connected, the users in this state will be counted in ‘At node.’",
    "1-0": "Moved Forward",
    "1-1": "The users who have moved forward via node connectors, such as Sent, Viewed, Clicked, Failed, and Unreachable.",
    "3-0": "Goal Met",
    "3-1": "These are the users who have performed the intended goal, such as viewing a movie or purchasing a product.",
    "4-0": "Journey timeout exits",
    "4-1": "These are the users who exited the Journey after the time duration set for the Journey, that is, Journey Timeout is complete.",
    "0-0": "Entered Node",
    "0-1": "The total number of users who entered the node. It includes the sum of all the users from Moved forward, Waiting users, Goal Met, and Journey timeout."
  },
  "cols": 2,
  "rows": 5
}
[/block]
## Frequently asked questions

Q. What are last nodes?
A. These are the nodes that do not have an output path. These nodes are present in Journeys without goals. 

Q. What happens to my users if my Journey does not have a goal? 
A. If you do not set a goal, the users from the last node exit the Journey. Their Journey is considered complete when they reach the last node. 

Q. Where can I see the Users that are waiting because of delay or sleep defined between two nodes? 
A. You will see them on the following node under 'Waiting users'. 

Q. Why is the number of users on nodes not matching or adding up? 
A. The count of the users depends on the selected date range. If the original date range of the Journey does not match with the date range in your search, then the numbers will differ from the original. 

Q. What is this intermediate stat on node stat?
A. If you draw the same connector, such as 'Yes',  multiple times from a node and connect it to multiple Segment nodes, the user's will move after the first action.  The stats for these Waiting users are displayed as an intermediate node on the connector.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e0d470f-Journeys_multiple_Yes_Build.png",
        "Journeys_multiple_Yes_Build.png",
        785,
        430,
        "#f5f1f0"
      ],
      "border": true,
      "caption": "Intermediate node - Build"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/960c1b8-Journeys_Multile_Yes_Node_stats.png",
        "Journeys_Multile_Yes_Node_stats.png",
        1080,
        553,
        "#faf9fa"
      ],
      "border": true,
      "caption": "Intermediate node - Stats"
    }
  ]
}
[/block]

Q. How will I see the stats for the Phantom node?
A.  A Phantom node appears when a Viewed or Clicked connector is drawn from a node. The stats displayed for this node are the same as a segment node. The originating node will display the Sent count and the Phantom node will display the Clicked or Viewed count. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/af5a2ea-Journeys_Pseudo_Node.png",
        "Journeys_Pseudo_Node.png",
        1162,
        243,
        "#f2f4f1"
      ],
      "caption": "Phantom node - Build"
    }
  ]
}
[/block]

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8fac40f-Journeys_Pseudo_Node_Stats.png",
        "Journeys_Pseudo_Node_Stats.png",
        839,
        223,
        "#f5f5f6"
      ],
      "caption": "Phantom node - Stats"
    }
  ]
}
[/block]
#Journey Stats

Click the Journey Stats tab. The Journey Stats page appears.  Select the date range from the calendar to display the Journey Stats.


The Journey Stats tab shows you the combined statistics for the entire Journey. All data except the user in Journey count that is displayed on the upper right corner of Journey stats tab, are based on the selected date range.

The main stats are displayed at the top section that relates to the main stages of the users Journey. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b68d6bb-Journey_Goal_Hero_stats.png",
        "Journey_Goal_Hero_stats.png",
        1345,
        120,
        "#f4f4f5"
      ],
      "border": true
    }
  ]
}
[/block]
The Goal conversion section displays the performance of the journey. You can see your influenced conversions here.  It also shows a comparison with the control group performance. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8f1e196-Journeys_Stats_Goal.png",
        "Journeys_Stats_Goal.png",
        1880,
        746,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
The trend section provides powerful insights about the Journey, such as:
  * The users that entered the Journey
  * The users that exited the Journey
  * The users that met the specified goal
  * The users that were timed out of the Journey on a daily, weekly or monthly basis
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/74da704-Journeys_Stats_Trends.png",
        "Journeys_Stats_Trends.png",
        1348,
        544,
        "#fafbfc"
      ],
      "border": true
    }
  ]
}
[/block]