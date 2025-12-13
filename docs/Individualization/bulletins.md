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
## Overview

Bulletins are a category of engagement campaigns that are not broadly capitalized in the mobile engagement space. Instead of an organization creating hundreds of campaigns a day for various SKUs, the process is automated in the CleverTap platform. Users can set up campaigns and dispatch bulletins for a business event with any number of properties. 

Bulletins provide the ability to send automated, scalable campaigns based on events that happen on the business side to users who are likely to be interested. When a user performs an event or does not perform an event in a certain amount of time, a message can be sent prompting action.

## User Scenarios

The following are examples of bulletin use cases:

### Example #1

A movie streaming app has a new notification for users who watch a particular movie genre on a regular basis. As an app subscriber, the customer receives a push notification regarding the new season that was just released. The business event *episode\_release* is sent to the CleverTap system via an API. A published bulletin for the business event is dispatched when the business event occurs.

### Example #2

A company creates 200 daily campaigns for their television shows. Each campaign is slightly different, and the customer does not want to come to the dashboard to spend around five minutes for every similar campaign they create. By using bulletins, they can automate the process to communicate with the interest groups with a personalized message.

### Example #3

A music streaming app sends a new notification for users as soon as a new album for an artist is released. As an app subscriber, the customer receives a push notification regarding the new album that was just released if the customer has heard, downloaded, or favorited 10 or more songs from the artist recently. The business event *album\_release* is sent to the CleverTap system via an API. A published bulletin for the business event is dispatched when the business event occurs.

## Create Business Events

Before a bulletin can be published, define a business event which is the event performed by the business (e.g., episode releases, book launch, or weekly sales). The following instructions illustrate a business event named *episode\_release* which represents a new episode being released. 

1. Select the *Bulletins* option on the left navigation menu.
2. Click **+ Business Event**. 

![1808](https://files.readme.io/ba9c478-2020-05-11_08-47-08_Define_business_event.png "2020-05-11_08-47-08_Define business event.png")

3. Enter the following information:

* Business event name: This is the event performed by your business (e.g., episode releases, weekly sales).
* Business event properties: These are the other identifiers related to a business event (e.g., movie title, genre, series, language).
* Goal (optional): This is the desired outcome of the Bulletin (e.g., app launched, movie watched, series watched).
* Value of user event property: This is the value of the user event property that should match the business event property (i.e., as a user I watched Show A and Show A is the business event property of the show being released).

![2590](https://files.readme.io/125bf9c-2020-05-11_08-57-53_Define_event_2.png "2020-05-11_08-57-53_Define event_2.png")

4. Click **Save & Continue**. If you need to edit, click the **Edit** button to return to the previous screen.

![2650](https://files.readme.io/6b6bb78-2020-05-11_09-09-10_Define_event_3.png "2020-05-11_09-09-10_Define event_3.png")

## Create a Bulletin

Once a business event is defined, click the **Create Bulletin** button and define an interest segment.

![2642](https://files.readme.io/e696d12-1_and_4_Select_an_event_property.png "1 and 4 Select an event property.png")

1. Select a segment from the dropdown menu options (e.g., All Users or Engaged Users).
2. Select one of the event properties defined earlier. (Refer to *Create Business Events* above.)
3. Select *User Event* from the dropdown menu.
4. Select an event property from the dropdown menu. The value of the property needs to match the business event property.

> 🚧 String Data Type
>
> CleverTap only supports the string data type for mapped property values.

![2642](https://files.readme.io/9a6bb90-1_and_4_Select_an_event_property.png "1 and 4 Select an event property.png")

5. Under the *Where* section, select *Count*, the type of count, and enter a quantity. Also, choose the value of property to match with a business event property.

![2736](https://files.readme.io/d1d38a4-Bulletins_new_count.png "Bulletins new count.png")

6. Click **+ User Events** or  **+ User Properties** to add additional events or properties.
7. Click **+ Filter by** to add additional properties to the event property.

![2738](https://files.readme.io/6965e30-7_Filter_by_to_add_additional_properties.png "7 Filter by to add additional properties.png")

8. Click **Continue**.
9. Select a channel for the bulletin and follow the onscreen instructions for the chosen method. 

![890](https://files.readme.io/6741cc4-2020-05-27_17-17-15_Select_channel.png "2020-05-27_17-17-15_Select channel.png")

The following is a sample notification:

![1768](https://files.readme.io/cf7899e-2020-05-11_10-57-09_Notification_example.png "2020-05-11_10-57-09_Notification example.png")

10. Apply a custom/campaign control group.
11. Specify the push notification time to live.

![1583](https://files.readme.io/2cee477-2020-05-11_11-37-48_control_groups.png "2020-05-11_11-37-48_control groups.png")

12. Click **Continue** to view the bulletin overview.

![1820](https://files.readme.io/3fedc9c-2020-05-11_11-52-53_Bulletin_overview.png "2020-05-11_11-52-53_Bulletin overview.png")

13. Select *Publish* and name the bulletin.

![1831](https://files.readme.io/6896ae5-2020-05-11_11-56-55_Naming_bulletin.png "2020-05-11_11-56-55_Naming bulletin.png")

14. Click **Publish**.

![1837](https://files.readme.io/60b84f2-2020-05-11_11-59-47_Done.png "2020-05-11_11-59-47_Done.png")

15. Click **Ok, Got It** to finish the bulletin setup.

![1801](https://files.readme.io/df160a7-2020-05-11_12-05-43_Done_2.png "2020-05-11_12-05-43_Done 2.png")

## Raise Business Event API

To raise a business event, trigger the event's API as shown below by using the following link:\
[https://location.api.clevertap.com/1/targets/trigger.json](https://location.api.clevertap.com/1/targets/trigger.json)

> 📘 URLs for Your Specific Location
>
> Use the URL based on your location:
>
> * India: in1.api.clevertap.com
> * Singapore: sg1.api.clevertap.com
> * U.S.: us1.api.clevertap.com

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

For more information, refer to [Bulletins API](https://developer.clevertap.com/docs/bulletins-api). 

## Monitor Bulletin Performance

CleverTap provides comprehensive monitoring for the performance of bulletins. The *Percentage of Users Converted* graph displays the percentage of qualified users who were sent a bulletin. It also displays the users who viewed or clicked the bulletin. The graph shows the total number of technical and non-technical delivery errors.

![1245](https://files.readme.io/c8c4884-2020-05-18_16-23-53_stats.png "2020-05-18_16-23-53_stats.png")

The technical errors can be analyzed further via the following table:

![1183](https://files.readme.io/48298b6-2020-05-18_16-24-49_stats1.png "2020-05-18_16-24-49_stats1.png")

This table displays a business activity log, the dispatched bulletins, the event time of the bulletins, the total number of bulletins sent, and the person who created the bulletin.

![1182](https://files.readme.io/0cbd4b7-2020-05-18_16-25-46_stats2.png "2020-05-18_16-25-46_stats2.png")

# Video Tutorial

For further information, you can watch the following video on bulletins:

<Embed url="https://www.youtube.com/watch?v=W-sYhkNcyXs&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=8" title="Product Demo: Bulletins" favicon="https://www.youtube.com/s/desktop/3a84d4c0/img/favicon.ico" image="https://i.ytimg.com/vi/W-sYhkNcyXs/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=W-sYhkNcyXs&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=8" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FW-sYhkNcyXs%253Flist%253DPLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DW-sYhkNcyXs%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FW-sYhkNcyXs%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
