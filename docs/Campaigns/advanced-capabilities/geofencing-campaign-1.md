---
title: Geofencing Campaign
excerpt: Send messages to your users based on their location.
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

A geofence is a virtual geographic area, represented as latitude and longitude pairs combined with a radius, forming a circle in a specific position on a map. CleverTap offers geofencing, a GPS location-based service. Customers can use this service to engage their audience by sending relevant messages to Android and iOS users. Geofences can vary in size, and a cluster can contain up to 100 geofences.

Customers can define geofences around the world from the CleverTap dashboard. Campaigns are delivered in real time to users as they exit or enter geofences or sent as follow-ups hours or days later. CleverTap's location analytics create user data as users enter or exit geofences. This data can be used for retargeting. Geofence-specific analytics can generate insight into activities or locations of interest.

# Create Geofences

To create geofences, perform the following steps:

1. From the CleverTap dashboard, navigate to _Settings_ > _Geofences_.
2. Click **Add Cluster** and select **Create** to create a new geofence cluster.


<Image src="https://files.readme.io/39cc26ea5dfb81d5a14cb6e6ad84e0862f952a5c5f41e88bc0f779fae8295265-Test.png" alt="1403" align="center" border={true} />


3. Select the preferred unit of measure for tracking the location of the geofence clusters. Select the distance in kilometers or miles and click **Continue**.


<Image src="https://files.readme.io/b3ef82f69d8349a1a1d24e8abe9f1965115bfc58471d0533264b7a3fece21f0d-Cluster_measurement_unit.png" alt="1404" align="center" border={true} />


5. Click the _Search for location_ window to select the area you want to display on the map or enter a location in the search bar. A setting pop-up window displays.
6. Enter a _Geofence_ name.
7. Determine the radius that the geofence must cover.
8. Click **Save** on the pop-up window.


<Image src="https://files.readme.io/115bdf5b9958ae4b03eb51755b26e20df561454b91a204b774fa5f117215cc82-Create_Clusters.png" alt="1404" align="center" border={true} />


9. Click **Continue**.
10. Enter a geofence cluster name.
11. Select the start and end time of tracking the users. If you select _Select date and time_, day and time options display beneath the radio buttons where you can choose a future start and end date and time.


<Image src="https://files.readme.io/330580a77552dc29d46fd59bf99d344f92251b7c6813d38a03bb6a8ed13d62ff-Add_Name.png" alt="Schedule Cluster Tracking" align="center" border={true} />


12. When entering the details for the geofence cluster, you can select Do Not Disturb (DND). The DND option prevents triggering an engagement for users who enter the geofence on specified days and times.


<Image src="https://files.readme.io/d9f09cdfb18c337ff15a27f6c4c8513696bf4cb4bee210d0bdbaa416ec8e8195-Do_not_disturb.png" alt="701" align="center" border={true} />


13. Click **Create** or **Save Draft**. You can also edit or delete a geofence by clicking the edit or delete icon.


<Image src="https://files.readme.io/250a3b2537c3fe846e722946e107ac696ab73c56c9af33fc95df50c5e65568ac-Edit.png" alt="Edit or Delete Geofences in a Cluster" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Geofence and Cluster Limits

  You can create up to 100 geofences in each cluster and up to 100 clusters for your app.
</Callout>

# Geofence Operations

You can perform different actions on the geofence clusters from the All Geofences page. The following sections briefly discuss each operation.

## Filter Geofence Clusters

You can quickly search your geofence clusters by applying the required filters. To do so, click **Filters** to filter the list of available geofence clusters based on their states, such as Draft, Scheduled, Active, Paused, and Archived.


<Image src="https://files.readme.io/b77a09b3cd7bb390bef309b4d9e2948cf5f1e81b46ca2b420d3654121e3840af-filter.png" alt="Filters" align="center" border={true} />


## Manage Individual Geofence Clusters

You can perform the following actions on a geofence cluster:

* Edit: Modify the geofence cluster's name, location, or radius.
* Copy: Duplicate an existing cluster to quickly create a similar one.
* Pause: Temporarily deactivate the cluster without deleting it.


<Image src="https://files.readme.io/dda294ff33e44c372036a3cb97d988ae640727edaad5f2d058a8e6c41ec286ad-bulk_action.png" alt="Manage Individual Geofences" align="center" border={true} />


## Bulk Actions

