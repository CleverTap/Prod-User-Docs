---
title: Engagement Strategy
excerpt: Learn how to create a strategy tailored to your use case.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
The Engagement Strategy tab defines how the agent decides to engage each user. You create an engagement strategy allowing you to define your own step names and entry and exit conditions. You can then choose whether the agent fully controls pacing or follows manually defined step rules.

1. Enter a name in the _Name_ field to identify this engagement strategy.
2. Under _Engagement Mode_, select one of the following modes:
   - **Guided** — Define each engagement step, its channels, and the conditions that move users out of that step. Use this mode when message content depends on step progression, for example, when a user must first learn about a product before receiving a promotional offer.&#x20;
   - **Autonomous&#x20;**&#x20;— Add channels and messages, and let the agent send them in the order it chooses. Use this mode when messages are self-contained and don't depend on each other, for example, when running variations of the same offer.&#x20;

### Guided

If you selected _Guided_, the Engagement steps section appears. Use it to set up each step of the user journey. A step is a phase of an engagement strategy. Users are guided through the steps you define to achieve goal events, and the agent selects suitable messages, channels, and timing based on the definitions set for each step.&#x20;

Every user enters Step 1 upon entering the agent and exits to the next step when the step's exit rules are met. Users move to any of the subsequent steps when they perform the event defined by the step's entry rules.&#x20;

The following image shows the _Engagement Strategy_ tab with steps:


<Image src="https://files.readme.io/6db94951f78657f1b943edb1999532bc412b9d26d2035e9881b0ca9dca47b326-image.png" alt="Engagement Strategy" align="center" caption="Engagement Strategy" border={true} />


<br />

To configure each engagement step:

1. Under _Engagement&#x20;_&#x73;teps, locate the step and enter a name in the _Name_ field.
2. Under _Definition_, click **Channel +** to add the channels this step can use. The supported channels are Push Notifications, Email, SMS, WhatsApp, Web Push, and Inbox.&#x20;
3. For Step 2 and onwards, under _Step Entry Rules_, set _Meets Intent_ to the event that a user must perform to enter this step. Click **+ Filter** to narrow the event definition.
4. Under _Step Exit Rules_, configure the conditions that cause a user to exit this step. When any of these conditions are met, the agent moves the user to the next step or stops sending messages if this is the last step.<br />a. Set _Maximum no of messages_ — the maximum number of messages the agent sends to one user in this step before moving them forward. <br />b. Set _Maximum no of days_ — the maximum number of days a user stays in this step before the agent moves them forward.&#x20;
5. Click **+ Add Step** to add another step, and repeat these steps.

### Autonomous

If you selected _Autonomous_, add the channels and messages. The agent sends messages without following a predefined order.

To configure agent-controlled mode:

1. Under _Definition_, click **Channel +** to add the channels the agent can use. The supported channels are Push Notifications, Email, SMS, WhatsApp, and Inbox.
2. Click **Next** to proceed to the _Messages_ tab.

<br />

<br />
