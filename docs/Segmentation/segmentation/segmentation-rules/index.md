---
title: Segmentation Rules
excerpt: >-
  Understand how you can create rules to segment your users based on different
  properties in CleverTap.
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

In CleverTap, user property and behavior are significant when creating user segments. You can target your audience for campaigns based on their user properties and behavior. You can do so by creating segmentation rules from the _Create Segments_ page.

## User Property

User property refers to a user's demographic attributes, such as age, gender, location, device type, subscription status, etc. You can define these properties from the CleverTap dashboard, which is later collected during signup or interaction with your application. The following are the specific factors used to create segments based on user property:

* **User property**: Segment users based on custom user property values such as email, phone number, customer type, etc. For example, you can create a segment of users whose _customertype_ is _Gold_.


<Image src="https://files.readme.io/26e646e-User_Property_Rule.png" alt="Users Property Rule" align="center" caption="Segment by User Property Rule" border={true} />


* **User bucket**: Segment users based on a system user property called [User Bucket](doc:user-bucket). For example, you can create a segment of users with bucket numbers 7, 100, and 999.


<Image src="https://files.readme.io/b86aea6-User_Bucket.png" alt="Segment by User Bucket Rule" align="center" caption="Segment by User Bucket Rule" border={true} />


* **Demographic**: Segment users based on demographic user property values such as gender, age, etc. For example, you can segment your users based on their gender.


<Image src="https://files.readme.io/dc14c9a-Demographics_Rule.png" alt="Demographics Rule" align="center" caption="Segment by Demographics Rule" border={true} />


* **Geography**: Segment users based on their location. For example, you can create a segment of users living in Los Angeles, California, the United States, and so on.


<Image src="https://files.readme.io/fe644d9-Geography_Rules.png" alt="Geography Rule" align="center" caption="Segment by Geography Rule" border={true} />


* **Geography Radius**: Segment users that are located at a certain distance from the particular location. For example, you can create a segment of users within a particular retail store's radius.


<Image src="https://files.readme.io/64478f1-Gegraphy_Radius_Rule.png" alt="Geography Radius Rule" align="center" caption="Segment by Geography Radius Rule" border={true} />


* **Technographics**: Segments users based on the technical specifications of their devices. For example, you can create a segment of users who use your App on a mobile device with an Android OS.


<Image src="https://files.readme.io/c83a72f-Technographics_Rule.png" alt="Technographics Rule" align="center" caption="Segment by Technographics Rule" border={true} />


* **Reachability**: Segment users based on their reachability via different messaging channels such as push notifications, SMS, or email. For example, you can create a segment of unsubscribed users to receive emails.


<Image src="https://files.readme.io/b8b831a-Reachability_Rule.png" alt="Reachability Rule" align="center" caption="Segment by Reachability Rule" border={true} />


* **App fields** Segment users by app version or type. For example, you can create a segment of users with a Samsung device using app version 5.2.0.


<Image src="https://files.readme.io/05e8306b52d56c32cfdd44f98cd46f6c18f0b485c89384036c89a6faac2bcb57-image.png" align="center" caption="Segment by App Fields Rule" border={true} />


You can now use greater than ( > ), less than ( \< ), and between operators to create more precise segments based on version numbers. These operators are available for the following attributes:

* App version
* OS version
* SDK version

For instance, you can target users with an app version greater than 5.2.0, those on an OS version less than 13, and those on an SDK version between 1.2.0 and 1.3.8.

* **Segments**: Segment users based on their membership in a particular segment. For example, you can create a segment of users who have purchased in the past 30 days and save it as _Charged Users_. You can then include and exclude this segment based on your target audience while creating a new segment, rather than creating a complex query each time.


<Image src="https://files.readme.io/0904d67-Segments_Rules.png" alt="Segments Rule" align="center" caption="Segment by Segments Rule" border={true} />


