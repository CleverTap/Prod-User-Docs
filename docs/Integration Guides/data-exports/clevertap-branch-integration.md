---
title: CleverTap <> Branch Integration
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
We’ve improved our deep linking integration with Branch for email. Marketers can now directly route users to the app from an email, bypassing the web browser.\
This ensures a seamless user experience and reduces dropoffs as users are redirected to the app or an app store

# Who will the integration work for ?

This integration will work only for clients who have a Branch and Sendgrid account.

# Steps for integration

1. App should have the Branch SDK.
2. CNAME the sendgrid domain to Branch. [https://help.branch.io/using-branch/docs/universal-email-integration-guide](universal-email-integration-guide).

# Steps to use deeplinks

1. Ensure that you send emails using the Sendgrid account that has been CNAMED to Branch.
2. Ensure you add universal = "true" parameter at the end of your deeplinks , this converts the deeplink into a universal link.

```text
<p><a href="http://cdn.branch.io/branchster-angular/?body_index=4&color_index=2&face_index=1&monster=true&monster_name=DLE_Deep_link" universal="true">Deep_Link</a></p>
```

# What elements from the Email editor can be used for sending deeplinks ?

1. You can use the HTML and Custom HTML elements to form and embed deeplinks in your email.
2. Be sure to test the email once before you deploy as sometimes the deeplinks can be malformed.
