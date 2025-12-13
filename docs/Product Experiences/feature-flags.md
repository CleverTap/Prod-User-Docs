---
title: Feature Flags
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
DOCS NOTE: BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE IS UNPUBLISHED AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES: [https://docs.clevertap.com/docs/product-experiences](https://docs.clevertap.com/docs/product-experiences)

## Overview

Feature flags provide the capability for product managers to remotely turn a feature on or off on your app without any latency or coding. This lets you display a new feature to a user segment and an existing functionality to the remaining segment. 

# Example

For example, you want to want to enable an automatic playlist of recommended videos on your app. While this is a useful feature, it freezes the app screen for some versions of iOS. You want the following options:

* You must be able to target iPhone users.  
* You want to test it on 20% of New York users and 30 % of Miami users before you roll it out to all users. 
* You must also be capable of disabling the feature if it needs more work. 

Feature flags can enable or disable a feature with a simple toggle. You can also test the feature on your users before you make it available to everyone. Your users will now have access to the feature and enjoy a better experience. 

# Use Cases 

The following use cases demonstrate how feature flags can be used:

* Show targeted TV content to beta users.
* Show specific buttons to fast-forward or jump to the next episode to a user segment.

In both cases, you can enable the feature only for a selected few people and if everything looks good, you can enable it for the entire audience. If you run into some bugs in the feature, you can simply disable it by turning off the feature instantly while product teams fix the issue. 

# Create Feature Flags

To create feature flags, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Feature Flags*.  
2. Click **+ Feature Flag** to create a new feature flag. 

![1395](https://files.readme.io/1b7eee7-Plus_feature_flag.png "Plus feature flag.png")

3. Enter the name and description for your feature flag. 
4. Select the segments and keys for your feature flag. The keys are the keys that you have assigned in your app for each feature and the segments are the group of users who will receive this feature. 

For example, select the iPhone users in New York and iPhone users in Miami segment. Select the keys called *Auto Playlist* key.  For more information on creating keys, refer to [Keys](https://docs.clevertap.com/docs/product-config#section-create-keys).

> 📘 Boolean Values and Key Limit
>
> A feature flag can only have boolean values such as, true or false. A key can only be used in one feature flag.

5. Under *Key value and priority*, add the set key value for each segment. 
6. Toggle the selected segment and define the percentage of users who will receive this change. 

<Image title="ProductExp_Feature_Flag_Create.png" alt={779} className="border" width="100%" border={true} src="https://files.readme.io/683d874-ProductExp_Feature_Flag_Create.png" />

6. Publish your feature flag or schedule it to a later date.

<Image title="ProductExp_feature_flag_schedule.png" alt={698} className="border" border={true} src="https://files.readme.io/88c5406-ProductExp_feature_flag_schedule.png" />

# Edit or Archive Feature Flags

To edit or archive a feature flag, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Feature Flags*. 
2. Click the ellipsis menu to edit or archive a product config.  

![1402](https://files.readme.io/9db3548-Edit_or_Archive_Feature_Flags.png "Edit or Archive Feature Flags.png")

> 📘 Feature Flag Changes
>
> Any changes to a feature flag are saved in a new version. You can always revert to an earlier version.

# View Statistics

The stats show you the distribution and value of the key stats for your feature flag. To view stats for a feature flag, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Feature Flags*.  
2. Click the feature flag from the list and scroll down to view the stats. 

You can view the following information:

* You can see a trend of the total number of keys delivered for all segments or a particular segment from the first chart.
* In the second box, you can further break it down to get the count of each type of key value.

![723](https://files.readme.io/be9202d-ProductExp_Feature_Flags_Stats.png "ProductExp_Feature_Flags_Stats.png")

# Feature Flag Version

A new version is created every time you edit a feature flag. If the current feature is not working for some reason, you can always revert to an older version of the feature flag:

To revert to an older version, perform the following steps:

1. From the dashboard, navigate to *Product Experiences* > *Feature Flags*.  
2. Click the ellipsis menu to edit a feature flag.  

![1402](https://files.readme.io/cca3987-Edit_or_Archive_Feature_Flags.png "Edit or Archive Feature Flags.png")

3. Click the required version number on the right side, then click **Publish Version**. The selected version becomes active and the current version becomes inactive. 

<Image title="feature flag version.png" alt={1181} className="border" width="100%" border={true} src="https://files.readme.io/bbe4adc-feature_flag_version.png" />
