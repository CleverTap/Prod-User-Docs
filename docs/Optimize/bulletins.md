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
[block:api-header]
{
  "title": "Introduction"
}
[/block]
Bulletins are a category of engagement campaigns that are not broadly capitalized in the mobile engagement space. Instead of an organization creating hundreds of campaigns a day for various SKUs, the process is automated in the CleverTap platform. Users can set up campaigns and dispatch Bulletins for a business event with any number of properties. 

Bulletins provide the ability to send automated, scalable campaigns based on events that happen on the business side to users who are likely to be interested. When a user performs an event or doesn’t perform an event in a certain amount of time, a message can be sent prompting action.
 
##User Scenarios
 
The following are examples of Bulletin use cases:
 
Example #1
 
A movie streaming app has a new notification for users who watch a particular movie genre regularly. As an app subscriber, the customer receives a push notification regarding the new season that was just released. The business event “episode_release” is sent to the CleverTap system via an API. A published Bulletin for the business event is dispatched when the business event occurs.

Example #2
 
A company creates 200 campaigns daily for their television shows. Each campaign is slightly different, and the customer doesn’t want to come to the dashboard and spend approximately five minutes for every similar campaign they create. By using Bulletins, they can automate the process to communicate with the interest groups with a personalized message.
[block:api-header]
{
  "title": "Create Business Events"
}
[/block]
Before a Bulletin can be published, define a business event, which is the event performed by the business (e.g., episode releases, book launch, or weekly sales). The following instructions illustrate a business event named *episode_release* which represents a new episode being released. 

1. Select the *Bulletins* option on the left navigation menu.
2. Click **+ Business Event**. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3faca62-2020-05-11_08-47-08_Define_business_event.png",
        "2020-05-11_08-47-08_Define business event.png",
        1808,
        849,
        "#fbfbfc"
      ]
    }
  ]
}
[/block]
3. Enter the following information:
  * Business event name - This is the event performed by your business (e.g., episode releases, weekly sales)
  * Business event properties - These are the other identifiers related to a business event (e.g, movie title, genre, series, language) 
  * Goal (optional) -  This is the desired outcome of the Bulletin (e.g., app launched, movie watched, series watched)
  * Value of user event property - This is the value of the user event property, which should match the business event property (i.e., as a user I watched Show A and Show A is the business event property of the show being released).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/125bf9c-2020-05-11_08-57-53_Define_event_2.png",
        "2020-05-11_08-57-53_Define event_2.png",
        2590,
        1180,
        "#f9fafc"
      ]
    }
  ]
}
[/block]
4. Click **Save & Continue**. If edits are required, click the **Edit** button to return to the previous screen.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6b6bb78-2020-05-11_09-09-10_Define_event_3.png",
        "2020-05-11_09-09-10_Define event_3.png",
        2650,
        1558,
        "#e5e6eb"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Create Bulletin"
}
[/block]
Once a business event is defined, click the **Create Bulletin** button and define an interest segment.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/304997e-2020-05-11_09-28-49_Define_user_segment.png",
        "2020-05-11_09-28-49_Define user segment.png",
        1847,
        754,
        "#f9fafc"
      ]
    }
  ]
}
[/block]
1. Select a segment from the dropdown menu options (e.g., All Users or Engaged Users).
2. Select one of the event properties defined earlier. (Refer to *Create Business Events*.)
3. Select *User Event* from the dropdown menu.
4. Select an event property from the dropdown menu. The value of the property needs to match the business event property.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e04592-2020-05-11_09-55-33_Define_user_desegment_2.png",
        "2020-05-11_09-55-33_Define user desegment_2.png",
        2632,
        1016,
        "#f9fafb"
      ]
    }
  ]
}
[/block]
5. Click **+ User Events** or  **+ User Properties** to add additional events or properties.
6. Click **+ Filter** to add additional properties to the event property.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9c5ef68-2020-05-11_10-08-31_Define_user_segment_3.png",
        "2020-05-11_10-08-31_Define user segment_3.png",
        2632,
        1552,
        "#f9f9fb"
      ]
    }
  ]
}
[/block]
6. Click **Continue**.
7. Select a channel for the Bulletin and follow the onscreen instructions for the chosen method. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6741cc4-2020-05-27_17-17-15_Select_channel.png",
        "2020-05-27_17-17-15_Select channel.png",
        890,
        762,
        "#f8f8f8"
      ],
      "caption": ""
    }
  ]
}
[/block]
The following is a sample notification:
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf7899e-2020-05-11_10-57-09_Notification_example.png",
        "2020-05-11_10-57-09_Notification example.png",
        1768,
        830,
        "#fafafb"
      ],
      "caption": ""
    }
  ]
}
[/block]
8. Apply a Custom/Campaign control group.
9. Specify the push notification time to live.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2cee477-2020-05-11_11-37-48_control_groups.png",
        "2020-05-11_11-37-48_control groups.png",
        1583,
        747,
        "#fafaf8"
      ]
    }
  ]
}
[/block]
10. Click **Continue** to view the Bulletin overview.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4525be7-2020-05-11_11-52-53_Bulletin_overview.png",
        "2020-05-11_11-52-53_Bulletin overview.png",
        1820,
        872,
        "#fcfdfd"
      ]
    }
  ]
}
[/block]
11. Select **Publish** and name the Bulletin.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/511eb2b-2020-05-11_11-56-55_Naming_bulletin.png",
        "2020-05-11_11-56-55_Naming bulletin.png",
        1831,
        875,
        "#a5a5a6"
      ]
    }
  ]
}
[/block]
11. Click **Publish**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/141db60-2020-05-11_11-59-47_Done.png",
        "2020-05-11_11-59-47_Done.png",
        1844,
        831,
        "#a1a1a1"
      ]
    }
  ]
}
[/block]
12. Click **Ok, Got It** to finish the Bulletin setup.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/db02dcc-2020-05-11_12-05-43_Done_2.png",
        "2020-05-11_12-05-43_Done 2.png",
        1801,
        987,
        "#fafaf9"
      ]
    }
  ]
}
[/block]

