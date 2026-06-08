---
title: Push-Troubleshooting and FAQs
excerpt: >-
  Refer to our frequently asked questions and troubleshoot any issues with your
  Push campaign.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# FAQs

<Accordion title="Existing Campaigns and Migration">
  **1. What happens to my existing campaigns?**\
  All existing campaigns will continue to run without any changes or disruption.

  **2. Will my past campaigns be converted into templates automatically?**\\

  Yes, existing campaigns will be auto-converted. You can also clone those campaigns effortlessly.

  **3. Can I still edit or duplicate old campaigns?**\
  Yes, all existing campaigns remain editable and duplicable.

  **4. What happens to scheduled campaigns during rollout?**\
  Scheduled campaigns will execute as planned without any impact.

  **5. Will existing template campaigns still work?**\
  Yes, they will load seamlessly in the new UI with all configurations intact.

  **6. I use recurring campaign exports in my data pipelines. Will this change impact me?**\
  If you consume CleverTap event data in downstream systems. New events and fields may be added that could affect how your pipelines process or interpret campaign data.
  No existing events are being removed; however, new event properties may start appearing in your exports, so validating your pipelines is advised.
  CleverTap recommends to review the updated [Event Changelog](https://docs.clevertap.com/docs/events-changelog).
</Accordion>

<Accordion title="SDK & Technical Dependencies">
  **7. Do I need to upgrade my SDK?**\
  An upgrade is not required for basic usage. However, it is needed to access advanced features such as GIF support and newer template capabilities.

  **8. What happens if I don’t upgrade my SDK?**\
  Your campaigns will continue to work. However, some features may not render or behave as expected. It is recommended to test your push messages before launching a campaign.

  **9. Will push delivery be impacted?**\
  No, the delivery infrastructure remains unchanged.
</Accordion>

<Accordion title="Rendering & Customization">
  **10. How does this impact custom push rendering?**\
  Custom rendering will continue to work as implemented via the Standard template.

  **11. Can I still use personalization and dynamic variables?**\
  Yes, full personalization support remains unchanged.

  **12. Will rich media pushes continue to work?**\
  Yes, all existing capabilities are supported within templates.

  **13. Are GIFs supported across all devices?**\
  GIF support depends on SDK versions and platform capabilities. Updating your SDK is recommended for the best experience. For more information, refer to [GIF Support for Android Push Notifications](https://developer.clevertap.com/docs/android-push-templates?utm_source=vision#gif-support) and [GIF Support for iOS Push Notifications](https://developer.clevertap.com/docs/rich-push-notifications?utm_source=vision#gif-support).

  **14. Why am I getting an error when publishing my Push notification campaign?**\
  A: Ensure that a Notification Channel is selected under Android Options. Notification Channel is a mandatory field; without it, the campaign cannot be published. For more information, refer to [Create Notification Channels](https://developer.clevertap.com/docs/android-o-updates#create-notification-channels).
</Accordion>

<Accordion title="Feature Specific">
  **15. What is “Skip active users”?**\\

  This feature prevents push notifications from appearing when the app is already open. It is available on Android only.

  **16. What are sticky notifications?**\
  Sticky notifications remain visible even after using the “clear all” option.

  **17. What is auto-dismiss?**\
  Auto-dismiss is a setting that automatically removes notifications after a defined duration.
</Accordion>

<br />

<br />
