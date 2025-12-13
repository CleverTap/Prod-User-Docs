---
title: Email Editor New
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

The Email Editor tool is a feature available when building an email campaign in CleverTap. It lets you add content to pre-built templates, or customize and build your own templates. After creating an email template, you can use it in the current campaign or save it for future campaigns.

<Image title="Email_Campaign_Templates.png" alt={1027} className="border" width="80%" border={true} src="https://files.readme.io/a301a97-Email_Campaign_Templates.png" />

From the *What* section in the Email builder, click **Go to Editor.**  

The Email Editor tool displays.

<Image title="Email_editor_main.png" alt={1121} className="border" border={true} src="https://files.readme.io/670c841-Email_editor_main.png" />

# Select a Template

Decide which template you want and click **Select**.

You can choose between pre-built templates or empty templates under *Basic Templates*. You can also save customized templates and view them under **Saved Templates**.

<Image title="Email_editor_main.png" alt={1121} className="border" border={true} src="https://files.readme.io/93bc164-Email_editor_main.png" />

Let's choose a pre-built template and explore a few ways to edit a template.

# Edit a Template

There are many edits you can make to a template. In this step, we will look at three of them: how to change an image, add a new block, and delete an element.

### Change an Image

1. Click inside the box of the image you want to change.

<Image title="Email_Campaign_Templates_select.png" alt={1053} className="border" border={true} src="https://files.readme.io/f0237ec-Email_Campaign_Templates_select.png" />

2. Click the image.

<Image title="Email_Campaign_Templates_change_image1.png" alt={1225} className="border" border={true} src="https://files.readme.io/44d57b7-Email_Campaign_Templates_change_image1.png" />

3. Click the **Change Image** button. The *File manager* displays.
4. Select an image from the gallery or upload a custom image. 

<Image title="Email_Campaign_Templates_change_image_select.png" alt={1225} className="border" border={true} src="https://files.readme.io/3cd76ca-Email_Campaign_Templates_change_image_select.png" />

4. Click Insert. Your new image will appear in the selected box.

<Image title="Email_Campaign_Templates_image_inserted.png" alt={1305} className="border" border={true} src="https://files.readme.io/e1e933f-Email_Campaign_Templates_image_inserted.png" />

### Add a New Text Block

1. Under the Content tab, find Text.

<Image title="Email_Campaign_add_new_text.gif" alt={1324} className="border" border={true} src="https://files.readme.io/ceae7fa-Email_Campaign_add_new_text.gif" />

2. Drag the Text icon to the desired location.

Now you have a new text block.

Similarly, you can also drag other elements such as Images, Buttons, or Videos in your template.

### Delete an Element

1. Click the box of the element you want to delete.

<Image title="Email_Editor_delete_element.gif" alt={1324} className="border" border={true} src="https://files.readme.io/7610436-Email_Editor_delete_element.gif" />

2. Click the trashcan icon.

3. Click **Delete**.

The element you deleted will no longer appear.

## Save A Template

1. Click **Save template**.

<Image title="Email_Editor_save_template.png" alt={1324} className="border" border={true} src="https://files.readme.io/38aef42-Email_Editor_save_template.png" />

2. Name your template.

3. Click Save.

Your template will now be saved in My Gallery.

## Create an Email Template with HTML

1. Click **Email with custom HTML**.

<Image title="Email_Campaign_select_templates.png" alt={1140} className="border" border={true} src="https://files.readme.io/9eb5ed9-Email_Campaign_select_templates.png" />

2. Add your HTML into the box.

<Image title="Email_Campaign_template_custom_html.png" alt={1140} className="border" border={true} src="https://files.readme.io/d38dd3b-Email_Campaign_template_custom_html.png" />

3. Name your template.

<Image title="Email_Campaign_template_custom_html_Name.png" alt={1140} className="border" border={true} src="https://files.readme.io/6890680-Email_Campaign_template_custom_html_Name.png" />

4. Click Save.

Your customized template will now be saved to *Saved Templates*.

### **Inbox Previews with Code Analysis**

Inbox Previews with Code Analysis offers you an analysis of your HTML code. It also offers you previews across devices and inboxes before you send out a campaign. 

Before we begin, check that you have enabled Inbox Previews. For enabling the Inbox Previews, see [Enable Email Previews](doc:enabling-previews). Follow the steps to create an email campaign.

1. Select the template. 
2. If you are using custom HTML, then enter or paste the HTML in the email editor.
3. Click **Preview and Test**button.  The *Previews and test* window displays.
4. Click the **Spam Report** tab.
5. Click **Generate Report**. The display may take some time if you have selected multiple inboxes. We will render the results and send you a notification email so that you know when the preview is loaded. 

<Image title="Screenshot 2021-07-12 at 7.07.10 PM.png" alt={1648} className="border" border={true} src="https://files.readme.io/9091e36-Screenshot_2021-07-12_at_7.07.10_PM.png" />

6. Click **Inbox Previews** to view the preview report. The tests will display email previews across all the selected inboxes. It displays the errors, if any, for each inbox. For selecting inboxes, see [Enabling Previews](doc:enabling-previews). \<\<@vishal, dk, the spam reports and inbox reviews do not render>>

<Image title="Screenshot 2021-07-12 at 7.08.00 PM.png" alt={1646} className="border" border={true} src="https://files.readme.io/439b55a-Screenshot_2021-07-12_at_7.08.00_PM.png" />

7. Select any of the previews to fix the errors. The code analysis displays the error type and details. You can sort these errors by severity or property. 

<Image title="Screenshot 2021-07-12 at 7.08.29 PM.png" alt={1644} className="border" border={true} src="https://files.readme.io/d94922b-Screenshot_2021-07-12_at_7.08.29_PM.png" />

8. Click the Fix issues in the editor link to fix the issues. You are redirected to the email editor. 
9. Click the Source button to view your HTML and fix the issues.\
   Run the preview tests again to check that the previews are in order. 

# FAQ

## Q. How do I delete a saved template?

Currently, it is not possible to delete a saved template.

## Q. What if I want to choose a different template?

Click **Change template** at the top left in the email editor.

## Q. I received the error message: "Please set the email credentials". How do I fix it?

<Image title="Screen Shot 2018-07-15 at 8.40.27 PM.png" alt={519} className="border" border={true} src="https://files.readme.io/e527565-Screen_Shot_2018-07-15_at_8.40.27_PM.png" />

This error message means you have not integrated your email provider with CleverTap. You can do this by following [this guide](doc:email-partners).
