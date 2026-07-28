---
title: Control Groups
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
# Overview

Marketing teams typically run various campaigns and journeys to onboard, convert, and retain their users. However, it is hard to measure the efficacy of these campaigns and journeys independently. For example, was the purchase increase today due to the reminder email we sent last night, or could it have been that those users would have bought anyway without the reminder?

A control group is a set of users marked to be excluded from all marketing campaigns. You can measure the effectiveness of your initiatives by comparing this group with the target group of users who received your campaigns.

CleverTap allows you to measure and track the performance of your engagement efforts by comparing it to the Control Group

You can create 4 different types of Control Groups:-

- System Control GroupThe&#x20;
  - System Control Group is created for your entire user base
  - You can create one System Control per account
  - You can create a system control group of size between 2% to 5%
- Custom Control Group
  - Custom Control Group is created on your entire user base
  - You can create up to 10 Custom Control Groups per account
  - You can create a custom control group of size between 2% to 5%
  - Custom Control Groups are generally created for short-duration strategies<br />For example, determining engagement impact for Christmas campaigns
- Campaign Control Group&#x20;
  - The Campaign Control Group is created on the user base that qualifies for the campaign.
  - You can create a campaign control group at the time of campaign creation.
  - You can create a campaign control group of size between 2% to 99%
- Journey Control Group
  - Journey Control Group is created on the user base that qualifies for the journey.
  - You can create a journey control group when creating the journey.
  - You can create a journey control group of size between 2% to 99%

# Control Group Qualification

- When a Control Group is created, it includes all users who are part of the application at that time.<br />For example, if a 5% Control Group is created, then every 1 in 20 users will be a part of the Control Group.
- This selection of users who are a part of the Control Group is completely random. We do not introduce any bias for qualification
- For all new users who join the application after the control group is created, qualification for the Control Group will be based on the size of the control group.<br />For example, if a 5% Control Group is created, every 1 in 20 new users will be a part of the Control Group

# Creating a System Control Group

1. You can create a system control group from _Settings_ > _Control Group_.<br />Here, you can create a System Control Group


<Image src="https://files.readme.io/cdfc1f4-Screenshot_2020-06-09_at_4.35.14_PM.png" alt="1001" align="center" caption="Create a System Control Group" border={true} />


2. You can apply the Control Group to existing campaigns and journeys by selecting _Apply to all current campaigns and journeys_.

<Callout icon="🚧" theme="warn">
  #### **Important Note**

  After you make this selection, you cannot change it.
</Callout>


<Image src="https://files.readme.io/1af5b41-Screenshot_2020-06-09_at_4.36.00_PM.png" alt="703" align="center" caption="Apply System Control Group to All Journeys and Campaigns" border={true} />


3. Now, you will be able to see the details of the system control group you created


<Image src="https://files.readme.io/7fc7693-Screenshot_2018-12-28_at_4.01.09_PM.png" alt="763" align="center" caption="System Control Group Details" border={true} />


# Creating a Custom Control Group

<Callout icon="📘" theme="info">
  #### **Note**

  Custom Control Group can be created only after you have a created a System Control Group.
</Callout>

1. When you move to _Custom Control Group_ and create a new custom control group, a new group will be created for you.


<Image src="https://files.readme.io/e15bc24-Screenshot_2020-06-09_at_4.39.47_PM.png" alt="985" align="center" caption="Create a Custom Control Group" border={true} />


2. Once you click on **+ Create New**, you are prompted to provide a name, purpose, and control group size


<Image src="https://files.readme.io/3243bbf-Screenshot_2018-12-28_at_4.13.51_PM.png" alt="458" align="center" caption="Enter Details for Custom Control Group" border={true} />


3. Now, you will be able to see the details of the custom control group(s) you created<br />You can create up to 10 Custom control groups


<Image src="https://files.readme.io/dc6291f54714ec95d8c57a97e49e9249e011a66a2e6c52406324b5b9cd52377f-Custom_Control_Group.png" alt="1247" align="center" caption="View Details of all Custom Control Groups" border={true} />


# Campaign and Journey Creation

<Callout icon="❗️" theme="error">
  #### **Removing System Control Group**

  Although CleverTap provides the option to remove the System Control Group, we recommend to only use this option for transactional messages. Removing the System Control Group will impact the campaign and journey reports
</Callout>

## Campaign Creation

After you have created a System and/or Custom control group, you can now use this control group in your campaigns. In the campaign creation workflow, when in the _Setup_ section, you are given the option to add/remove the Control Group

- The system control group is applied by default for every campaign.
- You can choose to add a Custom control group to the campaign.
- Optionally, you can also add a _Campaign_ control group. This control group will be applicable only to the related campaign.


<Image src="https://files.readme.io/78b2456-Screenshot_2020-06-09_at_4.47.17_PM.png" alt="1122" align="center" caption="Use Control Groups in Campaigns" border={true} />


## Journey Creation

After you have created a System and/or Custom control group, you can now use this control group in your _Journeys_.<br />In the entry node of the Journey, you are given the option to add/remove the Control Group.

