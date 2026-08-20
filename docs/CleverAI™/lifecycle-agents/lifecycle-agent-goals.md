---
title: Goals
excerpt: Learn how to set the goals in Lifecycle Agent.
deprecated: false
hidden: true
metadata:
  robots: index
---
### Set Goals

The _Goals_ tab defines the success for this agent. You set the conversion goal, the time period beyond which a user exits the agent, and the behavioral signals for reinforcement learning.&#x20;

To complete the _Goals_ tab:

1. From the _CleverTap dashboard_, navigate to _Decisioning_, and then click **Create New Agent**. The _Create New Agent&#x20;_&#x73;ection appears.


   <Image src="https://files.readme.io/75c643e8f6edc0d7123a4f57ea5d6e0acbc843b7273265e41c3e9812e2b4eb73-image.png" alt="Define Goal" align="center" caption="Define Goal" border={true} />


2. Enter a descriptive name in the _Agent Name_ field.

3. Enter a short summary for the agent in the _Agent Description_ field.

4. Under _Goal_, select the conversion event the agent must drive users toward (for example, `Charged`). This is the primary outcome the agent optimizes for. To narrow the goal definition, click **+ Filter** next to the event. For example, you can restrict the goal to purchases of a certain product category. For example, an e-commerce store creates an agent that optimizes conversion for a particular product category, such as electronics.&#x20;

5. (Optional) Select the **User Re-entry** option to allow users who have already completed the goal, or whose timeout window has expired, to re-enter the agent as a new episode. Enable this when users can achieve the goal more than once. For example, if your goal is Repeat Purchase, a user who completes a purchase must re-enter the agent so the agent can nudge them toward a second purchase. If your goal is First Purchase, re-entry is typically not required.

6. Set the _Timeout_ (in days). This is the maximum duration the agent keeps trying to convert each user. When a user's timeout window expires without a goal completion, the user exits the agent.

7. Under _Guiding Events_, configure the user behavioral signals the agent uses for reinforcement learning. The agent's decisions are rewarded or penalized based on the favorable or unfavorable events, respectively.<br />a. Click **Add Event** under _Favorable Events_ to add events that show a positive user intent (for example, `Product Viewed`, `Add to Cart`). Each favorable event sends a positive signal to the agent.<br />b. Click **Add Unfavorable Event** under _Unfavorable Events_ to add events that show negative user intent (for example, `Channel Unsubscribed`, `App Uninstalled`).&#x20;

<Callout icon="📘" theme="info">
  ### Note

  At least one favorable event is required.
</Callout>

8. Under _Guiding Events Priority_, review and set the priority order for your guiding events. The agent treats higher-priority favorable events as stronger positive signals and vice versa. Drag and drop events in the table to reorder them.
9. Click **Next** to proceed to the _Target Segment_ tab.