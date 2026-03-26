---
title: Session Analytics
excerpt: >-
  Understand how users engage within sessions by analyzing session duration,
  distribution, and activity patterns across your app.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

_Session Analytics_ can be used to track the events that users perform within a session. Analyzing session length is a great way to measure engagement for certain apps, such as video or music streaming, news, and so on.

A session is a period of continuous activity by the user. A user can perform as many events as required over a period of time; however, we consider a session timeout after 20 minutes of user inactivity. A new session is created after this session timeout. Sessions can be tracked on the Web as well as mobile apps.

> 📘 Tracking Sessions
>
> Sessions cannot be tracked for events pushed through API calls.

# Activate Sessions

You can start tracking user sessions after activating sessions from the CleverTap dashboard. The ability to track sessions is available in _Settings_ > _Session Analytics_.

<Image align="center" alt={1168} border={true} caption="Activate Session Tracking" title="Toggle ON the Session Tracking" src="https://files.readme.io/6f30c1f-Analytics_Session_Activate.png" width="100%" />

After you activate session tracking, you have the following:

* The _Session Concluded_ event is raised to mark the end of every session.
* A new system property called _CT Session ID_ is available for every custom event.
* A _Session Board_ is available within the _Boards_ section.

> 🚧 List of Events that Are Not Considered
>
> The following events are not considered for a session:
>
> * App Installed
> * App Uninstalled
> * UTM Visited
> * Identity Set
> * Identity Reset
> * Identity Error
> * Push Impressions
> * Notification Sent
> * _Notification Clicked_: These events are not considered for engagement channels like Email, Web Push, or Mobile Push.  
>   However, they are considered for channels such as Native Display, App Inbox, In-App, Web Exit Intent, and Web Popup.
> * _Notification Viewed_: These events are not considered for engagement channels like Email or Web Push.  
>   However, they are considered for channels such as Native Display, App Inbox, In-App, Web Exit Intent, and Web Popup.

# CT Session ID

A system property called _CT Session ID_ is available for each custom event. This _CT Session ID_ also appears on the user’s profile page.

# Session Concluded Event

A system event called _Session Concluded_ marks the end of a session. This event is raised after 20 minutes of inactivity.

The _Session Concluded_ event contains the following event properties:

* **Session Length**: It is the time period from the first event up to the last event measured in seconds. When analyzing session length in charts such as _Trends_ or the _Session Dashboard_, values may be grouped into bucket ranges for visualization. For details on how these ranges are calculated and displayed, refer to [Session Length Distribution Buckets](doc:session-analytics#session-length-distribution-buckets).
* **Session ID**: It is a unique ID to identify the session.

> 🚧 Availability Note
>
> This event is not available for engagement in the live user segments.

> 📘 Timestamp for a Session Concluded
>
> The timestamp for the _Session Concluded_ event is the same as the most recent event.
>
> For example, _Event 1_ was performed at 11:00 AM and _Event 2_ was performed at 11:10 AM. There is a period of inactivity after this event. After waiting for 20 minutes, a _Session Concluded_ event is raised at 11.30 AM, however, the timestamp for the _Session Concluded_ event is marked as 11:10 AM to identify the exact time of the last activity.

# Session Dashboard

This board is created automatically after you turn on session tracking. To view the session dashboard, perform the following:

1. From the CleverTap dashboard, click **Boards**.
2. Check for a board called _Session_ and open it.

<Image align="center" alt={947} border={true} caption="From the Boards Click Session to View Session Dashboard" title="Analytics_Session_Distribution.png" src="https://files.readme.io/c85d6ed-Analytics_Session_Distribution.png" width="100%" />

The session dashboard displays an overview of the app sessions with the following information:

* **Session length distribution**: The distribution of session length (in seconds).
* **Sum of session lengths per day**: The total session length across all users per day in the last 30 days.
* **Number of sessions**: The number of sessions in a day that occurred over the past 30 days.

## Session Length Distribution Buckets

The session length distribution is displayed using bucketed ranges rather than exact session durations.

These buckets follow a power-of-two (2^x) scaling pattern, grouping session lengths into progressively larger ranges such as:

* 0–4,096 seconds
* 4,096–8,192 seconds
* 8,192–16,384 seconds

Each bucket represents a range of session durations, not a specific value.

For example, if a session appears in the 0-4,096 seconds bucket, it does not mean the session lasted close to 4,096 seconds. The actual session duration could be much smaller (for example, a few minutes), but is grouped into this range for distribution analysis.

### Why Bucketing is Used?

Bucketing helps visualize how sessions are distributed across different duration ranges, especially when session lengths are highly variable. It allows you to:

* Identify where most user sessions fall
* Compare relative distribution across short vs long sessions

### Important Considerations

Use the following points to correctly interpret session length buckets and avoid misreading the data:

* Bucket ranges are not exact session values
* Most sessions within a bucket are typically concentrated toward the lower end of the range
* Higher buckets may appear large, but often contain very few sessions
