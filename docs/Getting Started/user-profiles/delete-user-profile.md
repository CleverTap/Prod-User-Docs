---
title: Delete User Profile
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
## Overview

This section covers how an admin can delete a user profile.

<Callout icon="❗️" theme="error">
  ### Permanent Deletion

  Once an admin deletes a profile, the profile is permanently deleted and cannot be retrieved.
</Callout>

# Delete a User Profile

To delete a user profile, perform the following steps:

1. From the dashboard, go to _Segments_ > _Find People_.
2. Click on the appropriate profile once you have identified it.
3. Click **Delete Profile**.


<Image src="https://files.readme.io/b8d9fbf-1_Delete_Profile.png" alt="1415" align="center" border={true} />


4. In the window pop-up, select the checkbox to agree to delete profile data.
5. Click **Delete**.


<Image src="https://files.readme.io/462245d-2_Confirm_Delete_Profile.png" alt="412" align="center" border={true} />


## Deletion Timeline

Once a profile is marked for deletion, the actual deletion happens within approximately 48 hours. Our system processes profiles marked for deletion during a maintenance window (2 AM–6 AM local time) and deletes them in batches.

<Callout icon="📘" theme="info">
  ### Note

  For each user profile deleted, the events will be saved with CleverTap as per the data retention policy
</Callout>

<Callout icon="📘" theme="info">
  ### Bulk Delete Profiles

  You can bulk delete profiles using the API. For more information, refer to the [delete user profile API](https://developer.clevertap.com/docs/delete-user-profile-api).
</Callout>
