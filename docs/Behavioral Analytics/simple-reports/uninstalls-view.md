---
title: Uninstalls View
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
# Overview

The *Uninstall* dashboard presents data on the number of users uninstalling your app, the number of new activations (first-time app launches), and the net number of new installs (new installs and total uninstalls for specific date ranges).

For more information, refer to [Uninstall Tracking](https://developer.clevertap.com/docs/uninstall-tracking).
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/07773d4-f469e26-Analytics_View_Uninstall.png",
        "f469e26-Analytics_View_Uninstall.png",
        1719,
        658,
        "#fcfbfc"
      ]
    }
  ]
}
[/block]
To get to the uninstall view, navigate to *Boards* > *Uninstall*.
[block:callout]
{
  "type": "info",
  "body": "Here are some things to consider: \n * You must explicitly enable *Uninstall* detection feature from your dashboard.\n * Uninstall detection is only available for iOS and Android apps. \n * Uninstall data is not available for Windows apps.",
  "title": "Things to Consider"
}
[/block]


# Troubleshooting and FAQ

### Q. Why are most of my uninstalls tracked between 2 AM and 4 AM?
CleverTap runs a daily task at 2 AM (local time) to detect the number of uninstalls. You can account for this time to create campaigns and journeys to retain these users.