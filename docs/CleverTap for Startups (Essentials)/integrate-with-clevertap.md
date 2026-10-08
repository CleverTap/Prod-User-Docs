---
title: Integrate with CleverTap
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

This document includes a guided video series that walks you through the complete CleverTap setup—from initial understanding to activating user engagement. It is designed to help you integrate CleverTap correctly and use it effectively.

The document covers the following:

- Understand the core concepts and data flow in CleverTap
- Set up the SDK across supported platforms
- Create and manage unified user profiles
- Track events using correct syntax and best practices
- Configure and send push notifications

Before you even start with the integration, read about CleverTap as a product and the core capabilities. Also, understand how real-time data drives personalized user engagement.

You can also check the following video to understand the basics of integrating CleverTap into your project:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/N58DtgKIyBiKJN4CQ6dTDA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Prerequisites

Before you begin, ensure you have:

- CleverTap account credentials (Account ID, Token, Region)
- Access to your application codebase
- Sample user data (optional, for CSV upload)

# Integrate CleverTap

Integrating your application with CleverTap includes the following steps:

1. [Initialize SDK](doc:integrate-with-clevertap#initialize-sdk)
2. (Optional) [Import User Data to CleverTap](doc:integrate-with-clevertap#import-user-data-to-clevertap)
3. [Configure User Profiles and Identity](doc:integrate-with-clevertap#configure-user-profiles-and-identity)
4. [Set Up Event Tracking](doc:integrate-with-clevertap#set-up-event-tracking)
5. [Configure Push Notifications](doc:integrate-with-clevertap#configure-push-notifications)

## Initialize SDK

Set up the CleverTap SDK in your application.

The following are the key steps:

1. Add SDK to your project.
2. Configure Account ID and Token.
3. Set the correct region.
4. Enable required initialization settings.

After completing the steps above, the SDK is now ready to send user and event data to CleverTap.

Watch the following video for an overview of the steps to integrate the CleverTap SDK into your application:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/t2umQ9Wd3DiU24YO91CBGQ/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

Watch the video below for a detailed walkthrough on integrating the CleverTap SDK into your application:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/hEMHCu5b3bjiKQG91Q25DA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

## Import User Data to CleverTap

You can import historical or offline user data using CSV uploads.

The following are some of the use cases where you will have to upload a CSV file to push user data to CleverTap:

- Migrating existing users
- Adding offline data
- Enriching user profiles

Once you upload the CSV file, user profiles are created or updated in the dashboard.

Check the following video to learn how to upload and process CSV files with user profile mapping:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/bm4VMPBFmhT7FhhK0cymtA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

## Configure User Profiles and Identity

Define how user identities are managed.

The following are some of the key considerations:

- Unique identifiers (for example, Identity, Email)
- Profile update behavior
- Identity merging across devices

After you are done configuring, users are consistently identified across sessions and devices.

Check the following video to understand how identity management works in the CleverTap dashboard:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/3JxOmNpP0H0dQevy8fi9gQ/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

## Set Up Event Tracking

The next step is to implement event tracking in your application.

The following are some of the best practices you should follow when setting up event tracking for your application:

- Use consistent event naming
- Define relevant event properties
- Follow the recommended event structure

Check the following video to learn how to configure event tracking on the CleverTap dashboard. Once done, you can use these events for segmentation, analytics, and campaigns.

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/tDqkuyQ8CHxvY418ct1piw/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

## Configure Push Notifications

Set up push notifications for user engagement.

The following are the key actions that you must take when setting up Push Notifications:

1. Configure platform-specific push settings
2. Enable push permissions
3. Test notification delivery

Check the following video to learn how to set up push notifications using CleverTap for Android, iOS, and Web:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/M392awgClU1CzgHyzEZmbA/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Validate Integration

Before using CleverTap for campaigns, verify the following:

- User profiles are visible in Live View
- Events are being tracked correctly
- Identity merging works as expected
- Event timestamps are accurate
- Test push notifications are delivered successfully

# Troubleshooting

If you encounter issues:

- Verify SDK initialization settings
- Check event payload structure
- Validate identity fields
- Review push configuration

If the issue still persists, raise a ticket or contact the CleverTap Support team.