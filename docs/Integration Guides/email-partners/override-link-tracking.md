---
title: Override Link Tracking
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
To track clicks on email links, CleverTap redirects links in your email body first to a CleverTap server and then back to your landing page. 

If you are using a mobile app deeplink in your email body, you might want to avoid this redirection. You can do this by setting the following tag in your email body:

```html
<a data-track="off" href="donotoverrride"> Your link </a>
```

Setting this tag will ensure that CleverTap does not redirect the links that you have specified in your email body.

> 🚧 If you set this tag, CleverTap will not be able to track clicks on your email message.
