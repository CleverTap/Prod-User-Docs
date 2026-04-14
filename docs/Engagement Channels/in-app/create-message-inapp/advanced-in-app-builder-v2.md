---
title: Advanced In-App Builder 2.0
excerpt: Learn how to edit and design In-App campaigns from the CleverTap dashboard.
deprecated: false
hidden: false
metadata:
  title: Advanced In-App Builder 2.0
  robots: index
---
# Overview

CleverTap's Advanced In-App Builder enables the creation of visually appealing and engaging mobile In-App messages that align with your brand's aesthetics. This document guides you through the main features of the In-App Editor and its usage, helping you maximize the feature's potential.

<Image align="center" alt="Sample In-App with Advanced Builder" border={false} caption="Sample In-App Message with Advanced Editor" src="https://files.readme.io/70dd7cd5e206879de2a4edbe492e11ab7d733e3879aedc4cae3a553d6121405b-Starting-image-1.png" width="40% " />

The Advanced In-App Builder offers remarkable flexibility and ease of use. Here are the key features:

* **Automatic Scaling**: Content automatically adjusts to fit any device size, ensuring consistent presentation across all platforms.
* **Custom Layout**: Arrange elements in the container to create any desired layout.
* **Stacking Elements**: Overlay images or other elements for more complex and visually engaging designs.
* **Styling Options**: Access a wide range of styling options for every element, giving you precise control over the appearance.
* **Dismiss Button Controls**: Customize the appearance and behavior of the dismiss button, including its style and placement.
* **Animation**: Enhance user interaction with dynamic effects such as slide or fade-in animations.

# Advanced In-App Builder Template

To use the Advanced In-app Builder template:

1. From the _What_ section in the In-App builder, select the _Message Type_ and click **Go to Editor**. The In-App templates are displayed.

<Image align="center" alt="Advanced In-App Builder" border={true} caption="Advanced In-App Builder" src="https://files.readme.io/886bdbb6e9513fa588e41a43d85f09af9c4b0d7431a0b81cdbe25d1e69f858bc-Screenshot_2024-10-11_at_11.53.15.png" />

2. From _Basic Templates_, select _Advanced In-app Builder_. The Advanced In-App Builder displays.

<Image align="center" alt="Advanced In-App Builder" border={true} caption="Advanced In-App Builder" src="https://files.readme.io/b71a90dc51c963fa8eb012090cb6794a5b06fda319cf5132001f75264bb43fa8-Controls.png" />

The Advanced In-App Builder has a _What You See Is What You Get (WYSIWYG)_ interface, which allows you to make modifications in real-time.

It is divided into two main sections:

* **Canvas (Left Side)**: The canvas is where you design your In-App message. It is fully interactive, allowing you to drag and drop elements and adjust their position and size with ease.
* **Controls & Styling Menu (Right Side)**: This menu contains controls and styling options for the elements on the canvas. Any changes made here are instantly reflected on the canvas in real-time.

> 📘 Test and Preview
>
> The _Preview and Test_ feature is currently unavailable for the Builder. To test your In-App message on a real device:
>
> 1. **Send the Campaign**: Exclusively send the campaign to a specific user for testing.
> 2. **Recreate and Send**: After you are done testing, recreate the campaign and send it to your intended audience.

## Builder Elements

In the Advanced In-App Builder, _Elements_ are the core components used to construct your message. Upon opening the builder, three default elements are available, as shown in the following image:

<Image align="center" alt="Default Elements" border={true} caption="Default Elements" src="https://files.readme.io/77bb8a26baf882c3b13aedce32a82f8b811ccab024ae59f5f80077b3ed0e39ac-image.png" width="50% " />

### Overlay

The overlay provides a background for your In-App message, ensuring a seamless, integrated look.

<Image align="center" alt="Design Overlay" border={true} caption="Design Overlay" src="https://files.readme.io/59d4503d9c0cbbc300f4e5d245189b55d4b065e499d310f33724c110f8d82b84-Overlay_slider.gif" />

