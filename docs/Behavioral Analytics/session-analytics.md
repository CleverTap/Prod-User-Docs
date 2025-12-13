---
title: Session Analytics
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
*Session Analytics* can be used to track the events that users perform within a session. Analyzing session length is a great way to measure engagement for certain apps, such as video or music streaming, news, and so on.

A session is a period of continuous activity by the user. A user can perform as many events as required over a period of time; however, we consider a session timeout after 20 minutes of user inactivity. A new session is created after this session timeout. Sessions can be tracked on the Web as well as mobile apps. 
[block:callout]
{
  "type": "info",
  "body": "Sessions cannot be tracked for events pushed through API calls.",
  "title": "Tracking Sessions"
}
[/block]
#Activate Sessions

You can start tracking user sessions after activating sessions from the CleverTap dashboard. The ability to track sessions is available in *Settings* > *Session Analytics*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6f30c1f-Analytics_Session_Activate.png",
        "Analytics_Session_Activate.png",
        1168,
        495,
        "#f9f9fa"
      ],
      "border": true
    }
  ]
}
[/block]
After you activate session tracking, you have the following:

  * The *Session Concluded* event is raised to mark the end of every session.
  * A new system property called *CT Session ID* is available for every event.
  * A *Session Board* is available within the *Boards* section.
[block:callout]
{
  "type": "warning",
  "body": "The following events are not considered for a session:\n  * App Installed\n  * App Uninstalled\n  * Notification Sent\n  * Notification Clicked\n  * UTM Visited\n  * Identity Set\n  * Identity Reset\n  * Identity Error",
  "title": "List of Events that Are Not Considered"
}
[/block]
#CT Session ID
A system property called *CT Session ID* is available for each event. This *CT Session ID* also appears on the user’s profile page.

#Session Concluded Event
A system event called *Session Concluded* marks the end of a session. This event is raised after 20 minutes of inactivity.

The *Session Concluded* event contains the following event properties:

  * Session Length: It is the time period from the first event up to the last event measured in seconds. 
  * Session ID: It is a unique ID to identify the session. 
[block:callout]
{
  "type": "warning",
  "body": "This event is not available for engagement in the live user segments.",
  "title": "Availability Note"
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Timestamp for a Session Concluded",
  "body": "The timestamp for the *Session Concluded* event is the same as the most recent event.\n\nFor example, *Event 1* was performed at 11:00 AM and *Event 2* was performed at 11:10 AM. There is a period of inactivity after this event. After waiting for 20 minutes, a *Session Concluded* event is raised at 11.30 AM, however, the timestamp for the *Session Concluded* event is marked as 11:10 AM to identify the exact time of the last activity."
}
[/block]
#Session Dashboard
This board is created automatically after you turn on session tracking. To view the session dashboard, perform the following:

  1. From the CleverTap dashboard, click **Boards**. 
  2. Check for a board called *Session* and open it. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c85d6ed-Analytics_Session_Distribution.png",
        "Analytics_Session_Distribution.png",
        947,
        1118,
        "#f6f7fc"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
The session dashboard displays an overview of the app sessions with the following information:

  * Session length distribution: The distribution of session length (in seconds).
  * Sum of session lengths per day: The total session length across all users per day in the last 30 days.
  * Number of sessions: The number of sessions in a day that occurred over the past 30 days.