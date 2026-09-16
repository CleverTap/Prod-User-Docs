---
title: Advanced Web Pop-up Builder
excerpt: >-
  Learn how to edit and design Web Pop-up campaigns from the CleverTap
  dashboard.
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

CleverTap's Advanced Web Pop-up Builder allows marketers and designers to create visually appealing and engaging desktop and mobile Web Pop-up messages. It is fully interactive, allowing you to easily drag and drop elements and adjust their position and size. Marketers can use such pop-ups to capture leads, announce flash sales, or offer personalized discounts, without disrupting the user experience. This document walks you through the main features of the Web Pop-up Editor and its usage to help you maximize your website's experience.

The Advanced Web Pop-up Builder provides flexibility and ease of use to craft visually rich and responsive pop-ups. Using the Web Pop-up Builder you can do the following:

* **Custom Layout**: Arrange and layer elements in the desired layout to suit your campaign design.
* **Element Stacking**: Overlay elements such as text, images, and buttons for more visually engaging designs.
* **Built-in Animations**: Enhance user interaction with entry and exit animations.
* **Comprehensive Styling Controls**: Access a wide range of styling options for every element, such as color, position, border, and more, giving you precise control over the appearance.

# Advanced Web Pop-up Builder Template

The Advanced Web Pop-up Builder Template enables you to create highly customized and responsive web pop-ups directly from the campaign builder, tailored for both desktop and mobile devices. To use the Advanced Web Pop-up Builder template:

1. From the _What_ section in the Web Pop-up campaign, select the _Message Type_ and click **Go to Editor**. The Web Pop-up templates are displayed.


<Image src="https://files.readme.io/cbffccb3e763bb0ca067919f75f30f787c1ca0e43ec94b23d68cd55c1f6b2b5b-Builder.png" alt="Advanced In-App Builder" align="center" border={true} />


2. From _Builders_, select _Advanced Web Pop-up Builder_.


<Image src="https://files.readme.io/d4bc66f27d6521486e649c949546b3882d4e694360927db3465d7915e5b82b6d-Editor_-_Pop_up.png" alt="Advanced In-App Builder" align="center" border={true} />


It is divided into two main sections:

* **Canvas (Left Side)**: The canvas is where you design your Web Pop-up.
* **Controls & Styling Menu (Right Side)**: This menu contains controls and styling options for the elements on the canvas. Any changes made here instantly reflect on the canvas in real time.

# Element Operations

This section explains how to add, layer, remove, and edit elements in the Advanced Web Pop-up Builder. In the Advanced Web Pop-up Builder, _Elements_ are the core components used to construct your message. You can perform the following operations:

