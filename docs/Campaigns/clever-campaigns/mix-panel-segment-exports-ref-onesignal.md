---
title: Mix Panel Segment Exports (Ref - OneSignal)
excerpt: CleverTap - Mixpanel Integration for Segments Exports
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
Export Mixpanel cohorts to CleverTap to create custom segments that you can apply in your CleverTap campaigns. Manage the CleverTap integration from the Mixpanel integrations page.

CleverTap also supports an integration to send messaging interactions to Mixpanel - for more details, see [CleverTap's Mixpanel integration](https://documentation.CleverTap.com/docs/mixpanel).

Permissions and Account Requirements
------------------------------------

You must be a Mixpanel project admin to enable the CleverTap integration. [Read more about project roles and permissions here.](https://help.mixpanel.com/hc/en-us/articles/360024613412)

Additionally, you must have a paid CleverTap plan to use the integration. If you attempt to sync cohorts while on a free CleverTap plan, you will receive the following error: *"**App may not submit cohort updates from Mixpanel"*.

Enable the Integration
----------------------

To enable the integration, select Integrations under the Data Management tab in the top navigation bar:

![Screen_Shot_2020-09-16_at_2.32.09_PM.png](https://help.mixpanel.com/hc/article_attachments/360072870671/Screen_Shot_2020-09-16_at_2.32.09_PM.png)

From the Integrations page, select the CleverTap dropdown, and select Connect

![Screen_Shot_2020-10-14_at_9.59.52_AM.png](https://help.mixpanel.com/hc/article_attachments/360072639332/Screen_Shot_2020-10-14_at_9.59.52_AM.png)

You will need to provide two credentials to authorize the connection: API Key and App ID. You can find these values in your CleverTap settings page.

The CleverTap integration will show a "Connected" tag in the UI once the connection succeeds.

Matching Users between CleverTap and Mixpanel
---------------------------------------------

Mixpanel only exports [identified user profiles](https://help.mixpanel.com/hc/en-us/articles/115004501966-User-Profiles) to match to CleverTap - users without user profiles (i.e. anonymous users) will not export.

In order to match an exported Mixpanel user to CleverTap, the user's Mixpanel profile must contain a user property, "$CleverTap_user_id". The value of this property is a string representing either that person's Player ID or External User ID in CleverTap. [CleverTap recommends using External User ID](https://documentation.CleverTap.com/docs/mixpanel#step-4-send-mixpanel-the-CleverTap-user-id), as it's a cross-platform user identifier and allows for CleverTap's email capabilities. In your implementation, reference the Player ID from CleverTap's SDK or reference your External User ID and set the user property "$CleverTap_user_id" on the user's Mixpanel profile.

User profiles without this user property will not export to CleverTap - it is a requirement for user matching.

In addition, when its ingestion service detects calls setting this user property, [Mixpanel will also alias](https://developer.mixpanel.com/reference/http#create_alias) the value of "$CleverTap_user_id" to the user's distinct_id when setting the "$CleverTap_user_id" user property. This ensures that messaging events passed from CleverTap campaigns to Mixpanel still attribute to the correct user.

Export a Cohort
---------------

You can export a cohort to CleverTap from the Cohorts report. Navigate to Cohorts by clicking Cohorts under Users in the navigation bar.

Select the cohort that you want to export. Click on the three-dot icon on the right side of the cohort.

Click Export to > CleverTap. Select either one-time sync or dynamic sync. Click Start Sync.

![Screen_Shot_2020-10-14_at_3.24.04_PM.png](https://help.mixpanel.com/hc/article_attachments/360072870791/Screen_Shot_2020-10-14_at_3.24.04_PM.png)

Sync Types
----------

This integration supports two types of exports: one-time export and dynamic sync.

### One-Time Export

In a one-time export, Mixpanel sends CleverTap a static export of users who currently qualify for the cohort. The cohort data will not be updated in CleverTap after a one-time export.

### Dynamic Sync

In dynamic sync, Mixpanel initiates sync between a cohort and CleverTap every fifteen minutes. The exported cohort will be updated every fifteen minutes to reflect the most recent list of users in a cohort.

When you generate a one-time export or dynamic sync, it overwrites the previous export with an updated export that reflects users who qualify for the cohort at the time of export.

Select the Segment in CleverTap
-------------------------------

Once the export completes, you will see a Segment reflecting the set of users from your Mixpanel cohort:

![Screenshot_2020-10-14_CleverTap_Mobile_Push_Notifications_2_.png](https://help.mixpanel.com/hc/article_attachments/360072649672/Screenshot_2020-10-14_OneSignal_Mobile_Push_Notifications_2_.png)

CleverTap events into Mixpanel & MTU exemptions
-----------------------------------------------

CleverTap offers the ability to forward campaign interaction events to Mixpanel. For more detail, [please refer to CleverTap's integration guide](https://documentation.CleverTap.com/docs/mixpanel).

Because CleverTap's event structure follows Mixpanel's naming convention for messaging events, it will have the same exemptions [outlined in the MTU calculation guide](https://help.mixpanel.com/hc/en-us/articles/360001465686-Billing-for-Monthly-Tracked-Users#monthly-tracked-users-calculation) for which events do not count towards MTU tallies. Message delivery events will not count towards a user being in MTU counts, while message engagement events will.