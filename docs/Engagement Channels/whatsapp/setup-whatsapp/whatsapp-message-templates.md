---
title: WhatsApp Message Templates
excerpt: Learn more about setting up and creating WhatsApp Message Templates
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
As businesses increasingly leverage WhatsApp as a powerful communication channel, creating well-crafted templates becomes paramount. Creating templates ensures compliance with WhatsApp guidelines and provides a structured framework for delivering messages that resonate with your audience. This documentation aims to provide you with the following information:

* **Best Practices**: Understand the fundamental principles that govern successful WhatsApp template creation, including clarity, relevance, and compliance.
* **Template Categories**: Explore different template categories, such as Marketing, Limited-Utility, and Authentication, each tailored to meet specific communication needs.
* **Template Types**: Explore different template types, such as Basic, Limited Time Offers (LTOs), and Carousel, each tailored to meet specific communication needs.
* **Creation Steps**: Step-by-step instructions for crafting templates in CleverTap, ensuring you can seamlessly implement your messaging strategy.
* **Template Approval Process**: Steps to follow for Meta's approval on your configured message templates.
* **Template Operations**: Steps to Import, Edit or Delete templates.
* **Testing the Message Templates**: Steps to test your configured message template
* **FAQs**: Find answers to common queries that WhatsApp customers often encounter while using WhatsApp for marketing.

# Best Practices for WhatsApp Template

Creating effective WhatsApp templates requires adherence to certain guidelines. To increase the likelihood of approval and ensure impactful communication, follow these best practices

* **Keep it Concise:** Keep your template text brief and focused for clear and effective communication.
* **Eliminate Errors:** Avoid grammatical and spelling mistakes to prevent rejection and maintain professionalism.
* **Avoid Mix of Languages:** Stick to a single language within a template for consistency and clarity.
* **Choose Appropriate Message Category:** Align the template's goal with the selected message category for better categorization and understanding.
* **Use Placeholders for Template Personalization:** Contextualize template content with placeholders for relevance. For example: "Hey \{\{1}}, You've been pre-approved for our credit card! Enjoy an introductory offer of \{\{2}} via your personalized link: \{\{3}}."
* **Easy Opt-out Steps:** Clearly state how end-users can opt out of WhatsApp notifications, ensuring a smooth and respectful opt-out process.
* **Avoid Promoting Forbidden Business Verticals:** Steer clear of promoting forbidden business verticals to prevent template rejection and potential account bans.
* **Formatting Rules:** Adhere to guidelines on naming, size, and text formatting for template compliance and approval.

# WhatsApp Template Categories

> 📘 Template Category Selection
>
> CleverTap BSP (Whatsapp Direct) users can select categories during template creation for Meta review, ensuring content alignment. This feature is specific to CleverTap BSP.  
> However, for external providers, template creation occurs in their WhatsApp provider's dashboards. Hence, template category selection is not available during template configuration in the CleverTap dashboard for external providers.

WhatsApp templates are divided into various categories, each serving specific communication needs. Understanding these categories and their ideal use cases is crucial for effective messaging.

## Marketing Categories

WhatsApp provides the most flexible marketing templates. These templates enable businesses to achieve various goals, from generating awareness to driving sales.

* **Awareness:** Introduce new products or services.
* **Sales:**Promote general offers, coupons, or sales events.
* **Retargeting:** Re-engage customers who visit your website or app.

## Utility Categories

Utility templates are triggered by a user action or request. They must include details about the active or ongoing transaction, account, subscription, or interaction to which they relate. For example, an order confirmation must contain an order number.

* **Opt-In Management on WhatsApp:** Confirm opt-in or opt-out preferences.
* **Order Management:** Confirm, update, or cancel orders with specific details.
* **Account Alerts or Updates:** Send important account updates and alerts.
* **Feedback Surveys :**Collect feedback on orders or interactions.

## Template Library

For WhatsApp Direct, Template Library provides out-of-the-box WhatsApp template structures that are predefined for common messaging use cases. These templates help you quickly create WhatsApp messages without starting from scratch.

