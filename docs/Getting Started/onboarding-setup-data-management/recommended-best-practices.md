---
title: Recommended Best Practices
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
FROM PM SOUMYA: ' This section is not relevant for our customer. It mostly talks about best practices from the user perspective which is not relevant for the consumer of our documents (our clients)'

@DOCS NOTE: MAYBE MOVE TO THE BOTTOM OF [https://docs.clevertap.com/docs/data-setup\_hackathon\_wip](https://docs.clevertap.com/docs/data-setup_hackathon_wip)? SUNIL TO CONFIRM.

## Overview

This section covers some recommended best practices when performing a data setup.

# What to Consider

Consider the following recommended best practices:

* Do not use a single device as this can create multiple orphan profiles. To avoid this, your app should allow users to log in with an email ID or user identity before registering.

* Use OnUserLogin for identifying the users rather than ProfilePush for maintaining multiple profiles on a single device.

* Do not clear cache often since every time you do so, it wipes out the identity, and all the activity will be associated with the synonymous profile and create an orphan profile.
