---
title: Create A/B Test Journeys_WIP
excerpt: Test different journeys to chart an optimum path
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

You can test different paths for a user journeys, to test which performs well. This way you can see which path provides better results to repeat it for any future engagements. You can randomly distribute users (equally or unequally) in two or more paths.

# A/B Test

1. Create a Journey. 
2. Drag and drop the **A/B Test node** under *Controllers* in the left pane to the canvas. 
3. Click **A/B Test** in the canvas to begin charting paths for the journeys.

<Image title="Click_A_B.jpg" alt={1280} className="border" width="80%" border={true} src="https://files.readme.io/6d409bd-Click_A_B.jpg" />

4. Give your A/B test a name and select whether you want the tests to be configured manually or automatically.\
   Automatic selection will configure the percentage of users according to the number of paths you select. You can edit the user percentage for a particular path in the manual mode.
5. Click *+Path* to add paths to a user journey.\
   You may set upto 7 different paths for the user journeys, either in the automated or the manual mode.

<Image title="A_B_Test_path.jpg" alt={746} className="border" width="80%" border={true} src="https://files.readme.io/1d83a47-A_B_Test_path.jpg" />

## A/B Goals

You may define the A/B test goals and align them to the different paths, you've created.

1. Enter the **A/B goal name**.
2. Edit the events for which you have defined the goals.\
   a. Click *New segment* to configure more than one segment for a goal.
3. Click **+A/B Goal** to add more goals.
4. Click *Save & Close*

<Image title="A_B_Goal.jpg" alt={367} className="border" width="80%" border={true} src="https://files.readme.io/ef7f3c3-A_B_Goal.jpg" />

## Configure Paths

1. Click the path you want to configure

<Image title="Click_Paths.jpg" alt={454} className="border" width="80%" border={true} src="https://files.readme.io/331c8f7-Click_Paths.jpg" />

2. Configure the path including the sleep time, and delay, if required.\
   Delay is the time delay between an event occurrence and the path action.\
   Sleep time is the time taken for subsequent path actions.

![522](https://files.readme.io/0c3a709-Configure_path.jpg "Configure_path.jpg")

## Publish

Click **Publish**. This makes the journey live.
