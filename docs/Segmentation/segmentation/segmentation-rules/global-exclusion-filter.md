---
title: Global Exclusion Filter
excerpt: >-
  Learn how to precisely target your audience by excluding users in real time
  using the Global Exclusion Filter in the Query Builder.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

Global Exclusion Filter enhances the CleverTap Query Builder by introducing a dedicated _Exclude Users_ section. This addition allows you to first define the users you want to include, and then explicitly remove users who meet specific disqualification criteria.

Instead of relying only on inclusion filters, you can apply exclusion rules that subtract users from the final audience. These exclusion criteria provide more precise targeting control and ensure your segment contains only eligible users.

Global Exclusion Filter is beneficial when you need to do the following:

* Exclude users based on reachability conditions
* Prevent unnecessary spending on costly channels such as SMS
* Remove users who match repeat or reusable exclusion criteria
* Apply disqualification rules across the entire segment definition

Inclusion and exclusion are calculated separately, and the final audience is created by removing excluded users from the included users. The _Exclude Users_ section excludes users from the final segment if they match any exclusion rules.

## Purpose

The _Global Exclusion Filter_ is especially useful when your exclusion conditions are not naturally expressible as part of your inclusion logic, and you want a clear _include this, exclude that_ approach.

The following are examples of exclusion criteria:

* Users who have no push token on any device
* Users who opened the last 3 campaigns
* Internal employees
* Users already in another live journey
* Users with invalid email IDs or phone numbers
* Dormant or inactive users

## Example Scenario

If a user has multiple devices, and only some of them have push tokens:

| User   | Device   | Device Token Exists? |
| ------ | -------- | -------------------- |
| User 1 | Device 1 | Yes                  |
| User 1 | Device 2 | No                   |
| User 1 | Device 3 | Yes                  |
| User 1 | Device 4 | No                   |
| User 1 | Device 5 | Yes                  |

If you want to target only users who are unreachable via push, _User 1_ must not qualify, since they are still reachable on some devices.

