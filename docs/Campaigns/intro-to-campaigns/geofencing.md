---
title: Geofencing
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

CleverTap offers geofencing which is a GPS location-based service that customers can use to engage their audience by sending relevant messages to Android and iOS users. A geofence is a virtual geographic area, represented as latitude/longitude pairs combined with a radius, forming a circle in a specific position on a map. Geofences can vary in size and a geofence cluster can contain up to 100 geofences. 

Users can define geofences on the CleverTap dashboard and trigger campaigns in real-time as users enter and exit them around the world. Campaigns are delivered in real-time to users as they exit or enter geofences, or sent as followups hours or days later. As the users enter or exit geofences, CleverTap's location analytics create user data that can be used for re-targeting, and geofence-specific analytics can generate insight on activities or locations of interest.

# Create Geofences

To create geofences, perform the following steps:

1. From the CleverTap dashboard, select *Settings* > *Geofences*.

![918](https://files.readme.io/187896f-2020-09-01_19-28-13_Select_Geofences_from_Settings.png "2020-09-01_19-28-13_Select Geofences from Settings.png")

2. Click **+Geofence Cluster** to create a new geofence cluster.

![1684](https://files.readme.io/fc31f55-2020-09-01_19-33-29_Select_Unit_of_Measure.png "2020-09-01_19-33-29_Select Unit of Measure.png")

3. Select the preferred unit of measure that will be used to track location for the geofence clusters.
4. Click **Save**.
5. Click in the *Search for location* window to select the area or business locations you want to display on the map. 

> 📘 Note
>
> You can create up to 100 Geofences in each Cluster and can create up to 100 clusters for your app.

*Note*: Clicking on any of the search options creates a geofence with a setting pop-up open beside the circle.

![1676](https://files.readme.io/14c8d93-2020-09-01_19-42-59_Click_Map_to_Add_New_Geofence.png "2020-09-01_19-42-59_Click Map to Add New Geofence.png")

6. Enter the *Geofence* name.
7. Input the field radius you want the geofence to cover.
8. Click **Add**.

![1690](https://files.readme.io/329ca37-2020-09-03_17-31-00_Add_New_Geofence.png "2020-09-03_17-31-00_Add New Geofence.png")

9. Click **Continue**.
10. Add geofence cluster name.
11. Select a tracking start and end. Selecting date and time displays day and time options beneath the radio buttons.

![1675](https://files.readme.io/19f8208-2020-09-03_17-33-08_Creating_Cluster_Name.png "2020-09-03_17-33-08_Creating Cluster Name.png")

12. Click **Activate**.

## Optional Features

When entering the details for the geofence cluster, you can select a DND window and if you select start and end time, you can also set a dwell time. The DND option prevents triggering an engagement for users who enter the geofence on specified days and times. Dwell time specifies the amount of time a user can remain inside the geofence before triggering an engagement.

![413](https://files.readme.io/2b58e20-2020-09-03_18-07-51_DND_and_Dwell.png "2020-09-03_18-07-51_DND and Dwell.png")

> 📘 Add, Edit, or Delete Geofences
>
> Repeat the steps to add more geofences in your cluster. You can have up to 100 geofences in a cluster. In addition, you can edit or delete a geofence by clicking on the location and clicking the edit or delete icon. You can also edit or delete geofences by selecting them from the list on the left.

# Use Geofence Events

CleverTap raises two system events every time a device enters or exits a geofence that can be used to run campaigns, analytics, and segmentation:

* Geocluster Entered
* Geocluster Exited

Details about the event are provided in the events documentation section [here](https://docs.clevertap.com/docs/events#section-system-events).

# Add Geofence Clusters in a Campaign

Once you have configured your geofence clusters, you can add them to a campaign by performing the following steps.

1. Select *In-action within time* as your mobile push type. 
2. Select the campaign start and end time.
3. Click **+ Create an ad-hoc segment** .

![1885](https://files.readme.io/61a911a-2020-09-03_18-20-29_Select_Ad_hoc_segment.png "2020-09-03_18-20-29_Select Ad hoc segment.png")

4. From *As soon as user does*, select *Geocluster Entered*.
5. Click **+Filter** by to add geofence properties.

![1281](https://files.readme.io/ee7f234-2020-09-03_18-24-56_Adding_Geofence_Properties_to_Campaign.png "2020-09-03_18-24-56_Adding Geofence Properties to Campaign.png")

6. Click **Continue**.

# Video Tutorial

For further information, you can watch the following video on geofencing:

<Embed url="https://www.youtube.com/watch?v=JFhaDTKe228&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=3" title="Product Demo: Geofencing" favicon="https://www.youtube.com/s/desktop/1f1401a5/img/favicon.ico" image="https://i.ytimg.com/vi/JFhaDTKe228/hqdefault.jpg" provider="youtube.com" href="https://www.youtube.com/watch?v=JFhaDTKe228&list=PLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8&index=3" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FJFhaDTKe228%253Flist%253DPLTXk2GzdxAChuuVW4i_H3VwQ9obTRs1L8%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DJFhaDTKe228%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FJFhaDTKe228%252Fhqdefault.jpg%26key%3Df2aa6fc3595946d0afc3d76cbbd25dc3%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
