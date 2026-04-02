---
title: Web Pop-up Editor
excerpt: The Web Pop-up Editor allows you to edit and design your messages.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
# Overview

The Web Pop-up Editor is a feature available when building a Web Pop-up message in CleverTap. It enables you to add content to pre-built templates or customize and build them. After creating a Web Pop-up template, you can use it in the current campaign or save it for future campaigns.

From the _What_ section in the Web Pop-up builder, Select Message Type and click **Go to Editor**.

The Web Pop-up Editor tool displays.

```
```

<br />

<br />

# Editors and Templates

There are three types of editors available:

* Basic Editor
* Custom HTML Editor
* Drag and Drop Editor

You can choose between pre-built or empty templates under _Basic Templates_. With the Drag and Drop Editor, you can save customized templates and view them under **Saved Templates**.

# Basic Editor

You can choose from the following types of templates under Basic editor:

* **Basic Editor**
  * **Basic Templates**: Different types of popup layouts.
  * **Ratings Templates** : Used for gathering feedback and rating.
  * **Lead Generation Templates** : Used to generate new leads by recording anonymous users' email addresses and mobile numbers.

## Basic Templates

At a high level, one can choose from four styles of popup layouts available under Basic Templates:

* **Box** - It is a small popup that can be placed at the desired corners of the browser window.
* **Banner**- It is a wide horizontal popup that can be placed at the top or bottom of the browser window.
* **Interstitial** - It is a center-aligned popup for driving better engagements.
* **Image only** - As the name suggests, this template can render an image as a popup on your website. The Image can have all the content like title, description, and CTA as part of it.

## Ratings Template

Marketers can now create feedback-related popups (Interstitials only) for their website users using the _Ratings Template_.

Marketers can now create the following types of rating templates for gathering feedback from their customers:

* NPS
* NPS with Follow-up Question
* User Rating
* User Rating with Follow-up Question

The following images represent a sample user rating popup and an NPS popup.

<Image alt="User Star Rating Popup" border={true} width="50% " src="https://files.readme.io/4062d44-Web_Popup_NPS_rating_Star.jpg" className="border" /> User Ratings Popup

<Image alt="NPS Popup" border={true} width="50% " src="https://files.readme.io/ce8fb86-Web_Popup_NPS_rating_Numbered.jpg" className="border" />  NPS Ratings Popup

Marketers get the complete flexibility to explicitly define the rating scale, style,  its shape (Star, Heart, Emojis), labels, and the overall content of the popup. One can also add a comment box to get accurate user feedback/comments.

<Image alt={1710} border={true} width="70% " src="https://files.readme.io/7bbc6cc-styling.png" title="Edit Style" className="border" />  Define Element Style

