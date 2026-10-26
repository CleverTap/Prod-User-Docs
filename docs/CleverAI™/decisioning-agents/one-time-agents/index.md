---
title: One-Time Decisioning Agents
excerpt: Learn how to create and manage One-Time Decisioning Agents.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

One-Time Decisioning Agent is an AI-powered agent that decides which campaign to send when several campaigns compete for the same user. You configure the agent once by specifying a goal, a Reward Function, an engagement scope, and guardrails. The agent then scores every competing campaign against that goal and selects the one most relevant to each user, within your existing frequency limits.

Unlike a Lifecycle Agent, which runs a continuous, multi-stage journey toward a single lifecycle goal, a One-Time Decisioning Agent makes a single selection decision among your existing campaigns, once per day, per user. It doesn't create its own messaging path; it decides which of your already-scheduled campaigns gets through.

## Prerequisites

Confirm the following before you create a One-Time Decisioning Agent:

- You have One-Time Agent access enabled on your CleverTap account.
- You have a Reward Function ready, or you'll define one during the Goal step.
- You have the necessary permissions to create campaigns and agents on your CleverTap account.

<Callout icon="📘" theme="info">
  ### Note

  Currently, this feature is a Private Beta Release for Ultimate customers. To access this feature, contact your Account Manager.
</Callout>

## Create One-Time Decisioning Agent

To create a One-Time Decisioning Agent, from the _CleverTap dashboard_, go to _Decisioning_ > _Agents_, select the _One-Time_ tab, and then click **Create One-Time Agent**. The _Create One-Time Agent_ section appears.

Creating a One-Time Agent involves the following steps:

- [Set Goal:](#set-goal) Define the agent's name and description, the Stats Conversion Window, and the Reward Function.
- [Set Engagement & Decisioning Scope](#set-engagement--decisioning-scope): Define the agent, channels, and team (if enabled for your account).&#x20;
- [Set Guardrails:](#set-guardrails) Configure applicable frequency limits, Explore Percentage, Holdout User Bucket, and Do Not Disturb behavior.


<Image src="https://files.readme.io/2db07aec1fe6cc5ebf40e955c45da46c998d67d4f12cc862005caf9491c82b72-image.png" align="center" caption="One-Time Agent" border={true} />


### Set Goal

The _Goal_ tab defines success for this agent. You set the agent's name and description, the Stats Conversion Window, and the Reward Function used to rank campaigns. The agent uses this to measure performance and track whether users completed the intended action after the send.


<Image src="https://files.readme.io/65798d7a5e0c8dc011e09ac5d2b162e245128206c715456f106c8bc2a0b895ed-image.png" align="center" caption="Set Goal" border={true} />


To set up goals, perform the following steps:

1. Enter a descriptive name in the _Agent Name_ field.

2. Enter a short summary for the agent in the _Agent Description_ field.

3. Set the _Stats Conversion Window_, in days. This is the time period after a send during which a conversion counts toward the agent's stats.

4. Under _Reward Function_, select the Reward Function that this agent ranks campaigns against. Each Reward Function defines:&#x20;

   - _Positive Signal(s):_ the event(s) that determine completion of a conversion, for example, `Product Sold` or `Payment Info Submitted`.
   - _Negative Signal(s):_ the event(s) that may adversely affect conversion, for example, `Push Unregistered` or `Channel Unsubscribed`.


   <Image src="https://files.readme.io/46739630ffe2f50854ba053d30d72f98af66fed09cc96dde6ca4768fdb67af4c-image.png" align="center" caption="Reward Function" border={true} />


5. Click **Next** to proceed to the _Engagement Scope_ tab.

<Callout icon="📘" theme="info">
  #### Note

  Under Goals, Reward Function (and its Positive/Negative Signals) can be only picked from the existing list. Reward Functions are created separately under _Decisioning > Reward Functions_. For more information, refer to [Reward Functions](doc:reward-functions).
</Callout>

### Set Engagement & Decisioning Scope

The _Engagement & Decisioning Scope_ tab defines which campaigns the agent acts on. The agent only acts on campaigns that match the channels and team set here. These must also be set during campaign creation; the agent automatically picks up matching campaigns.&#x20;


<Image src="https://files.readme.io/8bf0f3726611b5d46f7190e7e510823e388cc616fd84a16d6e5be3fa206838c6-image.png" align="center" caption="Engagement Scope" border={true} />


The _Engagement & Decisioning Scope_ tab specifies which campaigns can be included in this agent's ranking pool. Only engagements using the channels and teams selected here are eligible.

To define Engagement & Decisioning Scope, perform the following steps:&#x20;

1. Select what this agent decides under Agent Type:
   - **Campaign Decisioning**: The agent ranks and selects among competing campaigns.
   - **Variant Decisioning**: The agent ranks and selects among variants of a single campaign.
   - **Both**: The agent handles both campaign and variant decisioning. Under Eligible channels, select the channels this agent can act on. Select the matching channel when creating a campaign for the agent to cover.
2. Click **Next** to proceed to the _Guardrails_ tab.

### Set Guardrails

The _Guardrails_ tab configures the hard limits the agent must always respect, regardless of what its model recommends. Guardrails protect your users from over-communication and ensure every send respects your configured frequency limits.


<Image src="https://files.readme.io/1f0e024587de397cde2bc15243b7208e42e2e783e3b614e397bcd58a9841232e-image.png" align="center" caption="_Guardrails_" border={true} />


To set _Guardrails_, perform the following steps:

1. Review _Global message limits_: This is read-only and shows the global frequency limits currently active for your project.&#x20;
2. Set _Exploration size_: The percentage of decisions the agent makes that are exploratory, compared to those based on proven strategies. Click **Edit exploration size** to change this account-wide setting. For more information, refer to [Holdout and Exploration.](https://docs.clevertap.com/docs/holdout-and-exploration)&#x20;
3. Set _Holdout user bucket_: The user bucket excluded from this agent's decisions, defined as a condition (for example, _User Bucket not equals 2_). Click **Edit holdout user bucket** to change it. For more information on user buckets, refer [User Bucket.](https://docs.clevertap.com/docs/user-bucket)
4. Review _Do not Disturb_: DND settings are inherited from each campaign within the agent's scope, and sends are suppressed during the DND hours configured on each campaign. There is no override at the agent level.
5. Click **Publish** to activate the agent.

Enabling or starting an agent does not put it to work immediately. The agent needs to learn before it starts ranking campaigns, which takes up to 24 hours. This duration depends on the dataset used for decision-making and other factors.

## Manage One-Time Agents

On the Agents page, click the ⋮ icon on an agent's card to:

- Stop: Pause the agent. Send pauses immediately, and its tagged campaigns revert to standard delivery.
- Delete: Permanently remove the agent and its model. Tagged campaigns revert to standard delivery.


<Image src="https://files.readme.io/0505aba306d9367efd5b83c55c09c42af4c8e600a486ff23fb602f0d8b2d6fa4-image.png" align="center" caption="Manage Agents" border={true} />


On the _Agents_ page, use **Filters** to narrow the list of agents:

- **Time Period**: Filter by when the agent was created. Defaults to _All time_.
- **Created By**: Filter by the user who created the agent.
- **Status**: Filter by _Available_, _Learning_, _Active_, or _Stopped_.

Click **Apply** to update the list, or **Reset** next to a filter to clear it individually.


<Image src="https://files.readme.io/0af51327f62df108add944ccd92f3141bae1da0838524d13d448c59a490b4e37-image.png" align="center" caption="Filter the Agents" border={true} />


<br />

<br />