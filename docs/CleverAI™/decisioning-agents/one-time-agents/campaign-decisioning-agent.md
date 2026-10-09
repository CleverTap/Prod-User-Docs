---
title: Campaign Decisioning Agent
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Campaign Decisioning Agent is an AI-powered agent that ranks eligible campaigns for each user and decides which ones to send, so you do not have to rely on manual schedules or priorities to manage competing campaigns.

Campaign Decisioning Agent is user-based: for each user, it evaluates every campaign they qualify for and determines which is best for that user, not for users in general. Two users who qualify for the exact same set of campaigns can end up receiving different campaigns because each user's ranking is based on their own behavior and likelihood of responding.

When several teams or business lines run campaigns simultaneously, the same user often qualifies for more than one. Message limits cap how many messages a user receives, but the cap alone does not decide which messages get through. By default, the campaigns scheduled earliest consume the available limits, so a user may receive every message from one business line and none from the others.

The Campaign Decisioning Agent resolves that competition. Each day at midnight, it evaluates every campaign a user qualifies for against a goal you define, then delivers the most relevant campaign to that user within the limits you have already configured.

This evaluation is performed separately for each user. Campaign Decisioning Agent never ranks or compares campaigns across users; it only compares within what a single user qualifies for.

<Callout icon="📘" theme="info">
  #### Private Beta

  Currently, this feature is released in Private Beta and is available for accounts on Ultimate plan. To access this feature, contact your Account Manager.
</Callout>