You can perform bulk actions on multiple geofence clusters at once using the toolbar at the top of the All Geofences page. The following bulk actions are available:

* Pause: Temporarily deactivate the selected clusters. They will stop tracking user activity until reactivated.
* Start: Activate selected clusters to begin location tracking.
* Archive: Archive clusters that are no longer needed. They can be reactivated if needed and event tracking will resume.


<Image src="https://files.readme.io/dd43c97c2f6b0ea3da97e9ae67a6ccd9a94968fa1ddb839992a7ff8aa44843ae-bulk.png" alt="Bulk Actions" align="center" border={true} />


## Bulk Upload

You can upload multiple geofences in bulk to new and existing clusters using a CSV or JSON file, instead of manually adding geofences. This feature is useful for scenarios involving a large number of geofences, such as, for franchises, stores, or branches.

To bulk upload geofences, perform the following steps:

1. From the CleverTap dashboard, navigate to _Settings_ > _Geofences_.
2. Click **Add Cluster** and select **Upload** to bulk upload geofences.


<Image src="https://files.readme.io/656965ebe257f63c4f6c7005ba3b5b77e30ed80e4b2a8a4fce59f976129ab275-Test.png" alt="Upload Geofence Cluster" align="center" border={true} />


3. Click **Upload File** or drag and drop the files to start the upload process.


<Image src="https://files.readme.io/0a4300e8b0f295b4a43b9706426b8eafce251769f8ffe49bbc791f16ea6a0ebb-upload_cluster.png" alt="Upload Cluster" align="center" border={true} />


3. To see previously uploaded files, click **View Uploaded Files**. Here you can filter by status: **Processing**, **Imported**, **Partially Imported**, and **Failed**. Once your upload is processed, you will receive an email confirmation.


<Image src="https://files.readme.io/c98268f2e66fd9005f5954d1b2dcb0d6b3aaaa608bd8692e96ba12c6fb1821d9-view_files.png" alt="View Uploaded Files" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  * If a file includes mixed units for a new cluster, the first valid unit is used and others are adjusted accordingly. For existing clusters, their unit is retained.
  * Follow the below general guidelines for bulk uploads:
    * Maximum 100 clusters can be added to the dashboard, including existing clusters. Each geocluster can contain maximum 100 geofences.
    * Maximum upload limit per file is 10,000 geofences.
    * Start and end time must be in YYYYMMDDHHMM format. For example, 202512300445.
    * For unit of measure, use `km` for kilometers and `mi` for miles.
    * Latitude and longitude must be in decimal format without symbols (For example, 19.1114, 72.8677)
    * The supported file formats are CSV and JSON.
    * Maximum file size is 5 MB.
</Callout>

### Error Scenarios & Messages

If the file fails validation, it will not be uploaded. You will receive detailed feedback by email, including an error report. Refer to the following table for common error scenarios:

| Scenario                             | Message                                                                                               |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| Invalid format                       | _Invalid file format. Try again using a CSV or JSON file._                                            |
| File too large                       | _File size limit of 5MB exceeded._                                                                    |
| Duplicate geofence/cluster name      | _Geofence with this name already exists. Try another name._                                           |
| More than 100 geofences in a cluster | _Limit of 100 geofences per cluster exceeded._                                                        |
| Archived cluster                     | _Cannot import to archived cluster._                                                                  |
| Invalid coordinates                  | _Invalid coordinates. Check and rectify._                                                             |
| Invalid name characters              | _Name must start with a letter. Only letters, numbers, and special characters ( ) . -_ are allowed.\_ |

## Geofence Cluster States

Geofence Clusters' states helps track progress and manage campaigns efficiently. Each state has distinct characteristics that determine what actions can be performed. The following table explains the campaign states.

| **State** | **Description**                                                                      |
| --------- | ------------------------------------------------------------------------------------ |
| Draft     | The geofence is created but not yet live.                                            |
| Scheduled | The geofence is set to go live at a future time.                                     |
| Active    | The geofence is currently live and tracking user activity.                           |
| Paused    | The geofence is temporarily paused; can be resumed later.                            |
| Archived  | The geofence is no longer in use. This will pause tracking and stop all engagements. |

