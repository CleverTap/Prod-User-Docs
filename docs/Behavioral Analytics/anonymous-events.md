---
title: Anonymous Events
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
@DOCS: AFTER PUBLISHING, CONSIDER LEAVING A HYPERLINK ON THE FOLLOWING 2 EXISTING LINKS:\
[https://docs.clevertap.com/docs/user-profiles#user-scenarios-for-anonymous-profiles](https://docs.clevertap.com/docs/user-profiles#user-scenarios-for-anonymous-profiles)\
[https://docs.clevertap.com/docs/upload-past-user-profiles#section-existing-profiles](https://docs.clevertap.com/docs/upload-past-user-profiles#section-existing-profiles)

## Overview

Anonymous events refer to a non-logged-out state within CleverTap. These events are still captured on the profile with the same CTID which has been logged out and it only works with the first device. Anonymous events from a second and third device (and so on) will be blacklisted and not captured.

The user can view all the events and its reachability in the entire blacklisted profile in the gray area. This happens when there are multiple identities on the profile. Due to the OnUserLogin being called after every cache, this creates an identity hence the profile becomes blacklisted. When the reachability is in the grey area, it is not possible to reach the user via any communication.

@PM: SEEMS LIKE WE COULD BENEFIT FROM A SCREENSHOT BELOW THE OVERVIEW. WOULD YOU BE ABLE TO HELP PROVIDE ONE? THANKS.

# Event and Profile Blacklisting

When you have users with events that are shown in the grey background, it means that these users have done these events before they identified themselves (identity being pushed to CleverTap); these events are called anonymous events. 

The way a user is identified on CleverTap depends on the way data is stored for an account. It is stored across multiple databases for faster execution of queries and faster technical assistance test. The profile blacklisting affects users who are already identified on CleverTap (i.e., their identity already exists and then, they log in from a new device).

# Anonynous Event Example

In this example, an existing profile is on database 1 which is the earlier existing profile with the given identity. Now, the user is attempting to log in again on a new device. In this case, since the device is new and the user is still anonymous, we create an anonymous profile. Given the number of databases, the probability that this user is on a different database is high.

The database number is decided on the basis of our internal algorithm with regards to the CleverTap device ID. Once the user logs in to the new device, the profile is then updated with the identity, and since the identity already exists on the account, we merge the profiles.

In these types of scenarios, all anonymous events performed by this user when they were anonymous on device 2, then the events are blacklisted. As the new profile is present on a different database, the profile is blacklisted but is given in the *Find People* or the events dashboard when we try to execute the query.
