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

Campaign Decisioning Agent is an AI-powered agent that ranks eligible campaigns for each user and decides which ones to send, so you don't have to rely on manual schedules or priorities to manage competing campaigns.

Campaign Decisioning Agent is user-based: for each user, it evaluates every campaign they qualify for and determines which is best for that user, not for users in general. Two users who qualify for the exact same set of campaigns can end up receiving different campaigns because each user's ranking is based on their own behavior and likelihood of responding.

When several teams or business lines run campaigns simultaneously, the same user often qualifies for more than one. Message limits cap how many messages a user receives, but the cap alone does not decide which messages get through. By default, the campaigns scheduled earliest consume the available limits, so a user may receive every message from one business line and none from the others.

Campaign Decisioning Agent resolves that competition. Each day, it evaluates every campaign a user qualifies for against a goal you define, then delivers the most relevant campaign to that user within the limits you have already configured.

This evaluation is performed separately for each user. Campaign Decisioning Agent never ranks or compares campaigns across users; it only compares within what a single user qualifies for.

<Callout icon="📘" theme="info">
  #### Private Beta

  Currently, this feature is a Private Beta Release for Ultimate customers. To access this feature, contact your Account Manager.
</Callout>

Campaign Decisioning Agent decides which campaigns are selected from a competing set. It does not raise or lower the number of messages a user receives. That is governed by your message limits. For more information, refer to Messaging Frequency Caps.

# Use Case

Consider a food delivery app that runs three business lines: Food Delivery, Grocery, and Restaurant Discovery. Each line schedules its own push campaigns. The account has a limit of two push notifications per user per day.

Five campaigns are scheduled for Wednesday morning, and all five are assigned to a Campaign Decisioning Agent:

| Campaign                 | Business line        | Label              | Scheduled |
| ------------------------ | -------------------- | ------------------ | --------- |
| Free Delivery Weekend    | Food Delivery        | `food-offer`       | 9:15 AM   |
| Weekly Grocery Restock   | Grocery              | `grocery-reminder` | 9:30 AM   |
| New Restaurants Near You | Restaurant Discovery | `discovery`        | 10:00 AM  |
| Fresh Fruit Deals        | Grocery              | `grocery-offer`    | 10:30 AM  |
| Lunch Combo Offer        | Food Delivery        | `food-offer`       | 11:00 AM  |

We have two users, John and Mark. Both qualify for all five campaigns. Because the account's daily limit is two push notifications per user, each of them can receive only two of the five, but which two depends entirely on their own individual behavior.

- For John:
- Free Delivery Weekend and Lunch Combo Offer campaigns score highest for John, so those are the two delivered. The Grocery and Restaurant Discovery campaigns are held back for John today, not because they're lower priority in general, but because they score lower specifically for John.
- At 9:30 AM, John still had capacity left, but Weekly Grocery Restock wasn't sent. The Agent held that capacity for Lunch Combo Offer, which was scheduled later and scored higher. This is the intended behavior, without it, the campaigns scheduled earliest would consume the quota again, which is the problem Campaign Decisioning Agent exists to solve.
- For Mark:
- Similarly, the Agent scores all five campaigns against Mark's behavior. Weekly Grocery Restock and New Restaurants Near You score the highest. Two Food Delivery campaigns are held back for Mark today, even though they're identical in content and priority, to the ones sent to John.

Same five campaigns, same schedule, same account-wide limit, but both users receive a different pair, because the Agent ranks campaigns independently for every user based on that user's own behavior.

## How Campaign Decisioning Agent Works

Here's a quick look at how the Campaign Decisioning Agent works:

- Scoring: Once a day, the Agent scores every campaign a user qualifies for, based on how much sending that specific campaign is relevant to that specific user.
- Ordering: For each user, the relevant campaigns competing for their attention are ranked by score, highest first.
- Selection: As campaigns come up for delivery through the day, the Agent checks whether sending a lower-scoring campaign now would use up capacity a higher-scoring campaign will need later. If so, it holds the lower-scoring campaign back so the higher ranked campaign goes out instead.

This is how the Agent intelligently makes sure each user gets the campaigns most relevant to them, without exceeding your existing frequency limits.

# System and Custom Agents

Campaign Decisioning Agent comes as System Agents, which come with your account, and Custom Agents, which you create.

- _System Agents_: If Campaign Decisioning Agent is included in your plan, System Agents are available out of the box in Draft state. They are pre-built in your account and collect some data by default. You can enable or disable a system agent, but you cannot edit it.
  <Callout icon="📘" theme="info">
    ### Note

    Enabling or starting an agent does not put it to work immediately. The agent needs to learn before it starts ranking campaigns, which takes approximately 24 hours. This duration depends on the dataset used for decisioning and other factors.
  </Callout>

