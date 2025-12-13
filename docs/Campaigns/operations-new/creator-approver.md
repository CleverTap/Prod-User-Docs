---
title: Creator and Approver
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
# Overview

Campaign Approver is a security feature that provides the capability to have increased control over who can send campaigns within your organization.

Within your marketing team, you might have one person who is responsible for creating campaigns in CleverTap, and then have another person who reviews and approves these campaigns before they can be sent. The approver feature enables this workflow in CleverTap by requiring approval before a campaign can be sent. Review for the campaign can be done in the segment, time, and campaign copy.

As part of this feature, we introduced a new system role called Approver. Users in this role have the ability to approve campaigns created by users in the creator role. Once the approver is enabled in your account, a creator will not be able to send a campaign unless it is approved.

# Enable Approver Role

This feature is a part of our advanced role-based access control. You will have access to the feature if you have opted-in for [CleverTap for Enterprises](https://clevertap.com/pricing).

<Image title="Approver.png" alt={1248} className="border" border={true} src="https://files.readme.io/c0a4296-Approver.png" />

# Campaign Workflow with Creator Approver Enabled

After the Approver Creator feature is enabled in your account, there will be a new workflow to send campaigns using the following steps:

1. The creator creates a campaign in CleverTap.
2. The creator requests approval to send the campaign. This sends an email to the approver or admin to review the campaign, and then decide either to approve or not approve the campaign. 
3. If the approver or admin approves the campaign, the campaign is sent. If the campaign is rejected, the campaign is not sent.
