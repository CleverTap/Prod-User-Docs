---
title: Recommended Delay for Inaction Campaigns
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

*Recommended Delay* is a feature that recommends the best time to send a message for an Inaction campaign. 

This feature is built for Inaction campaigns, which are designed to engage users who do not do something. For example, with an Inaction campaign, you can message users who install your app (action), but do not purchase something within 2 hours (inaction). Using the Recommend Delay feature, you can let CleverTap automatically decide the best time to send a message to re-engage users who do not purchase something.

<Image title="image2.png" alt={709} className="border" border={true} src="https://files.readme.io/c24a751-image2.png" />

In this second scenario, the average time it takes a user to add an item to their cart (action 1) and then checkout (action 2) is five minutes. If the user has not completed the checkout process within five minutes of adding the item to their cart (inaction), then the likelihood that a user will checkout drops substantially. In this example, if you use the *Recommended Delay* feature we will automatically recommend that you send a notification to the user if they have not completed the checkout process after five minutes.

# How It Works

CleverTap creates this recommendation by calculating the average time users take to convert from one action to another action. 

Beyond this average time, the likelihood that a user will complete the second action drops substantially. However, if you send a message to the user at that point, you can increase the conversion rate for the second action.

# Feature Guide

## Create an Inaction Campaign

<Image title="campaigns_push_type_Inaction.png" alt={1012} className="border" border={true} src="https://files.readme.io/62977ce-campaigns_push_type_Inaction.png" />

## Select When to Send the Campaign

<Image title="image1.png" alt={644} className="border" border={true} src="https://files.readme.io/e06f79b-image1.png" />

## Select the Action and Inaction 

<Image title="image2-updated.png" alt={709} className="border" border={true} src="https://files.readme.io/27cb111-image2-updated.png" />

## Click on Find Best Delay to Enable the Recommended Delay Feature

<Image title="image2.png" alt={709} className="border" border={true} src="https://files.readme.io/86faec1-image2.png" />
