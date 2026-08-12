---
title: Create Segments
excerpt: Learn how to create Segment in CleverTap.
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

Creating segments in CleverTap empowers you to target and engage specific groups of users precisely based on various criteria. This flexibility enables you to design segments based on past behavior and live user interaction with the app. The steps to create Segments vary based on the type of segment you want to create.

# Create Past Behavior Segments

Consider the example of creating an action-based segment where users qualify if they purchased a particular product at least once in the past 30 days.

To create the above example segment, perform the following steps:

1. Navigate to _Segments_ > _Segments_ from the dashboard.
2. Click **+Segment**.
3. Select the _Past Behavior_ segment type.
4. Click **Add a rule group to start building your query**.
5. Select the _Event (Did)_ rule from the _User Behavior_ option.
6. Select the _Charged_ event where the count is one and then click **Refresh Data**.


<Image src="https://files.readme.io/002d2c9-Create_Past_Behavior_Segment.gif" alt="Create Past Behavior Segment" align="center" border={true} />


The qualified segment of users for the defined rule is calculated.


<Image src="https://files.readme.io/a842acb-Reachability_Stats.png" alt="View Reachability of Qualified Users" align="center" border={true} />


7. Click **Save Segment**.
8. Enter the _Segment name_ and click **Save**.


<Image src="https://files.readme.io/1379c79-Save_Past_Behavior_Segment.gif" alt="Save Segment" align="center" border={true} />


Your new segment, _Charged Users_ , can now be seen in the main section on the _Segments_ page.

