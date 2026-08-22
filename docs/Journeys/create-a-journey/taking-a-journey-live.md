---
title: Publish a Journey
excerpt: Understand how to get your journey to work by saving and publishing it.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

 After building your Journey, you can save it as a draft for further editing or publish it to make it live. This document offers a step-by-step guide to managing CleverTap Journeys, detailing the processes of saving drafts, publishing Journeys, and activating them effectively.

Once a Journey is published, you can still edit it to make changes. This creates a new version of the Journey without disrupting the live version. For more information, refer to [Edit a Journey](doc:edit-a-journey). 

# Save Journeys

Once you create and save a journey, the status of the Journey changes to the *[Draft state](doc:journey-states#draft-state)*. You can make more changes to it at a later date or time. Any unsaved changes in this state may be lost unless explicitly saved.

To save a journey, follow these steps:

1. Click **Save Draft** from the Journey canvas. The *Save this journey as* popup opens. 
2. *Enter journey name* and click **Save**.

<Image title="Save a Journey as a draft" alt={912} align="center" width="90% " border={true} src="https://files.readme.io/570cbb3-Save_Journeys.png">
  Save Journeys
</Image>

The other journey actions, such as *Archive*, *Stop*, and so on, are unavailable, as the journey has still not been published. 

# Publish Journeys

After setting up the Journey, click **Publish** on the Journey canvas to activate it. The *Publish journey* popup opens. Enter or verify the Journey name. You can also update the name here if needed. Add a description or summary for your Journey to help understand its purpose and click **Publish**. For example, *This journey aims to onboard new users by sending a welcome push notification immediately after signup*. 

The description can be up to 120 characters long.

<Image title="Publish the Journey" alt={540} align="center" width="40% " border={true} src="https://files.readme.io/6b89aa78c9ac56edb625aa80b84f6c6eeb7ebaaa1d50b9c8cf07c520bd3cc22f-Publish_a_Journey.png">
  Add a Description and Publish the Journey
</Image>

You can view the description from the Journey List page. Click the ![](https://files.readme.io/cb2b6e04c22c3145eae93b4cf2c3b463b799052b6581563c12ba4b2bf69b327c-ellipses_icon.png) icon and select *View description* from the available actions. You can also edit the description when editing the Journey.

<Image alt="View Journey Description" align="center" border={true} src="https://files.readme.io/62e0cb410bb851eabeccf029e103e6c1a967eb80db7303da785c37197de277e6-View_Description.png">
  View Journey Description
</Image>

Once you publish a journey, the journey status on the *Journey List* page changes to *Running* or *Scheduled*. 

You can edit any part of the published Journey, including entry criteria, paths, and content, by creating a new version. This allows you to iterate without disrupting the currently running version. You can still edit the *What* section of a message node inline without creating a new version. For more information about how editing works, refer to [Edit a Journey](doc:edit-a-journey). 

<Image alt="Edit a Currently Active Journey" align="center" border={true} src="https://files.readme.io/c84266b1c924ebf6f6b522818f7ca5caf558c195b510fcab67f7960ff42e6b91-Edit_Journey_Popup.png">
  Edit a Currently Active Journey
</Image>

# Journey Activation, User Qualification, and Message Delivery

Once the journey is activated, users qualify, and messages are sent to the users based on the [Journey Entry Timeline](doc:setup-journey#define-the-journey-entry-timelines)they are activated as follows:

* **Activation**: Journeys activate immediately after publishing or at a scheduled start time.
* **User Qualification**: Users qualify for the Journey at midnight the day after activation. It applies to both multi-date and recurring Journeys.
* **Message Delivery**: Messages are sent to users starting from the night of publishing and continue as scheduled. It applies to both multi-date and recurring Journeys.
