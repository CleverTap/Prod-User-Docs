---
title: Export Format
excerpt: ''
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

This document provides information about the file format and the name format of the files exported to different Data-Warehouse partners.

# Event Export

# File Name Format

The example below shows the file name format for event export:

```text
<export request id>-<timestamp of the export run>-<event name>-<yyyymmdd>-<file index>-<database-id>.json
```

* *Export request ID*: Indicates the export request ID generated when you create a request in the CleverTap dashboard.
* *Timestamp of export run*: Indicates the time when the export was run in EPOCH format.
* *Event name*: Indicates the event type included in the file. For example, the *Charged* event. 
* *File index*: Larger data exports are split into several files. We limit file records to 1,000 K event exports per file.
* *Database ID*: Indicates the database ID of the CleverTap from where the file was exported. 
* *File format*: Indicates the file format exported to the S3 bucket. For instance, CSV file format will be as .csv.gzip

## File Data Format

### Event Export Schema

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Sub-Headers
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ts
      </td>

      <td>

      </td>

      <td>
        Indicates the time when the event occurred. [Need to add format] 
      </td>
    </tr>

    <tr>
      <td>
        eventName
      </td>

      <td>

      </td>

      <td>
        Indicates the name of the exported event. 
      </td>
    </tr>

    <tr>
      <td>
        profile
      </td>

      <td>

      </td>

      <td>
        Includes the profile properties of the user who performed the event.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.identity
      </td>

      <td>
        Denotes the identity of the user. We will add the details as per the identity priorities set while creating the export. For more information, refer to [Prioritize User Identity for Exports](https://docs.clevertap.com/docs/event-and-profile-exports#prioritize-user-identity-for-exports).
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.objectId 
      </td>

      <td>
        Denotes the CleverTap ID of the user. This data is not exported by default. to export this information, contact your CSM or raise a support ticket.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.all\_identities 
      </td>

      <td>
        Denotes all the unique identities of the user present on the CleverTap.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.platform 
      </td>

      <td>
        Denotes the platform from which they have raised the event.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.phone
      </td>

      <td>
        Denotes the phone number of the user, if present.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.name 
      </td>

      <td>
        Denotes the name of the user.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.email 
      </td>

      <td>
        Denotes the email address of the user.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        profile.push\_token
      </td>

      <td>
        <li> Indicates the device token.</li>  
        <li> It is present if the user raises an event through the device having a token associated with it.</li>
      </td>
    </tr>

    <tr>
      <td>
        deviceInfo
      </td>

      <td>

      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.make
      </td>

      <td>
        Denotes the make of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.model 
      </td>

      <td>
        Denotes the model of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.appVersion 
      </td>

      <td>
        Denotes the application version of the user device through which the event is raised
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.sdkVersion 
      </td>

      <td>
        Denotes the CleverTap SDK version installed on the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.osVersion 
      </td>

      <td>
        Denotes the OS version of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.browser 
      </td>

      <td>
        Denotes the Browser (for example, Chrome, Firefox, etc.) on the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.dpi 
      </td>

      <td>
        Denotes the DPI of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.dimensions.width  
      </td>

      <td>
        Denotes the width of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.dimensions.height 
      </td>

      <td>
        Denotes the height of the user device through which the event is raised.
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        deviceInfo.dimensions.unit
      </td>

      <td>
        Indicates the unit of measure for user device dimensions through which the event is raised. For example, px (pixels), etc. 
      </td>
    </tr>

    <tr>
      <td>
        controlGroupName
      </td>

      <td>

      </td>

      <td>
        Only present for the **Custom control group**event export. The custom control group will have a name associated with it in the control group name column. If the column does not have any name in it, that entry is for the Campaign/Journey control group
      </td>
    </tr>

    <tr>
      <td>
        eventProps
      </td>

      <td>

      </td>

      <td>
        Indicates the properties of the event raised by the user. For more information, refer to Event Properties.
      </td>
    </tr>

    <tr>
      <td>
        sessionProps
      </td>

      <td>

      </td>

      <td>
        Includes the properties only for *UTM Visited* events.
      </td>
    </tr>
  </tbody>
</Table>

## Event Properties

### Notification Sent

This event is tracked when a message is sent to a user. This event is recorded for Mobile Push, Web Push, App Inbox, Email, SMS, WhatsApp, and Remarketing Channel campaigns. It is available under the *Event* page on the dashboard but not displayed under the user profile.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Keys
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        * \*For Recurring Campaign\*\*:\
          The value is always the CampaignID\_eventtimestamp. This can help you to identify on which day users receive notifications from the campaign.\
          Format = campaignID\_YYYYMMDD\
            
        * \*For Trigger Campaign\*\*:\
          The value is always the Campaign ID\_timestamp. The timestamp is in EPOCH format, representing time in seconds. This can help you to identify when the users received these notifications from the campaign.\
          Format = campaignID\_EpochTS\
            
        * \*For One Time Campaign\*\*:\
          The value is always Campaign ID and is unique since it was sent only once time -\
          Format = campaignID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Contains the type of campaign. For example, Push, Email, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Contains the name of the campaign. For example, Black Friday Sales, New Year Sales, and so on.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Contains the campaign variants created for A/B Testing. For example, Variant A, Variant B, Variant C, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Contains the labels added for the campaign. For example, Diwali Offer, New User Offer, and so on.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Helps uniquely identify the journey in which the campaign is present.
      </td>
    </tr>
  </tbody>
</Table>

### Notification Viewed

This event is tracked when a user views an Email, SMS, In-App notification, App Inbox, Web notification or WhatsApp sent from the CleverTap dashboard.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Keys
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Ignore this field. To get details, refer to **eventProps.Campaign id**
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_animated
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the campaign variants created for A/B Testing.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl
      </td>

      <td>
        Indicates the time to live for the campaign.\
        (check for web channel, whatsapp - if available?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acct\_id
      </td>

      <td>
        Indicates the CleverTap Account ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pid
      </td>

      <td>
        Ignore this field. To get details, refer to **eventProps.Campaign id**
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_rnv
      </td>

      <td>
        If present then the Notification Viewed event will be raised
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pn
      </td>

      <td>
        If present then it indicates that the notification is sent from the CleverTap dashboard 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cid
      </td>

      <td>
        Indicates the channel ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bc
      </td>

      <td>
        Indicates the badge count.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bi
      </td>

      <td>
        Indicates the badge icon. 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dl
      </td>

      <td>
        Indicates if the campaign includes a deep link URL.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acts
      </td>

      <td>
        Indicates the action button payload.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bp
      </td>

      <td>
        Indicates the Image URL included in the notification.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTSource
      </td>

      <td>
        Indicates the mobile phone or desktop on which the user viewed the notification.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTLatitude
      </td>

      <td>
        Indicates the last known latitude captured by CleverTap on launching the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTLongitude
      </td>

      <td>
        Indicates the last known longitude captured by CleverTap on launching the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_c2a
      </td>

      <td>
        <li> Indicates the value of the button clicked by the user. </li>  
        <li> This button can be present for the following campaign types: In-App, App Inbox or Email </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.browser
      </td>

      <td>
        Indicates the browser of the device. 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Session Id
      </td>

      <td>
        Indicates the CleverTap Session ID. 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.User Agent
      </td>

      <td>
        Indicates the agents where the email was viewed. For example, Mozilla Firefox. More reference: [https://docs.clevertap.com/docs/track-email#track-client-names](https://docs.clevertap.com/docs/track-email#track-client-names)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Client Name
      </td>

      <td>
        Indicates the client where the email was viewed. For example, Gmail. Reference: [https://docs.clevertap.com/docs/track-email#track-client-names](https://docs.clevertap.com/docs/track-email#track-client-names)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.skipTCM
      </td>

      <td>
        Available if the message was sent from autoresponders or agent chat. The following are the values for this key: True or False. 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        * \*For Recurring Campaign\*\*:\
          The value is always the CampaignID\_eventtimestamp. This can help you to identify on which day users receive notifications from the campaign.\
          Format = campaignID\_YYYYMMDD\
            
        * \*For Trigger Campaign\*\*:\
          The value is always the Campaign ID\_timestamp. The timestamp is in EPOCH format, representing time in seconds.. This can help you to identify when the users received these notifications from the campaign.\
          Format = campaignID\_EpochTS\
            
        * \*For One Time Campaign\*\*:\
          The value is always Campaign ID and is unique since it was sent only once time -\
          Format = campaignID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Contains the campaign variants created for A/B Testing. For example, Variant A, Variant B, Variant C, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_sdk\_version
      </td>

      <td>
        The app uses the CleverTap SDK version when an event is raised. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_os\_version
      </td>

      <td>
        The operating system of the device. For example, 1.0.0.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_app\_version
      </td>

      <td>
        This is the current version of your application installed on the user's device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_connected\_to\_wifi
      </td>

      <td>
        Status of Wi-Fi on the device when the event is raised. The possible values are True or False.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_carrier
      </td>

      <td>
        The network carrier of the device. For example, AT\&T, Vodafone, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_type
      </td>

      <td>
        The network type of the device. For example, 4G.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_bluetooth\_version
      </td>

      <td>
        The Bluetooth version of the device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_bluetooth\_enabled
      </td>

      <td>
        Indicates if Bluetooth is enabled on the device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.mimeType
      </td>

      <td>
        This property helps you understand the performance of your AMP emails. For more information, refer to [Email Campaigns](doc:ampforemail#amp-for-email-campaign-stats).
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the labels added for the campaign
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Helps uniquely identify the journey in which the campaign is present. This is recorded only if the campaign is part of any journey.
      </td>
    </tr>
  </tbody>
</Table>

### Notification Clicked

This event is tracked only when a user clicks on the message sent via CleverTap.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Keys
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Campaigntype
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the campaign variants created for A/B Testing.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bi
      </td>

      <td>
        Indicates the badge icon.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl
      </td>

      <td>
        Indicates the time to live for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bc
      </td>

      <td>
        Indicates the badge count.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dt
      </td>

      <td>
        Indicates the service used to send the message. For example, Firebase, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        * \*For Recurring Campaign\*\*:\
          The value is always the CampaignID\_eventtimestamp. This can help you to identify on which day users receive notifications from the campaign.\
          Format = campaignID\_YYYYMMDD\
            
        * \*For Trigger Campaign\*\*:\
          The value is always the Campaign ID\_timestamp. The timestamp is in EPOCH format, representing time in seconds.. This can help you to identify when the users received these notifications from the campaign.\
          Format = campaignID\_EpochTS\
            
        * \*For One Time Campaign\*\*:\
          The value is always Campaign ID and is unique since it was sent only once time -\
          Format = campaignID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTSource
      </td>

      <td>
        Indicates the mobile phone or desktop on which the user viewed the notification. (@parth: pls check the explanation.)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cid
      </td>

      <td>
        Indicates the Channel ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_push\_amp
      </td>

      <td>
        <li> Accepts the following boolean value: true or false</li>  
        <li> If true, indicates that the notification is rendered through Push amplification. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pn
      </td>

      <td>
        Indicates that the notification is sent from the CleverTap dashboard when present.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pid
      </td>

      <td>
        Ignore this field. To get details, refer to **eventProps.Campaign id**
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bp
      </td>

      <td>
        Indicates the Image URL included in the notification.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acct\_id
      </td>

      <td>
        Indicates the CleverTap Account ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_rnv
      </td>

      <td>
        <li> A flag that indicates if the Notification Clicked event is raised. </li>  
        <li> If present and not empty, it indicates that the Notification Viewed event was raised. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTAppVersion
      </td>

      <td>
        This is the current version of your application installed on the user's device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ck
      </td>

      <td>
        Indicates whether the collapse key is present or not
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl\_s
      </td>

      <td>
        Indicates the time-to-live for the campaign in seconds.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dl
      </td>

      <td>
        Contains Deep Link URL
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_mutable\_content
      </td>

      <td>
        <li> Captured for iOS push notification. </li>  
        <li> Value is 1 if enabled and 0 if disabled. </li>  
        (@Parth: what does this property indicate?) 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_collapsible
      </td>

      <td>
        Indicates the Collapse key (the actual key which you have provided).
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_st
      </td>

      <td>
        Content of the subtitle added in the push notification
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_nms
      </td>

      <td>
        Indicates the summary text when sending push notifications.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_sound
      </td>

      <td>
        A boolean flag that indicates if the custom sound is to be played when the push notification is rendered on the device
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acts
      </td>

      <td>
        Indicates the action button payload.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_c2a
      </td>

      <td>
        <li> Indicates the value of the button clicked by the user. </li>  
        <li> This button can be present for the following campaign types: In-App, Push, or Mobile In-Box. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_c2a\_short\_url
      </td>

      <td>
        Indicates the short URL on which the customer clicked (available only for SMS and WhatsApp). It is available only if you use CleverTap's Click Tracking feature.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.mimeType
      </td>

      <td>
        Helps understand the performance of the AMP emails. For more information, refer to [Email Campaigns](doc:ampforemail#amp-for-email-campaign-stats).
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the labels added for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Uniquely identifies the journey in which the campaign is present. This is recorded only if the campaign is part of any journey.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Contains the campaign variant name created for A/B Testing. For example, Variant A, Variant B, Variant C, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_slideNo
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_click\_innerText
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_click\_c2a
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acct\_id
      </td>

      <td>
        Indicates the CleverTap Account ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bpds
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_interruption\_level
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_relevance\_score
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

### Push Impression

This event is raised when a push notification is rendered on the device.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.wzrk\_acct\_id
      </td>

      <td>
        Indicates the CleverTap Account ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the campaign variants created for A/B Testing.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cid
      </td>

      <td>
        Indicates the Channel ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pid
      </td>

      <td>
        @Parth: Please provide input.]
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_rnv
      </td>

      <td>
        <li> A flag that indicates if the Notification Viewed event is raised. </li><li> If present and not empty, it indicates that the Notification Viewed event was raised. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl
      </td>

      <td>
        Indicates the time-to-live for the campaign
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bc
      </td>

      <td>
        Indicates the batch count.
      </td>
    </tr>

    <tr>
      <td>
        feventProps.wzrk\_bi
      </td>

      <td>
        Indicates the badge icon. (@parth: Is it batch or badge?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Indicates the Campaign ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pn
      </td>

      <td>
        Indicates that the notification is sent from the CleverTap dashboard when present.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_sound
      </td>

      <td>
        A boolean flag that indicates if the custom sound is to be played when the (@Parth: When is this custom sound played?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acts
      </td>

      <td>
        Indicates the action button payload.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bp
      </td>

      <td>
        Indicates the Image URL included in the notification.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dl
      </td>

      <td>
        Indicates if the campaign includes a deep link (@Parth: Is the explanation correct?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ck
      </td>

      <td>
        Indicates the collapse key.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTAppVersion
      </td>

      <td>
        Indicates the Application version
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTSource
      </td>

      <td>
        Indicates the source of the event i.e., Mobile, Desktop, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTLatitude
      </td>

      <td>
        Indicates the last known latitude captured by CleverTap on launching the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTLongitude
      </td>

      <td>
        Indicates the last known longitude captured by CleverTap on launching the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_push\_amp
      </td>

      <td>
        <li> Accepts the following boolean value: true or false</li>  
        <li> If true, indicates that the notification is rendered through Push Amplification. </li>  
        (@parth: Should we use the push amp term here - we are not using that term anymore.)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dt
      </td>

      <td>
        Indicates the service used to send the message. For example, Firebase, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl\_s
      </td>

      <td>
        Indicates the time to live for the campaign in seconds.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_st
      </td>

      <td>
        Indicates the subtitle 
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the labels added for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Uniquely identifies the journey in which the campaign is present. This is recorded only if the campaign is part of any journey.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_interruption\_level
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_relevance\_score
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cts
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_os\_version
      </td>

      <td>
        The operating system of the device. For example, 1.0.0.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_app\_version
      </td>

      <td>
        This is the current version of your application installed on the user's device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_sdk\_version
      </td>

      <td>
        The CleverTap SDK version used by the app when an event is raised. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_carrier
      </td>

      <td>
        The network carrier of the device. For example, AT\&T, Vodafone, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Contains the campaign variants created for A/B Testing. For example, Variant A, Variant B, Variant C, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Indicates the Campaign ID.
      </td>
    </tr>
  </tbody>
</Table>

### Notification Replied

This event is raised when a user replies to any WhatsApp campaign. (@Parth: this will be applicable for both WhatsApp and SMS - pls comfirm.)

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.CTSource
      </td>

      <td>
        Indicates the WhatsApp provider that received the message
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Indicates the campaign ID and batch ID  of the WhatsApp campaign sent to the user.\
        (@Parth: should we say "campaign ID & Batch ID of the SMS & WhatsApp campaign?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Incoming message type
      </td>

      <td>
        Indicates the type of message received from the user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Incoming text
      </td>

      <td>
        Indicates the incoming text received from the user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Destination WABA number
      </td>

      <td>
        Indicates the Business Phone number that received the incoming message.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Source WABA number
      </td>

      <td>
        Indicates the end user's number that sent the message.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the message variant of the last campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Indicates the message variant of the last campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Incoming media URL
      </td>

      <td>
        Indicates the incoming media URL in case the customers have sent a media.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Lat
      </td>

      <td>
        Indicates the Latitude of the location if the customer has sent a location.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Long
      </td>

      <td>
        Indicates the Longitude of the location if the customer has sent a location.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.QR Paylolad
      </td>

      <td>
        Indicates the custom payload of the quick reply button that the customer clicked.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the label of the last campaign sent to the user
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Message Id
      </td>

      <td>
        Message ID to last campaign sent to the end user (applicable in case of the message via identity API)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Uniquely identifies the journey in which the campaign is present. This is recorded only if the campaign is part of any journey.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Indicates the message variant of the last campaign delivered to the end user.
      </td>
    </tr>
  </tbody>
</Table>

### Notification Delivered

This event is captured when messages get delivered to the user's WhatsApp. (Raised only for WhatsApp).\
(@Parth: Should we modify it to say - raised for both SMS and WhatsApp?)

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        Indicates the WhatsApp provider that was used to send the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Indicates the WhatsApp campaign's ID and batch ID sent to the user.\
        (@Parth: should we say "campaign ID & Batch ID of the SMS & WhatsApp campaign?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the message variant of the campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        events props.skipTCM
      </td>

      <td>
        Available if the message was sent from autoresponders or agent chat. The following are the values for this key: True or False.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.pivot\_index
      </td>

      <td>
        Indicates the message variant of the campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Message Id
      </td>

      <td>
        Message ID of the campaign sent to the end user (applicable in case of the message via identity API)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign sent to the user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the labels added for the campaign sent to the user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Uniquely identifies the journey in which the campaign is present.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Indicates the message variant of the last campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        Indicates the ID of the last campaign sent to the user.
      </td>
    </tr>
  </tbody>
</Table>

### Reply Sent

This event is recorded when an agent (CleverTap user) replies to a message from the end user.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the communication channel where this reply was sent.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        Indicates the ID of the last WhatsApp campaign sent to the user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>
  </tbody>
</Table>

### App Installed

This event is recorded when the user installs the application.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.ct\_app\_version
      </td>

      <td>
        This is the current version of your application installed on the user's device.\
        (@Parth: How is it different from eventProps.CTApp Version mentioned under Push Impression)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CTSource
      </td>

      <td>
        Indicates the source of the event, i.e. Mobile, Desktop, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_latitude
      </td>

      <td>
        Indicates the last known latitude captured by CleverTap on launching the application. (@Parth: How is it different from eventProps.CTLatitude mentioned under Push Impression?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_longitude
      </td>

      <td>
        Indicates the last known longitude captured by CleverTap on launching the application. (@Parth: How is it different from eventProps.CTLongitude mentioned under Push Impression)
      </td>
    </tr>
  </tbody>
</Table>

### App Launched

This event is recorded every time the user launches the application.

| Key                                | Description                                                                                                  |
| :--------------------------------- | :----------------------------------------------------------------------------------------------------------- |
| eventProps.CTNetworkCarrier        | Indicates the network carrier for the user's device.                                                         |
| eventProps.CTSource                | Indicates the source of the event i.e. Mobile, Desktop, etc.                                                 |
| eventProps.CTBluetoothVersion      | Indicates the Bluetooth version of the user's device.                                                        |
| eventProps.CTSDKVersion            | Indicates CleverTap SDK version which is used (@parth: where is the SDK version used?)                       |
| eventProps.CT BluetoothEnabled     | Indicates if Bluetooth is enabled for the user's device.                                                     |
| eventProps.CTOSVersion             | Indicates the OS version of the user's device.                                                               |
| eventProps.CTNetworkType           | Indicates the type of network being used on the user's device. For example, Wifi, 4G, etc.                   |
| eventProps.Model                   | Indicates the model of the user's device.                                                                    |
| eventProps.CT Longitude            | Indicates the last known longitude captured by CleverTap on launching the application.                       |
| eventProps.CT Latitude             | Indicates the last known latitude captured by CleverTap on launching the application.                        |
| eventProps.CTConnectedToWiFi       | Indicates if the user's device is connected to Wifi.                                                         |
| eventProps.CT Session Id           | Indicates the CleverTap session ID. (@parth: need more information here.)                                    |
| eventProps.CTAppVersion            | Indicates the version of the application installed on the user's device. (@parth: check if this is correct.) |
| eventProps.ct\_sdk\_version        | CT SDK version used by the app when an event is raised.                                                      |
| eventProps.ct\_app\_version        | This is the current version of your application installed on the user's device.                              |
| eventProps.ct\_os\_version         | The operating system of the device. For example, 1.0.0.                                                      |
| eventProps.ct\_network\_carrier    | The network carrier of the device. For example, AT\&T, Vodafone, etc.                                        |
| eventProps.ct\_first\_time         |                                                                                                              |
| eventProps.ct\_latitude            | Indicates the last known latitude captured by CleverTap.                                                     |
| eventProps.ct\_longitude           | Indicates the last known longitude captured by CleverTap.                                                    |
| eventProps.ct\_connected\_to\_wifi | Status of Wi-Fi on the device when the event is raised. The possible values are True or False.               |
| eventProps.ct\_network\_type       | The network type of the device. For example, 4G.                                                             |
| eventProps.ct\_bluetooth\_version  | The Bluetooth version of the device.                                                                         |
| eventProps.ct\_bluetooth\_enabled  | Indicates if Bluetooth is enabled on the device.                                                             |

### App Uninstalled

This event is recorded every time the user uninstalls the application.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.clevertapId
      </td>

      <td>
        Indicates the unique device identifier. This is assigned to all the users when they launch the app for the first time. (@parth: Pls confirm if this is correct.)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.token
      </td>

      <td>
        Indicates the Device token of the event
      </td>
    </tr>

    <tr>
      <td>
        eventProps.source
      </td>

      <td>
        Indicates the source of the event, i.e., FCM or API
      </td>
    </tr>
  </tbody>
</Table>

### Webhook Delivered

This event is recorded when a Webhook campaign is delivered successfully.

| Key                                           | Description                                                                                                                                                                                                                                                                                                                                                            |
| :-------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| eventProps.ContentName                        |                                                                                                                                                                                                                                                                                                                                                                        |
| eventProps.CT Source                          | <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul> |
| eventProps.ct\_app\_version                   | This is the current version of your application installed on the user's device.                                                                                                                                                                                                                                                                                        |
| eventProps.ct\_latitude                       | Indicates the latitude of the user.                                                                                                                                                                                                                                                                                                                                    |
| eventProps.all\_identities                    | Indicates all Identity of the user                                                                                                                                                                                                                                                                                                                                     |
| eventProps.ct\_longitude                      | Indicates the longitude of the user.                                                                                                                                                                                                                                                                                                                                   |
| eventProps.session\_props \\| session\_source |                                                                                                                                                                                                                                                                                                                                                                        |
| eventProps.Campaign Id                        | Uniquely identifies the campaign.                                                                                                                                                                                                                                                                                                                                      |
| eventProps.mp\_processing\_time\_ms           | Indicates the time in which we get a response from the customer API.                                                                                                                                                                                                                                                                                                   |
| eventProps.ts                                 | Indicates the timestamp of the event.                                                                                                                                                                                                                                                                                                                                  |

### Channel Unsubscribed

This event is raised when a user unsubscribes from any group in an email.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Indicates the campaign variants created for A/B Testing.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Resubscribed
      </td>

      <td>
        Yes/No
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Group
      </td>

      <td>
        Subscription Group
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        Helps uniquely identify the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Subscription Type
      </td>

      <td>
        Indicates the type of Subscription
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Identity
      </td>

      <td>
        Indicates the Unique Identity of the User
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Reason
      </td>

      <td>
        Indicates the reason for Unsubscribing/Resubscribing
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        @Parth, How is it different from eventProps.Type ?\
        (Amrita to take description from page history)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Clevertap ID
      </td>

      <td>
        CleverTap account ID. [@Parth: Please confirm.]
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT SDK Version
      </td>

      <td>
        The CleverTap SDK version. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT App Version
      </td>

      <td>
        This is the current version of your application installed on the user's device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.mimeType
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.Type
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

### Custom Control Group

This event is raised when a campaign is activated with a Control group.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Indicates the Campaign ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pivot
      </td>

      <td>
        Indicates the campaign variants created for A/B Testing.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign name
      </td>

      <td>
        Indicates the name of the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign labels
      </td>

      <td>
        Indicates the labels added for the campaign.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Journey id
      </td>

      <td>
        Helps uniquely identify the journey in which the campaign is present.
      </td>
    </tr>
  </tbody>
</Table>

### System Control Group

This event is raised when a campaign is activated with a Control group.

| Key                      | Description                                                                      |
| :----------------------- | :------------------------------------------------------------------------------- |
| eventProps.CT Source     | Indicates the source of the event, i.e., Mobile, Desktop, etc.                   |
| eventProps.wzrk\_id      | Indicates the Campaign ID.                                                       |
| eventProps.wzrk\_pivot   | Indicates the campaign variants created for A/B Testing.                         |
| eventProps.Campaign id   | Indicates the CleverTap campaign ID (@Parth: How is it different from wzrk\_id?) |
| eventProps.Campaign name | Indicates the name of the campaign.                                              |
| eventProps.Campaign type | Indicates the type of campaign - Push, Email, etc.                               |
| eventProps.Journey id    | Helps uniquely identify the journey in which the campaign is present.            |

### Custom & Journey Control Group (Journeys)

This event is raised when a custom control group user or journey control group user qualifies for the journey.

| Key                     | Description                                                                                   |
| :---------------------- | :-------------------------------------------------------------------------------------------- |
| eventProps.Journey id   | Helps uniquely identify the journey in which the campaign is present.                         |
| eventProps.Journey name | Indicates Unique Journey identifier (@Parth, how is it different from eventProps.Journey id?) |

### System Control Group (Journeys)

This event is raised when a system control group user qualifies for the Journey.

| Key                     | Description                                                                                   |
| :---------------------- | :-------------------------------------------------------------------------------------------- |
| eventProps.Journey id   | Helps uniquely identify the journey in which the campaign is present.                         |
| eventProps.Journey name | Indicates Unique Journey identifier (@Parth, how is it different from eventProps.Journey id?) |

### Geocluster Entered

This event is raised when a user enters a Geo Cluster.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.ct\_connected\_to\_wifi
      </td>

      <td>
        Status of Wifi on the device when the event is raised. The possible values are True or False.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_source
      </td>

      <td>
        Source is mobile or web
      </td>
    </tr>

    <tr>
      <td>
        eventProps.network\_carrier
      </td>

      <td>
        Network Carrier for the device
      </td>
    </tr>

    <tr>
      <td>
        eventProps.longitude
      </td>

      <td>
        Longitude
      </td>
    </tr>

    <tr>
      <td>
        eventProps.latitude
      </td>

      <td>
        Latitude
      </td>
    </tr>

    <tr>
      <td>
        eventProps.os\_version
      </td>

      <td>
        [@Parth: What's the difference between os_version and ct_os_version]
      </td>
    </tr>

    <tr>
      <td>
        eventProps.application\_version
      </td>

      <td>
        Version of App
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_sdk\_version
      </td>

      <td>
        CT SDK version used by the app when an event is raised
      </td>
    </tr>

    <tr>
      <td>
        eventProps.geofence\_id
      </td>

      <td>
        CT Geogence ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.cluster\_name
      </td>

      <td>
        CT Geofence Cluster Name
      </td>
    </tr>

    <tr>
      <td>
        eventProps.cluster\_id
      </td>

      <td>
        CT Geofence Cluster ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_type
      </td>

      <td>
        The network type of the device. For example, 4G.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_os\_version
      </td>

      <td>
        The operating system of the device. For example, 1.0.0.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_app\_version
      </td>

      <td>
        Indicates the version of the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_latitude
      </td>

      <td>
        Indicates the last known latitude captured by CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_longitude
      </td>

      <td>
        Indicates the last known longitude captured by CleverTap.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_carrier
      </td>

      <td>
        The network carrier of the device. For example, AT\&T, Vodafone, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Geofence id
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.Cluster name
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

### GeoCluster Exited

This event is raised when a user enters a Geo Cluster.

| Key                                | Description                                                                                   |
| :--------------------------------- | :-------------------------------------------------------------------------------------------- |
| eventProps.ct\_source              | Source is mobile or web                                                                       |
| eventProps.network\_carrier        | Network Carrier for the device                                                                |
| eventProps.longitude               | Longitude                                                                                     |
| eventProps.latitude                | Latitude                                                                                      |
| eventProps.os\_version             | OS Version of the device                                                                      |
| eventProps.application\_version    | Version of App                                                                                |
| eventProps.ct\_sdk\_version        | CT SDK version used by the app when an event is raised.                                       |
| eventProps.geofence\_id            | CT Geogence ID                                                                                |
| eventProps.cluster\_name           | CT Geofence Cluster Name                                                                      |
| eventProps.cluster\_id             | CT Geofence Cluster ID                                                                        |
| eventProps.ct\_connected\_to\_wifi | Status of Wifi on the device when the event is raised. The possible values are True or False. |

### AB Experiment Stopped

This event is raised when the A/B experiment is stopped.

| Key                            | Description                   |
| :----------------------------- | :---------------------------- |
| eventProps.ct\_source          | Source is mobile or web       |
| eventProps.stickiness          | Yes/No                        |
| eventProps.mutually\_exclusive | Should show only 1 experiment |
| eventProps.variant             | Variant of Experiment         |
| eventProps.variant\_id         | Unique Variant ID             |
| eventProps.version             | Version of Experiment         |
| eventProps.experiment\_id      | Experiment ID                 |

### AB Experiment Rolled Out

This event is raised when the A/B experiment is sent to users.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Variant of Experiment
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant Id
      </td>

      <td>
        Unique Variant ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Version
      </td>

      <td>
        Version of Experiment
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Experiment Id
      </td>

      <td>
        Experiment ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Stickiness
      </td>

      <td>
        Yes/No
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Mutually Exclusive
      </td>

      <td>
        Should show only 1 experiment
      </td>
    </tr>
  </tbody>
</Table>

### AB Experiment Disqualified

This event is raised when a user is disqualified from the A/B experiment.

### AB Experiment Rendered

This event is raised when the A/B experiment is rendered to a user.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Variant of Experiment
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant Id
      </td>

      <td>
        Unique Variant ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Version
      </td>

      <td>
        Version of Experiment
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Experiment Id
      </td>

      <td>
        Experiment ID
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Stickiness
      </td>

      <td>
        Yes/No 

        [@Parth: Need inputs.]
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Mutually Exclusive
      </td>

      <td>
        Should show only 1 experiment
      </td>
    </tr>
  </tbody>
</Table>

### State Transitioned

This event is recorded for lifecycle optimizer when a user transitions from one stage to another.

| Key                    | Description             |
| :--------------------- | :---------------------- |
| eventProps.Destination | Destination Value       |
| eventProps.Type        | Type Value of Lifecycle |
| eventProps.Model       | Model Value             |
| eventProps.Source      | Value of Source         |

### Session Concluded

This event is raised when a user session is completed.

| Key                       | Description                        |
| :------------------------ | :--------------------------------- |
| eventProps.Session Length | Time for which user was using apps |
| eventProps.Session Id     | Unique CT Session identifier       |

### UTM Visited

This event is tracked when a user clicks on a link from a marketing campaign that has a UTM parameter defined on it.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.Campaign id
      </td>

      <td>
        Unique campaign ID for campaigns
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_latitude
      </td>

      <td>
        Indicates the last known latitude captured by CleverTap
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_longitude
      </td>

      <td>
        Longitude
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_app\_version
      </td>

      <td>
        Indicates the version of the application.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Install
      </td>

      <td>
        Y or N
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Variant
      </td>

      <td>
        Indicates the message variant of the last campaign delivered to the end user.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.action
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.browser
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_slideNo
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_c2a
      </td>

      <td>
        <li> Indicates the value of the button clicked by the user. </li>  
        <li> This button can be present for the following campaign types: In-App, Push, or Mobile In-Box. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_click\_innerText
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_click\_c2a
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_acct\_id
      </td>

      <td>
        Indicates the CleverTap Account ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cid
      </td>

      <td>
        Indicates the Channel ID.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pid
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_rnv
      </td>

      <td>
        <li> A flag that indicates if the Notification Clicked event is raised. </li>  
        <li> If present and not empty, it indicates that the Notification Viewed event was raised. </li>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ttl
      </td>

      <td>
        Indicates the time-to-live for the campaign
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_push\_amp
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bc
      </td>

      <td>
        Indicates the batch count.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bi
      </td>

      <td>
        Indicates the badge icon. (@parth: Is it batch or badge?)
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_ck
      </td>

      <td>
        Indicates the collapse key.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_dt
      </td>

      <td>
        Indicates the service used to send the message. For example, Firebase, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pn
      </td>

      <td>
        Indicates that the notification is sent from the CleverTap dashboard when present.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_sdk\_version
      </td>

      <td>
        The CleverTap SDK version used by the app when an event is raised. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_os\_version
      </td>

      <td>
        The operating system of the device. For example, 1.0.0.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_connected\_to\_wifi
      </td>

      <td>
        Status of WiFi on the device when the event is raised. The possible values are True or False.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_carrier
      </td>

      <td>
        The network carrier of the device. For example, AT\&T, Vodafone, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_bluetooth\_version
      </td>

      <td>
        The Bluetooth version of the device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_bluetooth\_enabled
      </td>

      <td>
        Indicates if Bluetooth is enabled on the device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.ct\_network\_type
      </td>

      <td>
        The network type of the device. For example, 4G.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_cts
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_bpds
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_interruption\_level
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_relevance\_score
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_c2a\_short\_url
      </td>

      <td>
        Indicates the short URL on which the customer clicked (available only for SMS and WhatsApp). It is available only if you use CleverTap's Click Tracking feature.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_pn\_h
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT App Version
      </td>

      <td>
        This is the current version of your application installed on the user device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.button\_id
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.install\_time
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.provider
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.wzrk\_id
      </td>

      <td>
        Unique campaign ID for campaigns.
      </td>
    </tr>

    <tr>
      <td>
        sessionProps.utm\_campaign
      </td>

      <td>
        Campaign name
      </td>
    </tr>

    <tr>
      <td>
        sessionProps.utm\_medium
      </td>

      <td>
        Medium such as email, banner, etc
      </td>
    </tr>

    <tr>
      <td>
        sessionProps.utm\_source
      </td>

      <td>
        Origination source
      </td>
    </tr>
  </tbody>
</Table>

### Identity Set

| Key                        | Description |
| :------------------------- | :---------- |
| eventProps.ID              |             |
| eventProps.Type            |             |
| eventProps.Dropped History |             |
| eventProps.Source          |             |

### Identity Error

| Key               | Description |
| :---------------- | :---------- |
| eventProps.ID     |             |
| eventProps.Source |             |

### Identity Reset

| Key               | Description |
| :---------------- | :---------- |
| eventProps.ID     |             |
| eventProps.User   |             |
| eventProps.Source |             |

### App Version Changed

| Key                            | Description                                                                                                                                                                                                                                                                                                                                                            |
| :----------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| eventProps.CT App Version      | This is the current version of your application installed on the user's device.                                                                                                                                                                                                                                                                                        |
| eventProps.CT App Version Prev |                                                                                                                                                                                                                                                                                                                                                                        |
| eventProps.CT Source           | <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul> |
| eventProps.CT Latitude         | Indicates the last known latitude captured by CleverTap on launching the application.                                                                                                                                                                                                                                                                                  |
| eventProps.CT Longitude        | Indicates the last known longitude captured by CleverTap on launching the application.                                                                                                                                                                                                                                                                                 |

### Reachable By

| Key              | Description |
| :--------------- | :---------- |
| eventProps.value |             |
| eventProps.type  |             |
| eventProps.state |             |

### Push Unregistered

| Key                    | Description |
| :--------------------- | :---------- |
| eventProps.Token Type  |             |
| eventProps.Token Value |             |

### Partner Sync

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Partner Name
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.Partner Segment Name
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.Partner Segment ID
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>
        eventProps.Action
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

### Channel Subscribed

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Key
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        eventProps.CT Source
      </td>

      <td>
        <p>The source of the event.</p><p>For example, the event may originate from a Mobile SDK or an API.</p><p>All possible values:</p><ul><li>Mobile (Mobile SDK)</li><li>MobileWeb (Web SDK)</li><li>Web (Web SDK)</li><li>API</li><li>segment</li><li>appsflyer</li><li>apsalar</li><li>branch</li><li>tune</li><li>System (for events generated by CleverTap)</li></ul>
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT App Version
      </td>

      <td>
        This is the current version of your application installed on the user's device.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Campaign type
      </td>

      <td>
        Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.CT SDK Version
      </td>

      <td>
        The CleverTap SDK version. For example, 30501.
      </td>
    </tr>

    <tr>
      <td>
        eventProps.Clevertap ID
      </td>

      <td>
        CleverTap account ID 

        [@Parth: Could you confirm if this is correct?]
      </td>
    </tr>
  </tbody>
</Table>

### Notification Sent

| Key                      | Description                                                                       |
| :----------------------- | :-------------------------------------------------------------------------------- |
| eventProps.Campaign id   | Unique campaign ID for the campaign.                                              |
| eventProps.Campaign type | Indicates the CleverTap campaign type. For example, Push, Web Push, Webhook, etc. |
| eventProps.Labels        |                                                                                   |
| eventPropsVariant        | Indicates the message variant of the last campaign delivered to the end user.     |

# User Profile Export

## File Name Format

```text
<export request id>-<timestamp of the export run>-<event name>-<yyyymmdd>-<file index>-<database-id>.json
```

* **File Name Format for User Profile Export**:\
   The example below shows the file name format for user profile export:
  * *Account ID*: Indicates the integer value for your CleverTap project ID. 
  * *Request ID*: Indicates the export request ID generated when you create a request in the CleverTap dashboard.
  * *Timestamp of export run*: Indicates when the export was run.
  * *Database ID*: Indicates the database ID of the CleverTap from where the file was exported. 
  * *File format*: Indicates the file format exported to the S3 bucket.

```text
<account id>-<request id>-<timestamp of the export run>-<database-id>-<file format>.gz
```

## File Data Format

Files are split by event names for event exports, and each file will have all event data for the given period for the event.

### JSON

The first line of the file contains the event name. After the first line, each line in JSON describes the timestamp, object ID, and event properties.

```json
{
	"profile": {
		"identity": "dqsndckfk234"
	},
	"ts": 20171109000015,
	"eventProps": {
		"ct_connected_to_wifi": "false",
		"ct_bluetooth_version": "ble",
		"ct_bluetooth_enabled": "false",
		"ct_sdk_version": 30107,
		"ct_latitude": -6.1975594,
		"ct_longitude": 106.52913,
		"ct_os_version": "5.1.1",
		"ct_app_version": "2.30.1",
		"ct_network_carrier": "3",
		"ct_network_type": "4G"
	}
}
```

### CSV

CSV files are comma-delimited and have each event in separate rows.

<Image title="Sample CSV File" alt={2032} align="center" border={true} src="https://files.readme.io/aa71f9f-Screenshot_2020-02-28_at_12.53.22_PM.png">
  Sample CSV File
</Image>

### XML

XML has the timeStamp, eventName, followed by eventProperties.

```typescript
<Event>
    <ts>20200220130735</ts>
    <eventName>Export Custom Event</eventName>
    <profile>
        <all_identities>exportProfile+81@clevertap.com</all_identities>
        <platform>Web</platform>
        <email>exportProfile+81@clevertap.com</email>
    </profile>
    <deviceInfo>
        <browser>Others</browser>
    </deviceInfo>
    <eventProps>
        <entry>
            <key>CT Source</key>
            <value>API</value>
        </entry>
        <entry>
            <key>Category</key>
            <value>Mens Watch</value>
        </entry>
        <entry>
            <key>Product name</key>
            <value>Casio Chronograph Watch</value>
        </entry>
        <entry>
            <key>Price</key>
            <value>59.99</value>
        </entry>
        <entry>
            <key>Currency</key>
            <value>USD</value>
        </entry>
    </eventProps>
</Event>
```

### Parquet

Parquet has a timestamp, eventName, and eventProperties for each event. 

> 📘 Parquet File Format
>
> Parquet is an open-source file format for Hadoop. Parquet stores nested data structures in a flat columnar format.
