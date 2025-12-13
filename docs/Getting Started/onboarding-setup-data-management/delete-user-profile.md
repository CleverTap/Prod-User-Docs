---
title: Delete User Profile
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
[block:api-header]
{
  "title": "Overview"
}
[/block]
This section covers how an admin can delete a user profile.
[block:callout]
{
  "type": "danger",
  "body": "Once an admin deletes a profile, the profile is permanently deleted and cannot be retrieved.",
  "title": "Permanent Deletion"
}
[/block]
#Delete a User Profile
To delete a user profile, perform the following steps:

1. From the dashboard, navigate to *Segments* > *Find People*.
2. Click on the appropriate profile once you have identified it.
3. Click **Delete Profile**.


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b8d9fbf-1_Delete_Profile.png",
        "1 Delete Profile.png",
        1415,
        527,
        "#fafafb"
      ]
    }
  ]
}
[/block]
4. On the window popup, select the checkbox to agree to delete profile data.
5. Click **Delete**.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/462245d-2_Confirm_Delete_Profile.png",
        "2 Confirm Delete Profile.png",
        412,
        336,
        "#faf6f5"
      ]
    }
  ]
}
[/block]
##Deletion Timeline
Once a profile is marked for deletion, the actual deletion happens in the next 48 hours. Every day from 2 AM to 4 AM (local time), our system fetches the profiles which are marked for deletion, then deletes them in batches.