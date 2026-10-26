---
title: Setting Up a Journey
excerpt: >-
  Understand how to set up your journey with settings like entry criteria,
  timelines, and timezones.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Overview

Set up your journey by defining the following:

* [Journey Entry](https://docs.clevertap.com/docs/setup-journey#define-the-journey-entry-criteria)
* [Journey Entry Timelines](https://docs.clevertap.com/docs/setup-journey#define-the-journey-entry-timelines)
* [DND and Timezone](https://docs.clevertap.com/docs/setup-journey#dnd-and-timezone)
* [Control Group](https://docs.clevertap.com/docs/setup-journey#define-the-control-group)
* [Journey Timeout](https://docs.clevertap.com/docs/setup-journey#select-a-journey-timeout)
* [Journey End Date](https://docs.clevertap.com/docs/setup-journey#set-a-journey-end-date)
* [User Exit From a Journey](https://docs.clevertap.com/docs/setup-journey#user-exit-from-a-journey)

The first step in building a Journey is to define its configuration within the Setup node.<br />Click **Journeys** from the dashboard and click the **+Journey** button to set up a Journey. A new Journey canvas is displayed.


<Image src="https://files.readme.io/1ea159c-Journey_Setup.png" alt="1348" align="center" border={true} />

Click **Setup**. The *Setup* window displays.  Enter the **Journey Name**. 

Using keyboard shortcuts, you can efficiently set up and manage journeys. Click the ![](https://files.readme.io/62eb9da-Keyboard_Shortcuts.png) icon to learn about the keyboard shortcuts.

<Image alt="Keyboard Shortcuts in Journeys" align="center" border={true} src="https://files.readme.io/a37fd3d-Keyboard_Shortcuts_in_Journeys.gif">
  Keyboard Shortcuts in Journeys
</Image>

## Define the Journey Entry Criteria

Select the *Journey entry criteria*. It can be a specific time or an event trigger. 

When you start building your Journey, you must define your _entry criteria_. This condition determines whether users will be included in the Journey. The entry criteria of a Journey is essentially the segment of users you want to target.

The various types of segments you can use are:

* **Live User segments**: These segments qualify people as soon as they meet your specified criteria
* **Past Behavior segments**: In this type of Entry Criteria, users who match your specified entry criteria will qualify once every twenty-four hours.

Live user segments are further classified as follows: 

* **Action**: In this type of _entry criteria_, users will enter your Journey as soon as they perform an event. For example, enter people into your Journey as soon as they install your application.
* **Inaction**: Users enter your Journey as soon as they don’t take any action in the future. For example, If someone adds an item to their cart, but doesn’t transact within 15 minutes.
* **Property Date-time segments**: Qualify a user relative to a specific date and time in a property.
* **Page visit**: Users will qualify as soon as they reach a web page that matches your specifications.
* **Referral entry**: When users come to your website from a specific referrer, such as Facebook or Twitter, they will be eligible for your Journey.
* **Page count**: As soon as the user sees the specified number of pages, they will be a part of your Journey.


<Image src="https://files.readme.io/ada99a2-Journeys_setup_entry_criteria.png" alt="766" align="center" border={true} />

## Define the Journey Entry Timelines

We support one-time, multiple dates, and recurring Journeys. For example, for monthly payment reminders, you can schedule a Journey to start on the 1st of every month


<Image src="https://files.readme.io/2a5ce7b93b489900cd50c3de4f5fdc65c85ddb8c6b4352af027ce5b8a47279e4-Define_Journey_Entry_Timelines.png" alt="726" align="center" border={true} />


### Enter Once

This Journey type runs only once at the start time. Users who have exited the journey due to journey timeout, forced exit, or Goal completion cannot re-enter. No new users will be added after the journey runs its course at the start time.

### Enter on Specific Dates

This Journey type runs on multiple selected dates. Select the journey end time according to your business requirements. The option to allow users to re-enter the journey may be selected.

### Enter on a Recurring Basis

This Journey type runs repeatedly and allows new users to enter based on the criteria selected in the _Repeat every_ section. The first run is immediate upon publishing the Journey. The subsequent runs are based on the selected criteria. The option to allow users to re-enter the journey may be selected. For more information about entry timelines for a PBS Journey, refer to [FAQ](doc:faqs#q-how-does-a-past-behavior-segment-journey-work).

### Allow Users to Re-Enter the Journey

By default, a user qualifies for a Journey only once. However, you can optionally allow users who have exited from a Journey to re-enter it, should they meet the entry criteria at a later date.

Once a user enters the journey, they can exit the journey by matching different exit criteria, and only then can they qualify to re-enter the journey.

Consider an example where the user qualifies for the journey if they have not made any purchase in the last 30 days. After waiting for one day, qualifying users receive a Push Notification with a discount promotion code at 10 AM, as shown in the following image:


<Image src="https://files.readme.io/8f93e69004ca4b15b2a0abfebd72fa4f5052775b6fa40f474a5d961392e4b518-Re-Entry_of_Users_in_Journeys.png" alt="698" align="center" width="85% " border={true} />


If the Journey was set up with the default behavior (users cannot re-enter the Journey), then after they purchase and receive the push notification, they would continue moving ahead in the journey and finally exit it. As the  _Allow users to re-enter the journey_ option was not selected, the users would not enter the journey again.

If the Journey is configured with the setting where _Allow users to re-enter the journey_ option was selected, they will receive the corresponding push notification and exit the Journey after completing a purchase.

However, if the users again qualify in the entry criteria while the journey is still running, they will enter the journey and receive the promotional offer to make the purchase.


<Image src="https://files.readme.io/f8a8c7210683541760ae2eeb75ae4ee0f78381dc9499b3a7376dd39e4af7c16c-Allow_Users_to_Re-Enter_the_Journey.png" alt="Allow Users to Re-Enter the Journey" align="center" border={true} />

## DND and Timezone

CleverTap provides an option to configure _Do Not Disturb_ hours for notification delivery when creating a journey. The DND feature manages message delivery via engagement nodes in Journeys so that campaigns are only sent after the DND period or discarded. To configure DND for Push, SMS, Email & Web Push journeys, select the days and enter the time when you do not want to send campaign notifications. If you will use the same time inactive period for each day, click the **Apply to all** link.

<Image alt="Configure DND and Timezone for Journeys" align="center" width="75% " border={true} src="https://files.readme.io/a0f920cded3c563fa8f58d40ed8942f9b2940606d900d8cf9814536ff9dffc94-image.png">
  Configure DND and Timezone for Journeys
</Image>

When sending a message during Do Not Disturb (DND) hours, you can select one of the following options:

* _Don't send a message_: Select this option to discard the message altogether. In this case, the message is not sent to the user, and the user proceeds along the unreachable path. If the unreachable path is not defined or drawn, the user is stuck at the engagement node.
* _Send message after DND_: Select this option to send a message after DND.

  * _Scenario 1 (Before Feature Release)_<br />DND Period: Monday 11:00 PM to Tuesday 12:00 PM<br />User qualifies for the campaign: Tuesday 11:00 AM (During DND)<br />The engagement is delayed as it falls within the user's DND period. The user receives the engagement as soon as the DND period ends, at 12:00 PM on Tuesday.
  * _Scenario 2 (After Feature Release)_<br />DND Period: Monday 11:00 PM to Tuesday 12:00 PM<br />User qualifies for the campaign: Tuesday 11:00 AM (During DND)<br />The engagement is delayed as it falls within the user's DND period. The user receives the engagement on Wednesday at 11:00 AM, which is at the time scheduled. This ensures that notifications respect the user's active and inactive times and are only sent during their designated active hours.


  <Image src="https://files.readme.io/d3398f19a4d62d7f24eb243c245990941d506de273e89544302344919c7635ef-Send_Message_After_DND.png" alt="Send Message After DND" align="center" border={true} />


<Callout icon="❗️" theme="error">
  ### DND Conflict Hours

  If you schedule a message node to send out delivery during the scheduled DND hours, you will receive an error message. This error message appears at the publishing of the journey.


  <Image src="https://files.readme.io/7ff47d7-2020-08-17_16-14-20_DND_hours_Conflict.png" alt="1206" align="center" border={true} />

</Callout>

## Define the Control Group

Define the required control groups. For more information on control groups, see [Control Groups](doc:control-groups). 


<Image src="https://files.readme.io/7092b2a-Journeys_setup_control_group.png" alt="725" align="center" border={true} />

## Select a Journey Timeout

Journeys are sequences of campaigns. At each stage of a Journey, you can choose to segment your audience further and deliver campaigns across multiple channels.

While creating Journeys, you can specify a Journey Timeout, which is the maximum time a user can spend in a Journey. Users exit the journey once this window is complete, regardless of the journey stage.

<Callout icon="🚧" theme="warn">
  #### Journey Re-Entry

  Once a user has exited the Journey, the user is free to re-qualify, if you have allowed re-entry in your setup.
</Callout>


<Image src="https://files.readme.io/e182621-Journeys_setup_timeout.png" alt="724" align="center" caption="Timeout Duration setup" border={true} />


## Set a Journey End Date

Define when the journey should automatically stop. The Journey End Date section appears after the Timeout section in Journey Setup.

<Callout icon="📘" theme="info">
  #### Private Beta

  End date  is currently released in Private Beta. If you want to enable this for your account, contact Customer Success Manager.
</Callout>

Select one of three options:

### Never end

The journey runs indefinitely until you stop it manually. No end condition is applied. Never End is the default selection and preserves existing behavior for all journeys.

Best suited for evergreen journeys such as cart abandonment, onboarding, and loyalty triggers.


<Image src="https://files.readme.io/bb2e9c6b189f51ee8ddfcf178b6c82cff60f90e2b478dee8fb13dff3604aecb2-Screenshot_2026-09-28_at_2.46.57_PM.png" alt="The Journey end date with the Never end option selected" align="center" caption="Journey End Date with the Never End option selected" border={true} />


### End

The journey stops on a specific calendar date, regardless of when it was launched.

To set a fixed end date:

1. Select **End**.
2. Select the date and time when the journey should stop.
3. Click **Continue**.


<Image src="https://files.readme.io/e3ccbaed82b49c4e563df518c59c9656420caca8d02b264802e9dd78c8ca776e-Screenshot_2026-09-28_at_2.49.08_PM.png" alt="The Journey end date with the End option selected" align="center" caption="Journey End date with the End option selected" border={true} />


The selected date is shown with your account's timezone label for confirmation.

Best suited for campaigns tied to a fixed calendar event, such as a seasonal sale deadline, a regulatory cutoff date, or an offer expiry. For example, an e-commerce team running a "50% off in March" promotion can set March 31 as the fixed end date so the journey stops automatically, no manual intervention needed at midnight.

<Callout icon="📘" theme="info">
  #### Fixed End Date uses Account Timezone

  The end date is applied in your account's timezone. Per-user timezone support is not available for this setting in the current release.
</Callout>

### End after

The journey stops after a set duration from the **journey start date**. This is useful when the campaign window is known in advance, but the exact launch date may vary.

To set an end duration:

1. Select **End after**.
2. Enter the duration.
3. Select the required time unit. You can choose either:
   1. Day(s)
   2. Week(s)
   3. Month(s)
4. Click **Continue**.

**Example**&#x20;

If you set **End after** date to 30 days, the journey automatically stops 30 days after its start date.


<Image src="https://files.readme.io/40554ab3775182807d0190ed4b7517d99f0f805dd88995ad0957cc794ed27e26-Screenshot_2026-09-28_at_2.50.52_PM.png" alt="The Journey end date with the End after option selected" align="center" caption="Journey End date with the End after option selected" border={true} />


Best suited for campaigns where the window is fixed relative to launch, such as a 30-day post-purchase upsell sequence, a KYC nudge campaign, or a time-boxed event-based window.

#### What Happens When the End Date Is Reached

When the configured end date is reached, CleverTap automatically stops the journey:

- No new users can enter the journey.
- All users currently active in the journey are immediately exited. No further communications are sent to users who have exited.
- The journey transitions to a _Stopped_ state.&#x20;

<Callout icon="🚧" theme="warn">
  #### End Date Configuration Limits

  The Journey End Date configuration is locked once the journey goes live. If you need to change the end date, stop the journey and create a new version.
</Callout>

## User Exit From a Journey

Assessing a Journey's effectiveness becomes challenging when a user gets stuck in a Journey. Hence, exiting users from the Journey is crucial in various scenarios.

Users exit the Journey based on four conditions:

* If the Journey goal is set:
  * User achieves the Journey goal.
  * User times out of the Journey.
  * User is forced to exit the Journey via the **Force Exit** node.
* If the Journey goal is not set:
  * User exits the Journey through the last engagement node.