The overlay allows you to modify the following:

* **Transparency level**: Control the transparency level of the Overlay.
* **Color Background**: Add a color background.
* **Image Background**: Add an image as a background. Click **Upload** to add an image.

### Container

The _Container_ holds all the content in your In-App message, such as text, images, and buttons, and defines how the message appears on a user’s screen.

<Image align="center" alt="Design Container" border={true} caption="Design Container" src="https://files.readme.io/1626def427219d29d0892846f9c54eb4ce46a4b19a1ecb09fdd2a24c40f8d890-image.png" />

#### Container Properties

You can customize the following properties to control the look, behavior, and visual design of your In-App message:

* **Position:** Choose where the message appears on the screen (Top, Center, or Bottom).
* **Size:** Select from predefined size options such as Wide, Square, Tall, or Extra Tall, depending on your layout.
* **Margin:** Adjust the margin percentage to create space between the message and the device edges.
* **Delay:** Set a delay after which the in-app message automatically dismisses.

#### Container Action

Define what happens when users tap the container.

| Action Type            | Description                                                                                                                                                                   |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **No Action**          | No behavior is triggered when the container is tapped.                                                                                                                        |
| **Close Notification** | Closes the in-app message.                                                                                                                                                    |
| **Open URL**           | Opens a specified URL link.                                                                                                                                                   |
| **Key–Value Pair**     | Adds a key-value pair for tracking or personalization.                                                                                                                        |
| **App Function**       | Triggers app-level functions such as requesting push permission or app rating. For more information, refer to [App Functions](https://docs.clevertap.com/docs/app-functions). |

#### Background

Apply a background color or image to your design. You can do the following:

* Choose a **solid color** using a color picker or hex code.
* **Upload an image** directly from your system and add **alt text** for accessibility and search. For more information on images, refer to [Image Size and Aspect Ratios](https://docs.clevertap.com/docs/advanced-in-app-builder#image-size-and-aspect-ratios).

#### Font and Text

Control how text appears within your container. For more information, refer to [Custom Fonts](https://docs.clevertap.com/docs/advanced-in-app-builder#custom-fonts).

#### Border Radius

Adjust the level of rounding on the container’s corners. A higher value results in more rounded corners.

For example: `Border Radius: 2` gives slightly curved edges, while higher values create a more pill-shaped container.

#### Initial Animation

Control how your container appears when the in-app message loads.

| Animation Type | Description                                                       |
| -------------- | ----------------------------------------------------------------- |
| **Instant**    | The container appears immediately without animation.              |
| **Dissolve**   | The container fades into view smoothly.                           |
| **Move In**    | The container slides into the screen from a predefined direction. |

### Image Size and Aspect Ratios

The available container size options vary depending on the orientation of the container. Use the following tables to understand the aspect ratio of each option.

<Callout icon="📘" theme="info">
  #### Note

  Aspect ratios ensure your in-app content appears correctly across different devices and orientations. Confirm the correct orientation before finalizing your design.
</Callout>

<Tabs>
  <Tab title="Portrait Orientation">
    Welcome to the content that you can only see inside the first Tab.

    | Size Option | Aspect Ratio |
    | ----------- | ------------ |
    | Extra Short | 4:1          |
    | Short       | 7:2          |
    | Mid         | 3:1          |
    | Tall        | 2:1          |
    | Extra Tall  | 5:4          |
    | Square      | 1:1          |
    | Wide        | 16:9         |
  </Tab>

  <Tab title="Landscape Orientation">
    Here's content that's only inside the second Tab.

    | Size Option | Aspect Ratio |
    | ----------- | ------------ |
    | Extra Short | 8:1          |
    | Short       | 7:1          |
    | Mid         | 6:1          |
    | Tall        | 5:1          |
    | Extra Tall  | 9:2          |
    | Square      | 1:1          |
    | Wide        | 16:9         |
  </Tab>
</Tabs>

#### Supported Media

You can use the following media for your content:

| File Format | Description                                     |
| ----------- | :---------------------------------------------- |
| **JPEG**    | Best for photos and detailed images.            |
| **PNG**     | Ideal for transparent or high-quality graphics. |
| **GIF**     | Use for lightweight animations.                 |
| **Video**   | Use for short videos (up to 50 MB).             |

<Callout icon="📘" theme="info">
  #### Best Practices

  Optimize your images to improve message load time and prevent rendering issues on low-performance devices.
</Callout>

### Dismiss Button

The _Dismiss Button_ allows users to close the In-App message.

<Image align="center" alt="Hide/Display Dismiss Button" border={true} caption="Hide/Display Dismiss Button" src="https://files.readme.io/889f6fa799897269c2d9e9e3fe4ddc331f73720c8cffc3eb5cfdf946e48c8132-screenshot-1.png" />

## Add New Elements Inside Container

Click **Add** on the canvas to add _Text_, _Image_, or _Button_.

<Image align="center" alt="Add Elements in Container" border={true} caption="Add Elements in Container" src="https://files.readme.io/c1950ae9cf14eb15e517649ad93edc2319c50b83ef422e708c1b27c40e54e851-screenrecording-2.gif" />

You can enhance your In-App message by adding the following elements inside the container:

* **Text**: Add text to convey your message. Use the available styling options to ensure it aligns with your brand's style.
* **Image**: Incorporate visuals or branding images to create an engaging experience.
  * The builder supports multiple image elements, which you can stack on top of each other.
  * Image elements can also function as buttons, enabling a call-to-action directly from the image.
* **Button**: Create call-to-action buttons, such as _Shop Now_ or _Learn More_, with precise control over the design and positioning.

### Display Element Over or Behind an Element

When working with stacked elements such as images, text boxes, or buttons, the _Bring Forward_ and _Send Backward_ buttons manage their visibility on the user's screen. If one element overlaps another, clicking **Bring Forward** brings the selected element to the front, ensuring it is fully visible.

<Image align="center" alt="Bring Forward and Send Backward Buttons" border={true} caption="Position Elements" src="https://files.readme.io/296be8c99677e1a5a42d5b3070322bdf13c6bfbb8bb9ef33a4ef829fbe0ff4f8-screenrecording-3.gif" />

## Add Animations

The builder offers built-in animation options to enhance the user experience flow. Animations are configured from the Container element.

<Image align="center" alt="Animation" border={true} caption="Design Animation" src="https://files.readme.io/e3e774a3fdb678a01416ff17dbfd20226ab3fa857e7359e2551ae55449bd0a40-scheenrecording-1.gif" />

You can enhance user interaction with the help of various animation options as follows:

* **Animation types**: Choose from Instant (default), Dissolve, or Move In animations.  
  The Duration is set in milliseconds, allowing you to experiment with different values and observe the effect in the canvas.
* The **Duration** value can be set in milliseconds, and you can try different settings and see how they behave in the Canvas.
* The **Repeat** button replays the animation in the Canvas.

# Banners

Mobile Banner ads are a type of in-app message designed to subtly engage users without interrupting their app experience. They appear as small, rectangular strips anchored to either the top or bottom of the screen and can be static or animated using rich media.

Unlike Interstitial messages or full-screen Covers, Banners are _nonintrusive_. They do not block app interactions or obscure the rest of the screen. They allow seamless user activity while still effectively delivering your message.

<Image align="center" alt="Create in-app banner" border={true} caption="In-App Banner" src="https://files.readme.io/9405d9f1a56e914769b2147a3627b4e57d6592202ff5bfafe8a099c71ac95d6d-image.png" />

## Create Banners

You can customize Mobile Banners using the Container Element, which gives you complete control over the banner’s design, content, and behavior.

To create a Banner, follow these steps:

1. Go to _Advanced In-App Builder_ from the _Builders_ tab when creating an In-App message campaign.
2. Select the _Container_ element and apply the Top or Bottom position to create a Banner.
3. Customize your Banner by adding text or images. For more information, refer to [Adding New Elements inside Container](https://docs.clevertap.com/docs/advanced-in-app-builder#add-new-elements-inside-container).
4. Configure optional behaviors such as animations, tap actions, or dismiss rules.

Your Banner is ready to be used in an In-App campaign.

# Custom Fonts

The Advanced In-app Builder supports **Custom Fonts** for all Text content in your Mobile In-app Campaign. To use custom fonts, follow these steps:

1. Select _Advanced In-App Builder_ from the _Builders_ tab when creating an in-app message campaign. \{Go to, Navigate - What is used across the documentation?}
2. Select the _Container_ element to manage custom fonts.

<Image align="center" alt="Font Settings in Container" border={true} caption="Font Settings in Container" src="https://files.readme.io/154da0d64ddecb9d44d104b8e2d7e46e54f3e7e83244f6d98d0ffe263f67c420-image.png" width="50% " />

2. From the _Font_ list, select a font from _System Fonts_ or your _Custom Fonts_, which will be applied to all elements with Text in your Campaign.

<Image align="center" alt="Select Font " border={true} caption="Select Font" src="https://files.readme.io/99b50bebbb4e609093789b37b8d8907402b5d6639541bd57f7c628c98373d10a-Screenshot_2025-01-09_at_16.32.57.png" width="80% " />

3. Click the **Add** button to add your new Custom Font. You can either upload a **CSS file** containing your Custom Font or use the **URL** of an already hosted file.

<Image align="center" alt="Add New Custom Font" border={true} caption="Add New Custom Font" src="https://files.readme.io/015cb3f946f84d8d6a1b64e8604f11a0959caeceb8e8a6f3d5f21b1e11bfdc64-image.png" width="70% " />

4. Enter the following details to create your Custom Font:

   | **Field Name**  | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
   | --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | **Font Name**   | Uniquely identifies the font. This field has a limit of up to 50 characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   | **Font Family** | Defines the style applied to the font. This field has a limit of up to 50 characters. The custom font family must match the name of the font face in the CSS file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   | **Fallback to** | If the Custom Font fails to load on the device, we will use one of the FallBack Fonts to render the In-app Campaign.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
   | **Font URL**    | If the font is not on your local system, you can select this option to add the URL for the required font. The URL must point to a CSS file.<br />- If your custom font is a public font available on the web, you can add the URL for the font.<br />- If you upload the font to your private server, check that CORS is enabled on the server to provide the custom font file.<br /><br />The custom font file must have the following header: `Access-Control-Allow-Origin: *`. When defining font URLs in the `src` attribute, utilizing the `https` protocol is essential. Refer to the [Sample CSS Code](doc:advanced-in-app-builder#sample-css-code). |
   | **Upload Font** | If you already have a font file on your local system, choose **Upload Font**, and click **Upload** to upload the CSS file for your custom font. The file size should be a maximum of 1 MB.                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

   <br />

## Sample CSS Code

```css CSS
@font-face {
  font-family: 'Dancing Script';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: url(https://fonts.gstatic.com/s/dancingscript/v25/If2RXTr6YS-zF4S-kcSWSVi_szLgiuEHiC4W.woff2) format('woff2');
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+0304, U+0308, U+0329, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}
```

# FAQs

### How do I add new elements other than the default ones?

To add new elements, use the controls on the right side of the builder to drag and drop images, text, and buttons directly into the container.

### Can I preview my In-App message before sending it out?

Yes. The Preview and Test feature is available from Android SDK v7.7.0 and CleverTap iOS SDK v7.4.0 and later.

### Can I use personalized message content?

Yes. You can use the [Inline Personalization](doc:personalize-message-inapp#inline-personalization) in the preview message.

### Are there limitations on device sizes or layouts

No, the content automatically scales to fit any device size, ensuring consistency across platforms.

### What aspect ratio should I pick for landscape orientation?

Aspect Ratios of 1:1 and 16:9 are ideal for creating In-App content in landscape orientation.