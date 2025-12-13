---
title: FELICE_Push Notification_overview_hackathon
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
@DOCS: GET RID OF THIS PAGE AFTER PULLING OUT THE SUB-SECTION OUT ONTO NEW USER DOCS.

(iii) Product Feature : Send Test Push Notifications
Approach 1 : If the requirement is to send the push notification to a user for a specific campaign content, this can be sent during the creation of the campaign. 

Under the What section of campaign creation flow, you have the option to send a test push notification to any CleverTap user profile you have marked as a Test profile.

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Approach 2 : Alternatively, on a specific user profile page, you can initiate “Send Push” for the required device to send test push notifications to the user. 

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
(iv) Product Feature : Token moves to the latest  profile when there are multiple logins - test push notifications
If a user has multiple devices associated with a profile, then the push notification from the campaign that he has qualified into will be received by the latest device, through which the event is being captured in real time. As the campaign sends notification to the latest active device. 
So in this case the token is moved to the latest profile. 
If a user does multiple logins after clearing the cache every time, then a new firebase token is created for the device.   
FAQ:
How do I analyse the CTA button for a push campaign?
To track the number of clicks on the click to action (CTA) buttons of the push notification, you can check so by navigating to:
Analytics → "Events"
Query for the "Notification Clicked" event filtered by the Campaign 
On the result, go to "Trend & Properties", then scroll down to the "Event property" table and filter in the dropdown by "wzrk_c2a" to see a distribution of clicks across the various buttons on that respective campaign.


Why is the push notification image not rendering for android?
Rendering of the image in a push notification is dependent on 3 factors:
Image size: The image size should be less than 40Kb.
User's internet connection: The OS (both Android and iOS) tries to download the image for ~10 seconds. If within this time, it is unable to download the image, the push is rendered only with title and message without the image.
CDN(Content Delivery Network) throughput: As the OS downloads the image every time a push is sent to a user, the CDN you are using to host the images also needs to be scalable. Say, the notification is sent to 5 mn users, for all these users, the OS tries to download the image from the CDN and it should be scalable for a base like this.

Chinese OEMs not receiving the notification or why the images are not being rendered on the push notifications?
Battery optimization plays an important role in image not rendering on a push notification.
For Battery Optimisation, the Chinese handsets have tweaked the OS to enhance battery life. This is prominent across makes like Oppo, One Plus, etc. Because of the battery optimisation layer, sometimes, the app kills the background services and does not render the notification. We have seen this behaviour vary from user to user who is using a One Plus device based on the app’s usage pattern by the user along with his device usage and timings. Additionally to update you, if the notification is clicked as soon as it is received, the app might open irrespective of the settings. However, if the notifications stays in the user’s tray for a certain time (threshold we have seen vary from device to device) on clicking the notification the app does not open.
Please find the further details as follows:
Based on our observations, in One Plus Devices: 
When you go under “Settings” -> “Recent App Management” , you have two options available. “Normal Clear” and “Deep Clear”, we have observed that whenever “Deep clear” is selected, clicking on a notification does not open the app
Along with “Recent App Management”, there is Battery Optimisation, which has two options under “Advanced optimisation” -> “Deep optimization” & “Sleep standby optimization”.
This option also makes it possible for the app not opening on clicking the notification
Also, we have seen this behaviour vary from user to user who is using a One Plus device basis the app’s usage pattern by the user

What is the recommended image dimension in push notifications with CTA? 
Aspect ratio: 16:9 and Recommended Size - 533.33 X 300 pixels minimum.
Supported file types are PNG, JPG, JPEG
Max size: 40Kb
We would recommend maintaining an Aspect ratio of 16:9. You will need to adjust the dimensions accordingly. Sharing a calculator below for reference:https://calculateaspectratio.com

If I send a push notification to my users but their device is inactive at that moment then when they open it again, does the notification appear for them? 
If the user device is inactive which can happen if the user’s internet service is off or if the phone is switched off or out of network/coverage area the user will not receive any notification but when the user receives connectivity then push notification will be delivered within TTL period.  


How can I map device ID with customer ID to find the profile? 


To identify the to map the mobile devices on any profile we need to find the profile for which each device id belongs. Which can be identified from CT-ID or the identity associated with the device.











My application infrastructure can only support handling 100K users in a given time duration. How do I achieve this rate limiting from CleverTap while sending push notifications?
This can be achieved via setting up throttle for campaigns. The push campaign adheres to the throttle limit that is set for push notifications in the Campaign Limits under Account Settings.
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
This can then be enabled/disabled during the setup of campaign creation.



[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]