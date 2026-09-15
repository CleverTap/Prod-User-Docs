---
title: Journey Stats
excerpt: >-
  Gain actionable insights into user behavior, goal completion, and campaign
  effectiveness, version by version.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

The Journey Stats tab provides comprehensive performance metrics for the journey. This view helps you understand how users are progressing through the journey, evaluate goal performance, and compare target vs. control group behavior.


<Image src="https://files.readme.io/9a4babab4fbbc9f1661e8008bccacd5c6d7b31b0ab3c0371b333df9a96478d21-Journey_Stats.png" alt="Journey Stats" align="center" border={true} />


Use the calendar selector at the top to define a custom date range for which you want to view journey performance.

<Callout icon="📘" theme="info">
  ### Metrics for Journey Stats

  All metrics displayed on this page are based on the selected date range, except for the Users in journey count, which reflects the real-time number of users currently progressing through the journey.
</Callout>

The following metrics are displayed at the top for the selected journey version:

* **Entered Journey**: Users who entered the journey.
* **Qualified**: Users who met the entry condition and were processed by journey nodes.
* **Control Group**: Random users held out from the journey for A/B comparison.
* **Goal Met**: Users who fulfilled the defined journey goal.
* **Completed**: Users who completed the journey.
* **Timed Out**: Users who did not complete the journey within the allowed timeframe.
* **Force Exits**: Users forcibly removed due to defined conditions.


<Image src="https://files.readme.io/ba3f3b9a022c2aa9a639b94a7f0a38501a4272024bc8f0872dc4ba0e27818b6f-Journey_Stats_-_Key_Metrics.png" alt="1345" align="center" border={true} />


# Goal Conversion Rate

This section displays the conversion performance of the journey and compares the _Target Group_ to the _Control Group_.


<Image src="https://files.readme.io/ecc981ad72f966c5e78daf35546254e312bf3cef5988c2a1c770b7b67322c49a-Goal_Conversion_Rate.png" alt="1880" align="center" border={true} />


* The Boost for the journey is calculated as follows:<br />**Boost Rate** = \[(Target Group% - Control Group%)/Control Group%] x 100
* The Conversion Rate for the journey is calculated as follows:<br />**Conversion Rate** = (Number of Conversions/Number of Visitors) x 100

# Entry and Exit Trends

The Trends section offers a timeline view, such as daily, weekly, and monthly, of key journey metrics:

* Number of users who entered the journey
* Number of users who completed the journey
* Users who met the journey goal
* Users who timed out of the journey

These insights help identify behavioral patterns and performance fluctuations over time.


<Image src="https://files.readme.io/8af820ea015a7d689800f66ce5ba566c8b37889d43f5db128ecd2ab48285732e-Weekly_Entry_and_Exit_Trends.png" alt="1348" align="center" width="90% " border={true} />