<Callout icon="📘" theme="info">
  ### Include and Exclude

  The following are some of the points that you consider when you include and exclude segments:

  * The include and exclude segments are currently unavailable for bulletins and A/B Testing.
  * You can only include or exclude  [PBS](https://docs.clevertap.com/docs/segments#section-past-behavior-segments) and [Custom List](https://docs.clevertap.com/docs/custom-list-segments) segments.
</Callout>

## User Behavior

User behavior refers to a user's actions within your App or Website, such as completing a purchase, adding items to a cart, clicking on a specific link or button, abandoning a session, or leaving a review. CleverTap tracks these behaviors through event tracking. The following are the factors used to create segments based on user behavior:

* **Event (Did)**: Segment users based on the events they have done. For example, you can create a segment of users who have performed the _App Installed_ event in the last 30 days.


<Image src="https://files.readme.io/18dda8d-Did.png" alt="Segment by Did Rule" align="center" caption="Segment by Did Rule" border={true} />


* **Event (Have not done)**: Segment users based on the events they have not done. For example, you can create a segment of users who have not performed the _App launched_ event in the last 30 days.


<Image src="https://files.readme.io/7d2fa6e-Have_Not_Done.png" alt="Segment by Have Not Done Rule" align="center" caption="Segment by Have Not Done Rule" border={true} />


* **Combination of (Did any of)**: Segment users based on any of the events they have done in a specified period of time. For example, you can create a segment of users who have performed any of the events, such as Product Viewed, Added to Cart, or Charged in the last 30 days.


<Image src="https://files.readme.io/fbef063-Did_Any_Of.png" alt="Segment by Did Any Of Rule" align="center" caption="Segment by Did Any Of Rule" border={true} />


### Filter Inaction Events by Event Property

When you segment users on an event they did not do, you can now narrow that inaction down to a specific event property. This lets you go beyond a general _did not purchase_ condition to a more precise one, such as users who add a specific item to their cart but do not purchase it.

For example, you can create a segment of users who add shoes to their carts but do not purchase them. Without this filter, CleverTap could only detect that a user added something to their cart and did not complete a purchase, without distinguishing which item.

To apply this filter:

1. From the _Create Segments&#x20;_&#x70;ag&#x65;_&#x20;> Live Inaction in Time Frame_, select **Event (Does not do)** as your behavior rule.
2. Choose the event you want to track.
3. Add a property filter on that event and specify the value to match.
4. Save your segment.

The following table lists the channels for which this filter is currently available:

| Channel                                                                    | Availability         |
| :------------------------------------------------------------------------- | :------------------- |
| In-App                                                                     | Available (existing) |
| Push, SMS, Email, WhatsApp, Web Push, Webhooks                             | Available (new)      |
| Native Display, App Inbox, Web Pop-up, Web Native Display, Web Exit Intent | Not available        |

#### **Use Case**

- Media and OTT: target users who add a show or movie to their watchlist but do not start streaming it.

## User Interests

User Interests refer to the psychography of users, which enables you to segment your users based on event properties, including their relative frequencies, date, and time. It tells you how often the users do something and when they do it (by date and time).

There are three types of rules provided by CleverTap:

* **Event Property**: Interest by Event Property allows you to segment users based on specific actions they frequently perform. For example, you can segment users users who frequently read articles on technology out of all the articles they read. This helps in targeting users who have a specific interest in tech-related content.
* **Time of the day**: Interest by Time of the Day allows you to segment users based on when they usually perform actions during the day. For example, you can segment users who typically shop online between 8 PM and 10 PM. This allows you to send targeted promotions or reminders during their preferred shopping hours.
* **Day of the week**: Interest by Day of the Week allows you to segment users based on which day of the week they usually perform actions. For example, you can segment users who usually order food delivery on Fridays. This enables you to send special weekend offers or discounts to encourage repeat orders.

<Callout icon="📘" theme="info">
  ### Predominantly vs. At Least

  The _Predominantly_ option means the event property you select will only include users, where that event property is the most frequently occurring event property for the user. The _At Least_ option lets you specify the specific percentage you need.
</Callout>

# AND/OR Rules

The _AND/OR_ rules are an important segmentation feature in CleverTap. Combining different conditions using these operators allows you to create highly personalized campaigns that resonate with your users. When using these rules, it is important to understand the syntax and usage, ensuring you target the right segment for your campaign. The following sections provide information about the syntax and usage of _AND/OR_ rules when creating segments in CleverTap.

## Using AND Operator

The _AND_ operator combines multiple conditions that must be met simultaneously to qualify for the segment.

For example, if you want to target users who are both male and have purchased at least one product in the last 30 days. In this case, the _AND_ rule would be as follows:


<Image src="https://files.readme.io/ae30ff4-Segment_with_AND_Operator.png" alt="Segmenting with AND Operator" align="center" caption="Segmenting with AND Operator" border={true} />


In this case, the audience will only include users who match both the specified conditions.

## Using OR Operator

The _OR_ operator combines multiple conditions where at least one must be true to qualify for the segment.

For example, if you want to target users who have either made a purchase in the last 30 days or have added items to their cart but have not completed the purchase. In this case, the _OR_ rule would look like this:


<Image src="https://files.readme.io/9c0b2ec-OR_Operator.png" alt="Segmenting with OR Operator" align="center" caption="Segmenting with OR Operator" border={true} />


In this case, the segment will include users who match either of the specified conditions.

## Combining AND/OR Operators

Both _AND_ and _OR_ operators can be combined to create more complex segmentation rules. For example, if you want to target male users who have made a purchase in the last 30 days OR female users who have not completed the purchase in the last 30 days.

The following image shows how you can create the above segment query using the combination of  AND/OR operators:


<Image src="https://files.readme.io/519ac77-Combining_ANDOR_Rules.png" alt="Combining AND/OR Operators" align="center" caption="Combining AND/OR Operators" border={true} />


# Additional Filters

These filters allow customers to segment users based on count, average, or total sum of an event property value.

## Count

It allows customers to filter users by event count. The following query finds all users who performed a _Charged_ event greater than five times in the past 30 days:


<Image src="https://files.readme.io/72dc3a3-Count_Filter.png" alt="Filter by Count" align="center" caption="Filter by Count" border={true} />


## Total Sum of Property

It allows customers to filter users by the sum of a chosen event property. The following query finds all users who performed a _Charged_ event such that the _Revenue_ event property is greater than $10:


<Image src="https://files.readme.io/8b92312-image_13.png" alt="Filter by Total Sum of Property" align="center" caption="Filter by Total Sum of Property" border={true} />


## Average Sum of Property Filter

It allows you to filter users by the average of a chosen event property. For example, you can filter all the users who performed a _Charged_ event with an _Average sum of property_ being _greater or equal_ to $10. Let us assume that user A performed five _Charged_ events each for $8, $9, $10, $11, and $12. Here, the average of property from user A is ($8+9+10+11+12)/5 events = 50/5 = $10 per event, which is equal to $10. As a result, user A will qualify for this segment.

Let us assume that the value for two charged events is missing. The _Charged_ event values received are $5, $7, and $13. In this case, the value of the missing events will be considered as 0. As a result, the average of property is now ($5+7+13+0+0)/5 events = 25/5 = $5 per event. As a result, the user will not qualify for this segment.

If you want to exclude all the events that do not have event properties, you can select the property that _exists_ as a condition in the _Filter by_ section.

The following query finds all users who performed a _Charged_ event such that the _Average sum of property_ per event is _greater or equal_ to $10:


<Image src="https://files.readme.io/cbadd22-Filter_by_Average_Sum_of_Property.png" alt="1192" align="center" caption="Filter by Average Sum of Property" border={true} />
