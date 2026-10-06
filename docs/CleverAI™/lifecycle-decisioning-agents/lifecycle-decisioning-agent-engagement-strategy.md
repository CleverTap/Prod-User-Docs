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
The Engagement Strategy tab defines how the agent decides to engage each user. You create an engagement strategy allowing you to define your own stage names and entry and exit conditions. You can then choose whether the agent fully controls pacing or follows manually defined stage rules.

1. Enter a name in the _Name_ field to identify this engagement strategy.
2. Under _Engagement Strategy_, select one of the following modes:
   - **Manually Defined** — Define each engagement stage, its channels, and the conditions that move users out of that stage. Use this mode when message content depends on stage progression, for example, when a user must first learn about a product before receiving a promotional offer.&#x20;
   - **Agent Controlled** — Add channels and messages, and let the agent send them in the order it chooses. Use this mode when messages are self-contained and don't depend on each other, for example, when running variations of the same offer.&#x20;

### **Manually defined&#x20;**

If you selected Manually defined, the Engagement stages section appears. Use it to set up each stage of the user journey. A stage is a phase of an engagement strategy. Users are moved through the stages you define to achieve goal events, and the agent picks suitable messages, channels, and timing based on the definition set for each stage.&#x20;

Every user enters Stage 1 upon entering the agent and exits to the next stage when the stage's exit rules are met. Users move to any of the subsequent stages when they perform the event defined by the stage's entry rules.&#x20;

The following image shows the _Engagement Strategy_ tab with stages:


<Image src="https://files.readme.io/92d16040bf2a172e18e5081e39489608ec831bb8669d9b662cb80eaa785314b7-image.png" alt="Engagement Strategy" align="center" caption="Engagement Strategy" border={true} />


<br />

To configure each engagement stage:

1. Under _Engagement stages_, locate the stage and enter a name in the _Name_ field.
2. Under _Definition_, click **Channel +** to add the channels this stage can use. The supported channels are Push Notifications, Email, SMS, WhatsApp, Web Push, and Inbox.&#x20;
3. For Stage 2 and onwards, under _Stage Entry Rules_, set _Meets Intent_ to the event that a user must perform to enter this stage. Click **+ Filter** to narrow the event definition.
4. Under _Stage Exit Rules_, configure the conditions that move a user out of this stage. When any of these conditions is met, the agent moves the user to the next stage, or stops sending messages if this is the last stage.<br />a. Set _Maximum no of messages_ — the maximum number of messages the agent sends to one user in this stage before moving them forward. <br />b. Set _Maximum no of days_ — the maximum number of days a user stays in this stage before the agent moves them forward.&#x20;
5. Click **+ Add Stage** to add another stage, and repeat these steps.

### Agent Controlled

If you selected **Agent controlled**, add the channels and messages. The agent sends messages without following a predefined order.

To configure agent-controlled mode:

1. Under _Definition_, click **Channel +** to add the channels the agent can use. The supported channels are Push Notifications, Email, SMS, WhatsApp, and Inbox.
2. Click **Next** to proceed to the _Messages_ tab.

<br />

<br />
