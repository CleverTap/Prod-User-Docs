---
title: Push Editor
excerpt: >-
  Learn how to design and customize push notifications using pre-built templates
  from the CleverTap dashboard.
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

The Push Editor allows you to create and edit relevant and timely messages for your push campaign. This section explains the different pre-built Push templates designed to cater to your various push-campaigning needs. You can create your push message by selecting the appropriate push template for your campaign.

<Callout icon="📘" theme="info">
  #### Public Beta

  This feature is released in Public Beta. For more information about this feature, contact your Customer Success Manager or  CleverTap Support.
</Callout>

From the _What_ section, select the [Message Type ](doc:create-message-push#message-types)for your push notification and click **Go To Editor**. You can see the various push templates to help you create a contextual and timely message.

<Image align="center" alt="Push Templates" border={true} caption="Push Templates" src="https://files.readme.io/93a7bdf6e72fef4de198d03b9b26d60351824b0dc6d82175c4201ad8db29cff8-image.png" />

# Push Templates

The Push Editor in CleverTap enables you to design and edit impactful push notifications directly from the dashboard, eliminating the need for developer support or SDK updates. It offers a range of pre-built templates tailored for various campaign goals, making it easier to craft relevant, timely, and engaging messages.

You can select from the following template types:

## **Standard**

Supports simple layout with title, message, image, and optional buttons, ideal for quick, informative alerts. For example, an e-commerce business might want to inform customers that their order is being processed. You can add GIFs to your message content using the Standard Template. For more information on GIF sizing and format, refer to

[GIF Support](https://developer.clevertap.com/docs/android-push-templates#gif-support-in-standard-push-template).

<Image align="center" alt="Standard Template" border={true} caption="Standard Template" src="https://files.readme.io/ed55e473b9eb0f92e91a4572766a83db96535aa90ec95492113b6d66ad782aec-image.png" width="35% " />

## **Advanced**

Supports rich media, deep links, and enhanced customization for more engaging messages. It is great for interactive, visually appealing messages. For example, businesses can use it to build excitement for new product drops, early access offers, or feature rollouts that benefit from strong visuals and clear Call to Action (CTAs).

<Image align="center" alt="Advanced Template" caption="Advanced Template" src="https://files.readme.io/45e65c72a2e4c221854feefc82a0d58c8aaf6956c7a467c9c780c26613fad9ef-image.png" width="35% " />

## **Auto Carousel**

Allows multiple images with titles and links that users can swipe through, perfect for showcasing multiple offerings in one message. Businesses can utilize it to promote new product collections, travel packages, and content recommendations, among other offerings.

<Image align="center" alt="Auto Carousel Template" caption="Auto Carousel Template" src="https://files.readme.io/b06f01f282ddb61ab6bca44b51c79e65c9735b224432fadaf0799eb6c1dd7a70-Screen_Recording_Jun_4_2025_from_Google_Drive.mp4_1.gif" width="35% " />

## **Timer**

Adds a countdown timer to your template to enable immediate action from the user, ideal for time-sensitive campaigns. For example, businesses can utilize it for flash sales, limited-time discounts, and other promotional offers.

<Image align="center" alt="Timer Template" caption="Timer Template" src="https://files.readme.io/a0dd4a50b5b7783a1f970928b1d13d16d660728b9afb935e4947fbd3c942fb00-Timer_12_Light_Live.mp4_1.gif" width="35% " />

## **Text over Image**

Places bold text over a background image to deliver visually striking messages. For example, businesses can use it to highlight seasonal campaigns, special announcements, event invitations, and other relevant content.

<Image align="center" alt="Text over Image Push Template" caption="Text over Image Push Template" src="https://files.readme.io/c7df51a2d91796e9e7433afa2c3c04646037dc71f5e0b017978a35715e0a2f6a-image.png" width="35% " />

### Collapsed Media Support (Large Icon and Collapsed Image)

The Text over Image push template supports flexible media configurations for the collapsed view. You can use the same image for both expanded and collapsed views, use a different image for the collapsed view, or add a large icon as required. This enables multiple presentation styles depending on your campaign needs.

You can configure the collapsed and expanded views in the following ways:

* Use the same image for both collapsed and expanded views.
* Use a different image for the collapsed view.
* Use an image in expanded view only, with no media in collapsed view.
* Use a large icon in the collapsed view.
* Use a large icon along with an expanded/collapsed image in the collapsed view (supported in SDK PushTemplates `v2.3.0` and above).

The large icon is shown only in the collapsed view. It appears right-aligned next to the notification title and message for SDK PushTemplates `v2.3.0` and above, and left-aligned for earlier SDK versions.

<Image align="center" border={true} caption="Large Icon Right-aligned to the Notification" src="https://files.readme.io/144ddde8b4167abd4f1592fd3cb7e16a37dbc1f2b91786686786e0983888dfb2-image.png" />

#### Configure Expanded and Collapsed Media

To configure expanded and collapsed push notifications media:

1. Go to **Campaigns**.
2. Create or edit a **Push Notification campaign**.
3. Select the **Text over Image** template.

<Image align="center" border={true} caption="Push Editor" src="https://files.readme.io/562789466fe6c84b517ba4f426977d7d5b71fd04eff51e74f27d63739b84bda8-image.png" />

4. To add an image or GIF for the expanded view, click **Upload**, paste the image URL in  _Expanded Media_, or click **Generate with AI** to generate a new image.
5. Toggle **Same for collapsed media** to use the same media for both collapsed and expanded views.
6. To add a different image or GIF for the collapsed view, click **Upload**, paste the image URL in _Collapsed Media_, or click **Generate with AI**.
7. Upload the icon image from the _Large Icon_ section, or click **Generate with AI**.
8. Preview and save your changes.

#### Collapsed View Behavior Across SDK Versions

For SDK versions below PushTemplates `v2.3.0`, the collapsed view supports only one visual element at a time. Depending on your setup, the notification can render in one of the following ways:

* Collapsed Image + Text
* Expanded Image + Text
* Large Icon + Text
* Text only

## **Manual Carousel Template**

Manual Carousel is an interactive push notification format that lets users scroll through a series of cards or slides at their own pace. Each card can display rich content like images, headlines, brief descriptions, and a call-to-action (CTA). Users navigate between cards manually using swipe gestures or navigation arrows.

If only a single image is available for download, this template falls back to the Basic Template.

<Image align="center" alt="Manual Carousel Template" border={true} caption="Manual Carousel Template" src="https://files.readme.io/314a341e4efcff60b16c13c2d9d89c91866ff0a66eb39458de68670c9d1d7ab7-Screen_Recording_Jun_4_2025_from_Google_Drive_1.mp4_1.gif" width="35% " />

# Push Campaign Setup

Based on the selected template, the editor displays configurable fields grouped by functionality as follows:

* Content
* Android Options
* iOS Options
* Custom Key-Values
* Post Action Webhook
* App Inbox

Once you select the required push template for the _Title_ and _Message_ fields, you can use the following options to create personalized and engaging campaigns:

* Use text color to change the color of your text.
* Use emoticons (![](https://files.readme.io/9e57d16-Emoticon.png)) to create more engaging and visually appealing messages that can more effectively capture the audience's attention than plain text. Emojis, unlike simple emoticons, can be more complex and take up varying amounts of space in text.
* Use _@_ personalization or _\{\{}}_ to create more [personalized](doc:personalize-message-all)  or captivating messages. Enter the required details to create the message.
* Use liquid scripts  to check the usage.
* Use [CleverAI](doc:scribe), the AI-powered writing assistant that can also analyze and adjust the emotional tone of your content. It helps generate attractive and emotionally relevant messages for your campaign.

## Content

This section includes the core elements of your push notification, applicable across platforms:

| Field            | Description                                                                                                                                                                                                                                                                                                                                                                                          | Required/Optional | Available for Template                |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------- | :------------------------------------ |
| Title            | The main headline of your notification should be concise and attention-grabbing, defining the exact purpose of your campaign.                                                                                                                                                                                                                                                                        | Required          | All                                   |
| Message          | The body text of your notification. The message should clearly convey the purpose of your campaign.                                                                                                                                                                                                                                                                                                  | Required          | All                                   |
| Background Color | Defines the background color of your push notification. You can use it to match your brand theme or draw visual attention to the notification. It accepts HEX codes or color pickers.                                                                                                                                                                                                                |                   | Basic, Auto Carousel, Text over Image |
| Timer Duration   | Sets the countdown duration (in seconds, minutes, or hours) that appears in the push notification. Helps create urgency by indicating how much time is left before an offer expires. The following two options are available: <li>Relative: The countdown starts based on when the user receives the notification.</li><li>Absolute: The countdown ends at a fixed date and time for all users.</li> | Required          | Timer                                 |
| Timer Text Color | Allows you to customize the color of the timer text using a HEX code. This ensures the timer stands out or aligns with your brand colors.                                                                                                                                                                                                                                                            | Optional          | Timer                                 |
| Expiry Title     | The fallback title that appears when the timer has expired. This helps you communicate a follow-up message or next action.                                                                                                                                                                                                                                                                           | Optional          | Timer                                 |
| Expiry Message   | The message body displayed after the timer expires. You can use this to soften the missed opportunity or redirect the user elsewhere.                                                                                                                                                                                                                                                                | Optional          | Timer                                 |
| Expiry Img       | An image that replaces the original notification image after the timer expires. Helps reinforce the expiry visually                                                                                                                                                                                                                                                                                  | Optional          | Timer                                 |

<Image align="center" alt="Content Section" border={true} caption="Content Section" src="https://files.readme.io/bc77b4776c512b19f495b2df17b6656687f3a6cf173da2555407256f63a23353-image.png" />

<Callout icon="📘" theme="info">
  #### Recommended Character Limits

  While there are no enforced character limits for push notifications, following these best practices ensures your message is displayed seamlessly across devices, thus preventing the title from trimming. The recommended character limits are as follows:

  | Platform | Recommended Title Length | Recommended Message Length |
  | :------- | :----------------------- | :------------------------- |
  | iOS      | 25-50 characters         | 150 characters             |
  | Android  | 65 characters            | 240 character              |
</Callout>

## Android Options

You can use this section to customize Android-specific behavior for your push using the following fields:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Available for Template
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Notification Channel
      </td>

      <td>
        Starting from Android version 8.0, all notifications must be assigned to a channel. For each channel, you can customize the visual and auditory behavior.  Select the Android notification channel that defines the sound and visual behavior of your notification.
      </td>

      <td>
        Required
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Summary Text
      </td>

      <td>
        Summary shown when notifications are grouped or collapsed (especially on Android 7.0 and above). It provides a quick overview of the message content.
      </td>

      <td>
        Required
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Subtitle
      </td>

      <td>
        An optional line of text that appears next ti the app name and provides additional context for the message.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Expanded Image
      </td>

      <td>
        A larger image displayed when the user expands the notification. Supports image URL or upload. You can add a fixed or dynamically generated URL to include rich media in your push notifications—images for Android, and both images and videos for iOS.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Large Icon
      </td>

      <td>
        A small icon displayed on the left of the notification, usually used for logos or symbols. Supports image URL or upload.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Action Buttons
      </td>

      <td>
        Add up to two buttons that users can click to take immediate action (for example, _Shop Now_, _View Cart_, and so on).
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Deeplink URL
      </td>

      <td>
        A link that navigates users to a specific screen inside the app when the notification or button is clicked. The OpenURL method for your app is called with the deep link specified here. If you want to use external URLs, you have to whitelist the IPs or provide HTTP/https before the URL so the SDK can handle them properly.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Small Icon Background
      </td>

      <td>
        HEX color code for the background behind the small icon, matching your brand palette.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Badge icon
      </td>

      <td>
        Choose whether to show the app icon or a notification-specific icon on the status bar.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Badge ID
      </td>

      <td>
        Custom badge ID used for badge counts or grouping, based on app-specific logic.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Sound
      </td>

      <td>
        Defines the notification sound. Choose from the following options: _None_, _Default OS_, or _Custom_ sound.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        [Tray priority](https://docs.clevertap.com/docs/best-time?isFramePreview=true#notification-tray-priority)
      </td>

      <td>
        Determines the prominence of the notification in the tray. Choose from the following options: _Default_, _High_, or _Maximum_. For more information, refer to []().
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        [Delivery priority](doc:push-editor#notification-delivery-priority)
      </td>

      <td>
        Controls how quickly the push is delivered. Choose from the following options: _High_ or _Maximum_. Selecting _High_ ensures faster delivery but may affect the battery. For more information, refer to []().
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Render max
      </td>

      <td>
        Ensures standard rendering on battery-optimized devices. Also, disables custom key values and certain visuals. For more information, refer to [RenderMax](doc:rendermax).
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Skip active users
      </td>

      <td>
        Choose whether to mute the push notification when the user is currently using the app (app in foreground).

        * Yes: If the app is open, the notification is only added to the tray, and a popup is not shown to the user.
        * No (default): The notification is added to the tray, and a popup is shown to the user, even if the app is open.
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Notification behavior
      </td>

      <td>
        Defines how the notification behaves when users clear all notifications from their tray. Use this option to keep important alerts accessible even after bulk dismissal. For more information, refer to [Notification Behavior](doc:push-editor#notification-behavior).
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Dismiss notification
      </td>

      <td>
        Specifies how and when a notification is dismissed. Use this option for time-sensitive messages such as flash sales, daily updates, or event reminders. For more information, refer to [Dismiss Notification](doc:push-editor#dismiss-notification).
      </td>

      <td>
        Optional
      </td>

      <td>
        All
      </td>
    </tr>
  </tbody>
</Table>

## iOS Options

You can use this section to customize Apple-specific behavior for your push using the following fields:

| Field                                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                   | Required/Optional | Available for Template |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------- | :--------------------- |
| Rich Media                                               | Add a fixed or dynamically generated media URL to enrich push notifications. It supports images for Android and both images and videos for iOS. It is useful for visually engaging promotions or announcements.                                                                                                                                                                                                               | Optional          | All                    |
| Deep Link URL                                            | A clickable URL that takes the user to a specific screen or section within your app. Supports deep linking for seamless In-App navigation.                                                                                                                                                                                                                                                                                    | Optional          | All                    |
| Sound                                                    | Specifies the custom sound file to be played when the notification arrives. The sound file must be included in your iOS app bundle. Supported formats: `.aiff`, `.caf`, and `.wav`.                                                                                                                                                                                                                                           | Optional          | All                    |
| Badge Count                                              | Updates the app icon badge number to the specified value. Setting it to `0` hides the badge. This must be manually managed at the application level, as it does not auto-increment.                                                                                                                                                                                                                                           | Optional          | All                    |
| [Interruption Level](doc:push-editor#interruption-level) | Defines the priority and delivery timing of notifications on iOS 15 and above. The following are the three levels: <li>**Active** (default): Displays immediately and may break through focus modes.</li><li>**Passive**: Delivered quietly.</li><li> **Time Sensitive**: Can break through time-based focus modes such as Sleep or Do Not Disturb.</li> For more information, refer to []().                                 | Optional          | All                    |
| Relevance Score                                          | Determines the importance of a notification when grouped in the iOS notification summary. Marketers can now set up the _Relevance Score_ for every notification when creating a Push campaign. This directly impacts the order of notifications when grouped. The score ranges from`0` (lowest) to `1` (highest). Notifications with higher scores take precedence. This feature was introduced in iOS 15 and later versions. | Optional          | All                    |
| Category                                                 | Specifies a registered iOS category that groups notifications by type and defines custom actions (for example, buttons). Categories must be pre-registered in the app. Each category can support up to four actions.                                                                                                                                                                                                          | Optional          | All                    |
| Mutable Content                                          | Sends the `mutable-content` flag with the payload, allowing your app’s service extension to modify the push content before it is displayed (for example, attach media, customize text). For more info, refer to Apple’s documentation on [Modifying Content in Newly Delivered Notifications](https://developer.apple.com/documentation/usernotifications/modifying_content_in_newly_delivered_notifications).                | Optional          | All                    |

## Custom Key-Values

Use this section to send additional data in the form of key-value pairs as part of your push notification payload. Your mobile app can use these values to trigger specific in-app behaviors or business logic already configured in your app code.

You can define key-value pairs for:

* All platforms
* iOS only
* Android only

Each pair consists of:

* **Key**: A unique identifier (for example, discountType)
* **Value**: The corresponding value the app will read (for example, 20)

Consider an example where you are running a push campaign offering a 20% discount. By adding a custom key-value pair such as offerType: discount20, your app can read this payload and automatically route the user to a discount page upon tapping the notification.

You can add multiple pairs using the **Add pair** button to support different logic across platforms or campaigns.

## Post Action Webhook

Use this section to send a payload to your designated endpoint after a push notification is delivered.

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Description
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Available for Template
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Webhook URL

        <br />
      </td>

      <td>
        A server endpoint you want to call when the push is clicked.
      </td>

      <td>
        Required
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Method
      </td>

      <td>
        HTTP method to use (GET, POST, and so on)
      </td>

      <td>
        Required
      </td>

      <td>
        All
      </td>
    </tr>

    <tr>
      <td>
        Payload
      </td>

      <td>
        Optional data to include in the request (JSON format supported).
      </td>

      <td>
        Required
      </td>

      <td>
        All
      </td>
    </tr>
  </tbody>
</Table>

## App Inbox

Use this section to also save the notification in the App Inbox so users can revisit it later.

| Field            | Description                                                                                                         | Required/Optional | Available for Template |
| ---------------- | ------------------------------------------------------------------------------------------------------------------- | ----------------- | :--------------------- |
| Title Color      | Sets the color of the message title in the inbox card. Accepts HEX codes (for example, `#FFFFFF`).                  | Optional          | All                    |
| Message Color    | Defines the color of the message body text shown in the inbox. Accepts HEX codes.                                   | Optional          | All                    |
| Background Color | Specifies the background color of the App Inbox notification. Use brand-consistent colors for better visual appeal. | Optional          | All                    |
| Filter Tags      | Tags that help categorize and filter App Inbox messages within your app (for example, `promotions`, `reminders`).   | Optional          | All                    |

## Other Settings

### Notification Priority

You can set these priority levels from the CleverTap dashboard as you create your Android push campaigns.

<Image align="center" alt="Notiofication Priority" border={true} caption="Notification Priority" src="https://files.readme.io/89196f0e16cda364fdcb2d7bee03b9ae36f66045e18f9ccb7bc8c8d46313d420-image.png" />

Have your app running our latest SDK (versions v3.1.4 or higher) and follow the steps outlined above to send actionable push notifications and set notification priority on Android devices.

### Notification Tray Priority

On Android, you can also set a priority level for each notification to influence how prominently it is displayed. The higher the priority, the more noticeable it will be.

Select any of the following options from the _Notification tray priority_.

* **Default Priority**: Use for most of your messages that are not time-sensitive, such as general notifications and promotional offers.
* **High Priority**: Use for important communications that require extra attention, such as chat messages. These will also display as heads-up notifications and be given a higher priority in the user’s tray. Heads up notifications are notifications that pop up on your screen from the top even when you are using other apps. For example, receive a message on your chat app when you’re using the food delivery app. This feature is available for Android N (API 25) and below. For Android Oreo and above, define the priority in the _Notification Channel_.
* **Maximum Priority**: Use for urgent, time-sensitive notifications. These notifications will get higher placement inside the user’s tray and display as heads-up notifications.

### Notification Delivery Priority

You can assign delivery priority on Android for Push notifications as follows:

* **Normal**:  The data messages with normal priority are delivered immediately when the device is active. However, if the device is inactive to conserve battery, the delivery may be delayed until the device becomes active again. You must set the priority as _Normal_ for less time-sensitive messages (such as notifications of new emails, keeping your UI in sync, or syncing app data in the background).
* **High**: The messages with high priority are delivered immediately, even if the device is asleep. It wakes the device and allows limited processing (including minimal network use) to ensure the message is received. These messages are meant to provoke user action or response to your app or its notifications. You must set the priority as _High_ for time-sensitive or user-visible content. CleverTap recommends setting the notification priority as _High_ to ensure the time-sensitive content is rendered immediately on end-user devices. If FCM detects a pattern in which messages do not result in user-facing notifications, the messages are deprioritized to normal priority.

The value for this field is set to _High_ by default.

> 📘 Notification Priority for Cloned Campaigns
>
> Cloned campaigns retain the priority setting from the original campaign.

## Collapse Key

To replace an existing notification with the same collapse key, you can use the collapse notification option. For example, if push X and push Y have a collapse key A. Push X notification is present on the mobile device when push Y notification is received. The push X notification will no longer be visible (it is collapsed), and push Y is displayed. The collapse key must be added under the collapse notification field. For more information, see [Collapse Key](doc:collapse-key).

## Interruption Level

In iOS versions earlier than 15, users could choose to silence all calls and notifications by enabling Do Not Disturb mode. Starting in iOS 15, users can hone their notification preferences to fit different contexts by setting Work, Sleep, and Personal notification modes. With iOS 15, Apple introduced four interruption levels, including time-sensitive and critical notifications, to ensure urgent alerts, like weather emergencies, reach users effectively.

These interruption levels determine the priority and delivery timing of notifications, allowing users to be in control of their device notifications. The interruption levels are designed to cater to different scenarios while respecting user preferences and focus modes. Here are the three interruption levels:

<Image align="center" alt="Set up Interruption Level" border={true} caption="Set up Interruption Level" src="https://files.readme.io/7c5da3ebe282535fd58efb085c44800e87799a61c3cd312ea38e5cf4cab6158e-image.png" />

### Active (Default)

* **Behavior:** Active notifications replicate the existing notification behavior. Upon delivery, they trigger audible sounds and vibrations and illuminate the screen.
* **Focus Mode Compatibility:** Active notifications do not break through Focus modes, ensuring that the user's selected focus settings remain undisturbed.
* **Purpose:** Use this interruption level for notifications that require immediate attention and engagement.

### Time Sensitive

* **Behavior:** Time-sensitive notifications share similarities with active notifications. However, they are accompanied by a distinctive yellow banner, making them visually recognizable as urgent.
* **Focus Mode Compatibility:** These notifications can break through both scheduled delivery times and active Focus modes.
* **Purpose:** Reserve the Time Sensitive interruption level for notifications demanding immediate user action. Their unique appearance aids users in identifying critical messages quickly.

### Passive

* **Behavior:** Passive notifications are designed for non-urgent matters. They arrive discreetly without generating sounds or vibrations.
* **Focus Mode Compatibility:** Passive notifications are considerate of users' Focus modes and do not disrupt them.
* **Purpose:** Employ the Passive interruption level for notifications that do not require instant attention, minimizing distractions while keeping users informed.

> 📘 Critical Interruption Level
>
> Currently, this _Interruption level_ is not availabe in CleverTap dashboard. We recommend contacting your Customer Success Manager and sharing your use case if you want to send the campaign from the dashboard with _Interruption level_ set as _Critical_.

## Template Variations

Users can preview and render different variations of outputs for each Push template type based on the following factors:

* **Version-based Rendition**- Notifications render differently for Android version 12 and above and version 11 and below. Key considerations include the following:
  * **Android 13 and above**: Use images no larger than 450x450 px for optimal rendering.
  * **Android 12 and above**: Center-align any text within images is centered for to ensure better visibility.
  * **Android 11 and 12**: Use image file size below 100 KB to prevent rendering issues.
  * **Android 11 and below**: Use images of under 3 MB or lower is recommended for better to maintain optimal performance.
* **CTA-based Rendition** - Notification renders based on whether CTA buttons are included in the payload.

## Dark Mode

Push templates automatically adapt to the device's theme settings, rendering notifications in dark or light mode.

| **Theme Setting**      | **Notification Appearance**                       | Sample Output                                                                                           |
| ---------------------- | ------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| **Dark mode enabled**  | Notification renders with a **dark background**   | ![](https://files.readme.io/37884bc08c5375da82457ffc4f54c7b31d3dc1591e0430f65949b73003df5e35-image.png) |
| **Dark mode disabled** | Notification renders with a **light background**. | ![](https://files.readme.io/e5e9256facd596cdea7b325ad9945868ed3a4d3c5527ef09d46ae64ae350fc5d-image.png) |

> 📘 Custom Color Support
>
> Templates support **custom color definitions** that adapt to both themes for visual consistency.

## Image Scaling

Android supports various image scaling options to control how images appear in push notifications. CleverTap optimizes image rendering to maintain visual consistency across devices while leveraging Android native scaling behavior. To handle scaling in a Push template, you must add the key `pt_scale_type` key and the value is set as `fit_center` or `center_crop` based on the requirement.

The following table lists the different scaling settings in Push templates:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Image Scaling Type
      </th>

      <th>
        Description
      </th>

      <th>
        Sample Output
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Keep Original**
      </td>

      <td>
        Applies to all expanded images in Android push templates.

        The image is scaled proportionally (maintaining the aspect ratio) to ensure that both its width and height fit within the boundaries of the image container. This ensures the entire image is visible without any cropping.
      </td>

      <td>
        ![](https://files.readme.io/8ee6f3ee4c83f0c5858268cca7d494fdc6492c2eaff59a7daf85d504260f365c-image.png)
      </td>
    </tr>

    <tr>
      <td>
        **Scale to Fill**
      </td>

      <td>
        Applies to all expanded images in all Android push templates.

        The image is resized uniformly while preserving the aspect ratio.  If necessary, it is scaled down, so that both width and height fit within the image container. This ensures the full image is displayed without any part being cropped.
      </td>

      <td>
        ![](https://files.readme.io/ca12801ffa07a814fa59f413d383b80185acb5d6c9dc36b5aa04721bc21800ae-image.png)
      </td>
    </tr>
  </tbody>
</Table>

## Notification Behavior

This option defines how a notification behaves when users clear their notification tray. It determines whether a notification remains visible or gets removed when a bulk dismissal action is performed. It is available only for  Android 14 and above, Android SDK v7.6.0, and Push Templates SDK v2.2.0 and above.

The following are the available options:

* **Regular:** Notifications are cleared when the user dismisses their notification tray or when an automatic dismissal is triggered. This behavior is ideal for general messages or messages that do not require persistent visibility.
* **Sticky:**  On Android 14 and above, notifications remain in the tray even after the user performs a bulk dismissal, ensuring that important alerts such as critical system messages or high-priority updates stay visible until the user explicitly clears them. Use the Sticky option to keep important alerts accessible and prevent accidental dismissal.

<Image align="center" alt="Notification Behavior" border={true} caption="Notification Behavior" src="https://files.readme.io/b0cfaab970524e37fad67aa1e645e6f7d810be916fdfea6b3ab2b3c42b13b2c6-image.png" width="65% " />

## Dismiss Notification

This option determines how and when a notification is dismissed from the notification tray. It helps control the duration and visibility of messages, making it useful for time-sensitive messages such as flash sales, daily updates, or event reminders. It is available only for Android OS and is supported for Android SDK v7.6.0 and Push Templates SDK v2.2.0 and above.

The following are the available options:

* **Manual:** The notification stays in the tray until the user manually removes it. This option is ideal for important messages that should remain visible until acknowledged by the user.
* **Auto**: The notification is automatically dismissed after a specified duration, up to a maximum of 24 hours. This option works well for temporary or time-bound alerts that do not require user interaction.

<Image align="center" alt="Dismiss Notificatiom" border={true} caption="Dismiss Notification" src="https://files.readme.io/c740918fae5e4fbf4e8e8dad8203a1b9004967ae92bac1c429c9d7080107dc10-image.png" width="65% " />
