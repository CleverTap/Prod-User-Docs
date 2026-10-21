---
title: Define Entry Segment
excerpt: Learn how to define segment criteria for users to enter a Journey.
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

The Entry Segment block can be considered as a starting point for creating a Journey. It defines the criteria based on which the users enter a Journey. 

<Image alt="Entry Segment Block" align="center" border={true} src="https://files.readme.io/295b20e-Define_Entry_Segment.png">
  Entry Segment Block
</Image>

***

Remember that the selection made in the *Setup* determines the segments available for drag and drop on the Journey canvas: 

| Configuration in Setup                         | Enabled Segments                                                                                                                 |
| :--------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| If you selected *At a specific time* in Setup  | The *Past behavior*, *Journey Trigger*, and *Custom list* segments are enabled.                                                  |
| If you selected *By an event trigger* in Setup | The *Action*, *Inaction*, *Date time*, *Journey Trigger*, *Page visit*, *Referrer entry*, and *Page count* segments are enabled. |

***

To define the Entry Segment for a Journey: 

1. Drag and drop one of the desired segments to the **Entry Segment** block. For example, use the **Past behavior** segment. 

<Image alt="Entry Segment Node for Journeys" align="center" border={true} src="https://files.readme.io/42fe360-Entry_Segment_Node_for_Journey.gif">
  Entry Segment Node for Journeys
</Image>

2. Click the dropped **Entry Segment**. The **Segment** pane appears. The following image displays the **Who** section for a Past Behaviour segment. 

<Image align="center" className="border" width="50% " border={true} src="https://files.readme.io/459e7b4-PBSSegment.jpg" />

