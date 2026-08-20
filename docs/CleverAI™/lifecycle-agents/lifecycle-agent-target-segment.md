---
title: Target Segment
excerpt: Define the user segment to reach your users.
deprecated: false
hidden: true
metadata:
  robots: index
---
### Define the Target Segment

The _Target Segment_ tab determines which users enter the agent and defines a control group.&#x20;


<Image src="https://files.readme.io/e3e6b27676934e94fb5be10eb731d8e03de9d66e26d7c8a6fe7e2577124cb5ce-image.png" alt="Define Target Segment" align="center" caption="Define Target Segment" border={true} />


To complete the _Target Segment_ tab:

1. Select the audience type for this agent. The following options are available:
   - _Ad hoc_ - Build a one-time, custom segment using CleverTap's segment builder
   - _Saved_ - Use an existing saved segment from your CleverTap account
   - _All users_ - Target all users in your account (selected by default)
2. (Optional) Click **Build with AI** to describe your target audience in plain language. The [CleverTap Segmentation Agent](https://docs.clevertap.com/docs/segmentation-agent) generates the segment criteria for you.&#x20;
3. Set the _Control Group_ percentage. The control group is a portion of your target audience that receives no messages from this agent. The default is 5%. You use the control group to measure the agent's true incremental lift to help you compare conversions in the control group against conversions in the agent-target group.
4. Click **Next** to proceed to the _Engagement Strategy_ tab.