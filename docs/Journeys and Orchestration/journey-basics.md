---
title: Journey Basics
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

Here we explain the fundamentals of a Journey. 

# Past Behavior Segments(PBS) & Journey Qualification

* If your entry criteria is a Past Behavior segment, users will be qualified for your Journey at the start time specified.
* If you have added a Past Behavior segment along your Journey that segment will be evaluated once a day at 12:00 AM (in the timezone of your account).
* If you have added a Past Behavior segment as a goal that segment will be evaluated once a day at 12:00 AM (in the timezone of your account).
* Node timeout Evaluation - Node timeout evaluation happens every 1 hour at 1 PM, 2 PM, 3 PM, and so on, where start time depends on the account. Here is an example - 

- User A reaches node 4 at 2:30 PM with node time out of one hour. Her window closes at 3:30 PM after which even if the user performs the action, she will not move via the *Yes* path as the user is marked for node timeout. At 4 PM, user A will timeout. 
- User B reaches node 4 at 3:30 PM with a node timeout of one hour. Her window closes at 4:30 PM after which even if the user performs the action, she will not move via the *Yes* path as the user is marked for node timeout. At 4 PM, user B will *NOT* move out. At 5 PM (i.e. next evaluation run), the user will move via node timeout.
  * If you have added a Past Behaviour segment in the middle of the journey and have drawn a node timeout path with a qualifying window of less than 24hours value, then all users might move via node timeout path as PBS is only evaluated every 24 hours.

![1206](https://files.readme.io/7ff47d7-2020-08-17_16-14-20_DND_hours_Conflict.png "2020-08-17_16-14-20_DND hours Conflict.png")