3. Enter the segment name. 
4. Under the **Who** section, also called Query Builder, define the criteria as required. All rules defined are combined using the **AND** operator. Users qualify only if they fulfill all the criteria. 
   * From the first list, select the [segment of users](https://docs.clevertap.com/docs/define-entry-segment#find-users-from-the-segment).
   * From the second list, define the [user action criteria](https://docs.clevertap.com/docs/define-entry-segment#filter-by-action). 
   * From the third list, define the [user inaction criteria](https://docs.clevertap.com/docs/define-entry-segment#filter-by-inaction).
   * From the fourth list, define the [user properties criteria](https://docs.clevertap.com/docs/define-entry-segment#filter-by-user-properties).
   * From the fifth list, define the [user interests criteria](https://docs.clevertap.com/docs/define-entry-segment#filter-by-user-interest).
5. If required, select **Do not send users unsubscribed** to exclude the unsubscribed users from the Journey.
6. Click **Continue** and **Save & Close**. 

> 📘 Note
>
> * For more information about Journey entry criteria, refer to the [Define the Journey Entry Criteria](https://docs.clevertap.com/docs/setup-journey#define-the-journey-entry-criteria) section. 
> * For more information about what type of user segments can be used, refer to the [Segments](doc:segments) section.

# Entry Segment Criteria

Under the **Who** section, also called Query Builder, you can define the criteria for the user's entry into a Journey. 

## Find Users from the Segment

When you publish a Journey, users are filtered from the segment you select from this dropdown menu. Based on your Journey type, Past Behaviour, or Live Action, a list of existing segments appears. The below image shows the Past Behaviour Segments list. 

<Image align="center" className="border" width="60% " border={true} src="https://files.readme.io/9a70350-PastBehaaviourSegmentList.jpg" />

## Filter by Action

Using the **Who have done[Operator] of these events** filter in the **Who** section, you can filter users for your Journey based on their actions within a specified time. You may also filter the users depending on whether the event occurred for the first time, for the last time, at a given time of day, or on a specific day of the week. You can define one or more criteria to filter the users.

This set of criteria can be refined using the following two types of operators:

* **All (AND)**: Fetches users who match all the event criteria set in the action filter. For example, a user did *App Launched* event and *Charged* in the last 30 days. 

<Image align="center" className="border" width="60% " border={true} src="https://files.readme.io/ba54ec4-ANDOperator.jpg" />

* **Any (OR)**: Fetches users who fulfill any combination of the event criteria set in the action filter. You can also specify how many times these events occur. For example, a user did *Video Watched* event or *Video Liked* event more than once in the last 30 days. 

<Image align="center" className="border" width="60% " border={true} src="https://files.readme.io/827169a-OROperator.jpg" />

## Filter by Inaction

Using the **Who have not done** filter in the **Who** section, you can filter users for your Journey based on the actions they did not perform within a specified time. You may also filter the user depending on whether the event did not occur for the first time, for the last time, at a given time of day, or on a specific day of the week.

For instance, you can create a Journey that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; that is the golden window within which most users transact on iOS and Android app platforms. By default, it evaluates all the criteria using the **OR** operator. If you specify multiple criteria, the user is qualified if any of the criteria are met.

## Filter by User Properties

Using the **With user properties** filter in the **Who** section, you can filter users for your Journey based on the user's properties such as language, location, gender, phone number, and so on. By default, it combines all the criteria using the **AND** operator.

For example, you can send a push notification to English-speaking female and male users who have a phone number. 

<Image title="Add Multiple User Properties" alt={486} align="center" border={true} src="https://files.readme.io/cbc719c-user_properties_all.png">
  Filter by User Properties
</Image>

The following table explains the various user property types:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Property Type
      </th>

      <th>
        Description
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **User Properties**
      </td>

      <td>
        Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.
      </td>

      <td>
        Customer Type = Platinum
      </td>
    </tr>

    <tr>
      <td>
        **Demographics**
      </td>

      <td>
        Demographics filters include *Age* and *Gender*.
      </td>

      <td>
        Age = 25 to 40 years\
        Gender = Female
      </td>
    </tr>

    <tr>
      <td>
        **Geography**
      </td>

      <td>
        User's location Filters include *Country*, *Region*, and *City*. CleverTap's SDK can automatically detect this from the user's IP address.
      </td>

      <td>
        Country = United States\
        State = California\
        City = San Francisco
      </td>
    </tr>

    <tr>
      <td>
        **Geography Radius**
      </td>

      <td>
        User's exact location. You can select a city and then define the target radius. You can also select multiple cities. You can receive this information using CleverTap's SDK. For more information, refer to the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides.
      </td>

      <td>
        Locations = San Francisco, USA; Paris, France
      </td>
    </tr>

    <tr>
      <td>
        **Reachability**
      </td>

      <td>
        Reachability filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*. These filters help analyze the communication preferences of the users with the help of the following flags:  

        <li> _MSG-push_: Indicates that the user has enabled push notification from the application. Works with the DDND Flag.</li>  <li> _MSG-sms_: When set to true, it indicates that the user has subscribed to SMS notifications. When set to false, it indicates that the user does not want to receive SMS notifications.</li> <li> _MSG-email_: When set to true, it indicates that the user has subscribed to Email notifications. When set to false, it indicates that the user does not want to receive email notifications.</li> <li> _MSG-whatsapp_: When set to true, it indicates that the user has subscribed to WhatsApp notifications. When set to false, it indicates that the user does not want to receive WhatsApp notifications. </li>For more information about each of these flags, refer to communication preferences listed under the [Manually Updating Predefined User Profile Properties](https://developer.clevertap.com/docs/concepts-user-profiles#manually-updating-predefined-user-profile-properties) section.
      </td>

      <td>
        Unsubscribed email = No
      </td>
    </tr>

    <tr>
      <td>
        **App Fields**
      </td>

      <td>
        App fields filters include *App Version*, *Device Make*, *Device Model*, *OS Version*, and CleverTap *SDK Version*. CleverTap's SDK sends this information for each device with your app, meaning a single user can have multiple devices associated with the user profile.
      </td>

      <td>
        OS Version = 10
      </td>
    </tr>
  </tbody>
</Table>

## Filter by User Interest

Using the **With interests** filter in the **Who** section, you can filter users for your Journey based on the user's interests, such as event property, time of the day, and specific day of the week. For more information, refer to the [Psychographic Segmentation](https://docs.clevertap.com/docs/psychographic-segmentation) documentation. By default, it combines all the criteria using the **AND** operator.

The following table explains the various user interest types:

| Property Type       | Description                                                                            | Example                                        |
| :------------------ | :------------------------------------------------------------------------------------- | :--------------------------------------------- |
| **Event Property**  | Select the event property based on which you want to meet the criteria.                | For example, App Launched in the last 30 days. |
| **Time of the day** | Time of day when the event was raised. It contains the start and end times.            | 12 PM - 6 PM                                   |
| **Day of the week** | Day of the week when the event was raised, such as Sunday, Monday, Tuesday, and so on. | Day of the week = Sunday                       |

After defining the entry segment criteria, you can choose how you want to communicate with the users. For more information about Journey paths, refer to the [Define Journey Path](https://docs.clevertap.com/docs/construct-a-journey) section