Neither requires you to choose a goal, because each is tied to a goal that cannot be changed:

- Engagement Agent: Optimises for Clicks. Uses the Engagement Reward Function.
- Conversion Agent: Optimises for Conversion Event. Uses the Conversion Reward Function.

* _Custom Agents_: A custom agent is one you create when neither system agent matches your objective. You choose its goal, and you can narrow which campaigns it is allowed to rank. Use a custom agent when different parts of your business optimize for different outcomes. You can run several custom agents at the same time, each with its own goal. Running more agents does not increase how many messages a user receives. All agents compete for the same daily capacity per user, so the total never exceeds that user's message limit.

# Agent Lifecycle

Every agent moves through the following five states. The state controls whether the agent ranks and dispatches campaigns. It never controls whether a campaign is delivered.

| State        | Model Status                                                 | What Happens                                                                                                                                                                                                                  |
| ------------ | ------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Learning** | The model is training on the account's tagged campaign data. | Campaigns stay non-prioritized until training completes. The assigned campaigns are delivered using your existing scheduling logic.                                                                                           |
| **Active**   | The model is ready and scoring.                              | The agent runs on schedule, evaluates its tagged campaigns, and scores and dispatches them by priority in the arena.                                                                                                          |
| **Stopped**  | You paused the agent. The trained model is retained.         | Dispatch pauses immediately. The assigned campaigns are delivered using your existing scheduling logic. Restarting the agent moves it straight back to Active on the same model, with no time limit and no revalidation step. |
| **Failed**   | Training didn't complete successfully.                       | The agent training has failed.                                                                                                                                                                                                |
| **Deleted**  | You removed the agent.                                       | This action is permanent.                                                                                                                                                                                                     |

- No agent state stops a campaign from being delivered. If an agent is stopped, deleted, or fails to train, its campaigns behave as though they were never assigned to an agent and deliver on your existing schedule. Stopping an agent is not a way to stop a campaign.
- Delete is permanent and available from Active or Stopped. It removes the agent and its model, and any tagged campaigns revert to standard delivery.

# Create Custom Agent

# Use Agent in Campaigns

# FAQs

#### Can I use message limits without Campaign Decisioning Agent?

Yes. Message limits work independently.

#### Can I use Campaign Decisioning Agent without message limits?

No. An agent whose scope has no message limits cannot be selected during campaign creation.

#### If I run three agents, do my users receive three times as many messages?

No. All agents compete for the same daily capacity per user. The total never exceeds that user's message limit, however many agents you run.

**Can I use more than one agent on a single campaign?**
No. Only one Decisioning Agent can be assigned to a campaign at a time.

#### Why did a campaign I assigned to an agent not get ranked?

The most common reasons are that the campaign was scheduled on the same day it was due to send, or that its agent was not active. Ranking is generated once at the start of the day, so campaigns must exist in the system the day before they run.

**What happens if I stop or delete the agent?**<br />If the agent is Stopped, the campaign behaves as untagged but it is never blocked. If the agent is deleted, the campaign reverts to standard delivery.

#### Why was a campaign not sent when the user had capacity left at that moment?

Campaign Decisioning Agent reserves capacity for higher-scoring campaigns scheduled later the same day. In the example, Weekly Grocery Restock was not sent at 9:30 AM because capacity was being held for Lunch Combo Offer at 11:00 AM.

#### Does stopping an agent stop its campaigns?

No. The campaigns still deliver based on their schedules, rather than the agent's ranking. To stop a campaign, stop the campaign.

#### Two users qualified for the same campaigns but received different messages. Why?

Scores are calculated for each user individually. A and B qualified for the same five campaigns and received different pairs, because each user's score reflects their own behavior.

**Does Exploration % mean my agent will sometimes send an incorrect campaign?**<br />For a small share of sends, the system intentionally sends a non-top-ranked campaign so the model keeps learning about options it would otherwise never surface. This applies account-wide, not per agent.

**Why doesn't my agent appear in the dropdown during campaign creation?**
This usually means Message Limits aren't configured for the agent's scope, or the agent's scope doesn't match the campaign's channel or team. Add Message Limits to the agent, or check its scope configuration.

**Why isn't my tagged campaign being prioritized?**<br />The agent is likely still in Training, or is Stopped. Wait for training to complete, or restart the agent.

**How is a Custom Agent different from a System Agent?**<br />A System Agent (Engagement or Conversion) is ready to use immediately, with a fixed goal you can't edit. A Custom Agent lets you choose or author your own Reward Function and narrow its scope to a specific channel or team.

#
