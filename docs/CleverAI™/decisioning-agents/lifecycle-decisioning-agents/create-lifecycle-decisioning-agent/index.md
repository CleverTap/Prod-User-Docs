---
title: Create Lifecycle Decisioning Agent
excerpt: Learn how to create a Lifecycle Decisioning Agent
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Create an agent by defining its goal, target segment, engagement strategy, messages, and guardrails. You can save your work as a draft at any step and publish when you're ready.

# Prerequisites

Before you begin, check the following

- Lifecycle Decisioning Agent is enabled for your project. An admin enables it in Settings > CleverAI > Agents.
- Your account has capacity for another active agent. Your plan sets a maximum number of active agents. At the limit, stop or pause an active agent, or ask an admin to increase capacity.
- Your role lets you create agents.
- Message templates and, for Email, SMS, and WhatsApp, a configured service provider. If no provider exists, the editor prompts you to add one.&#x20;

# Create Agent

To create a Lifecycle Decisioning Agent, go to _Decisioning_ > _Agents_ > _Lifecycle&#x20;_&#x61;nd clic&#x6B;_&#x20;_**Create Agent**_._

The following image shows the _Create New Agent_ workflow with the five-step navigation bar:


<Image src="https://files.readme.io/9bdc70422b03a572e4a7181692bf8e7a4499cc3f1054148d3d9d1f95b03b766f-image.png" alt="Create new lifecycle decisioning agent" align="center" caption="Create new Lifecycle Decisioning Agent" border={true} />


You can create a new agent with a five-step workflow:&#x20;

| Window Section                                                      | What You Configure                                                          |
| ------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| [**Set Goals**](doc:set-goals-in-lifecycle-agent)                   | The conversion goal, guiding events, and the conversion window              |
| [**Define Target Segment**](doc:define-the-target-segment)          | Which users enter the agent and the control group                           |
| [**Select Engagement Strategy**](doc:configure-the-engagement-plan) | The engagement strategy and step rules                                      |
| [**Define Messages**](doc:add-messages-for-the-lifecyle-agent)      | The messages across different channels available to the agent for selection |
| [**Define Guardrails**](doc:set-guardrails)                         | Channel limits, Frequency caps, and Do Not Disturb (DND) windows            |