<Callout icon="ℹ️" theme="info">
  ### Geofence Events

  CleverTap raises three system events related to geofence interactions. The following events can be used to run campaigns, analytics, and segmentation:

  * **Cluster-level Events**: These events fire when a user enters or exits a geocluster.
    * Geocluster Entered
    * Geocluster Exited
  * **Fence-level Events**: These events fire when a user enters a geofence.
    * Geofence Entered

  Each event includes the following properties:

  * **Cluster ID**
  * **Cluster Name**
  * **Geofence ID**

  The geocluster name displays under event properties if the event has at least one occurrence.

  For more information, refer to [System Events](doc:events#section-system-events).
</Callout>

# Common Use Cases

Learn how to create personalized, location-triggered push campaigns using geofences.

## Scenario

A retail company that sells apparel wants to increase traffic to its physical stores in Mumbai. They have multiple store locations and want to send personalized promotions to customers close to their stores. Using CleverTap's geofence campaign, the retail company can target users who enter the specified radius around their store locations with real-time and location-based messages.

## Steps to Implement a Geofence Campaign

To solve the above business use case, create a push notification campaign adding the geofence cluster. The retail company can target users most likely to visit their physical stores and increase footfall. By using CleverTap's geofence campaign, they can send real-time, location-based messages that are personalized and relevant to the user.

The following are the steps to create a push notification campaign with a geofence cluster for users who enter the geofence:

### 1. Set Up a Geofence Cluster

Set up a geofence cluster around the store locations from the CleverTap dashboard. You can specify the radius and location coordinates of each store location. To set up a geofence cluster, refer to [Create Geofences](https://docs.clevertap.com/docs/geofencing-campaign-1#create-geofences).

### 2. Create a Campaign

After you have set up the geofence cluster and created the segment, you can create a geofence campaign from the CleverTap dashboard. To do so, perform the following steps:

1. From the dashboard, navigate to _Campaigns_.
2. Click **+ Campaign**.
3. Select _Push Notifications_ as a messaging channel.


<Image src="https://files.readme.io/a6b6a126a527a701301b3cce7b888877b179aa47d0d8a0c9fc3721cb76f95565-Select_the_Push_Campaign.png" alt="1571" align="center" border={true} />


4. Select the _Live Behavior_.
5. Click **Done**.


<Image src="https://files.readme.io/409c246-Live_Behavior.png" alt="1096" align="center" border={true} />


6. Select _Conversion Tracking_ under the _Set a goal_ section.
7. Select the conversion event, time, and revenue property.
8. Click **Done**.


<Image src="https://files.readme.io/0d02449-Select_a_Goal.png" alt="Set a Goal" align="center" border={true} />


9. Select the _Geofence Entered_ event with event property as _Geofence ID_ from the _Who_ section of campaign creation.


<Image src="https://files.readme.io/6da2df4a094e849e7138f109d72eda62118fe87426bfe1aa811627d5f505c038-Who_in_campaigns.png" alt="Define - Who" align="center" border={true} />


This ensures that the message is only sent to users close to the store locations.

10. Set up the message content and design. For more information, refer to [Define Message Content](https://docs.clevertap.com/docs/create-message-push#define-message-content)

### 3. Personalize the Message

You can also use CleverTap's personalization features to make the message more relevant to the user. For example, you can include the user's name or previous purchase history in the message. For more information, refer to [Personalize Message](doc:personalize-message-all).

### 4. Schedule the Campaign

Finally, schedule the campaign to be sent at a specific time or based on particular triggers. For example, send a campaign when the user enters the geofence for the first time.

Maximize your [Location-Based Marketing](https://clevertap.com/blog/location-based-marketing-guide/) with best practices and strategies to deliver targeted messages to users based on their physical location.

# FAQs

Here are answers to common questions about using Geofences with Campaigns.

### What happens when I unarchive a draft geofence?

When a draft geofence is unarchived, all clusters will go back to the draft state. Archived clusters can be seen using the _Filters_ dropdown.

### What happens if I pause a geofence and resume it later?

When you pause a geofence, it stops tracking user activity. You can resume event tracking for the geofence cluster anytime by clicking **Resume tracking**. You will also be able to create engagements for the cluster.

### Can I edit a geofence while it's active?

Yes, you can edit the name, radius, or coordinates of a geofence. The changes apply immediately to live tracking and may affect ongoing campaigns. It is recommended to pause the geofence before making major edits to avoid inconsistent behavior.

### Will users receive messages if they enter a geofence during the Do Not Disturb (DND) window?

No. If the user enters the geofence during an active DND window, no engagement is triggered even if the campaign is active.
