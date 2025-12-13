---
title: mParticle
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
TO EDIT LATER

mParticle\
Overview\
CleverTap provides bidirectional support for mParticle Integration. This allows data captured on CleverTap to be pushed to mParticle and also any data captured via mParticle can be pushed to CleverTap.

mParticle to CleverTap data flow\
Once the mParticle embedded kit is integrated, toggle CleverTap on in your mParticle dashboard, and add your CleverTap Region, CleverTap Account ID, CleverTap Passcode and CleverTap Account Token which you can find in the CleverTap Dashboard under Settings.

You can integrate CleverTap using a server-side or embedded-kit. If you are interested in using CleverTap’s push notifications or in-app notifications products, you should use the embedded-kit.

Data management

Embedded-kit setup\
When the embedded-kit is chosen for integration, the mParticle - CleverTap bundled SDK is utilized on the Mobile/Web app. These SDKs are a wrapper on CleverTap SDks which when the embedded-kit methods are called, the corresponding CleverTap SDK methods are called to enable tracking and pushing data to CleverTap from the device itself. 

Supported Events\
The following events are forwarded to CleverTap\
Custom Events\
Commerce Event\
Screen View\
User Attribute Change\
User Identity Change

All of the above Events are raised as Custom Events on CleverTap and if the Kit is used the following events are also tracked as CleverTap system events:\
Application State Transition\
Opt Out\
Push Message\
Push Registration

Supported Device Identity Types\
mParticle forwards the following Device ID types:\
Android ID\
Google Advertising ID (GAID)\
Apple Advertising ID (IDFA)\
Apple Vendor ID (IDFV)

Supported User Identity Types\
mParticle forwards the following User ID types:\
Email\
Facebook ID\
Google ID

CleverTap to mParticle data flow\
CleverTap offers mParticle exports as a direct option which allows any Marketer to push data out of Clevertap to mParticle and then to any destination supported by mParticle.

Step 1\
Connect Segment Account on CleverTap, navigate to Settings > Partners > Exports > mParticle. You will need to add your API key and API Secret to enable CleverTap instances to push to mParticle. More on how to find the key details: mParticle docs

Step 2\
Once the connection is made, you can configure different types of exports into mParticle. The exports on CleverTap are in the form of either Campaigns which can be User Profile info if Past behaviour segment or can be Events + User Profile if Live User Segment is selected.

These Exports are also available as a node in Journeys for more live use cases where only selective data needs to be passed based on Users actions and different segmentation performed as a part of the Journey on CleverTap. This enables Marketers to leverage the full force of CleverTap Segmentation + Engagement in a Journey and then connect it to mParticle to push it out to any other destination accordingly.
