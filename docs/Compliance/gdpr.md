---
title: General Data Protection Regulation (GDPR)
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Introduction

GDPR enforcement places control over the personal data businesses collect in the hands of the individuals to whom it belongs, protecting the rights of EU residents.

The regulation delineates individuals’ rights to [access, rectify, and restrict](https://gdpr-info.eu/chapter-3/) the processing of personal data, among other key provisions, and aims to unify privacy and security laws for all organizations operating within the EU.

In this user document, we will focus on how to implement the different rights once invoked by Data Subjects.

# Nomenclature

- Data Subject: End Users
- Data Controller: CleverTap Customers
- Data Processor: CleverTap

# Contractual Obligations

1\. [Data Processing Agreement](https://clevertap.com/data-processing-agreement/) (DPA)

All CleverTap customers must sign the DPA. To account for this, upon first login, each user must review and accept our ToS, Privacy Policy, and DPA.

2\. [Updated Terms of Service](https://clevertap.com/terms-service/)

3\. [Updated Privacy Policy](https://clevertap.com/privacy-policy/)

## Data Subject Rights

### Right to Erase

#### 1. What is it?

This right allows end users to delete all information about them from CleverTap servers.

<Callout icon="📘" theme="info">
  ### Note

  Backup snapshots are rotated automatically as part of CleverTap's standard infrastructure retention and are not a GDPR-specific guarantee tied to individual erasure requests.
</Callout>

#### 2. CleverTap Implementation

a. API _/delete/profiles.json_

- Data Controllers can use this Rest API to delete all data of the mentioned profiles from the CleverTap servers by calling one of the 2 unique profile identifiers:
  - List of identities
  - List of GUIDs

```text http://eu1.wzrkt.com/1/delete/profiles.json
{
    "guid":"df2e224d90874887b4d61153ef3a2508"
}

OR

{
    "identity":"john.doe@johndoe.com"
}
```

b. Dashboard Delete

- Data Controllers can navigate to the profiles of users whose profiles need to be deleted.
- When a Right to Erasure request is processed, the user's profile data is queued for deletion and removed within approximately 48 hours, during CleverTap's maintenance window. Event data associated with the profile is retained separately in accordance with CleverTap's Data Retention Policy (DRP). This action cannot be rolled back once initiated.

c. IMPORTANT NOTE<br />When a user's profile is deleted, if the data subject also wants their future data not to be captured, Data Controllers must ensure that the Data Suppress flag (on the device) is set to enable on all devices owned by the user. If this is not done, we will delete all data of the said user, BUT as soon as the same user logs in, we will create a new profile for the user and start capturing their data again

### 3. Access Control

Only Admin users have permission to delete user information.

### 4. Implications

a. Customer will have to stop sending Future data of the profile, thus suppressed

- Once the user hits delete for a profile, all data from any device associated with the user must also be stopped. Hence, if the delete function is called, the data controller sets the opt-out flag to the enabled state (check the right to suppress).

b. Unreachable on Marketing Channels

- Since the user's data has been deleted, there is no way to reach out to the user via marketing communication channels. Data controllers will have to opt the users out of ALL marketing channels.

c. Dashboard Implications

- You will not be able to view the user's profile page after deletion.
- You cannot roll back or erase once called. There is no way to get the information back once the delete function is invoked.
- The delete cannot be rolled back once initiated. The profile will be deleted within approximately 48 hours. Event data associated with the profile is retained separately in accordance with CleverTap's Data Retention Policy (DRP). This action cannot be rolled back once initiated.
- Funnels, cohorts, pivots, and other analytics will be affected, as the numbers may show some data inconsistencies for a short period due to data deletion.
- Users cannot download the specified user's profile information from any part of the dashboard.

### 5. Default state

The profile will be erased only by explicitly calling the API or the dashboard delete.

## Right to Modify/Rectify

### 1. What is it

This right allows users to modify/rectify any profile data stored about them

### 2. CleverTap Implementation

a. API&#x9;

CleverTap has provided this API, which allows Data Controllers to upload their users' profile information. Hence, if a Data Subject requests a profile change, the Data controller can upload the profile data of the user via the API

b. CSV Profile upload

In the settings section of your dashboard, you can upload user profiles via a CSV file. You will find it under _Settings -> Manage -> My Uploads._

### 3. Access Control

All non-members have the right to CSV upload

### 4. Implication

The old profile information will be overridden with the new profile for the given user identifier. If the user identifier is not found, a new profile will be created

### 5. Default State

Profile will be modified only by explicitly calling it via API

## Right to Access

This right allows users to access data that has been captured about them by the Data Processors

### CleverTap Implementation

a. Dashboard Download

This allows Data Controllers to download data about their specific users as a CSV file

b. API Download

This API allows users to download data about specific users via identities and/or guids

### Access Control

### All non-member users can download profile information. All users with the key can use the API download method

### Implication

Download will download the latest profile of the said user

### Default State

Profile will be downloaded by explicitly calling the download function

## Right to Data Suppress (Opt-Out)

### 1. What is it?

This right allows users to opt out of sharing any data with Data Processors.

### 2. CleverTap Implementation

a. New SDK version

- We have released an SDK update that lets you hook an opt-out flag to the CTA in your app.
- If the opt-out flag is set to disabled, we will continue collecting data from the user on the device.
- If the opt-out flag is enabled, our SDK will stop sending any data from that device to our servers. Data is blocked at the SDK level itself.

b. Multiple Devices

- If the same user logs in from another device, the Data Controller must validate the user's opt-out flag and set it accordingly.
- **Example**
  - User A has 2 devices, a1 and a2.
  - By default, opt-out is disabled on both devices.
  - A opts out of a1. In this case, opt-out will be set to enable on a1. The SDK will prevent any data from a1 from reaching CleverTap servers going forward.
  - At this time, the Data Controller should set opt-out to enable for all devices associated with A. If this is not done, when the user logs in through a2, data will flow to CleverTap servers via a2 (which violates GDPR).

c. Multiple Profiles on the Same Device

- If there are multiple users logging in to the same device where one of the profiles has set the opt-out flag to enable, CleverTap will suppress data coming from that device for that profile - refer to onUserLogin on our developer docs.
- **Example**
  - There are 2 users, A and B, who share the same device a1.
  - By default, optout is set to disable on a1.
  - A logs in to a1 and opts out of a1. In this case, optout will be set to true on a1. The SDK will prevent any data from a1 from reaching CleverTap servers going forward.
  - A logs out of a1.
  - B logs in to a1 via the ‘onUserLogin’ method, and then CleverTap sets the opt-out to be disabled by default for B.
  - If B's login to a1 is handled by the app/data controller, CleverTap will continue to suppress the data coming from a1. The Data Controller should reset the opt-out flag to disable when B logs in on the same device. If this is not done, B’s data will also be suppressed, although B has not opted out of sharing data.

### 3. Access Control

If the SDK has been updated and the updated version of the app is being used by a user, all end users have the right to suppress.

### 4. Implication

a. The profile page of the user who has opted out will be stale and will not have the latest events performed by the user.<br />b. We will auto-filter out all these users from all segment calculations and engagement (including, but not limited to, estimate reach, and so on).<br />c. All analytics data, such as funnels, flows, cohorts, etc., will not contain these users’ data.<br />d. Campaigns will not be sent to these users (even though they qualify) as the data is stale.<br />e. To validate the state of the opt-out, we will provide the flag as a profile variable on the profile page of each user.

### 5. Default state

a. By default, we will continue collecting profile and event data unless the SDK explicitly raises the flag.<br />b. Default state: opt-ou&#x74;_:disable,_ that is, CleverTap collects data from the device by default (to be compliant with GDPR, we recommend that users set this flag to enable by default, which ensures no collection of data unless explicit permission is provided by end users).



## Opt In

a. If the user who has opted out chooses to opt back in, all data will be appended to the same profile if identified as an existing user.

b. The user will be treated as the same user (we will not create a new profile for the user).

## Right to Marketing Opt Out

### 1. What is it?

GDPR provides the user the right to opt out of marketing communication.

### 2. CleverTap Implementation

a. Push Opt-out

- Our SDK has a flag `MSG-push` that, if set to disable, ensures that push notifications are blocked for the specific device.
- Our SDK has a flag `MSG-push-all`  . If set to disable, it blocks push notifications for ALL devices associated with the user.

b. SMS Opt-out

- Our SDK has a flag `MSG-sms`, which, if set to disable, ensures that no SMS is received by the phone number associated with the logged-in device.

c. Email Opt-out

- Our SDK has a flag `MSG-email`If set to disable, it ensures that no emails are received at the email ID associated with the logged-in device.
- Our SDK has a flag `MSG-dndemail` If set to disable, it ensures that no email is received at the email ID associated with the logged-in device during the DND period.
  <Callout icon="📘" theme="info">
    #### Note

    `MSG-email` controls whether a recipient receives marketing emails at all. It does not control whether their opens or clicks are tracked. To manage tracking separately from marketing consent, refer to [Manage Email Tracking Opt Out](doc:manage-email-tracking-opt-out).
  </Callout>

d. WhatsApp Opt-out

- Our SDK has a flag `MSG-whatsapp`If set to false, it unsubscribes that profile from WhatsApp messages; setting it to true resubscribes them. If the flag is never set, the profile defaults to unsubscribed.
- Our SDK has a flag `MSG-dndWhatsApp`, which unsubscribes all profiles sharing a given phone number, ensuring the number receives no WhatsApp messages from any CleverTap engagement, even across multiple profiles. Setting it to true adds the number to DND; setting it to false removes it from DND. If never set, it defaults to false (not on the DND list).

### 3. Access Control

If the SDK has been updated and a user is using the updated app, all end users have the right to opt out of Marketing.

### 4. Implication

a. If the data controller wants users to opt out of marketing communication across ALL channels, all the above flags need to be explicitly moved to the disabled state for the said profile.

b. Data Controllers need to be cognizant of sending transactional communication to the users who have opted out of marketing.

### 5. Default state

a. By default, we will continue marketing communication to said users, unless the SDK explicitly raises the flag.

b. Default state: enable, that is, we will send marketing messages by default.

## Privacy by Design

### Network Data

#### 1. What is it?

Part of the privacy-by-design notion in the GDPR.

#### 2. CleverTap Implementation

a. We have made an SDK release to allow Data controllers the capability to set 'enableDeviceNetworkInfoReporting' on individual devices.

b. When the user launches the app, the following data points WILL NOT be auto-collected:

- Android: Bluetooth, Wifi, Radio
- iOS: Wifi, Radio

#### 3. Implications

a. If the 'enableDeviceNetworkInfoReporting' is set to disabled, CleverTap will not be able to determine the location of the users based on their IP information.

b. This may affect sending out geo-targeted campaigns.

c. This may affect your ability to perform geo-based analytics.

d. The profile page of the user will not contain location information.

e. If you are using our ‘setLocation’ method, we recommend that you enable 'enableDeviceNetworkInfoReporting'.

#### 4. Access Control

If the SDK has been updated and the updated app is being used by a user, we will not collect network data for that user by default.

#### 5. Default State

enabledevicenetworkinfo’: _disable_, that is,  we will not collect network data by default.

## ADID

### 1. What is it?

Part of the privacy-by-design notion in the GDPR.

### 2. CleverTap Implementation

a. We have made an SDK release to allow Data controllers the capability to set Advertisement Identifiers (ADID): 'CLEVERTAP_USE_GOOGLE_AD_ID' (for Android) and ‘CleverTapUseIFA’ (for iOS).

b. If ADID is set to 0, when the user launches the app, CleverTap will NOT use the Advertising ID to generate a unique CleverTap ID for the said user.

c. If ADID is set to 1, when the user launches the app, CleverTap will use the Advertising ID to generate a unique CleverTap ID for the said user.

### 3. Implications

Data Controllers WILL NOT be able to search for specific profiles using the ADID. You will have to use the CleverTap to generate a unique identity to search for the said user.

### 4. Access Control

If the SDK has been updated and the updated version of the app is being used by any new user, no ADID will be shared with CleverTap for those users.

### 5. Default State

ADID: _disabled,_ that is, we will not collect ADID by default.

## FAQs

## How are profiles created on CleverTap -

1. CleverTap's SDK picks up the Google ADID for every Android device and the IDFA for every iOS device to create the CleverTap ID.

2. In case the SDK is able to successfully pick up the ADID and IDFA, respectively, the format of the CleverTap ID is as follows -

_Android_ \__g(ADID stripped of hyphens)_<br />_\_iOS_ -g(IDFA stripped of hyphens)

3. The CleverTap ID is used to identify distinct devices.

4. Later, when the end user provides his/her identity by logging in/registering, CleverTap will assign this identity to the previously anonymous profile.

## What is GDPR?

1. The General Data Protection Regulation (GDPR) came into force in May 2018 - primarily to give EU citizens more rights and control over their personal data and the information they share with businesses they deal with. Refer to [CleverTap GDPR](https://docs.clevertap.com/docs/gdpr).

2. To elaborate a little more, in the current situation, users of your app are the data subject, your app/business is the data controller, while CleverTap acts as a data processor.

3. As a data processor, our SDK captures only two data points about the user -

a) Advertising ID of the device - In case of Android, CleverTap's SDK captures the Google ADID and in case of iOS, the SDK captures the IDFA. We use this to generate a hashed CleverTap ID for device identification.<br />b) Location - Based on the latest app launch of the user, using a reverse IP lookup powered by Maxmind, CleverTap is able to capture the city-level location of the user.

Since May 2018 (SDK v3.1.9 and above), our SDKs have been GDPR-compliant, and we do not track the two data points above unless explicitly enabled. Note that all our SDKs from 3.1.9 onward are GDPR-compliant.

## How could this impact my user profiles on CleverTap?

1. If the user has uninstalled and reinstalled the app, and the SDK is not picking up the ADID and IDFA, there is no way for the SDK to identify the device as the same device. Hence, in every uninstall-and-reinstall scenario, CleverTap creates a new profile.

2. App install attribution may not work as expected if your attribution provider received the ADID, but CleverTap didn't. You wouldn't be able to perform an analysis or segment by the user's installation source. You will have to ensure that you have CleverTap GDPR compliant, and that your attribution partner is GDPR compliant

## Is GDPR applicable to me?

Under the GDPR, the location of the individual whose personal data is being processed determines whether the firm in question must comply. This means that the GDPR will apply to all organizations, whether within or outside the EU, that offer their products or services to individuals in the EU when their data is collected. In addition, the GDPR recommends that your marketing communications be on a default opt-out basis.

That said, your legal/compliance teams will be in a better position to answer whether your app/business falls under the purview of GDPR.

## GDPR does not apply to me. What next?

If GDPR doesn't apply to you, then life continues as usual for profile creation. You can simply allow [CleverTap to track the ADID and location](https://developer.clevertap.com/docs/sdk-changes-for-gdpr-compliance).

## GDPR applies to me. What next?

What your legal/compliance team needs to determine is whether allowing CleverTap to track the two data points (ADID & Location) falls within the scope of your GDPR compliance. If not, you can allow [CleverTap to track the ADID and location](https://developer.clevertap.com/docs/sdk-changes-for-gdpr-compliance).

However, if your app needs to be fully GDPR-compliant, you can disable tracking by following the steps outlined in the doc.

## What hygiene checks do I need to do?

Once you move to a GDPR-compliant SDK, you can perform some quick hygiene checks to ensure profiles are being created as per the GDPR norms applicable to you -

a) In case you need to be GDPR compliant, your CleverTap ID's wouldn't start from **g or -g.**<br />b) In case you do not need to be GDPR compliant, your CleverTap ID's would continue to start fro&#x6D;**&#x20;'**&#x67;' or '-g.'<br />c) In case you need to be GDPR compliant, but your legal team says that ADID can be tracked by CleverTap's SDK, your CleverTap IDs would continue to start from \__g or -g.
