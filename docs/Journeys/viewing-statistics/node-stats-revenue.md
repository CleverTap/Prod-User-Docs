---
title: Node Stats
excerpt: >-
  Track user flow across journey nodes with version-specific stats to evaluate
  performance, drop-offs, and conversion impact
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The _Node Stats_ tab enables tracking of user progression through journey nodes and displays performance metrics, including entry counts, drop-offs, and goal completion.&#x20;

If your journey has multiple versions, use the version dropdown on the _Node Stats&#x20;_&#x74;ab to analyze each version independently. This helps compare user movement, drop-offs, and conversion outcomes across versions.


<Image src="https://files.readme.io/6bd4e622a763638d65f35c1f7e167061aa82fad8da3fc8d62ef74f5a5ffe5797-Node_Stats.png" alt="Node Stats" align="center" caption="Node Stats" border={true} />


#

## Entry Node

This is the starting point of the Journey. There can be only one Entry node per journey version. An Entry node can only be a Segment node.


<Image src="https://files.readme.io/53a486bcfdb0d168359b16576f77015010e37eff2d252b2d9c8a9ccbb45dedb6-image.png" alt="Entry Node" align="center" border={true} />


| Metric          | Description                                                                             |
| :-------------- | :-------------------------------------------------------------------------------------- |
| Qualified       | Total users who qualified for the journey based on entry conditions.                    |
| Entered Journey | Users who progressed through node connectors, such as Yes or No, after qualification    |
| Control Group   | Users excluded from the journey to serve as a baseline for measuring the journey impact |

## Segment Nodes

The node functions as a decision point evaluating behavioral or profile conditions.


<Image src="https://files.readme.io/5a1ed63-Journeys_node_Segment.png" alt="316" align="center" border={true} />


| Stat                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| :-------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Entered Node          | Total number of users who entered the node. It includes the total number of users from Moved forward, Waiting users, Goal Met, and Journey timeout.                                                                                                                                                                                                                                                                                                                                                                                           |
| Moved forward         | Users who have moved forward via node connectors, such as Yes, No, or Node Timeout.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Waiting users         | Users waiting at a node to qualify. The users may wait for either of two reasons: <ul><li>Delay from a previous node</li><li>Waiting to perform an action</li></ul>                                                                                                                                                                                                                                                                                                                                                                           |
| Goal Met              | These users have performed the intended goal, such as viewing a movie or purchasing a product.<ul><li><em>Before Node</em><br />Indicates that the user achieved the goal while waiting on the delay path, but did not get a message from the next node.</li><li><em>At Node</em><ul><li>Indicates that the user is on the node</li><li>If the Failed connector is not connected to a subsequent node, users whose message could not be delivered are held at this node (counted as **At Node**) and do not proceed in the journey.</li></ul> |
| Journey timeout exits | Users exiting due to the Journey after the Journey Timeout period is complete.                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

## Engage Nodes

The node represents message delivery points across channels (Push, SMS, Email, WhatsApp, and others).  Click the **Engagement** node from the _Nodes Stats_ tab to see the campaign statistics.


<Image src="https://files.readme.io/e443e68-Journeys_nodes_Engage.png" alt="315" align="center" border={true} />


| Metric                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| :-------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Entered Node          | The total number of users who entered the node. It includes the sum of all the users from Moved forward, Waiting users, Goal Met, and Journey timeout.                                                                                                                                                                                                                                                                                                                                                                                                             |
| Moved Forward         | Users who have moved forward via node connectors, such as Sent, Viewed, Clicked, Failed, and Unreachable.<br />Unreachable profiles do not have any identity, email, phone, or token (web/ push).                                                                                                                                                                                                                                                                                                                                                                  |
| Waiting users         | These users may wait for either of two reasons:<ul><li><em>Before Node</em><ul><li>Delay from a previous node.</li><li>Unreachable profiles if an Unreachable path is not drawn. </li></ul></li><li><em>At Node</em><br />The outcome for these users is not defined. For example, if the 'Failed' connector is not connected, the users in this state will be counted in the <em>At node.</em></li></ul>                                                                                                                                                          |
| Goal Met              | <p>These users have performed the intended goal, such as viewing a movie or purchasing a product.</p><ul><li><em>Before Node</em><br />Indicates that the user achieved the goal while waiting on the delay path but did not get a message from the next node.</li><li><em>At Node</em><ul><li>Indicates that the user is on the node</li><li>If the Failed connector is not connected to a subsequent node, users whose message could not be delivered are held at this node (counted as **At Node**) and do not proceed in the journey.</em></li></ul></li></ul> |
| Journey timeout exits | Users exiting due to timeout or version changes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

<Callout icon="📘" theme="info">
  ### Campaign Stats

  You can view the campaign-level stats for every node. Click the **Engage** node to open the campaign-level stats.
</Callout>

<Callout icon="📘" theme="info">
  ### Unique Users Converted

  If a user enters the journey and performs the conversion event twice, only one conversion event for that unique user is counted.
</Callout>

## Force Exit Node

The node manually removes users from the journey at a specific point. No revenue metric is shown on Force Exit nodes.


<Image src="https://files.readme.io/200599b-Journeys_node_Force_exit.png" alt="310" align="center" border={true} />


<br />

# View Goal Conversion Performance

Click an Engagement node, then select the _Goals_ tab in the node panel to view goal conversion performance for that node.


<Image src="https://files.readme.io/885246c33bee7f4ed7ee8342a1b3ef9cf1a24f2ce6385235258fc65dff93575c-Goals_Tab_under_Node_Stats.png" align="center" caption="View Goal Conversion Performance" border={true} />


<br />

The tab shows a Total Goal Met count, followed by a table with one row per goal:

| Column    | Description                                                                                                                                                                                                                              |
| --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Goal name | Name of the goal as configured in the journey                                                                                                                                                                                            |
| Goal type | The goal type, such as Action, Inaction, or Past Behavior Segment                                                                                                                                                                        |
| Goal Met  | Users who met this goal via this node                                                                                                                                                                                                    |
| Revenue   | Total Target Group revenue from users who met this goal. Shown only when a revenue attribute is configured for the goal, and appears automatically once revenue stats is enabled for the account. Blank for Past Behavior Segment goals. |

Use the date range picker at the top of the tab to filter goal performance for a specific period.
