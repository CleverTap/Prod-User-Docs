---
title: Advanced Personalization
excerpt: Learn how to use Web Native Display Editor for advanced personalization.
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

Advanced Personalization in CleverTap lets you customize and personalize your website content dynamically based on user attributes, behaviors, and events. It includes powerful tools like the Visual Editor, helping you deliver relevant, real-time experiences with minimal development effort.

# Visual Editor

The Visual Editor template empowers marketers to tailor specific elements on their website, enhancing the user experience for their target audience. This feature lets marketers personalize various content types, such as text or images, using custom HTML or JSON. For instance, marketers can modify the textual content to better resonate with their audience or adjust image content to be more visually appealing and relevant, all through a user-friendly interface and zero development effort.

<Callout icon="📘" theme="info">
  ### Note

  CleverTap offers Visual Editor as a paid add-on. Contact your customer success manager to enable this feature for your account.
</Callout>

### Prerequisites

Before you start using the Visual Editor, ensure the following prerequisites are met:

- **Web SDK v1.13.1** and above support the Visual Editor. To check your Web SDK version, use the `clevertap.getSDKVersion` method.
- Ensure that the Content Security Policy (CSP) value for `frame-ancestors` contains `self`. Without this configuration, the Visual Editor will not work.
- Check that the following header is set on your website to enable the required functionality:

```
* Cross-Origin-Opener-Policy: same-origin-allow-popups
  Cross-Origin-Embedder-Policy: unsafe-none
```

### Access Visual Editor

To get started, from the _What_ section in the Web Native Display campaign builder, select your message type and click **Go to Editor**:

1. Go to _Advanced Personalization_  and select **Visual Editor**.


<Image src="https://files.readme.io/cf837f4296717228fbaddc0af9eedff07cfed6313eed05e7f15f25b361a76718-2025-03-23_16-00-49.png" alt="Visual Editor" align="center" caption="Visual Editor" border={true} />


2. Enter the webpage URL you want to personalize and click **Continue**. The web page loads within the editor in a new tab.


<Image src="https://files.readme.io/4abc617-url.jpg" alt="Define Webpage URL" align="center" caption="Enter Webpage URL" border={true} />