- The system control group is applied by default for every campaign.
- You can choose to add a _Custom_ control group to the campaign.
- Optionally, you can also add a _Journey_ control group. This control group will be applicable only to the related journey.


<Image src="https://files.readme.io/dc3a90d-Screenshot_2020-06-09_at_4.50.20_PM.png" alt="1066" align="center" caption="Use Control Groups in Journeys" border={true} />


# Reporting Stats

1. Campaign or Journey Qualification

- All users who have qualified for the campaign based on the _Who_ section selected by you.
- In Journeys, all users who have qualified for the _Who_ section you selected in the entry node are included.
- This will include users who are a part of the Control Group qualification.

2. Control Group Qualification

- All users who have qualified for the system or custom control group

3. Control Group Qualification for the campaign

- All users who have qualified for the campaign AND were qualified to be a part of the Control Group
- There may be users who are part of the Custom Control Group or System Control Group, but do not qualify for the campaign. These users will not be a part of the Control Group for this campaign.
- There may be users who are a part of the Control Group, but do not qualify for the campaign. These users will not be a part of the Control Group for the campaign in question.

4. Control Group Qualification for the journey

- All users who have qualified for the journey AND were qualified to be a part of the Control Group
- There may be users who are a part of the Custom Control Group or System Control Group, but do not qualify for the journey. These users will not be a part of the Control Group for this journey.

**Note**: If the _Campaign_ or _Journey_ qualifies a very small user base, there may be a condition, that no user from the qualified based is a part of the Control Group. In that case, we will not showcase the Control Group stats for that campaign.

<Callout icon="🚧" theme="warn">
  #### Deleting Control Group

  If a Control Group is deleted when campaigns and journeys are running with the Control Group, the corresponding campaign and journey report will be impacted
</Callout>

Once a campaign or a journey is created with a Control Group, the stats for it can be viewed on the stats page<br />Here you can see:

1. Number of users in the Control Group
2. Conversions of Target Group w\.r.t. Control Group
3. Revenue of Target Group w\.r.t. Control Group

   Revenue is calculated as ARPU (Average Revenue Per User)<br />\*\* where ARPU = Total Revenue / number of users

# Control Group Exports

<Callout icon="📘" theme="info">
  #### **Exports Disabled**

  Currently, the Journey Control Group exports option is disabled. If you want to enable this option, contact your Customer Success Manager.
</Callout>

Control group users can be exported to AWS S3. The option is available via _Settings_ > _Partners_ > _Exports_. To export control groups:

1. Click the **Create Export** button and choose the export partner.


<Image src="https://files.readme.io/90e5931-CreateExport.jpg" alt="Export Control Groups" align="center" width="90% " caption="Export Control Groups" border={true} />


2. Enter the following details to export the control group users:
   - **Type**: Select the export **Type**. Select events (you can choose multiple values here).
   - **Frequency**: Select the export frequency.
   - **Dates to export data**: Select the days you want to export the data.
   - **Format**: Select the export format from the available options: JSON, XML, CSV, or Parquet.
   - **Export data as a string**: Select this option to export data in string format.


<Image src="https://files.readme.io/c7f5f76-CreateNewS3.jpg" alt="Create an Export" align="center" width="90% " caption="Create an Export" border={true} />


When selecting events for exporting the control group, the following control groups are available:

- System Control Group
- Custom Control Group
- System Control Group (Journeys)
- Custom & Journey Control Group (Journeys)

If a user is part of a control group, then for each campaign, that the user qualifies for within the selected days to get data, there will be one entry present in the export. For example, if user A is part of the system control group and it qualifies for campaign ABC and campaign XYZ, then in _System Control Group_ export, we will have two entries for this user, one for each campaign. The same is applicable to all control group exports for journeys.

## System Control Group

Export System Control Group users' data in all campaigns within the selected days.

JSON format Example -

```json
{"ts":20200319221000,"eventName":"Control Group","profile":{"all_identities":["jamessmithi19020907-0@testwiz.com"],"platform":"iOS","name":"JamesSmith","email":"jamessmithi19020907-0@testwiz.com","push_token":"ios-19020907-0","phone":119021007089},"deviceInfo":{"make":"Apple","model":"iPhone8,1","appVersion":"App Version 4","sdkVersion":"0","osVersion":"9.1"},"controlGroupName":"System Control Group","eventProps":{"Campaign id":"1584635757","Campaign name":"ok","Campaign type":"Mobile Push - iOS"}}
```

## Custom Control Group

Export Custom Control Group users' data in all campaigns within selected days. Each entry has a Control group name.

JSON format Example -

```json
{"ts":20200319221000,"eventName":"Control Group","profile":{"all_identities":["johnjohnsoni13120107-3@testwiz.com"],"platform":"iOS","name":"JohnJohnson","email":"johnjohnsoni13120107-3@testwiz.com","push_token":"ios-13120107-3","phone":119112607389},"deviceInfo":{"make":"Apple","model":"iPhone8,1","appVersion":"AppVersion0","sdkVersion":"0","osVersion":"9.2"},"controlGroupName":"CustomCG1","eventProps":{"Campaign id":"1584635757","Campaign name":"ok","Campaign type":"Mobile Push - iOS"}}
```