[block:api-header]
{
  "title": "Raise Business Event API"
}
[/block]
To raise a business event, trigger the event's API as shown below by using the following link: 
[https://api.clevertap.com/1/targets/trigger.json](https://api.clevertap.com/1/targets/trigger.json)
[block:code]
{
  "codes": [
    {
      "code": "{\n    \"business_event\" : \"Program Released\",\n    \"name\" : \"Sa Re Ga Ma episode 12\",\n    \"properties\" : {\n        \"program_id\" : \"234567\",\n        \"language\":\"Hindi\",\n        \"prev_program_id\":\"123457\"\n    },\n    \"c-by\" : \"jdoe@clevertap.com\"\n}",
      "language": "text"
    }
  ]
}
[/block]
For detailed Bulletins API information, refer to [https://developer.clevertap.com/docs/bulletins-api](https://developer.clevertap.com/docs/bulletins-api). 
[block:api-header]
{
  "title": "Monitor Bulletin Performance"
}
[/block]
CleverTap provides comprehensive monitoring for the performance of Bulletins. The *Percentage of Users Converted* graph displays the percentage of qualified users who were sent a Bulletin. It also displays the users who viewed or clicked the Bulletin. The graph shows the total number of technical and non-technical delivery errors.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c8c4884-2020-05-18_16-23-53_stats.png",
        "2020-05-18_16-23-53_stats.png",
        1245,
        850,
        "#f1f2f9"
      ]
    }
  ]
}
[/block]
The technical errors can be analyzed further via the following table.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/48298b6-2020-05-18_16-24-49_stats1.png",
        "2020-05-18_16-24-49_stats1.png",
        1183,
        429,
        "#f6f7f9"
      ]
    }
  ]
}
[/block]
This displays a business activity log, the dispatched Bulletins, the event time of the Bulletins, the total number of Bulletin sent, and the person who created the Bulletin.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0cbd4b7-2020-05-18_16-25-46_stats2.png",
        "2020-05-18_16-25-46_stats2.png",
        1182,
        828,
        "#f8f9fa"
      ]
    }
  ]
}
[/block]