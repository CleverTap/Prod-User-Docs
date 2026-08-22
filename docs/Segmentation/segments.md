---
title: Segments
excerpt: Understand what are CleverTap Segments and how it works.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

A segment in CleverTap is a group of users that share the same characteristics such as actions performed, actions not performed, or user profile properties based on the defined criteria. For example, a segment can be users who launched the app for the first time in the past 30 days. A more complex segment could be users who live in New York, were acquired via a Facebook campaign in April, transacted three or more times in May and June, and have not transacted in the past two weeks.

The *Segments* page lets you create segments, perform different operations on the segments, and view segment trends over time to understand how a segment behaves in response to your marketing initiatives. The entire CleverTap dashboard can be filtered by any segment you create, including any of our analytics features.

<Image alt="Segment List" align="center" border={true} src="https://files.readme.io/5a2d5bd-Segment_List_Page.gif">
  View List of Created Segments
</Image>

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        <p>

        Field

        </p>
      </th>

      <th>
        <p>

        Description

        </p>
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        <p>Segment details</p>
      </td>

      <td>
        <p>Displays the details like segment name, ID, and email ID of the user who created the segment.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Type</p>
      </td>

      <td>
        Displays the type of segment. The following are the options available:  

        <li>Past Behavior Segment</li><li>Live User Segment</li><li>Custom List Segment</li><li>Partner Segment (where Partner Name can be Amplitude, Mixpanel)</li>
      </td>
    </tr>

    <tr>
      <td>
        <p>Created on</p>
      </td>

      <td>
        <p>Displays the date on which the segment was created.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Updated on</p>
      </td>

      <td>
        <p>Displays the date on which the segment was last updated.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Updated by</p>
      </td>

      <td>
        <p>Displays the email ID of the user who last updated the segment.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Goals</p>
      </td>

      <td>
        <p>Displays the number of goals that are running on the segment.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>IBS Goals</p>
      </td>

      <td>
        <p>Displays the number of goals running with Intent-Based Segment.</p>
      </td>
    </tr>

    <tr>
      <td>
        <p>Engagement</p>
      </td>

      <td>
        <ul><li>Displays the number of active and scheduled customer engagements such as campaigns and journeys that use the segment within <a href="doc:segments#include-and-exclude-segments">include/exclude</a> filters.</li><li>On clicking the number, it displays the list of campaigns and journeys where the segment is being used. You can also click on a particular campaign/journey from this list to view the campaign details.</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        <p>Dependent Segments</p>
      </td>

      <td>
        <ul><li>Displays the number of other segments that include or exclude the selected segment.</li><li>On clicking the number, it displays the list of segments that include/exclude the selected segment. You can also click on a particular segment from this list to view the segment details.</li></ul>
      </td>
    </tr>
  </tbody>
</Table>

# System User Segments

Before creating any segment on the CleverTap dashboard, there are default system segments already present on the dashboard. The following are the system-defined user segments that are available for your use: 