## System Control Group (Journeys)

Export System control group users' data in all Journeys within the selected days.

JSON format Example -

```json
{"ts":20200317193200,"eventName":"Journey Control Group","profile":{"all_identities":["jamessmithi19020907-0@testwiz.com"],"platform":"iOS","name":"JamesSmith","email":"jamessmithi19020907-0@testwiz.com","push_token":"ios-19020907-0","phone":119021007089},"deviceInfo":{"make":"Apple","model":"iPhone8,1","appVersion":"App Version 4","sdkVersion":"0","osVersion":"9.1"},"controlGroupName":"System Control Group","eventProps":{"Journey id":"171","Journey name":"PBS_All_users"}}
```

## Custom & Journey Control Group (Journeys)

Export data for Custom and Journey control group users in all Journeys within selected days. Each entry will have a Control group name. For the Journey control group, the value of this field is **Journey Control Group**.

JSON format Example (Custom control group user) -

```json
{"ts":20200310230600,"eventName":"Journey Control Group","profile":{"identity":"123","all_identities":["123"],"platform":"iOS","name":"Kritii Agrawal","push_token":"3dbf357c5a6db427714343d52f10cbf9d4b1c3859f96423370dcd595370363b2","phone":919833108201},"deviceInfo":{"make":"Apple","model":"iPhone9,3","appVersion":"2.0.0","sdkVersion":"30401","osVersion":"Others","dpi":326,"dimensions":{"width":58,"height":103,"unit":"mm"}},"controlGroupName":"Test group A","eventProps":{"Journey id":"145","Journey name":"trigger on jn 144 step 4- Testing Event"}}
```

JSON format Example (Journey control group user) -

```json
{"ts":20200310230600,"eventName":"Journey Control Group","profile":{"identity":"123","all_identities":["123"],"platform":"iOS","name":"Aditi Agrawal","push_token":"3dbf357c5a6db427714343d52f10cbf9d4b1c3859f96423370dcd595370363b2","phone":919833108201},"deviceInfo":{"make":"Apple","model":"iPhone9,3","appVersion":"2.0.0","sdkVersion":"30401","osVersion":"Others","dpi":326,"dimensions":{"width":58,"height":103,"unit":"mm"}},"controlGroupName":"Journey Control Group","eventProps":{"Journey id":"145","Journey name":"trigger on jn 144 step 4- Testing Event"}}
```

```json
{"ts":20200310230600,"eventName":"Journey Control Group","profile":{"identity":"123","all_identities":["123"],"platform":"iOS","name":"Kritii Agrawal","push_token":"3dbf357c5a6db427714343d52f10cbf9d4b1c3859f96423370dcd595370363b2","phone":919833108201},"deviceInfo":{"make":"Apple","model":"iPhone9,3","appVersion":"2.0.0","sdkVersion":"30401","osVersion":"Others","dpi":326,"dimensions":{"width":58,"height":103,"unit":"mm"}},"controlGroupName":"Test group A","eventProps":{"Journey id":"145","Journey name":"trigger on jn 144 step 4- Testing Event"}}
```

JSON format Example (Journey control group user) -

```json
{"ts":20200310230600,"eventName":"Journey Control Group","profile":{"identity":"123","all_identities":["123"],"platform":"iOS","name":"Aditi Agrawal","push_token":"3dbf357c5a6db427714343d52f10cbf9d4b1c3859f96423370dcd595370363b2","phone":919833108201},"deviceInfo":{"make":"Apple","model":"iPhone9,3","appVersion":"2.0.0","sdkVersion":"30401","osVersion":"Others","dpi":326,"dimensions":{"width":58,"height":103,"unit":"mm"}},"controlGroupName":"Journey Control Group","eventProps":{"Journey id":"145","Journey name":"trigger on jn 144 step 4- Testing Event"}}
```

# FAQs

### Do Control Group users re-enter a recurring journey when "Allow re-entry" is enabled?

Yes. When a Control Group user (System, Custom, or Journey CG) exits a journey, via goal completion or timeout, and Allow re-entry is enabled, they become eligible to re-qualify in subsequent cycles, just like Target Group users.

### If a user was in the Control Group once, will they stay in the Control Group on every re-entry?

Group assignment is re-evaluated on each re-entry. A user who was in the Control Group in one cycle is not guaranteed to stay in the Control Group on the next; they could be assigned to the Target Group, and vice versa. Control Group membership is determined per-qualification, not locked to the user for the life of the journey.

### How does this affect my reported Target vs. Control split over time?

Your reported Control Group and Target Group percentages will track your configured split consistently across all recurrence cycles. This means the Control Group share remains stable rather than shrinking over time as users re-enter and are reassigned.&#x20;

The Target Group and Control Group stats are computed and marked on the same day, so day-wise node stats between the two groups stay aligned.

# Video Tutorials

### Understanding Control Groups

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/eN1vAaBZWwOe7oPkIlOBdA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

### Using Control Groups

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/cKjWmj3wAAyCxYiQ2jeFZA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

<br />
