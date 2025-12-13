---
title: Geofencing_Campaign_redesign_WIP
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
CleverTap offers geofencing which is a GPS location-based service that customers can use to engage their audience by sending relevant messages to Android and iOS users. A geofence is a virtual geographic area, represented as latitude and longitude pairs combined with a radius, forming a circle in a specific position on a map. Geofences can vary in size and a geofence cluster can contain up to 100 geofences. 

Users can define geofences on the CleverTap dashboard and trigger campaigns in real-time as users enter and exit them around the world. Campaigns are delivered in real-time to users as they exit or enter geofences or sent as follow-ups hours or days later. As the users enter or exit geofences, CleverTap's location analytics create user data that can be used for re-targeting and geofence-specific analytics can generate insight on activities or locations of interest.

# Create Geofences

To create geofences, perform the following steps:

1. From the CleverTap dashboard, select *Settings* > *Geofences*.
2.  Click **+ Geofence Cluster** to create a new geofence cluster.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d47ee91-1_Geofence_Cluster.png",
        "1 +Geofence Cluster.png",
        1403,
        462,
        "#f5f7f9"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Geofence and Cluster Limits",
  "body": "You can create up to 100 geofences in each cluster and up to 100 clusters for your app."
}
[/block]
3. Select the preferred unit of measure that will be used to track the location for the geofence clusters.
4. Click **Save**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c40fcfa-2_Select_the_preferred_unit_of_measure.png",
        "2 Select the preferred unit of measure.png",
        1404,
        703,
        "#95999c"
      ]
    }
  ]
}
[/block]
5. Click in the *Search for location* window to select the area you want to display on the map or enter a location in the search bar. A setting pop-up window displays.
6. Enter a *Geofence* name.
7. Input a field radius you want the geofence to cover.
8. Click **Add** on the pop-up window.
9. Click **Continue**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/bbcdb82-3_Add_a_geofence_name.png",
        "3 Add a geofence name.png",
        1404,
        706,
        "#e8eff1"
      ]
    }
  ]
}
[/block]
10. Enter a geofence cluster name.
11. Select a tracking start and end. If you select *Select date and time*, day and time options display beneath the radio buttons where you can choose a future start and end date and time.
12. Click **Activate** or **Schedule**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/19f8208-2020-09-03_17-33-08_Creating_Cluster_Name.png",
        "2020-09-03_17-33-08_Creating Cluster Name.png",
        1675,
        637,
        "#eef2f5"
      ]
    }
  ]
}
[/block]
## Optional Do Not Disturb Feature
When entering the details for the geofence cluster, you can select a Do Not Disturb (DND) window and if you select start and end time, you can also set a dwell time. The DND option prevents triggering an engagement for users who enter the geofence on specified days and times. Dwell time specifies the amount of time a user can remain inside the geofence before triggering an engagement.

@PM: PER VISHAL SOMANI, RE-ADDED THE DWELL TIME TEXT FROM THE EXISTING USER DOC; HOWEVER,  UNABLE TO FIND THE ACTUAL 'DWELL TIME' CHECKBOX IN THE NEW DASHBOARD. DO WE NEED A NEW SCREENSHOT BELOW?
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/da7e4a0-DND.png",
        "DND.png",
        701,
        697,
        "#f4f6f9"
      ]
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Add, Edit, or Delete Geofences",
  "body": "Repeat the steps to add more geofences in your cluster. You can have up to 100 geofences in a cluster. In addition, you can edit or delete a geofence by clicking on the location and clicking the edit or delete icon. You can also edit or delete geofences by selecting them from the list on the left."
}
[/block]
# Use Geofence Events
CleverTap raises two system events every time a device enters or exits a geofence that can be used to run campaigns, analytics, and segmentation:
  * Geocluster Entered
  * Geocluster Exited

For more information, refer to [System Events](https://docs.clevertap.com/docs/events#section-system-events).

# Add Geofence Clusters in a Campaign
Once you have configured your geofence clusters, you can add them to a campaign by performing the following steps:

1. From the dashboard, navigate to *Campaigns*. 
2. Click **+ Campaign**.
3. Select a messaging channel.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5de46d2-2x_Create_a_campaign.png",
        "2x Create a campaign.png",
        1571,
        621,
        "#f7f8fa"
      ],
      "border": true
    }
  ]
}
[/block]
4. Navigate to *Setup* > *Delivery Type*.
5. Select *Live Behavior*. 
6. Click **Done**.
<<CHANGE SCREENSHOT WITH LATEST COPY>>
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/55f5b17-1_delivery_type.png",
        "1 delivery type.png",
        899,
        339,
        "#fafbfd"
      ]
    }
  ]
}
[/block]
7. Under the *Set a goal* section, select *Conversion Tracking*.
8. Select *Geocluster Entered* or *Geocluster Exited* and the funnel conversion time.
9. Click **Done**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d44be6c-2_select_Geocluster_Entered.png",
        "2 select Geocluster Entered.png",
        1325,
        453,
        "#fbfcfd"
      ]
    }
  ]
}
[/block]