* **All Users**: This user segment contains all the users added to your project.
* **Test Users**: The Test User segment is a default user segment in CleverTap that businesses can use to test their campaigns, journeys, and product experiences before sending them to actual users. This segment allows businesses to experiment with new features, messaging, and campaigns in a safe and controlled environment. Using Test Users helps businesses measure the effectiveness of their ideas before rolling them out to a larger audience. Test Users can be manually created from the CleverTap dashboard or imported through a CSV file and segmented based on various criteria. For more information, refer to [Mark a User Profile as a Test Profile](doc:user-profiles#mark-a-user-profile-as-a-test-profile).

# Types of Segments

There are three types of segments in CleverTap, which are explained in the following sections:

* [Past Behavior Segments](doc:segments#past-behavior-segments)
* [Live User Segments](doc:segments#live-user-segments)
* [Custom List Segments](doc:segments#custom-list-segments)

## Past Behavior Segments

Past behavior segments include users grouped by their actions in the past. You can group users based on a single activity or do complex combinations of actions, inactions, and user properties.

For example, you can create a segment of users from California, who are females, launched the application in the last 30 days, and have not purchased anything from the app.

Past behavior segments can be based on:

* **Actions**: Add users to a segment if they have performed an event. For example, users who added a product to the cart in the past 30 days.
* **Inaction**: Add users to a segment if they have performed an event but did not perform another event within a certain time. For example, users who added a product to the cart but did not purchase in the last 30 days.
* **Actions with user properties**: Add users to a segment if they did or did not perform an event and have a common user property. For example, platinum-level users who added a product to the cart but did not purchase in the last 30 days.

## Live User Segments

While past behavior segments let you evaluate users based on historic criteria, live user segments let you track what is happening in your app right now. When you define a set of behaviors of interest, CleverTap monitors for these behaviors as they happen in your app and immediately adds a user to a segment the moment their behavior matches your action criteria. You can create live user segments for the following:

* **Single action**: Add users to a segment as soon as they perform an event. For example, users who booked a movie ticket from your app.
* **Inaction within time**: Add users to a segment when they perform a particular event but did not perform another event within a certain time. For example, users who have added a product to the cart but did not purchase it within 10 minutes of adding the product to the cart.
* **On a date/time**: Add users to a segment based on date and time property value. For example, users who have an appointment five days from the current date.
* **Page visit**: Add users to a segment as soon as they visit a specific URL on your website. For example, users who have visited the Resources page of your website.
* **Referrer entry**: Add users to a segment based on a referring website or campaign. For example, users who have visited your website via a specific external referrer URL.
* **Page count**: Add users to a segment based on the number of pages visited by them. For example, users who have visited five web pages on your website.

## Custom List Segments

A custom list segment is a list of users from any source, including third-party tools or internal databases. You can deliver personalized messages to these users based on their past or real-time behavior in the app. For more information, refer to [Custom List Segment](doc:custom-list-segments).

# Create Segments

The steps vary based on the type of segment you want to create.

## Create Past Behavior Segments

In this example, we can create an action-based segment where users will qualify if they have applied for a payment offer at least one time in the past 30 days.

To create a past behavior segment, perform the following steps:

1. Navigate to *Segments* > *Segments* from the dashboard.
2. Click **+Segment**.

<Image alt="Create a New Segment" align="center" border={true} src="https://files.readme.io/b89f6b6-Create_Segments.png">
  Create a New Segment
</Image>

3. Select the box *Actions* underneath *Past behavior segments* from the main segment creation page.

<Image alt="Past Behavior Segments" align="center" border={true} src="https://files.readme.io/e12f3df-Past_Behavior_Segments.png">
  Past Behavior Segments
</Image>

4. Define the segment rule as shown below on the segment query page.

<Image title="Set Up Segment Options to Create a Past Behavior Segment" alt={1228} align="center" border={true} src="https://files.readme.io/6f6d353-Segments_PSB_Create_New.png">
  Create a Past Behavior Segment
</Image>

5. Click **Save segment** and name the segment.

You can now view your new segment on the *Segment List* page.

## Create Live User Segments

In this example, we can create an *Inaction within time* segment for which users will qualify in real-time as soon as they add a product to their cart but do not purchase the product within 10 minutes.

> 📘 Golden Window for Mobile Transactions
>
> The golden window within which most users transact on our iOS and Android app platforms is within 10 minutes.

To create a live segment with CleverTap, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Segments*.
2. Click **+ Segment**.
3. Under *Live user segments*, select the *Inaction within time* box.

<Image alt="Create Live User Segment" align="center" border={true} src="https://files.readme.io/21b8b4d-Inaction_Within_Time_Segment.png">
  Live User Segments
</Image>

4. Select the appropriate properties for your live user segment. 

You may choose to select the *Filter on past user behavior and common properties* checkbox to apply past action, inaction, or common user property filters.

<Image title="Set Up Segment Options and Click Save Segment" alt={1403} align="center" border={true} src="https://files.readme.io/033db1c-2_set_up_Live_user_segment_-_Inaction_within_time.png">
  Create a Live User Segment
</Image>

5. Click **Save segment** and name the segment.

> 📘 Segment Naming Best Practices
>
> Convey the core meaning of the segment while keeping the name brief.

You can now see your new segment in the main section as *Added to cart but no charge within 10 minutes*.

# View Segment Details

To view segment details, navigate to *Segments* > *Segments*, search for the segment you are looking for and then click on it. On clicking, segment details are displayed. At the top of the page, you can click *View segment definition* to understand more about the underlying query.

## Past Behavior Segment Details

The top portion of the past behavior user segment report consists of a way to first view the segment definition to understand its underlying query. There are graphs on the left-hand side showing the plot of the number of users who qualified for the segment going forward from the first complete day post-segment creation. The list on the right-hand side shows the sample list of users who qualified for the segment on this day.

<Image title="View Segment Trend Report" alt={1204} align="center" border={true} src="https://files.readme.io/1225063-report.png">
  Segment Trend
</Image>

The past behavior segment statistics are computed daily. However, when these segments are used in campaigns, the users who qualify for these segments are computed in real time. This ensures that users meeting the segment criteria during campaign execution reflect the most recent user activity data.

The lower portion of the past behavior segment report consists of reachability percentages for these users within each messaging channel. The lower-most part of the report shows you how to do more with this segment by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

<Image title="View Segment Size and Reachability Report" alt={1206} align="center" border={true} src="https://files.readme.io/8f416de-lower_report.png">
  Segment Size and Reachability
</Image>

## Live User Segment Details

To view a live user segment report, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Segments*.
2. Search for the segment you are looking for, then click on it.  

At the top of the report, you can click *View segment definition* to understand more about the underlying query. 

The two graphs describe the following:

* The left-hand side shows the plot of the number of users who qualified for the segment going forward from the first complete day after creating the segment.
* The right-hand side shows the real-time rate at which users are qualifying for the segment vs. all user activity on your app/website. 

<Image title="View Live User Segment Reports" alt={1272} align="center" border={true} src="https://files.readme.io/821380f-4a_top_report.png">
  Segment Reports
</Image>

* The lower portion of the live user segment report consists of a list of sample users trickling into your segment in real time on the right-hand side. It also shows the reachability percentages for these users within each messaging channel on the left-hand side.

<Image title="View Segment Size and Reachability" alt={1269} align="center" border={true} src="https://files.readme.io/25d5194-4b_middle_report.png">
  Segment Size and Reachability
</Image>

* The lower-most part of the report shows how to do more with this segment by either filtering relevant analytics dashboard views by this particular user segment or reaching out to this segment via relevant messaging channels.

<Image title="View Sample Users for an Event" alt={1266} align="center" border={true} src="https://files.readme.io/44308a1-4c_bottom_report.png">
  Sample Users
</Image>

# Export Users in a Segment

CleverTap allows you to export the users from any segment in the CSV format. To do so:

1. From the *Segments* page, select the segment from which you may want to export the users. You can also filter out the segments using the *Type* and *Goals* filters. The page opens where all the segment details are displayed.
2. Scroll down and navigate to the *Sample users* section and click **Download**.

<Image alt="Download Sample Users" align="center" border={true} src="https://files.readme.io/00397d4-small-Download_All_Users.png">
  Download Sample Users
</Image>

3. Select the fields you want to export and click **Proceed**.

<Image alt="Select the User Details" align="center" border={true} src="https://files.readme.io/4cab592-small-Include_the_Required_Fields_and_Click_Proceed.png">
  Select the User Details
</Image>

> 📘 Mismatch in Segment Size and Number of Users Exported to CSV File
>
> The number of users displayed under the *Segment size and reachability* section may vary from the number of users exported to the CSV file. This variation is due to the inclusion of blacklisted users under the *Segment size and reachability* section.

# View Analytics Filtered by Segment

Under the *Do more with this segment section,* you have the option to view an analytics report. This is for the chosen segment alone and not your entire user base. 

Real-time dashboard views such as the *Today* dashboard only enable filtering by live user segments. Analytics based on past behavior such as mobile app, revenue, funnels, cohorts, trends, and events will only enable filtering their stats by past behavior segments.

# Create Campaigns for a Chosen Segment

Under the *Do more with this segment* section, under *Engage*, you have the option to create a campaign to message a specific segment.

This immediately takes you to the messaging channel with your segment criteria pre-populated in the target.

<Image title="Click Campaign from the Do More with this Segment option" alt={617} align="center" border={true} src="https://files.readme.io/3c7905e-Segments_Do_More_Campaign.png">
  Create a Campaign from the Segment
</Image>

# Include and Exclude Segments

You can simplify complex queries by including or excluding the existing user segments. Create segments with complex conditions once and then reuse them in different scenarios. 

You can create powerful segmentation that is valid for a variety of scenarios. 

<Image title="Create Segments with Complex Conditions" alt={715} align="center" border={true} src="https://files.readme.io/30d054b-0fd3c96-Find_people_include_exclude_segments.png">
  Include and Exclude Segments
</Image>

## Exclude Segments

There may be instances when you want to exclude some users based on specific criteria. 

For example, you want to offer discounts to all the users who have expressed interest by adding the product to the cart in the past 30 days; however, you want to save your engagement dollars by excluding the power users.\
The parameters for these power users can be the following:

* Users who have charged three times in the past three months, and 
* Users who have launched the app 15 times in the past month, and
* Users who rated a product 10 times in the past year

Now, you can create a segment with these criteria called *Power Users* and use it every time rather than creating a complex query each time. You can save all these parameters in a segment called *Power Users* and exclude them from the discount message. 

The following is a campaign query for an e-commerce app that excludes the *Power Users* segment.

<Image title="Set Up the Options to Exclude a Segment from Campaign" alt={1050} align="center" width="100%" border={true} src="https://files.readme.io/2fb7f6a-exclude_segments_campaign.png">
  Exclude Segments
</Image>

## Include Segments

There may be instances when you want to include some users based on specific criteria. 

Consider the example of a ride-hailing app. You want to nudge your users to enroll for a monthly pass as soon as they open the app. The parameters for these users can be the following:

* The users must be power users, and
* The users have booked more than five rides in a month, and
* They belong to select cities in the country

Now, you can create a segment with these criteria called *Power Users* and using it repeatedly rather than creating a complex query each time. 

The following is a campaign query for a ride-hailing app that includes the *Power Users* segment.

<Image title="Set Up the Options to Include a Segment from Campaign" alt={1067} align="center" width="100%" border={true} src="https://files.readme.io/f9f341a-include_segments_campaign.png">
  Include Segment
</Image>

> 📘 Include and Exclude Segments
>
> * You can include and exclude segments in the same query. It is considered as an *AND* condition between the Included and the Excluded segments.
>   * The include and exclude segments are currently unavailable for bulletins and A/B Testing.
>   * The segments available for including or excluding users can only be of the type [PBS](doc:segments#section-past-behavior-segments) segment.

# Additional AND By Behavior Filters

*AND By behavior* filters provide customers the ability to segment users based on the count, average, or total sum of a property value.

### Count

The count filter allows customers to filter users by event count. The query finds all users who performed a *Charged* event greater than 5 times in the past 30 days. 

<Image title="Select Count to Filter Users by Count" alt={1192} align="center" border={true} src="https://files.readme.io/0678593-2020-11-24_17-51-01_Count.png">
  Count Filter
</Image>

### Average of Property Filter

The *Average of property* filter allows customers to filter users by the average of a chosen event property. The query finds all users who performed a *Charged* event such that the average *Revenue* event property per event is greater than $10. 

The *Average of property* filter allows averaging the value of the selected event property. For example, you can find out the average revenue earned from all users who performed purchases worth $10 or less. Let us assume that 5 users charged for each for $3, $5, $7, $2, and $8. The average value of all the purchases lower than $10 is ($ 3+ 5 +7+2+8)/5 events = 25/5= $5 per event. 

Let us assume that the value for 2 charged events is missing. The charged event values received are $3, $5, and $7. The value of the missing events will be considered as 0. The average of property is now ($3 + 5 +7 +0 +0)/5 events = 15/5 =$3 per event. 

If you want to exclude all the events that do not have event properties, you can select the property that exists a condition in the *Filter by* section.

<Image title="Select Average of Property Filter" alt={1192} align="center" border={true} src="https://files.readme.io/09c3239-2020-11-24_17-52-22_Average_of_property.png">
  Average of Property Filter
</Image>

### Total Sum of Property

The *Total sum of property* filter allows customers to filter users by the sum of a chosen event property. The query finds all users who performed a *Charged* event such that the *Revenue* event property is greater than $10.

<Image title="Select Total Sum of Property Filter" alt={1194} align="center" border={true} src="https://files.readme.io/d973ab4-2020-11-24_17-53-50_Total_sum_of_property.png">
  Total Sum of Property Filter
</Image>

> 📘 Include Users Who Did Not Do the Event
>
> If the query is to find people who performed the charged event fewer than five times, by default, the users who have not performed the charged event are not included in the result set. Only the users who did the charged event but did it fewer than five times are included; however, if the checkbox for *Include users who didn’t do the event* is selected, those users are also included in the result set. The same is true for sum and average.

<Image title="Select the Checkmark to Include Users Who Did Not Do an Event" alt={1187} align="center" border={true} src="https://files.readme.io/db44a26-2020-11-24_17-56-46_Checkbox_message.png">
  Include Users Who Did Not Do an Event
</Image>

# Segment Operations

You can perform different actions on the segments from the *Segments* page. Each of them is explained in the sections to follow

## Search Segment

You can search segments by their Name or ID from the *Segments* page.

<Image title="Search Segment.png" alt={2396} align="center" border={true} src="https://files.readme.io/1251882-Search_Segment.png">
  Search a Segment
</Image>

## Copy Segment Name and ID

To copy segment name and ID:

1. From *Segments* page, hover on the *name* or *ID* of the required segment.
2. Click the ![Copy](https://files.readme.io/0e1c106-Copy_icon.png) icon against the respective segment.

<Image title="Copy Segment name and ID .png" alt={2402} align="center" border={true} src="https://files.readme.io/0455ea5-Copy_Segment_name_and_ID_.png">
  Copy a Segment Name and ID
</Image>

## Engage with Segment

To engage with a segment directly from the *Segments* page:

1. Click ![Ellipses](https://files.readme.io/b15093f-ellipses_icon.png) icon displayed against the segment name under the *Segment details* column and click **Engage**.

<Image title="Engage from Segments page.png" alt={2394} align="center" border={true} src="https://files.readme.io/e73666c-Engage_from_Segments_page.png">
  Engage with a Segment
</Image>

   On clicking, *Messaging Channels* popup displays.

2. Select the *Messaging Channel*. 

<Image title="Messaging Channels popup.png" alt={2376} align="center" border={true} src="https://files.readme.io/6d679c6-Messaging_Channels_popup.png">
  Select a Messaging Channel
</Image>

On selecting the channel, you are navigated to the messaging channel with your segment criteria pre-populated under the *Who* section of the *New Campaign* page.

<Image title="Who section prepopulated.png" alt={2752} align="center" border={true} src="https://files.readme.io/4ebf6d1-Who_section_prepopulated.png">
  Create a Campaign
</Image>

## Clone a Segment

This operation helps to create a new segment from an already existing segment with minor or no modifications to the qualification criteria of the segment. To clone a segment directly from the *Segments* page:

1. Click the ![Ellipses](https://files.readme.io/b15093f-ellipses_icon.png) icon displayed against the segment name under the *Segment details* column and click **Clone**.

<Image title="Clone Segment.png" alt={2394} align="center" border={true} src="https://files.readme.io/d3fba76-Clone_Segment.png">
  Clone a Segment
</Image>

  On clicking, the *Create New* page opens with prepopulated qualification criteria.

2. Make the necessary modifications to the qualification criteria, if required.
3. Click **Save segment**.
4. Enter the *Segment name* and click **Save**.

## Delete

There may be times when you may need to delete unused segments. To delete the unused segments:

1. Click![Ellipses](https://files.readme.io/b15093f-ellipses_icon.png) icon displayed against the segment name under the *Segment details* column and click **Delete**.

<Image title="Delete Segment.png" alt={2394} align="center" border={true} src="https://files.readme.io/c9ab0c2-Delete_Segment.png">
  Delete a Segment
</Image>

On clicking, the *Delete Segment?* popup is displayed on the right side of the screen.

2. Click **Delete** to confirm your action.

> 📘 Note
>
> If your account's total number of segments exceeds 1000, you can view up to 500 segments on a single page and delete a maximum of 500 segments at a time. If the number of segments is less than 1000, you can view up to 50 segments on a single page and delete a maximum of 50 segments at a time.

## Sort

You can sort segments based on the following columns under *Segments* page by clicking the arrows against the respective columns :

* Segment details
* Created on
* Updated On
* Engagement
* Dependent Segments

<Image title="Sort Segments.gif" alt={1188} align="center" border={true} src="https://files.readme.io/ab3b2c8-Sort_Segments.gif">
  Sort Segments
</Image>

## Filter Segments

You can filter out segments based on the following fields by clicking the ![Filter](https://files.readme.io/9cb6680-Filter_icon.png) icon:

* Type: Indicates the type of segment. 
* Goals. Indicates the goals running on the segment.
* Created by: Indicates the name of the user who created the segment.
* Updated by: Indicates the name of the user who last updated the segment.

<Image title="Filter Segments.gif" alt={1196} align="center" border={true} src="https://files.readme.io/2382971-Filter_Segments.gif">
  Filter Segments
</Image>

You can also filter segments based on the date on which the segments were created. To do so, select the date range, available at the top, for which you want to view the segment.

<Image title="Filter Segments by creation date.png" alt={2398} align="center" border={true} src="https://files.readme.io/6a92678-Filter_Segments_by_creation_date.png">
  Filter Segments by Date
</Image>