The templates include predefined components such as structure, placeholders, and formatting. You can customize the content and configure supported fields as required before saving the template. For more information on WhatsApp message templates and their structure, refer to <Anchor label="Meta’s documentation" target="_blank" href="https://developers.facebook.com/documentation/business-messaging/whatsapp/templates/template-library">Meta’s documentation</Anchor>.

<Image align="center" border={true} caption="Template Library" src="https://files.readme.io/c404fffa2a64aed639553bdd7275d6ab5becd10cd4282d26d4a6ce7dc6603095-Template_Library.png" />

### Create a Template Using Template Library

To create a template using the Template Library, follow these steps:

1. From the dashboard, navigate to _Account_ > _Settings_ > _Engage_ > _Channels_ > _WhatsApp_.
2. Select the Provider Type as **WhatsApp Direct**.
3. Select the required _WABA account_.

   <Image align="center" border={true} caption="Template Library for WhatsApp Direct" src="https://files.readme.io/91937bfeeb0acabce941f938bfcd1ce1a37fb6aab529899177d1d23819ed9cd4-template_library_1.png" />
4. Navigate to the Templates tab and click **+ Template**.

   <Image align="center" border={true} caption="Add Template" src="https://files.readme.io/312b97383f56970489d51c0f1805d081feac7f6875fb3ab6983572dc0d01b44c-template_library_3.png" />
5. In Select Template Type, click **Template Library**.

After you select a template, CleverTap opens the template editor with the predefined content populated.

* The template structure, category, and components are populated based on the selected template.
* All available language variants are displayed for selection.
* Placeholders and formatting are populated by default.
* You can update sample values and the Template Name in CleverTap.

Proceed using the same editor flow described in Create WhatsApp Template.

## Support for Authentication Templates

Currently, CleverTap does not support WhatsApp Authentication Templates. For assistance or information on other template categories compatible with CleverTap, refer to our documentation or contact our support team.

# WhatsApp Template Types

CleverTap streamlines WhatsApp template creation by categorizing them into three distinct types, simplifying the template creation process for CleverTap users. The following are the types of WhatsApp templates, along with their features and use cases:

## Basic Templates

Basic Templates are designed for simplicity and quick setup. Use them when sending a single media item, a text body & footer, or a few buttons. These templates are perfect for straightforward messages without complex formatting. They include the following:

* **Header**: Optional with support for text, image, video, document, and locations.
* **Body**: Mandatory with support for up to 1024 characters in text format.
* **Footer**: Optional with support for up to 60 characters.
* **Buttons**: Optional with support for up to 10 buttons, including copy code, visit website CTA, call phone CTA, and quick reply buttons.

### Use Cases

The following are some of the use cases that can be addressed with basic templates:

* **Order Confirmation:**  
  Example Template: "Dear \{\{1}}, your order \{\{2}} has been confirmed. Track your package via \{\{3}}."
* **Service Updates**:  
  Example Template: "Hello \{\{1}}, we've made improvements to our service. Stay tuned for enhanced experiences."
* **General Announcements:**  
  Example: Template: "Exciting news, \{\{1}}! Explore our latest offerings and promotions. Don't miss out!."

