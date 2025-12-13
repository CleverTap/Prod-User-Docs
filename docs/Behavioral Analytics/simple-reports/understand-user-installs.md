---
title: User Installs View (Deprecated)
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
# Overview

You can use the CleverTap dashboard to track the number of app installs you are seeing and their details. Using CleverTap, you can realize common use-cases like\
– Report daily/weekly/monthly install rate\
– Find the number of users re-installing your app\
– View attribution details for app installs

# Tracking App Installs

In CleverTap, there’s a system event called “App Installed”, this event is raised automatically by the Android and iOS SDKs. The “App Installed” event is raised every time a user installs the application, and is raised when the first launch the app, post install.

This event includes all app install events – direct, organic and those coming from paid sources.

# Attributing Paid Installs

If you are using an attribution provider (such as Branch.io or AppsFlyer), you can integrate that provider with CleverTap to attribute installs to their acquisition source. You can view details of these installs and their sources by selecting the “UTM Visited” event in your CleverTap Dashboard, and filtering it by the property “Install = Y”. Once, this has been selected, you filter by an additional “UTM Source”, “UTM Medium” or “UTM Campaign” and use this information, for both analytics and engagement.

For you to track paid installs, its necessary that you integrate an attribution provider with CleverTap.