Besides, additional styling, such as the background color of the notification, text color, button color, and the color of the rating scale, is also possible from the editor, as shown in the image above. To learn more about tracking and monitoring user rating data, refer to the [Analyzing User Rating](https://docs.clevertap.com/docs/user-ratings).

The web popup notification text fields in the following image can be personalized for every user based on specific user property or event property values. For more information, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](https://docs.clevertap.com/docs/events).

Add all the required information. You can also flip the scale for languages that read from left to right. For example, Hebrew, Arabic, and so on.

<Image alt="Personalize Web Popup" border={true} width="70% " src="https://files.readme.io/5241786-web_inbox_NPS_Template.png" className="border" />  Personalize Web Popup

### NPS Campaign Video Tutorial

Here's a video tutorial that demonstrates how you can create an NPS campaign on CleverTap:

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/205P660UOtvYy6BLsVuvrg/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

#### Follow-up Question Templates

A follow-up question to your ratings can provide more insights about the user experience. CleverTap provides the following Follow-up Question templates:

* NPS with Follow-up Question
* User Ratings with Follow-up Question

For example, after a user has submitted a rating on your app, you can ask follow-up questions such as _What did you like most about us?_ and provide reply choices such as Variety, Prices, Quality, Customer Service, Delivery Process, and Website Usability. This can help you get more specific feedback to improve your product and services.

<Image alt="Short Keyword Choices" border={true} width="50%" src="https://files.readme.io/71b74e6-web_popup_Secondary_Tiles.jpg" className="border" /> Short Keyword-Based Choices

You can also list descriptive choices such as, _I like the available options and variety_, _I like the quality and durability of the products_, and so on.

<Image alt="Long Sentence Choices" border={true} width="50%" src="https://files.readme.io/a95c15a-web_popup_Secondary_List.jpg" className="border" /> Descriptive Choices

You can configure the follow-up question from the Web Popup editor with a short keyword-based grid (up to six choices) or a longer sentence-based list (up to four choices).

The label will be the text you want to display to your users. If you want to allow the user to select multiple choices, select _Allow multiple selections_.

<Image alt="Configure Follow-up Popup" border={true} width="80%" src="https://files.readme.io/fd33f9a-image_18.png" className="border" /> Configure Follow-up Popup

> 📘 Note
>
> In the case of the User Ratings template, the _Notification Clicked_ event is raised that records the user's clicks on the CTA buttons and the Close button.

## Lead Generation Templates

We know that a significant number of website visitors remain anonymous. This poses a challenge to continue engaging with potential customers after they leave a website. A lead generation template can solve this issue.
By integrating a lead generation form on your website, you can get important customer details such as name, email address, phone number, and so on. This information is helpful for further communication through channels such as SMS, Email, WhatsApp, and others. This post-visit communication not only helps to stay connected with your audience but also opens doors for future business opportunities. You can turn anonymous visitors into loyal customers with the CleverTap Lead Generation template.

<Image alt={1368} border={true} src="https://files.readme.io/888a43a-Lead_Gen_Template_Sample.png" title="Lead Gen Template Sample.png" className="border" /> Sample Lead Generation Template

### Lead Generation Campaign Video Tutorial

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/PSJucX1rI238Nvjwio4X7g/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

### Post Submit Actions

When a user submits information on your Lead Generation template:

* A _Notification Clicked_ event is raised that records the user's clicks on the CTA and the Close buttons.

* A custom event named _Lead Submitted_ records the details submitted by the user as event properties. Following is a sample form image:

<Image alt="Form Submit Actions" border={true} width="50% " src="https://files.readme.io/0cae15f-Lead_Gen_Template_preview_with_fields.png" className="border" /> Form Submit Actions

Following is a table that records the relevant event properties for the fields displayed on the form:

| Submitted Event Properties | Sample Property Value               |
| :------------------------- | :---------------------------------- |
| First Name                 | John                                |
| Last Name                  | Smith                               |
| Email ID                   | [john@abc.com](mailto:john@abc.com) |
| Phone Number               | +11234567890                        |
| Campaign ID                | 121110987654                        |
| Variant                    | wzrk_default                        |

* The user profile is automatically updated with the submitted event properties. For example, the lead generation template can ask for additional details from an anonymous user, such as first name, last name, email, and phone number. His profile will be updated with these details, and now you can identify the user as _John Smith_.

### Lead Generation Template Variants

The Lead Generation template has the following three variants:

* Text Only
* Image On Side
* Image On Top

<Image alt="Lead Generation Template Types" border={true} src="https://files.readme.io/dd75b54-Lead_Gen_Template_Tab.png" className="border" />  Lead Generation Template Types

Select any of the variants to create your Lead Generation template.

### Lead Generation Content

Create the content to record information from your users. The following image displays a preview of the form:

<Image alt={2364} border={true} src="https://files.readme.io/2daa708-Lead_Gen_Template_Editor_Content.png" title="Lead Gen Template Editor Content.png" className="border" />  Create Lead Generation Template in Editor

Enter all the required information.

* _Text_: Personalize the Title and Description.
* _Media_: Add the image URL or upload an image.
* _Input Fields_: You can add up to four input fields. Select input fields such as Name, Phone Number, Birthday, or Email Address for the template.

<Image alt={1304} border={true} width="60% " src="https://files.readme.io/6a87857-Lead_Gen_Template_Input_Fields.png" title="Lead Gen Template Input Fields.png" className="border" />  Upto Four Input Fields

* _Buttons_: The _Close_ button is selected by default. Add a button name such as _Submit_ or _Upload_.
* _Subtext_: Add subtext such as _privacy policy_ to your lead generation template.

<Image alt="Add Subtext" border={true} width="55%" src="https://files.readme.io/bb6e1f2-Lead_Gen_Template_SubText_preview.png" title="Lead Gen Template SubText preview.png" className="border" />  Add Subtext

The hyperlinked part must be closed between two asterisks. Add the URL in the following URL box. This is the URL where the user will be directed. You can also add a checkbox for your subtext.

<Image alt="Subtext and redirect URL" border={true} width="55%" src="https://files.readme.io/d740b86-Lead_Gen_Template_SubText.png" title="Lead Gen Template SubText.png" className="border" />  Subtext and redirect URL

* _Acknowledgement_: You can show appreciation to your user by adding an Acknowledgement popup. Select the auto-close timer for the popup.

### Lead Generation Template Style

You can select the layout and card position from this screen. You can also select the color of the text, input fields, and buttons.

> 📘 Mobile View
>
> The Mobile view can display images only at the _Top_, _Bottom_ or in the _Center_.

<Image alt={2378} border={true} src="https://files.readme.io/ae9c7d6-Lead_Gen_Template_Editor_Style.png" title="Lead Gen Template Editor Style.png" className="border" />  Style Elements for Lead Generation

# Custom HTML Editor

A Custom HTML Editor is used to create templates with custom HTML scripts. Users have a choice to customize their popup's appearance using the Box, Banner, and Interstitial templates. Insert the custom HTML scripts for the respective template layout in the HTML editor.

> 🚧 Manually Configured Click Tracking?
>
> If you are already raising the Notification Clicked event manually in your template, then ensure to disable the _Enable click tracking for Custom HTML_ checkbox to avoid overcounting.

To track the campaign stats, such as the number of total clicks and CTRs, marketers must select the _Enable click tracking for Custom HTML_ checkbox.

<Image alt={1510} border={true} src="https://files.readme.io/76d8b12-custom_html_click_tracking_web_popup.png" title="Disable if Clicks Recorded Manually " className="border" />  Track Campaign Stats

# Drag and Drop Editor

The Drag and Drop Editor helps create custom templates using different drag-and-drop elements, such as text, images, and buttons, to create a beautiful web popup message.

## Video Tutorial - Creating Custom Popups using Drag and Drop Template

<HTMLBlock>{`
<div
              style={{
                position: "relative",
                paddingBottom: "56.25%",
                height: "0",
                borderRadius: "0",
                boxShadow: "0 15px 40px rgba(63,58,79,.3)",
                overflow: "hidden",
                minWidth: "320px"
              }}>
  <iframe
              src="https://clevertap.portal.trainn.co/share/2ZZ17QPXh2UodpqZuPc2PA/embed?autoplay=false"
              frameBorder="0"
              webkitAllowFullScreen
              mozAllowFullScreen
              allowFullScreen
              allow="autoplay; fullscreen"
              style={{
                position: "absolute",
                top: "0",
                left: "0",
                width: "100%",
                height: "100%"
              }}></iframe>
</div>
`}</HTMLBlock>

Learn how to use a _Drag and Drop_ template. There are many edits you can make to this template. In this step, we will look at three of them: how to change an image, add a new element, and delete an element. To create a template:

1. From the _What_ section in the Web Pop-up editor, select _Drag & Drop Editor Templates_ .
2. Click **Blank Template** to create a new template or use a template saved earlier.

<Image alt="Select Drag and drop template" border={true} src="https://files.readme.io/f039372-blank_template.jpg" className="border" />  Create Template

The Drag and Drop editor displays.

<Image alt="Drag and Drop Editor" border={true} src="https://files.readme.io/ea030b3-Drag_and_drop_editor_empty.jpg" className="border" />  Drag and Drop Editor

Add elements from this editor to create a compelling message.

### Add an Image

You can either use an existing image or upload a new image in the [Content Manager](doc:clevertap-content-manager). To select an image:

1. Drag and drop the image element on the canvas.
2. Click **Browse** to select the image or drag and drop the image.

<Image align="center" alt="Drag and drop image" border={true} src="https://files.readme.io/8d87180-Image_drag_drop_template.jpg" className="border" />

### Add a New Text Element

You can add text boxes and format the text within this element.

1. Under the _Content_ tab, drag and drop the _Text_ element.

<Image alt={1324} border={true} src="https://files.readme.io/1206203-text_block.jpg" title="Add a Text Box to Email Content" className="border" />  Add a Text element

2. Drag the Text icon to the desired location.

Now, you have a new text element.

Similarly, you can also drag other elements, such as Images, Buttons, or Videos, into your template.

### Delete an Element

1. Click the box of the element you want to delete.

<Image alt="Delete an element" border={true} src="https://files.readme.io/5a6fc2b-row_delete.jpg" title="Delete a Saved Row" className="border" /> Delete an element

2. Click the trashcan <img src="https://files.readme.io/dd90a6a-delete_template_icon.jpg" height="30px" width="30px" /> icon.

The element you deleted will no longer appear.

## Rows

You can drag and drop, delete, rename, or re-organize your saved rows, right inside the editor.

1. Select the _Drag & Drop_ template.
2. Click the _ROWS_ tab.
3. Select the **Empty**, or **Saved Rows** from the list.
4. Drag and drop the row to the editor.

### Delete Rows

Delete saved rows from the editor.

1. You can delete saved rows from the editor.
2. Click the ROWS tab in the editor.
3. Select the saved row and click the delete icon.

<Image alt="Delete a row" border={true} src="https://files.readme.io/5d44ea3-row_delete.jpg" title="Delete a Saved Row" className="border" /> Delete a Saved Row

## Mobile View

You can switch between the mobile and desktop views of your message to view and edit content. You can check how the content will display on a mobile phone without going to Previews or sending a test message. Any changes made to the mobile view will be reflected on the desktop view as well. It is a What You See is What You Get (WYSIWYG) editor.

<Image alt="Desktop View and Mobile View" border={true} src="https://files.readme.io/46015a0-mobile_and_desktop_view.gif" title="View Email Content in Mobile" className="border" /> View Responsiveness on Desktop and Mobile

## Template Operations

### Advanced Customization

You can customize a template further to update the Web Pop-up display.

Click the **Advanced customization** button from the template editor to update the display. You can change the following settings:

<Image alt="Advanced customizationf or popups" border={true} width="50%" src="https://files.readme.io/726f50a-image.png" className="border" /> Advanced customization of web pop-up

* _Layout_:  Select the appropriate option to display the popup in the center of the page, bottom-right, top-left, and so on.
* _Popup Size_: A popup size must be relevant to the page. Select the appropriate width for your popup on mobile and desktop. The height is adjusted automatically.
* _Card Style_: Select if the popup should have rounded corners, borders, and also select the background color.
* _Close icon_: Select the icon's color to close the popup. For example, a black icon is distinctly visible on a white popup.
* _Overlay style_: An overlay keeps you focused on the popup content without distracting user from the rest of the website content. Generally, the overlay is used for centered or interstitial layouts by increasing the opacity of the background. A higher opacity will make the popup more visible, while a lower opacity can provide a subtle hint at the content without overpowering the user's attention. Opacity can vary depending on the design and purpose of the popup. It's essential to test different opacities to find the best balance for your design and audience. Select if you want to add an overlay and then its opacity.

### Save A Template

This step is optional. You can choose to save a template for future use. Click **Save template**.

<Image alt="Save a Template" border={true} src="https://files.readme.io/37acd05-save_template.jpg" title="Save a Template for Future Use" className="border" />  Save a Template

2. Name your template and click Save.

Your template is now saved under the **Saved Templates**  tab.

<br />

# On Click Actions

The _On Click Actions_ feature allows customers to trigger specific actions (such as opening a link, running a function, and so on) when a user clicks a web popup or the button within the popup. This functionality is essential for creating interactive and dynamic web experiences, giving customers greater control over how elements behave in response to user interactions.

<Image alt="On click Actions" border={true} src="https://files.readme.io/216a99152920048201bdc4be042a8fe76be5a02fb207d5306b6ff599a1d39b38-On_Click_Action.png" className="border" />  On click Actions

Available Actions:

* **Open Link**  
  _Description_: Opens a specified link in the new browser tab.  
  _Use Case_: Ideal for campaigns that use navigation buttons, external links, or any element that redirects users to a different webpage.
* **Open Link and Close Popup**  
  _Description_: Opens a specified link and closes any open popups.  
  _Use Case_: Ideal for campaigns that use buttons within popups that redirect users while also cleaning up the user interface by closing the popup.
* **Send Prompt to Allow Notifications**  
  _Description_: Sends a browser prompt requesting the user to allow notifications from the website.  
  _Use Case_: Ideal for web applications that rely on browser notifications for real-time updates, alerts, or promotional messages.
* **Close Notification**  
  _Description_: Closes the current notification popup.  
  _Use Case_: Ideal for campaigns allowing users to dismiss notifications or popups without taking any further action, ensuring a clean user interface.
* **Run a JavaScript Function**  
  _Description_: Executes a specified JavaScript function when the element is clicked.  
  _Use Case_: Ideal for campaigns that require running custom scripts for advanced actions, such as form validation, data submission, or trigger animations.