3. After the website loads in the editor, hover over the elements to highlight them. Click any element to open the inline editor menu to edit the specific element. The dropdown menu appears with the following options:
   - [Edit Element](https://docs.clevertap.com/docs/advanced-personalization#edit-element)
   - [Edit HTML](https://docs.clevertap.com/docs/advanced-personalization#edit-html)
   - [Hide](https://docs.clevertap.com/docs/advanced-personalization#hide)
   - [Insert Element](https://docs.clevertap.com/docs/advanced-personalization#insert-element)
   - [Add JSON](https://docs.clevertap.com/docs/advanced-personalization#add-json)
   - [Track Clicks](https://docs.clevertap.com/docs/advanced-personalization#track-clicks)


<Image src="https://files.readme.io/c85e7610925b65d319ebf070ed33a4b47eb7c0b36ae450b31738ba8ee6c57257-2025-03-23_16-20-39.png" alt="Select Editor" align="center" caption="Select Editor" border={true} />


#### Edit Element

The edit element feature allows you to modify various aspects of the element, such as color, margin, font, text style, etc.


<Image src="https://files.readme.io/3231a766c38ad64153087bb63af20bb25b558e22093c2471a89a07be9fd2e1a6-2025-03-23_18-00-18_1.gif" alt="Edit Element" align="center" caption="Edit Element" border={true} />


Visual Editor supports user-level personalization using profile and event properties. Click the \{\{ \}\} icon in the editor to use liquid scripting.


<Image src="https://files.readme.io/7e5f40fde7c193e6a6b079495333c7bf5c334800d94a15ed0f427544055336b8-2025-03-23_18-09-19.png" alt="Personalisation in Visual Editor" align="center" width="100% " caption="Personalization in Visual Editor" border={true} />


#### Edit HTML

You can change the Editor by selecting **Edit HTML** from the dropdown. The HTML editor allows you to modify the selected element's HTML according to your use case.


<Image src="https://files.readme.io/09dc96c7fe21166f3b80ceee4d606c3db0692aee614fc9fb66dba731fb405a16-html.png" alt="Custom HTML" align="center" caption="HTML Editor" border={true} />


#### Hide

The Hide option allows you to hide a particular element. You can hide it for desktop, mobile, all devices, or none.


<Image src="https://files.readme.io/a9e28e12650d4a6755b4539c5003b90d74146ada8b29e987cc21264cfc990f37-2025-03-23_17-52-26.png" alt="Hide on devices" align="center" caption="Hide on devices" />


#### Insert Element

This feature allows you to insert a new element to your webpage. You can configure its position and margin or duplicate an existing element.


<Image src="https://files.readme.io/d89ea5257531e0beaa999ec0240337c4b123cb9da42b62e0288e09b2e45f694c-2025-03-23_17-54-16.png" alt="Insert Element" align="center" caption="Insert Element" border={true} />


#### Add JSON

You can change the Editor by selecting **Add JSON** in the dropdown. The JSON editor allows you to define custom behavior or personalization logic.


<Image src="https://files.readme.io/fb3067387607ece0ce6ff232203fb840e00723a64555cae98c97127a22a53a2a-l.png" alt="Add JSON" align="center" caption="Add JSON" border={true} />


#### Track Clicks

The Click Tracking feature allows element-wise tracking. Click **Track Clicks**, add a name, and click **Save** to start tracking. This name will be added as a value of the `wzrk_c2a` property in the Notification Clicked event. You can view the Click Tracking data under _Dashboard_ > _Analytics_ > _Events_. For more information, refer to [Events](https://docs.clevertap.com/docs/events).


<Image src="https://files.readme.io/0b2e587c69925bd3ef26c3528c53f5f6f84bfca007bebeb4c9f86e59fd1eac09-2025-03-23_17-49-02.png" alt="Track Clicks" align="center" caption="Track Clicks" border={true} />


4. Preview and edit your website as it appears on desktop and mobile devices using the _Device Toggle_.


<Image src="https://files.readme.io/b2dc3a6daaa8bd3d07eb59676c835fafee7d17bd118aece7592010fd7037ee48-2025-03-23_16-42-07_1.gif" alt="Mobile View" align="center" caption="Mobile View" border={true} />


5. Use the dropdown menu to adjust screen sizes and test responsiveness.


<Image src="https://files.readme.io/e83e2b0506a6544ae5a677cefd8600276b1284beaec04d0bd43161445c411a6b-2025-03-23_16-44-30.png" alt="Web Size" align="center" width="100% " caption="Web Resolution" border={true} />


<br />


<Image src="https://files.readme.io/11942134a1cbf707b76db0af2cb7af5270b9dc263423a0f588cf575deb7ddd21-2025-03-23_16-46-17.png" alt="Mobile Size" align="center" width="100% " caption="Mobile Resolution" border={true} />


6. Toggle the **Browse mode** to make the webpage interactive inside the editor.


<Image src="https://files.readme.io/ae9ad6940d17b173d542a5fae23011f6de87ab02e3d3b0ac9c11242d9e1b2349-image.png" alt="Browse Mode" align="center" caption="Browse Mode" border={true} />


7. Click **Changelog** to view a summary of all changes made during the session. Clicking on each changelog automatically highlights the corresponding changed element. You can long press the view button to compare the original version with your latest changes. Click the delete button to delete a specific change or click **Clear All** to delete all changes.

<Callout icon="📘" theme="info">
  ### Note

  Deleted changes cannot be restored.
</Callout>


<Image src="https://files.readme.io/ce3132c035dd478c70249e369cf07ba363c7291174433351d3df598be2ecc172-2025-03-23_16-49-38.png" alt="Changelog" align="center" caption="Changelog" border={true} />


8. Click the **Preview** button at the top right corner to preview the HTML changes in a new tab.
9. Click **Save** to apply your changes.

# Custom Templates

For custom use cases, two new advanced web personalization templates are now available for Web Native Display campaigns. These templates are designed for creating more impactful campaigns and offer flexibility beyond basic UI-based templates. They allow for advanced web personalization use cases outside Visual Editor.

- [Custom HTML Template](doc:web-native-display-editor#custom-html-template)
- [Custom JSON Template](doc:web-native-display-editor#custom-json-template)

<Callout icon="📘" theme="info">
  ### Note

  - CleverTap offers Custom Templates as a part of the _Advanced Web Personalization_ paid add-on.
</Callout>


<Image src="https://files.readme.io/ff74e3ce480f8412fdc48492526b73dea436a23a87c0ee3d3380c2fdea4fcf6b-image.png" alt="Custom Templates in Advanced Personalization" align="center" caption="Custom Templates in Advanced Personalization" border={true} />


### Custom HTML Template

Custom HTML Template allows you to add dynamic content to your website to achieve advanced use cases such as modifying website layouts. By adding HTML, CSS, and JavaScript code directly within a built-in code editor, marketers can enable product recommendations, reorder elements, and display personalized offers based on user behavior.


<Image src="https://files.readme.io/ae36756a6fd85690fe69e291a16681da46f26fde4e0902fafbc458b30ccda044-Custom_HTML_template.png" alt="Custom HTML Template" align="center" width="100% " caption="Custom HTML Template" border={true} />


### Custom JSON Template

Custom JSON Template lets you send JSON data from CleverTap to your target user's website, allowing you to render advanced personalization use cases.


<Image src="https://files.readme.io/941447672dae7eb8100e84c6edf5afb30e871a7b81da8632ce12bdb852455d17-image.png" alt="Custom JSON Template" align="center" width="100% " caption="Custom JSON Template" border={true} />
