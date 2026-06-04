---
title: Time in User Property
excerpt: >-
  Learn how you can use your own best time logic to schedule campaigns with the
  Time in User Property feature.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Time in User Property gives you full control over when messages are delivered by allowing you to define the send time outside CleverTap for each user and pass it directly as a user property. Instead of relying on CleverTap’s system-calculated Best Time, you decide the best time logic using your own models, rules, or data pipelines, and CleverTap delivers messages exactly at the time you specify for each user.

The calculated time value is transferred to CleverTap by updating a user property through supported data ingestion methods such as the Profile API, CSV upload, or data sync integrations. The value is stored as a standard user property in the user profile and used during campaign execution to determine message delivery time for each user.

> 📘 Private Beta
>
> Currently, this feature is a Private Beta Release. If you want access to this feature, contact your Account Manager.

## When should you use this?

Use Time in User Property if:

* You externally calculate the best send time for each user.
* You want CleverTap to deliver messages exactly at the time you provide for each user.
* You want to avoid creating multiple time-based campaigns or segments.

# Setting up Time in User Property

Setting up Time in User Property involves two steps:

1. Pass the time value in a user property
2. Use the property in campaigns

> 📘 Note
>
> To set up Time in User Property using API, refer to [Time in User Property Object](https://developer.clevertap.com/docs/create-campaign-api#time-in-user-property-object).

## Step 1: Pass the time value in a user property

Pass a time-of-day value (in minutes) as a user property in the user profile. This value represents the number of minutes since the start of the day (00:00) and is used to determine the exact time at which the message should be sent to that user (in account timezone).

For example, if you set the user property to `1125`, CleverTap schedules the message to be delivered to that user at 6:45 PM (account timezone).  Similarly, `0` means 12:00 AM, `145` means 02:25 AM, `570` means 09:30 AM, and `1125` means 06:45 PM.

## Step 2: Use the property in campaigns

To configure the Send Time for a specific campaign,

1. Navigate to the _When_ section.
2. Select _Schedule for later_ or _Set as Recurring_ under the Data and time section, depending on the nature of your campaign.
3. Select _Time in User Property_ as the send-time option. This instructs CleverTap to schedule message delivery for each user based on the time stored in the selected user property.

<Image align="center" border={true} caption="Time in User Property" src="https://files.readme.io/e1b7403b986ed71a6ff664dea102a642021dafc5573cdad7d7b91945864d3cb8-2026-01-08_15-22-39.png" />

4. Specify the Start time and End time of the campaign. If End Time is not specified, the campaign runs for 24 hours.

<Image align="center" border={true} caption="Start and End Time" src="https://files.readme.io/06c31b2bb0bd5aa3ce23498301300a748170acc3367d6ac334729169753f9dc0-2026-01-08_15-25-50.png" />

5. In the _Delivery Preferences_ section, navigate to the _Time in user property configuration_. Select the **User Property** from the dropdown.
6. Configure the fallback behavior for the following scenarios:
   1. **Fallback for users with no/invalid time in user property:** Applies when the selected user property is missing, empty, or contains an invalid value, so CleverTap cannot determine a send time for that user using Time in User Property.
   2. **Fallback for users not qualifying in campaign time range:** Applies when the user has a valid time value in the selected user property, but that time falls outside the campaign’s configured Start Time and End Time, so the user cannot be included within the campaign’s send window.

<Image align="center" border={true} caption="Time in user property configuration" src="https://files.readme.io/e07914530f44ad70f973fcfce7ee84520b52a7ca502e8403a89f59f35b428dab-image.png" />

<Callout icon="📘" theme="info">
  ## Note

  * This option is available only for Past Behaviour Campaigns.
  * Campaign-level throttling and limits apply as usual.
  * Time in User Property uses the account timezone, not the user’s local timezone.
  * The send time is locked in when the campaign begins running for users who qualify at that time. Updates made to the user property after dispatch begins do not affect message delivery for those users. However, users who qualify later will follow the updated time value available at the time they enter the campaign.
  * Supported time format:
    * The user property must be passed as an integer representing the number of minutes since the start of the day `(00:00)`.
    * For example, `145` means 02:25 AM and `1125` means 06:45 PM.
    * Seconds are not supported.
</Callout>
