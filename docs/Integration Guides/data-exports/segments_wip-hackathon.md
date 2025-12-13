---
title: Segments_WIP hackathon
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
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

Segment
Overview
CleverTap provides bidirectional support for Segment Integration. This allows data captured on cleverTap to be pushed to Segment and also any data captured via Segment can be pushed to CleverTap.

Segment to CleverTap data flow

Once the Segment library is integrated, toggle CleverTap on in your Segment destinations, and add your CleverTap Account ID and CleverTap Account Token which you can find in the CleverTap Dashboard under Settings.

You can integrate CleverTap using a server-side or mobile destination (iOS or Android). If you are interested in using CleverTap’s push notifications or in-app notifications products, you should use the mobile destinations.

Data management
Mobile Destination 
When the Mobile destination is chosen for integration, the Segment - CleverTap bundled SDK is utilized on the Mobile/Web app. These SDKs are a wrapper on CleverTap SDks which when the Segment methods are called, the corresponding CleverTap SDK methods are called to enable tracking and pushing data to CleverTap from the device itself. 

Methods allowed from mobile SDKs -
Track - This method aligns with the Event method on CleverTap, where user actions are tracked on CleverTap. This method only accepts primitive data types and not nested structures except for transaction tracking under Charged Event.
Identify - This method aligns to onUserLogin method on CleverTap, where it is checked if the previously logged in User is the same or a new User
Alias - This method aligns to Profile.push method on CleverTap, which is used to just update profile properties of the User.

When you identify a user, Segment passes that user’s information to CleverTap with userId as CleverTap’s Identity value. A number of Segment’s special traits map to CleverTap’s standard user profile fields. You’ll pass the key on the left into Segment and we will transform it to the key on the right before sending it to CleverTap.
name maps to Name
birthday maps to DOB
avatar maps to Photo
gender maps to Gender
phone maps to Phone
email maps to Email
All other traits will be sent to CleverTap as custom attributes. Please also note that the default logic will lower case and snake_case any user traits - custom or special - passed to CleverTap.

Server-side destination

All server-side destination requests require either a Segment Anonymous ID or a userId in the payload. The Segment Anonymous ID will be utilized to create the CleverTap ID, to track Events for any unidentified User.

When you track an event using the server-side destination with the name Order Completed using the e-commerce tracking API, Segment will map that event to CleverTap’s Charged event.

Notification handling
If you choose not to bundle the CleverTap Mobile SDK, then you will have to implement your own Push Message processors (and you won’t have access to CleverTap’s In-App feature).
If you decide to implement your own Push Message processors, then you can pass push tokens to CleverTap using the server-side destination. You can do this by sending it inside context.device.token.

CleverTap to Segment data flow
CleverTap offers Segment exports as a direct option which allows any Marketer to push data out of Clevertap to Segment and then to any destination supported by Segment.



Step 1
Connect Segment Account on CleverTap, navigate to Settings > Partners > Exports > Segment. You will need to add your Segment Write key to enable CleverTap instances to push to Segment. More on how to find the write key: https://segment.com/docs/guides/#whats-a-source


[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Step 2
Once the connection is made, you can configure different types of exports into Segment. The exports on CleverTap are in the form of either Campaigns which can be User Profile info if Past behaviour segment or can be Events + User Profile if Live User Segment is selected.


[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
These Exports are also available as a node in Journeys for more live use cases where only selective data needs to be passed based on Users actions and different segmentation performed as a part of the Journey on CleverTap. This enables Marketers to leverage the full force of CleverTap Segmentation + Engagement in a Journey and then connect it to Segment to push it out to any other destination accordingly.