* [Device Previews](https://docs.clevertap.com/docs/advanced-web-pop-up-builder#device-previews)
* [Add New Elements](https://docs.clevertap.com/docs/advanced-web-pop-up-builder#add-new-elements)
* [Layer Elements](https://docs.clevertap.com/docs/advanced-web-pop-up-builder#layer-elements)
* [Remove Elements](https://docs.clevertap.com/docs/advanced-web-pop-up-builder#remove-elements)
* [Edit Elements](https://docs.clevertap.com/docs/advanced-web-pop-up-builder#edit-elements)
  * Text
  * Image
  * Button
  * Container

## Device Previews

Toggle between Desktop and Mobile device views to create the Popups for desktop and mobile users:

* **Desktop**: Use the Device Preview list to preview the pop-up across various screen widths, such as 320px, 768px, or 1024px. This helps ensure responsive behavior on different browser sizes.
* **Mobile**: Select the phone or tablet from the Device Preview list to preview the pop-up on a range of phone and tablet models. This allows you to tailor the experience based on screen dimensions and device form factors.


<Image src="https://files.readme.io/fc0fa714dc1f6f8363a58ae13c89b5a9e0c94d44e14ff26378328b98e63beb86-Devices.png" alt="Device Options" align="center" border={true} />


<Callout icon="⚠️" theme="warn">
  ### Note

  Desktop and Mobile sections are independent of each other and you must create separate designs for both device types.
</Callout>

## Add New Elements

You can enhance your Web Pop-up message by adding elements and using the available styling options to ensure it aligns with your brand's style/aesthetics. Click **Add** on the canvas to insert one of the following elements:

* **Text**: Add text to convey your message.
* **Image**: Incorporate visuals or branding images to create an engaging experience. Image elements can also function as buttons, enabling call-to-actions directly from the image.
* **Button**: Create call-to-action buttons, such as _Buy Now_ or _Learn More_, with precise control over the design and positioning.
* **Container**: Hold all the content, such as text, images, and buttons, and determine the layout structure.


<Image src="https://files.readme.io/ac77c95b59cde1ed9603df300b62ad975dcc5cfc554aa6307d75b640999647b3-2025-08-03_00-08-30_1.gif" alt="Add New Elements" align="center" border={true} />


## Layer Elements

The Web Pop-up Builder supports multiple elements and visual hierarchy. When working with stacked elements such as images, text boxes, or buttons, the _Bring Forward_ and _Send Backward_ buttons manage their visibility on the user's screen.

* Click **Bring Forward** to move an element to the front.
* Click **Send Backward** to push it behind other elements.


<Image src="https://files.readme.io/22c0e8c9014f95714ece81c8f9c4ea9b6994311d0ae88d4aae19c04c1d0a85a3-2025-08-02_21-39-15_1.gif" alt="Bring Forward and Send Backward Buttons" align="center" border={true} />


## Remove Elements

To delete an element:

1. Select the element on the canvas.
2. Click the **Remove Element** icon.

<Callout icon="⚠️" theme="warn">
  ### Note

  This action is permanent and cannot be undone.
</Callout>


<Image src="https://files.readme.io/50fbbb722545d35e610f2fe36eb5b391c1a06241c88d081c9f6905fa4631e9d8-2025-08-02_23-24-26_1.gif" alt="Remove Element" align="center" border={true} />


## Edit Elements

Each element has its own set of editable properties available from the **Controls & Styling Menu**. Refer to the following table for element-specific styles and behaviors:

<Table>
  <thead>
    <tr>
      <th>
        **Element**
      </th>

      <th>
        **Editable Properties**
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Text**
      </td>

      <td>
        * **Name**: Add an internal reference name for the Text element.<br /> - **Content**: Add or edit the display text as per your brand guidelines.<br /> - **Color & Gradient**: Customize solid or gradient fill for the text.<br /> - **Size & Style**: Adjust font size, bold, italics.<br /> - **Alignment**: Align the text in the left, center, or right position of the container.<br /> - **Background**: Apply solid (default) or gradient background color.<br /> - **Border**: Define border color, width, and radius.<br /> - **Size & Position**: Set width and height in percentages for responsive layout.
      </td>
    </tr>

    <tr>
      <td>
        **Image**
      </td>

      <td>
        * **Name**: Add an internal reference name for the Image element.<br /> - **Upload File**: Insert images from your system.<br /> - **Alt Text**: Add alternate text for accessibility.<br /> - **Action on Tap**: Assign click behavior (for example, open URL).<br /> - **Size & Position**: Adjust dimensions responsively.
      </td>
    </tr>

    <tr>
      <td>
        **Button**
      </td>

      <td>
        * **Name**: Add an internal reference name for the Button element.<br /> - **Action on Tap**: Choose the button’s function (for example, redirect, close pop-up).<br /> - **Text Content**: Label on the button.<br /> - **Text Styling**: Adjust font size, color, style (bold or italics).<br /> - **Background**: Customize default and active states.<br /> - **Border**: Customize the button border with color, width, and corner radius.<br /> - **Shadow**: Add depth with shadow color and blur.<br /> - **Size & Position**: Define layout using percentage values.
      </td>
    </tr>

    <tr>
      <td>
        **Container**
      </td>

      <td>
        * **Position & Size**:<br /> - **Aspect Ratio**<br /> - **Width** and **Position** (Top, Bottom, Center)<br /> - **Margin** around the container<br /> - **Dismiss After Delay**: Auto-dismiss pop-up after a defined time (in seconds).<br /> - **Container Action on Tap**: Trigger behaviors like close, redirect, etc.<br /> - **Background**:<br /> - **Color** and border radius<br /> - **Image** upload with alt text and styling
      </td>
    </tr>
  </tbody>
</Table>

## Add Animations

Animations enhance visual appeal and improve user experience. The builder provides built-in animation options for the **Container** element.


<Image src="https://files.readme.io/4e6849faba89920ee2272087500aa47889d47d1969d91cac8404f5fbb2a0eb4b-2025-08-02_21-21-32_2.gif" alt="Animation" align="center" border={true} />


From the Container element, configure various animation options as follows:

* **Animation types**: Choose from Instant (default), Dissolve, or Move In animations.
* **Duration**: Duration is set in milliseconds, allowing you to experiment with different values and observe the effect in the canvas.
* **Easing**: Following options are available for Dissolve and Move In animations.

| Easing Options  | Description                                                                                                                                         |
| :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------- |
| Linear          | Moves at a constant speed from start to finish, creating a uniform motion.                                                                          |
| Ease In         | Fades in, creating a smooth entrance.                                                                                                               |
| Ease Out        | Fades out, creating a smooth exit.                                                                                                                  |
| Ease In and Out | Fades in and out from start to finish.                                                                                                              |
| Cubic Bezier    | A customizable easing option where you define the exact acceleration curve using Bézier control points (ideal for fine-tuning advanced animations). |

* **Replay Animation**: Preview the effect by replaying the animation in the Canvas.

# Configuring Web Pop-up Campaigns

Once the Web Pop-up is designed using the builder, you can set up the Web Pop-up campaign to control when, where, and to whom the pop-up is displayed. These targeting and delivery rules are defined during the campaign creation process.

For more information on how to configure these options, refer to [Create Message](https://docs.clevertap.com/docs/create-message-web-popup).

# FAQs

### Can I stack images, buttons, and text?

Yes. Use the Bring Forward and Send Backward options to control the visual layering of elements.

### Can I preview my Web Pop-up before launch?

The _Preview and Test_ feature is currently unavailable for the Builder. To test your Web Pop-up message on a real device, exclusively send the campaign to a specific test user or segment for testing. After you are done testing, recreate the campaign and send it to your intended audience. For more information on test users, refer to [Mark a User Profile as a Test Profile](https://docs.clevertap.com/docs/user-profiles#mark-a-user-profile-as-a-test-profile).

### What happens if I only configure the desktop version and not the mobile version, or vice versa?

The Desktop and Mobile sections are independent of each other and you must explicitly configure pop-ups for both device types. Pop-ups created for desktop do not automatically adapt to mobile, and vice versa.

### Is Liquid Tag personalization supported in the Advanced builder?

Yes. Liquid Tags are supported, allowing you to personalize content dynamically within your Web Pop-up campaigns. For more information, refer to [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags).
