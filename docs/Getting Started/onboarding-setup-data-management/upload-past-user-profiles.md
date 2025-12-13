---
title: Upload Past User Profiles
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
[block:api-header]
{
  "title": "Overview"
}
[/block]
This section covers how identified user profiles are treated in the CleverTap dashboard.

#Already Identified User

When already identified users visit your app or website from another device or browser, CleverTap creates new profiles for such users. Once they identify with their identities on the app or website through login for example, CleverTap merges the newly created profile with the already present user profile and all the events that were recorded on the new profile before the user identification is blacklisted. 

These events are shown with a gray background on the user profile. Even though the profiles are merged together, they are stored in two separate memory locations in CleverTap.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cebe9ee-1_Upload_Past_User_Profiles.png",
        "1 Upload Past User Profiles.png",
        837,
        319,
        "#f6f7f9"
      ]
    }
  ]
}
[/block]
#Existing Profiles
If a user has an existing profile stored in your CleverTap account and if the user buys a new device and downloads your app and perform some events on this app without sign-up or log-in, the device does not know that this user has an existing profile. Therefore, the system creates an anonymous profile and stores the events in this newly created profile.

Once the user shares her identity (e.g., email, mobile phone number, or Google advertising ID) to the anonymous profile for example while login, then this profile gets merged with the user's original profile but the events captured before passing the identity are saved in an orphan profile with only a CleverTap ID and no email, mobile phone number, and other useful properties.

In this case, there is no use in qualifying orphan profiles in campaigns or journeys. However, to keep clear data as to how many profiles have been created on the CleverTap dashboard, we include the orphan profiles in the *Find People* count but these profiles are not included when downloaded.