The Campaign Decisioning Agent selects which campaigns from a set of competitors. It does not increase or decrease the number of messages a user receives. That is governed by your message limits. For more information, refer to [Messaging Frequency Caps](https://docs.clevertap.com/docs/messaging-frequency-caps).&#x20;

# Use Case

Consider a food delivery app that runs three business verticals: Food Delivery, Grocery, and Restaurant Discovery. Each vertical schedules its own push campaigns. The account has a limit of two push notifications per user per day.

Five push campaigns are scheduled for Wednesday morning, and all five are ranked by the Campaign Decisioning Agent:

| Campaign                 | Business line        | Scheduled |
| ------------------------ | -------------------- | --------- |
| Free Delivery Weekend    | Food Delivery        | 9:15 AM   |
| Weekly Grocery Restock   | Grocery              | 9:30 AM   |
| New Restaurants Near You | Restaurant Discovery | 10:00 AM  |
| Fresh Fruit Deals        | Grocery              | 10:30 AM  |
| Lunch Combo Offer        | Food Delivery        | 11:00 AM  |

The two users, John and Mark, both qualify for all five campaigns. Because the account's daily limit is two push notifications per user, each user can receive only two of the five, but which two depends entirely on their individual behavior.

- For John:&#x20;
  - Free Delivery Weekend and Lunch Combo Offer campaigns score highest for John, so those are the two delivered. The Grocery and Restaurant Discovery campaigns are held back for John today, not because they are lower priority in general, but because they score lower specifically for John.&#x20;
  - At 9:30 AM, John still had capacity left, but the Weekly Grocery Restock was not sent. The Agent held that capacity for the Lunch Combo Offer, which was scheduled later and scored higher. This is the intended behavior; without it, the campaigns scheduled earliest would consume the quota again, which is the problem Campaign Decisioning Agent exists to solve.&#x20;
- For Mark:&#x20;
  - Similarly, the Agent scores all five campaigns against Mark's behavior. Weekly Grocery Restock and New Restaurants Near You score the highest. Two Food Delivery campaigns are held back for Mark today, even though they're identical in content and priority to the ones sent to John.&#x20;

Same five campaigns, same schedule, same account-wide limit, but both users receive different campaign pairs because the Agent independently ranks campaigns for each user based on their behavior.

## How Campaign Decisioning Agent Works

Here is a quick look at how the Campaign Decisioning Agent works:

- Scoring: Once a day, the Agent scores every campaign a user qualifies for based on how relevant sending that campaign is to that user:
  - For campaigns that are created and scheduled before they are due to send, ranking occurs at midnight.
  - For same day or Send Now campaigns, ranking occurs at run time.
- Ordering: For each user, the relevant campaigns competing for their attention are ranked by score, with the highest ranked first.
- Selection: As campaigns come up for delivery throughout the day, the Agent checks whether sending a lower-scoring campaign now would use up capacity that a higher-scoring campaign will need later. If so, it holds back the lower-scoring campaign, so the higher-ranked campaign goes out instead.

This is how the Agent intelligently ensures each user receives the campaigns most relevant to them, without exceeding your existing frequency limits.

# System and Custom Agents

Campaign Decisioning Agent comes as System Agents, which come with your account, and Custom Agents, which you create.

- _System Agents_: If Campaign Decisioning Agent is included in your plan, System Agents are available out of the box in Draft state. They are pre-built in your account and collect some data by default. You can enable or disable a system agent, but you cannot edit it.&#x20;
  <Callout icon="📘" theme="info">
    #### Note

    Enabling or starting an agent does not put it to work immediately. The agent needs to learn before it starts ranking campaigns, which takes up to 24 hours. This duration depends on the dataset used for decisioning and other factors.
  </Callout>
  Neither requires you to choose a goal, because each is tied to a goal that cannot be changed:
  - Engagement Agent: Optimizes for Clicks. Uses the _Click Optimizer_ Reward Function.&#x20;
  - Conversion Agent: Optimizes campaign delivery for purchases. Uses the _Conversion_ Reward Function.

* _Custom Agents_: A custom agent is one you create when neither system agent matches your objective. You choose its goal, and you can narrow which campaigns it is allowed to rank. Use a custom agent when different parts of your business optimize for different outcomes. You can run several custom agents at the same time, each with its own goal. Running more agents does not increase the number of messages a user receives. All agents compete for the same daily capacity per user, so the total never exceeds that user's message limit.

# Agent Lifecycle

Every agent moves through the following five states. The state controls whether the agent ranks and dispatches campaigns. It never controls whether a campaign is delivered.&#x20;

| State        | Description                                                                          | What Happens                                                                                                                                                                                                                         |
| ------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Learning** | The agent is training on historical data from your engagements and users' responses. | Campaigns stay non-prioritized until training completes. The assigned campaigns are delivered using the existing schedule and message frequency caps.                                                                                |
| **Active**   | The model is ready and scoring.                                                      | The agent runs on schedule, scores the campaigns it ranks for each user, and sends the highest-scoring ones within your message limits                                                                                               |
| **Stopped**  | You stopped the agent. The trained model is retained.                                | Dispatch pauses immediately. Campaigns that use this agent are delivered using your existing scheduling logic. Restarting the agent moves it straight back to Active on the same model, with no time limit and no revalidation step. |
| **Failed**   | Training was not completed successfully.                                             | The agent training has failed.                                                                                                                                                                                                       |
| **Deleted**  | You removed the agent.                                                               | This action is permanent.                                                                                                                                                                                                            |

- You can only stop or delete an agent once no active campaign is being ranked by it. If one or more active engagements still use the agent, the dashboard blocks the action: _"One or more active engagements are being ranked by this agent. To stop this agent, stop the dependent active engagements."_ Stop those campaigns first, then stop or delete the agent.

- No agent state leaves a campaign unable to deliver, but the mechanism depends on the situation. If an agent's training fails, any campaigns tagged to it revert to standard delivery, since the agent never became Active. If an agent has no active campaigns, stopping or deleting it has no effect on campaigns.

- If a campaign is assigned to the agent at the same moment you try to stop or delete it, the action can fail, retry once the dependency clears.

# Use Campaign Decisioning Agent in a Campaign

To use Campaign Decisioning Agent in a campaign:

1. Create a campaign in the dashboard and choose a channel.
2. In _Setup_, open _Campaign Priority Management_.&#x20;
3. Under _Campaign priority_, choose one option:
   - **Manually manage priority**: _"Manually decide the priority for this campaign. This is best for must-go campaigns."_
   - **Agent manages priority**: _"Agent goes through all campaigns and decides the best priority of this campaign."_
4. Under _Agent Priority_, select an agent from the _Select an agent_ dropdown. The first agent is prefilled.
5. Click **Done**.

<Callout icon="📘" theme="info">
  #### Note

  If your account has no suitable agent, this step shows _"Agent not created for this project. Create a one-time agent to prioritize campaigns,"_ with an **Add One-time Agent** link. The link opens the Agents page in a new tab, so your campaign draft isn't lost. Use the refresh button on this step afterward to pick up the new agent.&#x20;
</Callout>

# FAQs

#### Can I use message limits without Campaign Decisioning Agent?

Yes. Message limits work independently.

#### Can I use Campaign Decisioning Agent without message limits?

No. An agent whose scope has no message limits cannot be selected during campaign creation.

#### If I run three agents, do my users receive three times as many messages?

No. All agents compete for the same daily capacity per user. The total never exceeds that user's message limit, however many agents you run.

#### Can I use more than one agent on a single campaign?

No. Only one Decisioning Agent can be assigned to a campaign at a time.

#### Why did a campaign I assigned to an agent not get ranked?

The most common reasons are that the campaign was scheduled on the same day it was due to send, or that its agent was not active. Ranking is generated once at the start of the day, so campaigns must exist in the system the day before they run.

#### What happens if I stop or delete the agent?

You can only stop or delete an agent once it has no active campaigns using it. If it does, the dashboard blocks the action and tells you to stop those campaigns first. Once the agent has no active dependents, stopping or deleting it goes through immediately — a campaign tagged to the agent afterward delivers using your existing scheduling logic.

#### Why was a campaign not sent when the user had capacity left at that moment?

Campaign Decisioning Agent reserves capacity for higher-scoring campaigns scheduled later the same day. In the example, Weekly Grocery Restock was not sent at 9:30 AM because capacity was being held for Lunch Combo Offer at 11:00 AM.

#### Does stopping an agent stop its campaigns?

You can't stop an agent while it still has active campaigns being ranked by it — the dashboard blocks the action until you stop those campaigns yourself. Once the agent has no active campaigns left, you can stop it; any campaign tagged to it after that point delivers on your existing schedule, not the agent's ranking.

#### Two users qualified for the same campaigns but received different messages. Why?

Scores are calculated for each user individually. John and Mark qualified for the same five campaigns and received different pairs, because each user's score reflects their own behavior.

#### Does Exploration % mean my agent will sometimes send an incorrect campaign?

For a small share of sends, the system intentionally sends a non-top-ranked campaign so the model keeps learning about options it would otherwise never surface. This applies account-wide, not per agent.

#### Why doesn't my agent appear in the dropdown during campaign creation?

This usually means Message Limits aren't configured for the agent's scope, or the agent's scope doesn't match the campaign's channel or team. Add Message Limits to the agent, or check its scope configuration.

#### Why isn't my tagged campaign being prioritized?

The agent is likely still _Learning_ or has _Stopped_. Wait for training to complete, or restart the agent.

#### How is a Custom Agent different from a System Agent?

A System Agent (Engagement or Conversion) is ready to use immediately, with a fixed goal that you cannot edit. A Custom Agent lets you choose or author your own Reward Function and narrow its scope to a specific channel or team.

<br />
