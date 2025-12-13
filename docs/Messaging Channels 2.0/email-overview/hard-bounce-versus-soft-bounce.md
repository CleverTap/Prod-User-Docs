---
title: Hard Bounce Versus Soft Bounce
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
Reference Confluence page:  [https://wizrocket.atlassian.net/wiki/spaces/SUC/pages/1720386423/SendGrid+Email+Onboarding](https://wizrocket.atlassian.net/wiki/spaces/SUC/pages/1720386423/SendGrid+Email+Onboarding)

[https://docs.google.com/document/d/1LO9-QvAUs8\_Pzt-7G-2wDjo0726ScrU3aNPNsruYJdo/edit](https://docs.google.com/document/d/1LO9-QvAUs8_Pzt-7G-2wDjo0726ScrU3aNPNsruYJdo/edit)

## Overview

When an email bounces in general, it means that it cannot be delivered to an inbox. Hard and soft designate the two groupings of delivery failures. A hard bounce is more permanent than a soft bounce which is less permanent. 

# Hard Bounce

A hard bounce is an email that could not be delivered for permanent reasons. There are lots of reasons that an email could be a hard bounce. Some reasons include:

* The email is a fake address.
* The email domain is not a real domain.
* The email recipient's server will not accept emails. 

The core problem is that it is a permanent failure, so you should remove all of these addresses from your email list.

# Soft Bounce

A soft bounce is an email that could not be delivered because of temporary reasons. Some reasons include:

* An inbox may be full.
* The email file might be too large.

If they get a soft bounce on an email send, most email providers will continue to try to deliver the email over the period of a few days. You should keep an eye on these addresses but if you notice that the same ones are popping up over and over again, it is best to remove them.

# Tips

Try to keep your total bounce rate under 2%. If that percentage becomes much higher than that, and you will start noticing some deliverability issues.
