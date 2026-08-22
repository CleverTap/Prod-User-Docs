---
title: Roles
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
DOCS NOTES

* BEFORE PUBLISHING THIS DOC, ENSURE THAT THE EXISTING PAGE ([https://docs.clevertap.com/docs/role-based-access-control](https://docs.clevertap.com/docs/role-based-access-control)) IS UNPUBLISHED (OR DELETED) AND THAT ALL ITEMS FROM THE EXISTING PAGE ARE COVERED IN THE NEW (HACKATHON) SUBPAGES
* [https://docs.clevertap.com/docs/add-role#section-add-a-custom-role](https://docs.clevertap.com/docs/add-role#section-add-a-custom-role) NEEDS TO BE PUBLISHED AT THE SAME TIME AS THIS PAGE 

## Overview

As a part of our commitment to account security, CleverTap offers role-based access control (RBAC) for account admins to enable different levels of access for dashboard users. 

> 📘 Advanced RBAC
>
> Advanced RBAC lets admins customize roles.

<HTMLBlock>{`
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;">A Blue Heading</h1>

<p style="color:red;">A red paragraph.</p>

</body>
</html>
`}</HTMLBlock>

# System Roles

CleverTap provides three standard system roles for every account (Admin, Creator, and Member). These roles cannot be cloned, deleted, or edited.

## Admin

The Admin system role provides full and unlimited access to the account, including:

* Assign new users as Admin, Creator, or Member.
* Revoke access of an existing user.
* Create campaigns.
* Stop and archive campaigns.
* Approve or reject campaigns created by users in the Creator role.
* View analytics.
* Download user profiles.
* Download reports.
* Add and update billing details.

## Creator

The Creator system role lets you create, edit, schedule, and stop any type of engagement such as campaigns, journeys, and product experiences, including:

* Create engagements.
* Stop and delete engagements.
* View analytics.
* Download reports.
* A Creator cannot revoke user access or view billing information.

## Member

The Member system role lets you view analytics and reports in the account, including:

* Read-only access.
* View analytics, including campaign performance.

# View Roles

To view roles, from the dashboard, navigate to *Setting* > *Roles*.

<Image title="Chunk 1 - Roles Overview.png" alt={1600} align="center" src="https://files.readme.io/f45cbca-Chunk_1_-_Roles_Overview.png">
  This is an example of alt text
</Image>

# Role Management

When inviting a new user, the admins can assign a custom role to the user, create a new custom role, or clone an existing custom role.
