---
title: Uninstalls View
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

The _Uninstall_ dashboard presents data on the number of users uninstalling your app, the number of new activations (first-time app launches), and the net number of new installs (new installs and total uninstalls for specific date ranges).

For more information, refer to [Uninstall Tracking](https://developer.clevertap.com/docs/uninstall-tracking).


<Image src="https://files.readme.io/91127715864d2355132e60f131972aa69ff9c56ffd47ce360a090b1efbe9bf28-Uninstall.png" alt="1719" align="center" border={true} />


To get to the uninstall view, navigate to _Boards_ > _Uninstall_.

<Callout icon="📘" theme="info">
  ### Things to Consider

  Here are some things to consider:

  - You must explicitly enable _Uninstall_ detection feature from your dashboard.
  - Uninstall detection is only available for iOS and Android apps.
  - Uninstall data is not available for Windows apps.
</Callout>

# Troubleshooting and FAQ

### Q. Why are most of my uninstalls tracked between 2 AM and 4 AM?

CleverTap runs a daily task at 2 AM (local time) to detect the number of uninstalls. You can account for this time to create campaigns and journeys to win back these users.