To know more about creating more complex rules, refer to the [Segmentation Rules](https://docs.clevertap.com/docs/segmentation-rules).

# Create Live User Segments

Consider the example of creating an _Inaction in Time Frame_ segment for which users will qualify in real-time as soon as they add a product to the cart but do not purchase it within 10 minutes.

<Callout icon="📘" theme="info">
  ### Golden Window for Mobile Transactions

  The golden window within which most users transact on our iOS and Android app platforms is within 10 minutes.
</Callout>

To create the above example segment, perform the following steps:

1. Navigate to _Segments_ > _Segments_ from the dashboard.
2. Click **+ Segment**.
3. Select the _Live - Inaction in Time Frame_ segment type.
4. Select the _Added to Cart_ event and set the _DOES NOT DO Charged within_ as **10** _minutes_.
5. You may select the _Filter on past behavior and common properties_ checkbox to apply filters to past actions, inactions, or common user property filters.
6. Click **Save segment**.
7. Enter the _Segment name_ and click **Save**.


<Image src="https://files.readme.io/5e2370b-Create_Live_User_Segment.gif" alt="Create Live - Inaction in Time Frame Segment" align="center" border={true} />


Your new segment, _Added to cart but no charge within 10 minutes_, can now be seen in the main section on the _Segments_ page.

<Callout icon="📘" theme="info">
  ### Segment Naming Best Practices

  Convey the core meaning of the segment while keeping the name brief.
</Callout>

## Create Live Segments with Multiple Triggers

The Multi-Triggers feature lets you segment users based on one or more events. Consider an example of _Live - User Actions_ segments where users qualify as soon as they perform any of the following events:

- App Launched
- UTM Visited
- Notification Clicked

To create a live user segment with multiple triggers:

1. Navigate to _Segments_ > _Segments_ from the dashboard.
2. Click **+ Segment** and select the _Live - User Actions_ segment type.
3. Click **Add Event** and select the events from the list. In this example, select the _App Launched_, _UTM Visited_, and _Notification Clicked_ events.
4. Click **Save segment**.
5. Enter the _Segment name_ and click **Save**.


<Image src="https://files.readme.io/cb4347e-Multitrigger_in_Segments.gif" alt="Multi-Triggers in Segments" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  - You can add a maximum of 10 events for multi-trigger.
  - Multi-Triggers are exclusive to the _Live - User Actions_ segment.
</Callout>

# Create Custom - List Based Segments

You can create a custom list segment by uploading user lists via the dashboard or API.

<Callout icon="📘" theme="info">
  ### File Size

  You can upload a maximum file size of 50 MB from the dashboard. The maximum file size allowed from an API upload is 5GB.
</Callout>

## File Format

Only CSV file format is supported for upload. Also, the list of users for your segment must follow a specific format. You can upload the profiles with identity type as _CleverTap ID_ (g) or _GUID_ and _identity_ (i).

The format of the CSV file is as follows:

| Type | Identity                                        |
| :--- | :---------------------------------------------- |
| g    | a1e2723cba7c4518bea8ef95b036ac83                |
| i    | [user@clevertap.com](mailto:user@clevertap.com) |

The Type and Identity columns are mandatory for successfully uploading a custom list segment in the above format.

The **Type** field specifies the type of identity used for each segment user. This can be either `g` for CleverTap ID or GUID for a third-party identifier, and `i` for identity.

The **Identity** field contains the sample value of the identifier for each user, which can be a string or a number, depending on the identifier type. For example, if using the `i` type, the identity field might contain email addresses, phone numbers, or your custom identifier for each user.

<Callout icon="🚧" theme="warn">
  ### User Profiles

  A Custom - List Based segment can only contain user profiles that are on the CleverTap dashboard. It does not create any new profiles or update the attributes for the existing user profiles.
</Callout>

## Create from Dashboard

1. Navigate to _Segments_ > _Segments_.
2. Click **+ Segment**.
3. Click **Custom - List Based**.


<Image src="https://files.readme.io/30191c1-Custom_-_List_Based_Segment.png" alt="2836" align="center" border={true} />


The **Create Segments** page is displayed.

4. Enter the _Segment name_.
5. Click **Browse** and select the CSV file to be uploaded.


<Image src="https://files.readme.io/b04d46e-Create_New.png" alt="1714" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Sample custom list CSV

  It is recommended to download the Sample custom list CSV file and format your custom list information as per the downloaded sample file.
</Callout>

6. Click **Save Segment**.

You will receive an email with the details after the file is processed.


<Image src="https://files.readme.io/0cd90b7-View_Segment_Details.png" alt="1109" align="center" border={true} />


The uploaded segment is now available for use.

## Create from API

You can create a custom list segment from API. For detailed steps, refer to [Custom list API](https://developer.clevertap.com/docs/custom-list-endpoints).

## Replace via Dashboard

You can replace a custom list segment from the dashboard. However, if the segment is currently in use for engagement through a Campaign or Journey, then you must stop the Campaign or Journey before replacing the segment.

To replace a segment:

1. Click the ellipsis ![](https://files.readme.io/b15093f-ellipses_icon.png) icon from the segment you want to replace.
2. Click **Replace**.


<Image src="https://files.readme.io/7550fa3-Replace_Custom_List.png" alt="1222" align="center" border={true} />


2. Click the Re-upload user list and select the CSV file.
3. Upload the CSV file.
4. Name the file and save it. Wait for it to be processed.
5. You will receive an email with the details after the file is processed.

The uploaded segment is now available for use.

## Troubleshoot Upload

### File size exceeds 50 MB

This error occurs when the file size exceeds 50 MB.


<Image src="https://files.readme.io/ad225fc-File_size_exceeds.png" alt="1552" align="center" border={true} />


<Callout icon="📘" theme="info">
  ### Note

  If the file size is more than 50 MB, it can be uploaded via [Custom list API](https://developer.clevertap.com/docs/custom-list-endpoints).
</Callout>

### Error uploading the file

You can see the following message when trying to upload the file.


<Image src="https://files.readme.io/e6fcff0-File_Upload_Error.png" alt="1107" align="center" border={true} />


If the file is not uploaded correctly, you can upload it again.

| Segment issue         | Resolution                                                                                                                                                                                                                            |
| :-------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| File upload failed    | The segment could not be created from the uploaded file. Fix the errors and re-upload the file.                                                                                                                                       |
| File re-upload failed | The segment could not be refreshed with the latest file. The segment will be available with the last successful update. Refer to the [View Segment Details](doc:create-segments#view-segment-details) page for the last updated file. |

<Callout icon="📘" theme="info">
  ### Segment processing

  The custom list segment is available for use only after the process of creating or updating is complete.
</Callout>

## View Segment Details

The segment details can be viewed from the Segment dashboard. The segment details page shows all the available information for the segment, such as:

- _Segment Trend_: If the users have increased or decreased over time.
- _Campaigns and Journeys_: The number of campaigns and Journeys currently using the custom list segment.
- _Segment size and reachability_: The total number of users in the segment and their reachability across various engagement channels.
- _Sample Users_: These are samples from your list. You can open any of them to check their details.

<Callout icon="📘" theme="info">
  ### Tip

  Click the ![](https://files.readme.io/8967517-Download_Segment_Icon.png) download icon to download all the users in your segment.
</Callout>


<Image src="https://files.readme.io/81840d5-Segments_Custom_lists_report.png" alt="1193" align="center" border={true} />


# Use Custom List Segment

When creating a campaign, you can use the custom list segment from the _Who_ section. All the custom list segments are listed under the WHO section of the _Campaigns_ page.


<Image src="https://files.readme.io/1742312-Target_Custom_List_Segment.png" alt="2744" align="center" border={true} />


# FAQs

This section provides the frequently asked questions and answers:

### Why do I see an increase in errors after migrating to the enhanced segment builder

After migrating to the enhanced segment builder, you may notice an increase in errors. This is due to a fundamental change in how user properties are evaluated.

Previously, filters in the _Who_ section were evaluated during campaign user qualification. With the enhanced Segment Builder, this evaluation now happens during campaign dispatch. Here is how it works:

Consider an example in which a campaign is triggered by user action and includes filters such as region = India or gender = M.

- **During the qualification phase**, all user profiles that perform the specified event qualify for the campaign, regardless of user property.
- **During the dispatching phase**:
  - Profiles without tokens are marked as unreachable, as their User Properties cannot be evaluated.
  - Profiles with tokens are evaluated:
    - Those matching the filters (for example, Region = India and Gender = M) receive the campaign notification.
    - Those that do not match the filters are silently dropped from the campaign.

While silently dropped profiles are excluded from the campaign, they can still be identified using the [Find People/Segments](doc:find-people) page from the CleverTap dashboard. For more information on user profile properties and events, refer to [User Profiles ](doc:user-profiles)and [Events](doc:events).
