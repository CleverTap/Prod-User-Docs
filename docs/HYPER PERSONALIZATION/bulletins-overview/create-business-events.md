---
title: Create Business Events
excerpt: Learn how to create and raise business events, and monitor their performance.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

A business event is an action or update in your business that gives you a reason to message users, such as a new episode release or a product restock. Create the business event before you create the bulletin that uses it.

Th&#x65;_&#x20;Business Events_ page lists your business events. You can search the list, filter it by time period and creator, and switch between _Active_ and _Archived&#x20;_&#x62;usiness events.

The following image shows the _Business Events_ listing page:


<Image src="https://files.readme.io/269314acecda9cd96d805be0fa6fea3e6719ca287a2ec0318f1946eb20a87ad8-image.png" align="center" caption="Business Events Listing" border={true} />


To create a business event, perform the following steps:

1. In the left navigation, go to _Bulletins_, and then click **Business Events**.
2. Click **Create Business Event**.
3. In _Business Event Name_, enter a unique name, for example `New Season Launched`.
4. In _Description_, enter a short description of the event.
5. In _Business Event Properties_, enter the name of each property that your trigger sends, and you can add more properties by selecting the plus icon. You must add at least one property. For example, add `series_name`.
6. Optional: To track a desired outcome, select _Goal_, and then define the goal. A goal needs a goal event, a business event property, and an event property that CleverTap matches to it. The match uses the equals condition. Composite events are not available as goal events.
7. Click **Save**.

The following image shows the _Setup_ tab of a business event:


<Image src="https://files.readme.io/34e657d374ad4abc14c8be4d7fe256f811bfe741da22583dad6a71dc288c5007-image.png" align="center" caption="Create a Business Event" border={true} />


The following table describes what you can change after you save a business event:

| Business Event State              | What You Can Edit                                    |
| --------------------------------- | ---------------------------------------------------- |
| No active bulletin uses the event | Name, description, and goal. You can add properties. |
| An active bulletin uses the event | You can add properties only.                         |

You cannot remove a property after you save it. Add only the properties that you need, and use clear names, because your trigger must send a value for every property that the business event defines.

## Raise a Business Event

Your system raises a business event each time the event occurs by calling the Raise Business Event API. The call starts the bulletin, and CleverTap sends the messages to the users who match.

The request includes the following information.

- The name of the business event.
- A value for every property that the business event defines. Send the values as strings.
- The `c-by` value, which identifies an active admin of your account.
- The `when` value, which is `now` or a date and time in the format `YYYYMMDD HH:MM`.

When the call succeeds, the response returns the `targets` count. This count equals the number of active campaigns that CleverTap triggered across the active bulletins that use the business event. For example, a bulletin with three active campaigns adds three to the count. The call returns a 400 error when the business event does not exist, a defined property is missing, the `c-by` value is not an active admin, or the `when` value is missing or invalid.

## Manage Business Events

The following table lists what you can do from the Business Events page.

| Page            | What you can do                                                                                                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Business Events | Search, filter, edit, clone, archive, and unarchive. You can archive and unarchive several business events at once. A cloned business event gets the suffix `- clone` in its name. |

CleverTap does not stop you from archiving a business event that active bulletins use. Check the Bulletins column on the Business Events page before you archive an event.

## Stats: Business Event

The _Stats_ tab of a business event shows how the messages that its bulletins send perform. In the left navigation, go to _Bulletins_, select _Business Events_, open the business event, and then select the _Stats_ tab.

The date range picker at the top of the page controls the period for every section. The default range is the last 30 days. When you change the range, CleverTap refreshes Users Converted, Delivery Errors, and the activity log.

The following image shows the _Stats_ tab of a business event:


<Image src="https://files.readme.io/ceb1437f67e27c259f7676d6e6b444cdc24c8cb4296fc9d80a625a5fddc16c52-image.png" align="center" caption="Stats for Business Event" border={true} />


The _Stats_ tab has the following sections:

### Users Converted

The Users Converted section shows how many of the users who received a message from the business event's bulletins completed your goal. This section needs a goal. When you do not set a goal for the business event, the section displays the message _View conversions by setting a goal_, and the goal dropdown is disabled. To set a goal, edit the business event. You can edit the goal only when no active bulletin uses the business event.

To read the section, select a value in _Select goal values_. The dropdown lists the goal values that you defined for the business event, with the first value selected by default.

CleverTap counts a user as converted when the user receives the message, views it, clicks it, and then performs the goal event with the selected goal value.

The following table describes the two tiles:

| Tile      | What it shows                                                                                                                                                                                                                                                                                                            |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| All Users | The number of users who converted, out of the number of users who received a message. For example, 648/1,200 means that 648 of 1,200 users converted. The percentage badge shows the conversion rate, which is the number of converted users as a percentage of users who received a message, rounded to a whole number. |
| Drop offs | The number of users who received a message but did not convert. This number equals the number of users who received a message minus the number of users who converted. The percentage badge shows the drop-off rate as a percentage of the users who received a message.                                                 |

The tiles show totals for the whole date range, not daily values.

### Actions Trend

The Actions Trend chart shows the trend of All Users and Drop-offs by day for the selected date range. Hover over a point to see the values for that day.

Use the Percentage and Count toggle to change how the chart displays the data. The toggle changes only the chart. The tiles always show counts.

- **Count**: The chart plots the actual daily values.
- **Percentage**: The chart scales each line against its own highest day, so each line's highest day shows as 100 percent.

### Delivery Errors

The Delivery Errors section shows the messages that CleverTap could not deliver for the selected date range. It starts with three tiles.

- **Total delivery errors**: All delivery errors, Android and iOS combined.
- **Technical delivery errors**: Errors that come from the setup, such as an invalid certificate or a payload that is too large.
- **Non-technical delivery errors**: Errors that arise from the user or the device, such as a user turning on Do Not Disturb, a group unsubscribing, or an app being uninstalled.

Two tables follow the tiles, one for technical errors and one for non-technical errors. The following table describes the columns in each table.

| Column       | What it shows                                                                                                                                             |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Error reason | One row for each distinct reason. CleverTap adds the counts across all campaigns that the business event triggered and across all days in the date range. |
| Android      | The number of times the error occurred on Android devices.                                                                                                |
| iOS          | The number of times the error occurred on iOS devices.                                                                                                    |

### Activity Log

The activity log lists each time your system raised the business event, so you can check when a trigger ran and how many messages it sent. To find a trigger, use _Search by name_. To change the order, select _Event time_. The log shows the newest events first by default. You can show 10, 20, 50, or 100 rows on a page.

The following table describes the columns in the log.

| Column                      | What it shows                                                             |
| --------------------------- | ------------------------------------------------------------------------- |
| Business event activity log | The name that your system sends with the trigger.                         |
| Bulletins dispatched        | The number of campaigns that the trigger created, shown as Bulletins (N). |
| Event time                  | The date and time when the trigger ran.                                   |
| Total sent                  | The total number of messages that the trigger sent.                       |
| Created by                  | The admin user who raised the business event.                             |

To see more about a trigger, expand its row. The left side lists the properties and values that your system sent with the trigger. The right side lists a link for each campaign that the trigger created. Select a link to open the campaign report in a new tab.
