---
title: Bulletins
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
## Introduction

Bulletins are a category of engagement campaigns that are not broadly capitalized in the mobile engagement space. Instead of an organization creating hundreds of campaigns a day for various SKUs, the process is automated in the CleverTap platform. Users can set up campaigns and dispatch Bulletins for a business event with any number of properties. 

Bulletins provide the ability to send automated, scalable campaigns based on events that happen on the business side to users who are likely to be interested. When a user performs an event or doesn’t perform an event in a certain amount of time, a message can be sent prompting action.

## User Scenarios

The following are examples of Bulletin use cases:

Example #1

A movie streaming app has a new notification for users who watch a particular movie genre regularly. As an app subscriber, the customer receives a push notification regarding the new season that was just released. The business event “episode\_release” is sent to the CleverTap system via an API. A published Bulletin for the business event is dispatched when the business event occurs.

Example #2

A company creates 200 campaigns daily for their television shows. Each campaign is slightly different, and the customer doesn’t want to come to the dashboard and spend approximately five minutes for every similar campaign they create. By using Bulletins, they can automate the process to communicate with the interest groups with a personalized message.

## Create Business Events

Before a Bulletin can be published, define a business event, which is the event performed by the business (e.g., episode releases, book launch, or weekly sales). The following instructions illustrate a business event named *episode\_release* which represents a new episode being released. 

1. Select the *Bulletins* option on the left navigation menu.
2. Click **+ Business Event**. 

![1808](https://files.readme.io/3faca62-2020-05-11_08-47-08_Define_business_event.png "2020-05-11_08-47-08_Define business event.png")

3. Enter the following information:

* Business event name - This is the event performed by your business (e.g., episode releases, weekly sales)
* Business event properties - These are the other identifiers related to a business event (e.g, movie title, genre, series, language) 
* Goal (optional) -  This is the desired outcome of the Bulletin (e.g., app launched, movie watched, series watched)
* Value of user event property - This is the value of the user event property, which should match the business event property (i.e., as a user I watched Show A and Show A is the business event property of the show being released).

![2590](https://files.readme.io/125bf9c-2020-05-11_08-57-53_Define_event_2.png "2020-05-11_08-57-53_Define event_2.png")

4. Click **Save & Continue**. If edits are required, click the **Edit** button to return to the previous screen.

![2650](https://files.readme.io/6b6bb78-2020-05-11_09-09-10_Define_event_3.png "2020-05-11_09-09-10_Define event_3.png")

## Create Bulletin

Once a business event is defined, click the **Create Bulletin** button and define an interest segment.

![1847](https://files.readme.io/304997e-2020-05-11_09-28-49_Define_user_segment.png "2020-05-11_09-28-49_Define user segment.png")

1. Select a segment from the dropdown menu options (e.g., All Users or Engaged Users).
2. Select one of the event properties defined earlier. (Refer to *Create Business Events*.)
3. Select *User Event* from the dropdown menu.
4. Select an event property from the dropdown menu. The value of the property needs to match the business event property.

![2632](https://files.readme.io/5e04592-2020-05-11_09-55-33_Define_user_desegment_2.png "2020-05-11_09-55-33_Define user desegment_2.png")

5. Click **+ User Events** or  **+ User Properties** to add additional events or properties.
6. Click **+ Filter** to add additional properties to the event property.

![2632](https://files.readme.io/9c5ef68-2020-05-11_10-08-31_Define_user_segment_3.png "2020-05-11_10-08-31_Define user segment_3.png")

6. Click **Continue**.
7. Select a channel for the Bulletin and follow the onscreen instructions for the chosen method. 

![890](https://files.readme.io/6741cc4-2020-05-27_17-17-15_Select_channel.png "2020-05-27_17-17-15_Select channel.png")

The following is a sample notification:

![1768](https://files.readme.io/cf7899e-2020-05-11_10-57-09_Notification_example.png "2020-05-11_10-57-09_Notification example.png")

8. Apply a Custom/Campaign control group.
9. Specify the push notification time to live.

![1583](https://files.readme.io/2cee477-2020-05-11_11-37-48_control_groups.png "2020-05-11_11-37-48_control groups.png")

10. Click **Continue** to view the Bulletin overview.

![1820](https://files.readme.io/4525be7-2020-05-11_11-52-53_Bulletin_overview.png "2020-05-11_11-52-53_Bulletin overview.png")

11. Select **Publish** and name the Bulletin.

![1831](https://files.readme.io/511eb2b-2020-05-11_11-56-55_Naming_bulletin.png "2020-05-11_11-56-55_Naming bulletin.png")

11. Click **Publish**.

![1844](https://files.readme.io/141db60-2020-05-11_11-59-47_Done.png "2020-05-11_11-59-47_Done.png")

12. Click **Ok, Got It** to finish the Bulletin setup.

![1801](https://files.readme.io/db02dcc-2020-05-11_12-05-43_Done_2.png "2020-05-11_12-05-43_Done 2.png")

## Raise Business Event API

To raise a business event, trigger the event's API as shown below by using the following link:\
[https://api.clevertap.com/1/targets/trigger.json](https://api.clevertap.com/1/targets/trigger.json)

```text
{
    "business_event" : "Program Released",
    "name" : "Sa Re Ga Ma episode 12",
    "properties" : {
        "program_id" : "234567",
        "language":"Hindi",
        "prev_program_id":"123457"
    },
    "c-by" : "jdoe@clevertap.com"
}
```

For detailed Bulletins API information, refer to [https://developer.clevertap.com/docs/bulletins-api](https://developer.clevertap.com/docs/bulletins-api). 

## Monitor Bulletin Performance

CleverTap provides comprehensive monitoring for the performance of Bulletins. The *Percentage of Users Converted* graph displays the percentage of qualified users who were sent a Bulletin. It also displays the users who viewed or clicked the Bulletin. The graph shows the total number of technical and non-technical delivery errors.

![1245](https://files.readme.io/c8c4884-2020-05-18_16-23-53_stats.png "2020-05-18_16-23-53_stats.png")

The technical errors can be analyzed further via the following table.

![1183](https://files.readme.io/48298b6-2020-05-18_16-24-49_stats1.png "2020-05-18_16-24-49_stats1.png")

This displays a business activity log, the dispatched Bulletins, the event time of the Bulletins, the total number of Bulletin sent, and the person who created the Bulletin.

![1182](https://files.readme.io/0cbd4b7-2020-05-18_16-25-46_stats2.png "2020-05-18_16-25-46_stats2.png")
