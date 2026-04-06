---
title: Push Primer
excerpt: Prompt the user to grant push notification permissions.
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

Push Primer is an In-App message that introduces the benefits of push notifications before invoking native OS permissions. It acts as a reversible, pre-permission layer that sets expectations and builds trust by helping users understand the value of enabling notifications, such as receiving timely updates or exclusive offers. By offering this context, Push Primer can improve opt-in rates and re-engage users who have yet to grant permission.

<Image align="center" alt="Push Primer using CleverTap" border={true} caption="Push Primer using CleverTap" src="https://files.readme.io/199c0af6337ee26538d7c6abbf1fd6b441c98f240e40b74de0fb4a2690b5618d-In-app_animation.gif" width="160px" />

# Create Push Primer Campaign

To create a push primer campaign, create a regular In-App message. Set the element (button, media, or container) action to _Request Push Permission_, and CleverTap automatically recognizes it as a push primer and displays the system prompt to request notification permission.

> 📘 Note
>
> * If the users have previously denied push permission, tapping the prompt will redirect them to the app settings,
> * On iOS, the system-level push primer prompt is shown only once and cannot be triggered again.

Push Primer campaign can be created using any native In-App templates. Following is an example of how to create a Push Primer campaign using the Advanced In-App Builder:

1. Go to the _Campaigns_ page and select _In-App Messages_ from the messaging channels list.
2. In the _Who_ section, select only the trigger event, such as _Charged_.  You do not need to specify a segment in this step.

> 📘 Note
>
> The campaign automatically excludes users who have already granted push permission allowing you to focus on new users and those who need to be re-engaged.

3. In the _What_ section, select the _Advanced In-App Builder_.   For more information, refer to [Advanced In-App Builder](doc:advanced-in-app-builder#container).
   1. Add a button element to the layout. Create your In-App campaign.
   2. Set the  _On Tap_  Container action of the button element to _App Function_.
   3. Select  _Request Push Permissions_ from the _Action_ list.

<Image align="center" alt="Push Primer Campaign" border={true} caption="Push Primer Campaign" src="https://files.readme.io/8332ecbbd83f6d357e7630d31aaa05d892b2ba14e2b5d68f14e674e1635bd02a-image.png" />

4. In the _When_ section, select the campaign frequency and display rules to avoid overwhelming users. For example, users who reject the notification or opt for _Maybe Later_.

<Image align="center" alt="Manage Frequency Caps" border={true} caption="Manage Frequency Caps" src="https://files.readme.io/5b7763c94dd4481a6545254c94bdaa1b1d2afbd5287575897380db4572ad2d57-Screenshot_2025-06-18_at_17.53.53.png" width="70% " />

> 📘 Create a Segment for Users Based on Android Version
>
> Create a separate segment for Android users who use android 13 and above. Filter with the _App Field_ > _OS Version_ > _contains_ > (Android Versions such as 13,14,15). This ensures that Push Primer messages are shown only to users on devices where notification permission is required on runtime.
>
> This will avoid sending the campaign to users on Android 12 and below, where the notifications do not require any permission and it is granted on app install itself.
>
> To do so, in the In-App Campaign, go to the _Who_ section and, under Target Segment, add filters for the app field OS Version that contain values such as 13, 14, and so on.
>
> <Image align="center" border={true} width="65% " src="https://files.readme.io/83bef9b916c5b72c6dbb5e150e4a3f5433350133d28cda67723bbc904660550c-image.png" className="border" />

5. Publish the campaign.

# Push Primer Best Practices

Push primers are one-time prompts to request user consent for notifications. A well-timed and clearly worded primer significantly improves opt-in rates and long-term user engagement.

* **Display Only Once at a Strategic Moment**: Trigger the Push Primer after a high-value event (for example, completing onboarding or a first purchase), when users are more receptive to receiving notifications. _Contextual timing can almost triple push opt-ins compared to first-launch prompts_.

* **Delay Until Value is Understood**:  Let users experience the core features before prompting. Value recognition increases the likelihood of opt-in. _Average opt-in rates can rise by 45% when shown after the third session_.

* **Communicate Clear Benefits**: Use specific, value-driven language such as:

  * _Track your delivery in real-time_
  * _Get notified of price drops instantly_

  Avoid vague text such as _Enable notifications to stay updated._

* **Trigger After Intent-Driven Events**: Display primers after meaningful user actions such as _Added to Cart_, _Search Completed_, or _Onboarding Finished_. These events correlate with higher intent and perceived utility of notifications.

* **Keep Messaging Short and Actionable**: Use a concise headline and a one-line benefit statement.

```
    For example: _Want delivery updates? Enable push alerts now._ 
```

* Stick to plain language and avoid any technical jargon.
* Use compelling visuals and clear reasons why the user should opt in.
* **Provide Clear, Non-Coercive Choices**: Always include two obvious options, such as _Allow Notifications_ and _Not Now._ Avoid dark patterns or forced opt-ins.
* **A/B Test Message Copy and Timing**: Continuously test variations in CTA labels, tone, and trigger moments to determine what performs best for your audience.
