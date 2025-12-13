---
title: Set Schedule & Message for Push Notifications
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Let 'Account Created' event have a property, say 'date set by user'. This property will have the date the user sets during account creation. 
(For your previous users, you can upload account created event using this API and by sending the 'date set by user' property as an epoch this way: "$D_epochValue")
Then on your dashboard, create a Past Behavior Push campaign:
User who did ‘Account Created’ greater than 1 times
where
occurred in the past 30 days
event property ‘date set by user’ in the past 1 day 
You can set this campaign to repeat daily, and also set a certain time for this campaign to start running daily
You can similarly create campaigns for +3days and +5days.