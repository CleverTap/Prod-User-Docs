---
title: Troubleshooting
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
This section covers FAQs related to journeys.

#FAQ
##What are the different journey types in the past behavior segment?
One Time Journey is the type of journey that runs only for one time at the start time of the journey. Here there is no option to re-enter for the users who have exited the journey through journey timeout, force exit, or Goal completed. New users will not be added after the journey ran its course on the start time.

Multiple Dates Journey is the type of journey that will run on the multiple dates selected by you. You get to select the journey end time as per your use case for the journey. In this type of journey, the users can re-enter if the option of Allow users to re-enter the journey is selected.

The recurring journey is the type of journey that will repeatedly run and allow entry to new users on the criteria selected by you under the Repeat section. The first run would be as soon as you publish the Journey. The next runs will be according to the selected criteria. The users once exited can re-enter the journey if the option of Allow users to re-enter the journey is selected.

https://docs.clevertap.com/docs/journeys#section-past-behavior-segments-journey-qualification