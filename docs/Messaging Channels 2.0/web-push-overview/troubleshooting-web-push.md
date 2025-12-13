---
title: Troubleshooting
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
# Campaign Considerations

Below are some things to consider for Safari.

## Safari Considerations

Safari, being a proprietary browser, has some built-in restrictions. Following are the considerations with Safari web push as compared to Chrome or Firefox:

* Deep link URL is mandatory or else the notifications will not be rendered.
* Custom icons are not rendered in the notifications as Safari uses the icons available in the Safari push package.
* Image and call to action buttons are not available for Safari notifications.
* Sent and viewed events are not supported as there is no handler unlike Service Worker in Chrome and Firefox to capture the click and view events.

## Safari Errors

You may encounter the following errors while sending web push notification on Safari:  

* Invalid Authentication
* BadRequest(400)
* DeviceTokenInactiveForTopic(410)
* ServerUnavailable(503)
