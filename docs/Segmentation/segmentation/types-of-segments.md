---
title: Types of Segments
excerpt: Understand the types of Segments available in CleverTap
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

CleverTap's Segmentation feature helps personalize user experiences and optimize your marketing strategies. In this document, you will learn about the types of segments available in CleverTap.

# System User Segments

Before creating any segment on the CleverTap dashboard, default system segments are already present. To view these system segments:

1. Navigate to _Segments_ > _Segments_ from the CleverTap dashboard.
2. Click the ![Filter icon](https://files.readme.io/1d37ff4-Filter_Icon.png) icon.
3. From the _Created By_ dropdown, select _System_.


   <Image src="https://files.readme.io/7614538-System_Segments.png" alt="Filter System User Segments" align="center" border={true} />

4. Click _Apply_, and all the system user segments display.


<Image src="https://files.readme.io/46f2bf6-View_System_Segments.png" alt="View All System User Segments" align="center" border={true} />


The following are the system-defined user segments that are available for your use:

* **First time App Users - Live View**: This system segment includes users who have recently installed and launched the app for the first time. First-time app users are crucial for businesses to understand, as they represent potential new customers or users. Analyzing this segment can help organizations tailor onboarding experiences, send targeted welcome messages, and implement strategies to encourage further engagement.
* **Engaged Users - at least 4 times in the past week**: This segment comprises users who have demonstrated high engagement with the app. To qualify for this segment, users must have interacted with the app at least four times within the past week. Analyzing the behavior of these users provides insights into the features that are popular and help businesses design targeted campaigns or promotions to retain and further engage this user segment.
* **All Users**: This user segment contains all the users added to your project.
* **Test Users**: The Test User segment is a default user segment in CleverTap that businesses can use to test their Campaigns, Journeys, and Product Experiences before sending them to actual users. This segment allows businesses to experiment with new features, messaging, and campaigns in a safe and controlled environment. Using Test Users helps businesses measure the effectiveness of their ideas before rolling them out to a larger audience. Test Users can be manually created from the CleverTap dashboard or imported through a CSV file and segmented based on various criteria. For more information, refer to [Mark a User Profile as a Test Profile](https://developer.clevertap.com/docs/concepts-user-profiles#mark-a-user-profile-as-a-test-profile).

# Types of Segments

The following are the three types of segments that can be created from the CleverTap dashboard:

* [Past Behavior Segments](doc:types-of-segments#past-behavior-segments)
* [Live User Segments](doc:types-of-segments#live-user-segments)
* [Custom List Segments](doc:types-of-segments#custom-list-segments)


<Image src="https://files.readme.io/9adfb41-All_Segments.png" alt="Types of Segments" align="center" border={true} />


## Past Behavior Segments

Past behavior segments include users grouped by their actions in the past. You can group users based on a single activity or do complex combinations of actions, inactions, and user properties. For example, you can create a segment of users from California who are females, have launched the application in the last 30 days, and have not purchased anything from the app.

## Live User Segments

While past behavior segments let you evaluate users based on historical criteria, live user segments allow you to track what is happening in your app right now. When you define a set of behaviors of interest, CleverTap monitors them as they occur in your app and immediately adds a user to a segment when their behavior matches your action criteria. You can create the following types of live user segments:

* **Live - User Actions**: Add users to a segment as soon as they perform an event. For example, users who booked a movie ticket from your app.
* **Live - Inaction in Time Frame**: Add users to a segment when they perform an event, but not another within a specific time. For example, users who have added a product to the cart but did not purchase it within 10 minutes of adding it.
  <Callout icon="📘" theme="info">
    ### Live - Inaction in Time Frame Support in Offline Channels

    Live - Inaction in Time Frame segments now support an _event property_ filter, so you can scope the inaction to a specific property value rather than the event as a whole. For example, users who add shoes to their cart but do not purchase shoes within 10 minutes. This filter is available for Push, SMS, Email, WhatsApp, Web Push, and Webhooks. For details, see [Segmentation Rules](doc:segment-rules#filter-inaction-events-by-event-property).
  </Callout>
* **Live - On a Date or Time**: Add users to a segment based on date and time property value. For example, users who have an appointment five days from today.
* **Live - Page Visit**: Add users to a segment as soon as they visit a specific URL on your website. For example, users who have viewed the landing page of a festival sale.
* **Live - Referrer Entry**: Add users to a segment based on a referring website or campaign. For example, users who have visited your website via a specific external referrer URL.
* **Live - Page count**: Add users to a segment based on the number of pages visited by them. For example, users who have visited five web pages on your website.

## Custom - List Based Segments

A custom - list based segment is a list of users from any source, including third-party tools or internal databases. You can deliver personalized messages to these users based on their past or real-time behavior in the app. For more information, refer to [Custom List Segment](doc:create-segments#create-custom---list-based-segments).
