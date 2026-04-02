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

<br />

<Image align="center" alt="Select Web Pop-up Editor Type" border={true} caption="Select Web Pop-up Editor Type" title="Email Editor Templates" src="https://files.readme.io/2199a47-Web_popup_Editors.jpg" />

# Editors and Templates

There are three types of editors available:

* Basic Editor
* Custom HTML Editor
* [Advanced Web Popup Builder ](https://docs.clevertap.com/docs/advanced-web-pop-up-builder)

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

<br />

<Image align="center" alt="User Star Rating Popup" border={true} caption="User Ratings Popup" src="https://files.readme.io/4062d44-Web_Popup_NPS_rating_Star.jpg" width="50% " />

<br />

<Image align="center" alt="NPS Popup" border={true} caption="NPS Ratings Popup" src="https://files.readme.io/ce8fb86-Web_Popup_NPS_rating_Numbered.jpg" width="50% " />

<br />

Marketers get the complete flexibility to explicitly define the rating scale, style,  its shape (Star, Heart, Emojis), labels, and the overall content of the popup. One can also add a comment box to get accurate user feedback/comments.

<br />

<Image align="center" alt="Define Element Style" border={true} caption="Define Element Style" title="Edit Style" src="https://files.readme.io/7bbc6cc-styling.png" width="70% " />

<br />

Besides, additional styling, such as the background color of the notification, text color, button color, and the color of the rating scale, is also possible from the editor, as shown in the image above. To learn more about tracking and monitoring user rating data, refer to the [Analyzing User Rating](https://docs.clevertap.com/docs/user-ratings).

The web popup notification text fields in the following image can be personalized for every user based on specific user property or event property values. For more information, refer to [User Profiles](https://docs.clevertap.com/docs/user-profiles) and [Events](https://docs.clevertap.com/docs/events).

Add all the required information. You can also flip the scale for languages that read from left to right. For example, Hebrew, Arabic, and so on.

<br />

<Image align="center" alt="Personalize Web Popup" border={true} caption="Personalize Web Popup" src="https://files.readme.io/5241786-web_inbox_NPS_Template.png" width="70% " />

<br />

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

<br />

<Image align="center" alt="Short Keyword Choices" border={true} caption="Short Keyword-Based Choices" src="https://files.readme.io/71b74e6-web_popup_Secondary_Tiles.jpg" width="50%" />

You can also list descriptive choices such as, _I like the available options and variety_, _I like the quality and durability of the products_, and so on.

<br />

<Image align="center" alt="Long Sentence Choices" border={true} caption="Descriptive Choices" src="https://files.readme.io/a95c15a-web_popup_Secondary_List.jpg" width="50%" />

You can configure the follow-up question from the Web Popup editor with a short keyword-based grid (up to six choices) or a longer sentence-based list (up to four choices).

The label will be the text you want to display to your users. If you want to allow the user to select multiple choices, select _Allow multiple selections_.

<br />

<Image align="center" alt="Configure Follow-up Popup" border={true} caption="Configure Follow-up Popup" src="https://files.readme.io/fd33f9a-image_18.png" width="80%" />

> 📘 Note
>
> In the case of the User Ratings template, the _Notification Clicked_ event is raised that records the user's clicks on the CTA buttons and the Close button.

## Lead Generation Templates

We know that a significant number of website visitors remain anonymous. This poses a challenge to continue engaging with potential customers after they leave a website. A lead generation template can solve this issue.
By integrating a lead generation form on your website, you can get important customer details such as name, email address, phone number, and so on. This information is helpful for further communication through channels such as SMS, Email, WhatsApp, and others. This post-visit communication not only helps to stay connected with your audience but also opens doors for future business opportunities. You can turn anonymous visitors into loyal customers with the CleverTap Lead Generation template.

<br />

<Image align="center" alt="Sample Lead Generation Template" border={true} caption="Sample Lead Generation Template" title="Lead Gen Template Sample.png" src="https://files.readme.io/888a43a-Lead_Gen_Template_Sample.png" />

<br />

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

<br />

<Image align="center" alt="Form Submit Actions" border={true} caption="Form Submit Actions" src="https://files.readme.io/0cae15f-Lead_Gen_Template_preview_with_fields.png" width="50% " />

<br />

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

<Image align="center" alt="Lead Generation Template Types" border={true} caption="Lead Generation Template Types" src="https://files.readme.io/dd75b54-Lead_Gen_Template_Tab.png" />

 

Select any of the variants to create your Lead Generation template.

### Lead Generation Content

Create the content to record information from your users. The following image displays a preview of the form:

<br />

<Image align="center" alt="Create Lead Generation Template in Editor" border={true} caption="Create Lead Generation Template in Editor" title="Lead Gen Template Editor Content.png" src="https://files.readme.io/2daa708-Lead_Gen_Template_Editor_Content.png" />

  

Enter all the required information.

* _Text_: Personalize the Title and Description.
* _Media_: Add the image URL or upload an image.
* _Input Fields_: You can add up to four input fields. Select input fields such as Name, Phone Number, Birthday, or Email Address for the template.

<Image align="center" alt="Upto Four Input Fields" border={true} caption="Upto Four Input Fields" title="Lead Gen Template Input Fields.png" src="https://files.readme.io/6a87857-Lead_Gen_Template_Input_Fields.png" width="60% " />

 

* _Buttons_: The _Close_ button is selected by default. Add a button name such as _Submit_ or _Upload_.
* _Subtext_: Add subtext such as _privacy policy_ to your lead generation template.

<br />

<Image align="center" alt="Add Subtext" border={true} caption="Add Subtext" title="Lead Gen Template SubText preview.png" src="https://files.readme.io/bb6e1f2-Lead_Gen_Template_SubText_preview.png" width="55%" />

<br />

The hyperlinked part must be closed between two asterisks. Add the URL in the following URL box. This is the URL where the user will be directed. You can also add a checkbox for your subtext.

<br />

<Image align="center" alt="Subtext and redirect URL" border={true} caption="Subtext and redirect URL" title="Lead Gen Template SubText.png" src="https://files.readme.io/d740b86-Lead_Gen_Template_SubText.png" width="55%" />

<br />

* _Acknowledgement_: You can show appreciation to your user by adding an Acknowledgement popup. Select the auto-close timer for the popup.

### Lead Generation Template Style

You can select the layout and card position from this screen. You can also select the color of the text, input fields, and buttons.

> 📘 Mobile View
>
> The Mobile view can display images only at the _Top_, _Bottom_ or in the _Center_.

<br />

<Image align="center" alt="Style Elements for Lead Generation" border={true} caption="Style Elements for Lead Generation" title="Lead Gen Template Editor Style.png" src="https://files.readme.io/ae9c7d6-Lead_Gen_Template_Editor_Style.png" />

<br />

# Custom HTML Editor

A Custom HTML Editor is used to create templates with custom HTML scripts. Users have a choice to customize their popup's appearance using the Box, Banner, and Interstitial templates. Insert the custom HTML scripts for the respective template layout in the HTML editor.

> 🚧 Manually Configured Click Tracking?
>
> If you are already raising the Notification Clicked event manually in your template, then ensure to disable the _Enable click tracking for Custom HTML_ checkbox to avoid overcounting.

To track the campaign stats, such as the number of total clicks and CTRs, marketers must select the _Enable click tracking for Custom HTML_ checkbox.

<Image align="center" alt="Track Campaign Stats" border={true} caption="Track Campaign Stats" title="Disable if Clicks Recorded Manually " src="https://files.readme.io/76d8b12-custom_html_click_tracking_web_popup.png" />

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
