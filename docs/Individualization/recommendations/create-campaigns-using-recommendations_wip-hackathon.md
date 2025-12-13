---
title: Create Campaigns using Recommendations_WIP hackathon
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
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

Using Recommendations in Campaigns/Journeys

Once the recommendations have been published, you can use them in your engagement workflow by creating personalized and contextual recommendations for your user base. Recommendations can be accessed by using “@” in any input field which has personalisation available.

The creation of recommendation content in Campaigns/Journeys has 3 steps:\
Select the Recommendation - Select the recommendation that will be used to create the content, you can select 1 out of the 5 recommendations set.\
Select the last action of the User - In this step you will need to also select the Event mapped to the recommendation and catalog pair. The Item of the last occurrence of this Event will be used for creating the content. Example - Product Viewed, if the Divyekant has last seen an IPhone 12, associations for that product will be used to create the content.\
Filter Recommended items - This step is to filter out any recommended items associated with the last action of the User.\
Filter by Event - This filter is used to include/exclude items filtered by properties of last action which match column values of the associated items. Example: exclude items which are from the same restaurant the User has last purchased from, include items which are of the same cuisine the User has last purchased from.\
Filter by Location - This filter is used to include/exclude recommended items which are within a defined distance of the users last known location. Example: Include items which are within 10KM of the Users last location\
Select Rank of the recommended items - This step is to select the ranked item for personalisation, example the 1st item or 2nd and so on. This allows multiple content creation in the same engagement.

Once the content creation is done, they will appear in the “@” drop down box with a list of all columns available within the recommendation-catalog pair selection.

Selecting the fields for personalization:

Using within HTML Email Editor:

Step 1:\
Add HTML content to the HTML editor by selecting the Source mode

Step 2:\
Switch back to editor mode from source to add the liquid tags, wherever required

Examples: 

1. Text personalisation:

2) URL Personalisation:\
   In this case click the Hyperlink button on the menu as shown below, the opened popup allows you to personalise the content and the link redirection

3. Personalise image via Liquid tags:\
   This can be achieved by using the Image adder option on the toolbar as shown below - 

Using within Drag and Drop Email Editor:

Step 1:\
Select the template that needs to use personalisation

Step 2:\
Add Liquid Tags in the body itself for any text personalisation or use Dynamic Content Block for URL, Email & HTML personalisation\
Text Personalisation:\
Usage of “@” symbol will directly invoke the personalisation drop down with recommendations in the options.

Dynamic Content Block:

1. Drag and drop the *Dynamic Content* block into the content box in the center of the email body.
2. Click on the new content box to display the menu on the right.
3. Click on the Add options button to access the dynamic content options.
4. When the window pop-up displays, select one of the following options:

* Image
* Deeplink
* Text
* Custom HTML

Note: Option Name is required field - When you create a dynamic block, the option name is mandatory. Also, these dynamic blocks can be re-used if required.

1. Image Personalisation - Type the @ symbol to personalize the image content using recommendations in the URL, alternative text, and target URL fields.

2) Deeplink Personalisaiton - Type the @ symbol to personalize the deeplink content using recommendations in the display text and URL fields.

3. Text Personalisaiton - Type the @ symbol to personalize the text content using recommendations in the text field.

4) Custom HTML Personalization - Type the @ symbol to personalize the custom HTML content using recommendations in the custom HTML code box.

Using within any other Editor\
The personalisation can directly be used in all available input fields wherever the “@” symbol is mentioned. This doesn’t require any special method for invocation, a simple @ can invoke the right fields for personalisation.