Learn how to [create Basic Templates](doc:whatsapp-message-templates#basic-templates-1) on the CleverTap dashboard.

## Limited-Time Offer Templates

Limited-time Offer templates are designed for time-sensitive promotions to create a sense of urgency. These templates are ideal for flash sales, special discounts, or any offers that require immediate attention and action from your customers.

> 📘 Availability
>
> These Templates are only available with Marketing Category Templates.

<Image align="center" alt="Limited Time Offer Message Components" border={true} caption="Limited-Time Offer Message Components" src="https://files.readme.io/cd2ade8-LTO_sample.png" width="50% " />

LTO templates include the following components:

* **Header**: Optional with support only for text, image, video, document, and location.
* **Limited-Time Offer**: Optional with sub-components:
  * Offer Title: Offer detailed text with a character limit of 16 characters.
  * Offer Expiration Timer: Optional field displaying offer expiration details.
* **Body**: Mandatory with support for up to 600 characters in text format.
* **Buttons**: These are optional and can support up to 10 characters. Button types include Copy code, Visit Website CTA, Call phone CTA, and Quick reply.
* **Limited-Time Offer Templates:** Limited-Time Offer Templates are designed for time-sensitive promotions. They include headers, limited-time offer components, body, and buttons.

> 🚧 Support for Limited-Time Offer (LTO) Templates in Utility Category
>
> Limited-Time Offer (LTO) Templates are not supported in the _Utility_ category by WhatsApp. Be aware of this restriction when planning your campaigns. You can explore other categories for optimal template utilization.

### Use Cases

The following are some of the use cases that can be addressed with Limited Time Offer templates:

* **Flash Sales or Exclusive Discounts**

<Image align="center" alt="Flash Sale" border={true} caption="Flash Sale" src="https://files.readme.io/5932e3b-B1g1.png" width="45% " />

Learn how to [create Limited Time Offer Templates](doc:whatsapp-message-templates#limited-time-offer-templates-1) on the CleverTap dashboard.

## Carousel Template

Carousel templates enable businesses to craft a single text message that features up to 10 dynamic carousel cards. This enables the recipients to scroll horizontally through a series of engaging content.

<Image align="center" alt="Carousel Template" border={true} caption="Carousel Template" src="https://files.readme.io/f710556-WhatsApp_carousel_graphic_2x.png" width="78% " />

The Carousel template comprises the following components:

* **Message bubble**: The message bubble provides detailed context and information about products or services, with a character limit of 1024. This allows for comprehensive communication to enhance user understanding and drive conversions.
* **Carousel Cards**: Brands can include up to 10 carousel cards within a template, each comprising the following components:
  * **Card Header**: Features images or videos. All cards must use the same media type. Card headers serve as engaging visual elements to promote products or services effectively.
  * **Card Body**: It can contain up to 160 text characters and complements the card header by concisely conveying the key information.
  * **Card Buttons**: Up to two buttons are allowed per card. Button types must be consistent across all cards. These buttons prompt user actions such as making a purchase, visiting a website, or accessing additional content.

### Use Cases

The following are some of the use cases that can be addressed using the Carousel templates:

* **E-commerce**
  * **Product Showcase**: Display a carousel of product images to highlight new arrivals, best sellers, or seasonal collections. Each card features a different product with details on features and pricing, providing users with a visually engaging shopping experience.
  * **Flash Sales Event**: Promote a limited-time flash sale with a carousel of select discounted products. Each card highlights a different deal, enticing users to explore offers and make quick purchasing decisions.
* **Fintech**
  * **Investment Portfolio Showcase**: Display a carousel featuring various investment options or portfolio recommendations. Each card highlights different investment products or strategies, providing users with insights for portfolio diversification.
  * **Financial Education Series**: Offer a carousel of educational content on personal finance or investing topics. Each card covers a different financial concept or tip, empowering users to make informed financial decisions.
* **Food Delivery Services**
  * **Menu Highlights**: Showcase popular dishes, meal combos, or new menu additions in a carousel format. Each card features appealing images, descriptions, and prices, enticing users to explore and order.
  * **Specialty Cuisine Showcase**: Present a carousel featuring various cuisine types or specialty dishes. Each card highlights a unique culinary experience with images, ingredients, and chef recommendations, inspiring users to try something new.  
    Learn how to  [create Carousel Templates](whatsapp-message-templates#carousel-templates) on the CleverTap dashboard.

# Create WhatsApp Template

Creating WhatsApp templates is simple with CleverTap. The steps vary depending on the type of template you choose.

> 🚧 Template Approval Process For Customers.
>
> * Customers using external providers (**WhatsApp Connect**) must create and submit their templates for approval in their vendor’s dashboard. Once approved, these templates should be replicated in the appropriate provider settings.
> * Customers using **CleverTap BSP (WhatsApp Direct)** can directly create and submit their template in CleverTap dashboard. New Templates will be automatically submitted to Meta and status will also be updated automatically.

> 📘 Template Categorization in CleverTap
>
> CleverTap organizes templates into **Basic**, **Limited-Time Offer (LTO**), and **Carousel** for easier use. Your vendor's dashboard might categorize them differently, but you can still use them effectively by following CleverTap's guidelines.

## Basic Templates

To create a Basic template in CleverTap, follow these steps:

1. From the dashboard, navigate to _Account > Settings > Engage > Channels > WhatsApp_.
2. Select the _Provider Type_ as  **WhatsApp Direct** for CleverTap BSP or **WhatsApp Connect** for external BSPs.

   <Image align="center" alt="Select WhatsApp Provider" border={true} caption="Select WhatsApp Provider" src="https://files.readme.io/f2f65ee-image.png" />
3. Select the appropriate WABA account or provider to add templates.

<Image align="center" alt={1894} border={true} caption="Select the WABA account" title="image.png" src="https://files.readme.io/c423fd6-image.png" />

4. Navigate to the _Templates_ tab and click **+ Template**.

<Image align="center" alt="Create a Template" border={true} caption="Create a Template" src="https://files.readme.io/c7bb73b-image.png" />

5. Select the appropriate category & _Basic_ Template

<Image align="center" alt="Basic Template" border={true} caption="Basic Template" src="https://files.readme.io/a897039c1b36cb5710105a4148261f7a612b87ba21c161f9991fafbc93b2348c-Basic_template_-_whatsapp.png" />

6. Once you select the Template type and Category, you will land on the Template editor.
7. Enter the _Template Name_, and configure headers and body as follows:

* For header: Select text, image, video, document, or location.
* For body text formatting: Select ![](https://files.readme.io/0e722c2b9160829fc9724e9497c493c9b3792fa7036998afc43dd3be1c26356b-EMOJI_icon.png) to insert emojis and select **B** for bold, _I_ for italics, and **S** for strikethrough.
* (Optional) Add footer text.
* Add the buttons and enter the required information:
  * **Copy Code buttons**: You can include only 1 copy code button. When tapped, the code is copied to the customer's clipboard.
  * **Visit Website CTA buttons**:  You can add up to 2 buttons, giving customers three choices:
    * **Static CTA buttons**: Use static URLs for redirection.
    * **Dynamic CTA Buttons**: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. For example: [https://www.clevertap.com/\{\{1}}](https://www.clevertap.com/\{\{1}}).
    * **CleverTap Click tracking CTA buttons**: Brands can leverage CleverTap click tracking functionality to monitor user details who clicked on the URL. They can personalize the URL for each user during campaign creation.
* **Quick Reply buttons**: You can add up to five quick reply buttons. Brands commonly use these buttons to enable users to swiftly respond to WhatsApp messages without typing.
* **Marketing Opt-out button** : You can add 1 marketing opt-out button. This button sends an unsubscription keyword in quick reply format, making it easy for end-users to opt-out. Brands need to handle these unsubscription flows properly to ensure end-users opt out when they tap this button.

8. Click **Save Template** to save the message template.

## Limited-Time Offer Templates

To create a Limited-Time Offer template in CleverTap, follow these steps:

1. From the dashboard, navigate to _Account > Settings > Engage > Channels > WhatsApp_.

2. Choose the _Provider Type_  as **WhatsApp Direct** for CleverTap BSP or **WhatsApp Connect** for external BSPs.

   <Image align="center" alt="Select WhatsApp Provider" border={true} caption="Select WhatsApp Provider" src="https://files.readme.io/ebaed56-image.png" />

3. Select the WABA account or provider to add templates.

   <Image align="center" alt={1894} border={true} caption="Select WABA account" title="image.png" src="https://files.readme.io/c423fd6-image.png" />

4. Select the _Templates_ tab and click **+Template**.

   <Image align="center" border={true} caption="Create a Template" src="https://files.readme.io/33da56f8406f438fe9fe23392a86eb8e900bd46c4fbfebb8544b86130a678d1a-create_template.png" />

5. Select the _Limited Time Offer_ template. **_Limited Time Offer_ templates are only available with Marketing category.**

<Image align="center" alt="Limited Time Offer Template" border={true} caption="Limited Time Offer Template" src="https://files.readme.io/7ae3368f72f02188974a65293630b8f06670cd2dbb292bc4e3f38a3010cbbf9f-Basic_template_-_whatsapp.png" />

6. Enter the _Template Name_ and configure headers and body as follows:

* For header: Select image or video.
* For body text formatting: Select ![](https://files.readme.io/0e722c2b9160829fc9724e9497c493c9b3792fa7036998afc43dd3be1c26356b-EMOJI_icon.png) to insert emojis and select **B** for bold, _I_ for italics, and **S** for strikethrough.
* If required, add the buttons and fill in the required information.
  * **Copy Code buttons:** You can include only 1 copy code button. When tapped, the code is copied to the customer's clipboard.
  * **Visit Website CTA buttons:**  You can add up to 2 buttons, giving customers three choices:
    * **Static CTA buttons:** Use static URLs for redirection.
    * **Dynamic CTA Buttons:** Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. For example: [https://www.clevertap.com/\{\{1}}](https://www.clevertap.com/\{\{1}}).
    * **CleverTap Click tracking CTA buttons:** Brands can leverage CleverTap click tracking functionality to monitor details of the user who clicked the URL. The entire URL can be personalized for each user during campaign creation.
* **Quick Reply buttons:** Add up to 5 quick reply buttons. Brands commonly use these buttons to enable users to swiftly respond to WhatsApp messages without typing.
* **Marketing Opt-out button:** You can add 1 marketing opt-out button. This button sends an unsubscription keyword in quick reply format, making it easy for end-users to opt out. Brands need to handle these unsubscription flows properly to ensure end-users get opted out when they tap on this button

7. Configure the Limited-Time Offer (LTO) component according to your specific requirements. The LTO component includes two essential components:

* **Offer Title:** Utilize this section to create a captivating heading for your promotional offer.
* **Offer Expiry Timer:** This field is optional. If selected, the template will display the time remaining for the offer's expiration, dynamically updating to reflect the time left for the offer to conclude.

<Image align="center" alt="Select Offer Expiration Timer" border={true} caption="Select Offer Expiration Timer" src="https://files.readme.io/f3c7941-image.png" />

8. Click **Save Template** to save the message template.

## Carousel Templates

To create a carousel template, follow these steps:

1. From the dashboard, navigate to _Account > Settings > Engage > Channels > WhatsApp_.

2. Choose the _Provider Type_  as **WhatsApp Direct** for CleverTap BSP or **WhatsApp Connect** for external BSPs.

   <Image align="center" alt="Select WhatsApp Provider" border={true} caption="Select WhatsApp Provider" src="https://files.readme.io/ebaed56-image.png" />

3. Select the WABA account or provider to add templates.

   <Image align="center" alt={1894} border={true} caption="Select WABA account" title="image.png" src="https://files.readme.io/c423fd6-image.png" />

4. Select the _Templates_ tab and click **+Template**.

<Image align="center" alt="Create a Template" border={true} caption="Create a Template" src="https://files.readme.io/ed0154b94d2af90d160785c8e12848eeca78f6a50930a08a9982bfa4f6e77c0b-create_template.png" />

5. Select the _Carousel Template_.

<Image align="center" alt="Carousel Template" border={true} caption="Carousel Template" src="https://files.readme.io/484ec0953f1b5124e82b0bc555974d13a22eca2f09f592c9a30e66dab1b097b7-Basic_template_-_whatsapp.png" />

6. Enter the _Template Name_ and configure the overall body as follows:
   1. For the Message bubble, enter the context of your campaign (maximum 1024 characters)
   2. For the Header, select the media type either **Image** or **Video**.
   3. Under the **Button** field, add the button (maximum of 2) per your use case and select the on-click operation (such as Visit Website, Call Phone Number, or Quick reply) for the buttons.
   4. You can add up to 10 cards as per your use case.
   5. For the Card body:
      1. Upload the media file (image/video) based on your selected media type.
      2. Enter the body text under the _Body_ field (maximum 160 characters).
      3. Enter the button text for the buttons based on the on-click actions you define. For example, if you add a button with the click action of Visit Website, you can add a button text - **Shop Now**.
      4. Click **Submit**.

# Template Approval Process

Once you have created your template, you can submit it for approval. It can take up to 24 hours to approve the template. After META approves your template, a notification appears in your WhatsApp Manager, and we email your Business Manager admins. In addition, we change the status of your template on the CleverTap dashboard.

After the status is updated to approved, you can send messages to your users. Click the refresh button to view the latest status of your template.

# Template Operations

You can edit a template and add or remove a language or other information. However, note that:

* Templates can be edited only once every 24 hours.
* You cannot edit a template that is being reviewed.
* If you edit a template, then all the campaigns and journeys using this template will be stopped.

If you delete a template, all the campaigns and journeys using this template will be stopped.

### Edit, Delete or Refresh WhatsApp Message Templates

To edit or delete an existing template:

1. Navigate to _Settings > Channels > WhatsApp Direct > Templates_.
2. Select any template and click the ellipsis icon adjacent to it.
3. Click **Overview** and then perform the desired operation.

<Image align="center" alt="Template Overview" border={true} caption="Template Overview" src="https://files.readme.io/d3d9f9e48704a227e442a9bcc267240dcedda8944873e6776f0d1cb842e53206-overview.png" width="45% " />

4. Similarly, select **Refresh Status** from the ellipsis menu to refresh the approval status of an existing template.

### Clone WhatsApp Message Templates

Template cloning allows you to reuse an existing WhatsApp template without recreating it from scratch. You can clone a template to the same WhatsApp Business Account (WABA) or to a different WABA, as long as it is configured with _WhatsApp Direct_.  The cloned template is created as a new template under the selected WABA and follows the standard template approval process described in the [Template Approval Process](doc:whatsapp-message-templates#template-approval-process) section.

To clone an existing template:

1. Navigate to _Settings > Channels > WhatsApp_. Ensure the _Provider Type_ is set to _WhatsApp Direct_ and select the WABA account that contains the template you want to clone.
2. Go to the **Templates** tab.
3. From the list of templates, select the template you want to reuse and click the ![](https://files.readme.io/01a229fb7482b62579be2f4fe48a5b7ca09a75f00687b65530ce4b00eb7623c2-ellipsis.png) icon adjacent to it.
4. Click **Clone**. The _Clone Template_ editor opens with the original template details pre-populated.
5. In the _Clone Template_ editor:
   * Enter a new **Template Name**. The name must be unique within the target WABA.
   * Under **Select WABA**, choose the WABA that will hold the cloned template. You can select the same WABA or a different WABA configured under WhatsApp Direct.
   * Review and, if required, edit the template content:
     * Update the _Header_, _Body_, _Footer_, _Buttons_, _language_, and _Sample content_ as needed.
     * The _Template type_ (for example, Basic, Limited-Time Offer, or Carousel) cannot be changed for the cloned template. To use a different template type, create a new template instead of cloning.
6. When you have finished reviewing and updating the cloned template, click **Done** to submit it.

### Import Templates

> 🚧 Template Import Limitations for External Providers
>
> Importing templates is supported only for CleverTap BSP. For all other providers, you must recreate templates separately within their interfaces.

CleverTap allows you to easily import templates from your WhatsApp Business Manager Account to streamline managing your WhatsApp templates. Follow the steps below to import them directly into the CleverTap dashboard with a few clicks:

1. Go to the CleverTap dashboard and navigate to _**Settings**_ > _**Channels**_ > _**WhatsApp**_.
2. From the list of available providers, select the appropriate provider's nickname.
3. Click the **Templates** tab and select **Import Templates**. The _Import Template_ button is visible only for CleverTap BSP. Clicking it will open a window for importing templates.

<Image align="center" alt="Import Template " border={true} caption="Import Template" src="https://files.readme.io/ca3870bd545767af14a5833622c8133e7cc52178bdefc31f41aa8e882a736a04-create_template.png" />

The _Import Template_ window opens.

<Image align="center" alt="Import WhatsApp Templates " border={true} caption="Replace or add new WhatsApp Templates" src="https://files.readme.io/d629f40-2023-09-25_17-21-03.jpg" width="60% " />

4. Click _Import_. Select this option to replace all existing templates on your CleverTap dashboard. This action will delete all current templates and import the latest approved templates from the Meta dashboard. This ensures CleverTap has the most up-to-date templates with their respective content and statuses.
5. Click **Continue** to replace or add templates.  The CleverTap dashboard shows the new templates. Your previous templates are mailed to your email account.

> 📘 Impact of Template Import on Failing WhatsApp Campaigns
>
> Importing templates will not automatically resolve errors or issues related to the existing WhatsApp campaigns or journeys. These campaigns and journeys will continue to fail until you manually update the imported template in the affected campaign's What section.
>
> To address campaign failures resulting from template-related errors, please follow the below steps:
>
> 1. Identify the specific campaign or journey that is encountering the error.
> 2. Access the _What_ section of the campaign or the specific journey node.
> 3. Edit the campaign or journey and select the specific imported templates.
> 4. Save and publish the changes, and check that the campaigns and journeys use the updated templates.

> 📘 Track Button Clicks
>
> Check the URL defined to track the button clicks in the META dashboard. For example, _ct1.io.//\{\{1}}_. This URL will be imported with the template in the CleverTap dashboard. This link cannot be updated later.

# Testing a Message Template

You can send a test message using the saved templates from the CleverTap dashboard as follows:

1. From the Templates tab, click the ellipsis below the required template and click **Send Test**.

<Image align="center" alt="Select Send Test!" border={true} caption="Select Send Test" src="https://files.readme.io/30e94225e48e3f4120643d16af7ce367f9bfc211aa2bf19b9759d865810e4d9e-overview.png" width="40% " />

2. Select the test profiles or manually enter the mobile number to whom you want to send the message and click **Send Test**.

<Image align="center" alt={1304} border={true} caption="Preview and Test" title="Preview the Template Message" src="https://files.readme.io/fbf00f7-test_template.png" />

The success or failure response is displayed on the dashboard. If the message is not delivered, you can copy the response payload and share it with the CleverTap team to debug the issue, as shown in the following figure.

<Image align="center" alt="send test rendering sample" border={true} caption="Test Template" title="Test the Message" src="https://files.readme.io/878b541-send_test_rendering.jpg" width="80%" />

# FAQs

### **Q. What are WhatsApp Templates?**

A. WhatsApp templates are predefined message formats businesses use to communicate with their customers via WhatsApp Business API.

### Q. Why are Templates Required?

A. WhatsApp only allows brands to send pre-approved messages with brand-initiated conversation. These pre-approved messages are templates.

### Q. How are Templates Approved?

A. WhatsApp provides approvals for templates. Once created, businesses submit the templates to WhatsApp for review, and upon approval, they can be used for customer communication.

### Q. How Long Does Template Approval Take?

A. Template approval times can vary. It typically takes a few minutes, but the process may take up to 24 hours.

### Q: When should I use Basic Templates?

A: Use Basic Templates for straightforward messages that require a single media item, a text body, a footer, or a few buttons.

### Q: When should I create Limited-Time Offer Templates?

A: Create Limited-Time Offer Templates for promotions with a specific expiration date or time-sensitive deals, such as flash sales and seasonal discounts.

### Q: When should I use Carousel Templates?

A: Use Carousel Templates to showcase multiple products or offers in a single message, allowing customers to swipe through different options.

### Q: What should I do if my WhatsApp template gets rejected?

A: Review the rejection reason provided by WhatsApp, correct any issues (such as grammatical errors or non-compliance with guidelines), and resubmit the template for approval