The Global Exclusion Filter enables you to exclude users who match the disqualification rule from the final segment output. For more use cases, refer to [Use Cases and Examples](doc:global-exclusion-filter#use-cases-and-examples).

# How to Use Global Exclusion Filter

This section explains how to build a _Target Segment_ using inclusion and exclusion rules.

1. [Build inclusion criteria](doc:global-exclusion-filter#build-inclusion-criteria)
2. [Add exclusion rules](doc:global-exclusion-filter#add-exclusion-rules)
3. [Define exclusion criteria](doc:global-exclusion-filter#define-exclusion-criteria)
4. [Preview user counts and segment insights](doc:global-exclusion-filter#preview-user-counts-and-segment-insights)

### Build Inclusion Criteria

In the _Filter users_ section, define the users you want to include.

Example:

* Users who added items to the cart in the last 30 days
* Country = India

### Add Exclusion Rules

Click **Add Exclusion Rules** to enable the _Exclude users_ section.

### Define Exclusion Criteria

In _Exclude Users_, define the users you want to remove from the final segment.

For example,

* Exclude users who are not reachable via push on any device
* Exclude users with invalid email IDs
* Exclude internal employees

### Preview User Counts and Segment Insights

Preview the following user counts and insights:

* Inclusion count
* Exclusion count
* Final audience count in _Segment Insights_

# Dashboard Overview

The Global Exclusion Filter is available in the existing query builder, where segmentation rules are created.

The following image shows the Exclusion Filter in the _Who_ section:

<Image align="center" border={true} caption="Global Exclusion Filter" src="https://files.readme.io/22e4c7c7bb30a22ff4ef881cbbc696749a9c57b4fda0ed3fa5a36257e6e0221c-2026-02-17_10-52-00_1.gif" />

The _Target Segment_ query builder is divided into the following two parts:

* **Filter users**: Includes the users you want
* **Exclude users**: Excludes the users you do not want

## Target Global Audience

Global Exclusion Filter applies to the entire audience definition. This means exclusion rules are applied after all inclusion groups are evaluated, regardless of whether your inclusion logic contains AND/OR combinations.

For example,

Final Segment =

(Users who _Added to cart_ AND Country = India)

OR

(Users who _Viewed product_ AND Country = Dubai)

AND

Exclude users who are not reachable via push on any of their devices

This ensures excluded users are removed from the final segment even if they match any inclusion rule group.

## Query Evaluation Logic

The Global Exclusion Filter uses a subtraction-based evaluation model.

Final Segment = (Included Users Set) − (Excluded Users Set)

This means the following:

* CleverTap evaluates the inclusion query independently.
* CleverTap evaluates the exclusion query independently.
* Any user who matches at least one exclusion rule is removed from the final segment.

## Supported Filters

You can use the following filters inside _Exclude Users_:

* Reachability
* App Fields

<Callout icon="🚧" theme="warn">
  **Exclusion Rule Behavior**

  A user is removed if they meet even one exclusion rule. This is important when you define multiple disqualification criteria, such as excluding both dormant users and invalid email users.
</Callout>

## Default Behavior

The Global Exclusion Filter follows specific interpretation rules when one section is left empty.

### No Rule in Filter Users

If you do not add any rules in _Filter users_, CleverTap treats it as _All Users_. This enables exclusion-only targeting.

For example,

You want to target all users except internal employees.

* _Filter Users_: Empty -> Targets all users
* _Exclude Users_: Internal Employees
* _Final Audience_: All users except internal employees.

### No Rule in Exclude Users

If you do not add any rules in _Exclude users_, CleverTap treats it as an exclusion of 0 users. This enables inclusion-only targeting.

For example,

You want to target users who _Added to cart_ in the last 7 days.

* _Filter Users_: Added to cart in the last 7 days
* _Exclude Users_: Empty -> excludes zero users
* _Final Audience_: All users who added to cart in the last 7 days.

## Validation Rules

Global Exclusion Filter ensures you do not accidentally create an undefined audience.

You cannot save a segment if:

* Filter Users is empty, _and_
* Exclude Users is empty

<Callout icon="📘" theme="info">
  **Rule Sections cannot be Empty**

  You must add at least one rule in either the _Filter users_ or the _Exclude users_ sections.
</Callout>

In addition, while creating a Campaign or Journey, you will not be able to proceed if both sections are empty. This ensures the audience definition is always meaningful.

# User Count and Insights

The Global Exclusion Filter shows separate counts for inclusion and exclusion. This helps you understand how many users qualify in each section before the exclusion is applied.

## Inclusion Count

The count shown in _Filter Users_ represents the number of users that meet the inclusion criteria.

The following image shows the _Filter users_ count:

<Image align="center" border={true} caption="Filter Users" src="https://files.readme.io/bac2c1c2096e3dbfb1b042b1231afe1a29d9a05257ea0c35cb3cb76e978fe307-image.png" />

## Exclusion Count

The count shown in _Exclude Users_ indicates the number of users matching the exclusion criteria.

The following image shows the _Exclude users_ count:

<Image align="center" border={true} caption="Exclude Users" src="https://files.readme.io/329948ff198aab0f995cb2c24d13c329afbea9ea8e8701820b31e40908240077-image.png" />

> 📘 Exclusion Count can be higher than the Inclusion Count
>
> Inclusion and exclusion are evaluated separately from the _All Users_ set.
>
> This means the exclusion set can be larger than the inclusion set.
>
> Example:
>
> * Filter Users returns 100 users.
> * Exclude Users returns 10,000 users.
>
> This does not mean 10,000 users will be excluded from your segment. Only users common to both sets will be removed.

## Final Segment Count

The _Segment Insights_ section displays the channel-wise final segment count after the exclusion.

`Final Segment Count = (Users matching Filter Users) - (Users matching Exclude Users)`

The following image shows the _Segment Insights_ section that displays the channel-wise user count:

<Image align="center" border={true} caption="Segment Insights" src="https://files.readme.io/aca5656b3229eabc91c00fcbd8092eec23eccf190c86935d8f563d9a711577e3-image.png" />

# Use Cases and Examples

These use cases and examples describe real scenarios where the Global Exclusion Filter improves targeting accuracy.

## Exclude Push-Unreachable Users from a Campaign Audience

This is the primary use case for push reachability.

### Scenario

You want to send a push campaign to intent-based users, but ensure the final audience includes only users who can receive push notifications.

### Rule

Filter Users:

* Users who added to cart in the last 30 days

Exclude Users:

* Users who are not reachable via push on any of their devices

### Result

The final audience consists only of users who added items to the cart and are reachable via push.

This improves campaign reachability and prevents wasted campaign sends.

## Exclude Users who Opened the Last 3 Campaigns

This use case helps prevent over-saturation and ensures you do not repeatedly message the same engaged users.

### Scenario

You want to run a campaign for users who have not engaged with your communications recently.

### Rule

Filter Users:

* Users who are eligible for the campaign

Exclude Users:

* Users who opened the last 3 campaigns

### Result

The final audience excludes highly-engaged users who have already opened recent campaigns.

## Exclude Internal Employees from Targeting

This use case prevents accidental targeting of internal users.

### Scenario

Your team’s test devices and employee accounts exist in production data, and you want to confirm they are never included in campaign sends.

### Rule

Filter Users:

* All users who match your campaign segment

Exclude Users:

* Users matching employee identifiers (for example, internal user property or user bucket)

### Result

Final audience excludes employees while retaining all eligible customers.

## Exclude Users already in Another Live Journey

This use case prevents conflicting experiences and avoids over-messaging.

### Scenario

You want to launch a journey for cart abandoners, but avoid users who are already part of another live journey.

### Rule

Filter Users:

* Users who added to cart in the last 7 days

Exclude Users:

* Users already in another live journey

### Result

The final audience contains cart abandoners who are not currently engaged in another Journey.

## Exclude Users with Invalid Email IDs or Phone Numbers

This use case ensures audience quality and reduces delivery failures.

### Scenario

You want to run an email or SMS campaign, but you need to remove users with invalid contact information.

### Rule

Filter Users:

* Users eligible for the campaign

Exclude Users:

* Users with invalid emails or phone numbers

### Result

The final audience contains only users with usable contact details.

## Exclude Inactive Users

This use case helps focus on active users and improves engagement performance.

### Scenario

You want to target users who are recently active and avoid dormant accounts.

### Rule

Filter Users:

* Users matching campaign intent criteria

Exclude Users:

* Dormant/inactive users

### Result

The final audience excludes dormant users, improving targeting relevance.

# Best practices

This section explains how to use the feature effectively and avoid confusion.

* **Use exclusion for global disqualification rules**

Use the Global Exclusion Filter when your condition applies to the entire audience.

For example,

Excluding internal employees should apply globally, not only to one rule group.

* **Use inclusion logic when 'Have not done' already solves the problem**

If your goal is to remove users who performed an event, you can often represent this using inclusion logic.

For example,

* Include users who launched the app
* Exclude users who completed a _Charged_ event

**Instead, use**

* Include users who launched the app, AND
* Have not done a _Charged_ event

This reduces query complexity.

* **Validate audience counts before launching engagements**

Always review the following before launching engagements:

* Inclusion count
* Exclusion count
* Final Insights count

This validation ensures you understand how exclusion affects the final audience.

# Frequently Asked Questions (FAQs)

The following are the FAQs on the Global Exclusion Filter:

### Why is the exclusion count higher than the inclusion count?

Exclusion count is evaluated independently from the All-Users set. Only users who appear in both inclusion and exclusion sets are removed from the final audience.

### What happens if a user matches multiple exclusion rules?

If a user matches even one exclusion rule, they are removed.

Matching multiple exclusion rules does not change the outcome; the user is excluded either way.

### What happens if I do not add any inclusion rule?

If _Filter users_ is empty, CleverTap treats it as all users.

### What happens if I do not add any exclusion rule?

If _Exclude users_ is empty, CleverTap excludes zero users.

### Can I save a segment if both sections are empty?

No. Saving is blocked if any of _Filter Users_ or _Exclude Users_ have no rules.

This validation also applies when proceeding with Campaigns and Journeys.
