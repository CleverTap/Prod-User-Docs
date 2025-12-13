---
title: Personalize Messages
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

When you create campaigns in CleverTap, you can personalize messages for each user based on user profile properties.

> 👍 Personalization Example
>
> If you run a multilingual news application, you can personalize each message based on the user's preferred language. 
>
> Using this feature, instead of making one campaign for each language and splitting your campaign stats, you can create one campaign and see its result as a whole, and for each language individually.

# Step 1: Pick the User Property to Personalize Messages

<Image title="Campaign_Main_Personalize.png" alt={925} className="border" border={true} src="https://files.readme.io/f69424c-Campaign_Main_Personalize.png" />

# Step 2: Create Default Message Copy

In this campaign, you have to specify a default copy, which will go to all users in your target segment that doesn’t have a user property you have selected a copy for. 

**Example**\
If you are sending a message based on language and your app supports 50 languages, you may choose to create copy for Spanish and French, and keep your default copy as English, which will be sent to everyone else.

<Image title="Campaigns_Message_Property_English.png" alt={1356} className="border" border={true} src="https://files.readme.io/8ade0ab-Campaigns_Message_Property_English.png" />

# Step 3: Choose and Create Your Message Copy Based on User Properties

After you have selected your default copy, you need to select the various user properties for which you’d like to create copies. Please note no message copy can be left blank.

<Image title="Campaign_Message_Property_Spanish.png" alt={1366} className="border" border={true} src="https://files.readme.io/70ff3a3-Campaign_Message_Property_Spanish.png" />
