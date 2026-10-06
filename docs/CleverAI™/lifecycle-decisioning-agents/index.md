---
title: Lifecycle Decisioning Agents
excerpt: Learn how to create and manage Lifecycle Decisioning Agents
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Lifecycle Decisioning Agent is an always-on, AI-powered marketing agent that manages a single lifecycle goal, such as First Purchase, Repeat Purchase, or Winback for your user segment. You only have to configure the agent once by specifying a goal, a user segment, messaging templates, and guardrails. The agent then continuously decides what to send, on which channel, and when, for each individual user, until that user converts or exits.

A traditional user Journey is a static messaging path for all users in that journey.  However, a Lifecycle Decisioning Agent creates a unique messaging path for each user. It operates in a continuous cycle: it reads each user's real-time behavior, decides the next-best action, sends it automatically, and uses reinforcement learning models to improve future decisions autonomously.

## Prerequisites

Confirm the following before you create a Lifecycle Decisioning Agent:

- You have Lifecycle Decisioning Agent access enabled on your CleverTap account.
- You have a few message templates ready for the agent to use across different channels. Lifecycle Decisioning Agent supports the following channels: Push Notifications, Email, SMS, WhatsApp, Web Push, and Inbox.
- Your role must have the following _write_ permissions:&#x20;
  - Campaign Creation&#x20;
  - Lifecycle Decisioning Agent Creation

<Callout icon="📘" theme="info">
  ### **Note**

  Lifecycle Decisioning Agent is currently in Beta. Contact your CleverTap account manager to request access.
</Callout>

## Create a Lifecycle Decisioning Agent

Creating a Lifecycle Decisioning Agent involves defining your goal, identifying your user segment, choosing an engagement strategy, adding messages across different channels, and configuring guardrails.&#x20;

To create a Lifecycle Decisioning Agent, go to _Decisioning_ > _Agents_ > _Create Agent._

The following image shows the _Create New Agent_ workflow with the five-step navigation bar:


<Image src="https://files.readme.io/9bdc70422b03a572e4a7181692bf8e7a4499cc3f1054148d3d9d1f95b03b766f-image.png" alt="Create new lifecycle decisioning agent" align="center" caption="Create new LIfecycle Decisioning Agent" border={true} />


You can create a new agent with a five-step workflow:&#x20;

| Window Section                                                     | What You Configure                                                          |
| ------------------------------------------------------------------ | --------------------------------------------------------------------------- |
| [**Goals**](doc:lifecycle-agent-goals)                             | The conversion goal, guiding events, and the conversion window              |
| [**Target Segment**](doc:lifecycle-agent-target-segment)           | Which users enter the agent and the control group                           |
| [**Engagement Strategy**](doc:lifecycle-agent-engagement-strategy) | The engagement strategy and step rules                                      |
| [**Messages**](doc:lifecyle-agent-messages)                        | The messages across different channels available to the agent for selection |
| [**Guardrails**](doc:lifecycle-agent-guardrails)                   | Channel limits, Frequency caps, and Do Not Disturb (DND) windows            |

##

To view the agent performance and activity, refer to the following:

- [Agent Statuses](https://docs.clevertap.com/docs/lifecycle-agent-statuses)
- [Agent Stats](https://docs.clevertap.com/docs/lifecycle-agent-stats)
- [Agent Activity](https://docs.clevertap.com/docs/lifecycle-agent-activity)

##
