---
title: Gmail Promotional Annotations
excerpt: >-
  Understand how to put the most valuable parts of email right at people's
  fingertips.
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

[Gmail Promotional Annotations](https://developers.google.com/gmail/promotab/) enables you to highlight your email on the Gmail Promotions tab. Your email can include additional information, such as promotion codes, featured images, and deal expiration dates. This information is visible to your email subscribers before they open the email, thereby setting your message apart from other emails in the Promotions tab of the user's inbox. This is an excellent way to excite your users to open your email. CleverTap provides you with a no-code way to annotate your email messages.

# Annotate Emails with Deal Annotation

With Deal Annotation, the deals and offers stand out prominently in the Promotions tab of your Gmail inbox, capturing your audience's attention and increasing the likelihood of conversions.


<Image src="https://files.readme.io/6fd6c27-Annotated_Email.png" align="center" width="65% " caption="Deal Annotation Email" border={true} />


To annotate emails in an email campaign, perform the following steps:

1. [Create an email campaign](https://docs.clevertap.com/docs/create-message-email).

2. [Define the message content](https://docs.clevertap.com/docs/create-message-email#define-the-message-content) from the Email Editor.

3. Click **Sender details**.

4. To annotate your email, select **Highlight with Gmail promotional annotations**. The following options display:


   <Image src="https://files.readme.io/b9ccbce-Gmail_Promotional_Annotation_.png" align="center" caption="Annotate Emails with Deal Annotation" border={true} />


5. Add the required information.

| Element        | Description                                                                                                            | Best Practices                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| :------------- | :--------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sender name    | Add your business name.                                                                                                | This field is populated automatically using the _From_ part of the _Sender Details_.                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Subject line   | Add a unique and relevant subject line for the inbox. We recommend a 44-character limit for optimal rendering.         | This field is populated automatically using the _Subject_ part of the _Sender Details_.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Company logo   | Upload an image or add a URL. Check that the URL is https (not http).                                                  | Ensure that you use an https (not http) URL. This logo selection only shows in the email preview. To render the logo, you must implement [Brand Indicators for Message Identification (BIMI)](doc:brand-indicators-for-message-identification) standards.                                                                                                                                                                                                                                                                         |
| Discount offer | Highlight any offerings such as _20% off_ or _Free Shipping_. We recommend a 20-character limit for optimal rendering. | • Avoid using more than four words or full sentences in this space, as it competes with your subject line. When your email text space is full, the offer title truncates (for example, "...").<br /><br />• Do not repurpose. Use promotional offerings to ensure clarity and simplicity. Do not utilize it for other actions such as _Open now_.<br /><br />• Do not use run-on sentences. Avoid saying things such as _25% off, unless you've already purchased from us, in which case other ..._ Long sentences are truncated. |
| Offer code     | Add the promo code. We recommend a 20-character limit for optimal rendering.                                           | Only use a discount code if it is featured in the email. Do not repurpose this space, as it always says _Code_ before the text.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Offer period   | Select the offer date range.                                                                                           | Using this feature allows an email to be previewed twice at the top in a bundle:<br /><br />• once when it is first sent.<br /><br />• again within 3 days of the offer expiry.<br /><br />When personalizing _Offer period_, specify the time and timezone. For example, _2018-12-30T23:59:59-0700_.                                                                                                                                                                                                                             |

5. Click **Preview & Test** to preview the annotated email message.

# Annotate with Promotion Cards

Adding Promotion Cards to your annotations enhances the impact of email marketing campaigns by introducing image previews, either as a single card or a carousel of cards. This helps amplify engagement and drive higher conversion rates. Each card can be configured with its own image, title, description, and target URL.


<Image src="https://files.readme.io/4f32a4d939159fd3d44e0a3d4329515618705b4f0565f7464383812d17c14d1a-image.png" align="center" width="65% " caption="Single Image Layout" border={true} />


<br />


<Image src="https://files.readme.io/0dcfcde9bdbc05e3e8b476417628beb88bff3e3301683ef8fb8445148ac4da4d-Carousel_Image_Layout.png" align="center" width="67% " caption="Carousel Image Layout" border={true} />


## Prerequisites

* Add your sending domain to the Google Allowlist by reaching out to [p-gmail-outreach@google.com](mailto:p-gmail-outreach@google.com).
* Register the domain with [DMARC](https://support.google.com/a/answer/2466563?hl=en).

## Annotate Email with Promotion Cards

To annotate an email campaign with promotional cards, perform the following steps:

1. [Create an email campaign](https://docs.clevertap.com/docs/create-message-email).

2. [Define the message content](https://docs.clevertap.com/docs/create-message-email#define-the-message-content) from the Email Editor.

3. Select the _Sender details_ tab.

4. Select **Highlight with Gmail promotional annotations** and select **Promotion Cards**. A single promotion card (Single Image Layout) is displayed to the user by default. You can add more cards by clicking **Promotion Card** for Carousel Layout. The following options display for each promotion card:


   <Image src="https://files.readme.io/ffda68725e844316f99a94057fc9e1dd4e190e94b8cbc90bf42b2aaa82d0c2fb-Annotate_Email_with_Promotion_Cards.png" align="center" caption="Annotate Email With Product Carousel Using Image URL Option" border={true} />



   <Image src="https://files.readme.io/577d56ec16b072b5ca0d4b53a877e5f3889f3dca5314ab93ad07f404c226a7f4-Upload_Image_for_Product_Carousel.png" align="center" caption="Annotate Email With Product Carousel Using Upload Image Option" border={true} />


5. Add the required information.

| Element          | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Mandatory                                           |
| :--------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------- |
| _Image URL_      | Provide the unique image URL. Supported formats include PNG and JPEG. The image must meet the aspect ratio requirements based on whether you are creating a single promotional card or a carousel.<br /><br />• **For Single Image Layout**: Supported Aspect Ratio: 1.91:1 only.<br /><br />• **For Carousel Layout**:<br /><br />   • Supported Aspect Ratios: 4:5, 1:1, or 1.91:1.<br /><br />   • All images in a carousel must use the same aspect ratio for compatibility. For additional guidelines, refer to the [Google Documentation](https://developers.google.com/gmail/promotab/overview#microdata_1).<br /><br /><br />For more information, refer to [Image Specification for Promotion Cards](doc:gmail-promotional-annotations#image-specification-for-promotion-cards).<br /><br /><br />**NOTE**: Google recommends not using personalized elements or user-specific UTM parameters in carousel image URLs. Only static images must be used across all campaign users for annotations to render in the email. | Yes, when the image is hosted on an external source |
| _Upload Image_   | You can upload images in PNG or JPEG format. The image must meet the aspect ratio requirements based on whether you are creating a single promotional card or a carousel. You can resize images using the cropper tool; the aspect ratio will be maintained based on the selected option.<br /><br />• **For Single Image Layout**: Supported Aspect Ratio: 1.91:1 only.<br /><br />• **For Carousel Layout**:<br /><br />   • Supported Aspect Ratios: 4:5, 1:1, or 1.91:1.<br /><br />   • All images in a carousel must use the same aspect ratio for compatibility. For additional guidelines, refer to the [Google Documentation](https://developers.google.com/gmail/promotab/overview#microdata_1).<br /><br /><br />For more information, refer to [Image Specification for Promotion Cards](doc:gmail-promotional-annotations#image-specification-for-promotion-cards).                                                                                                                                                 | Yes, when uploading an image from your local system |
| _Target URL_     | Provide the specific URL that opens when the user clicks on the promotional image. The target URL can include personalized elements, such as UTM parameters for tracking or any other parameters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Yes                                                 |
| _Headline_       | Provide a concise 1 to 2-line description accompanying the promotional card.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | No                                                  |
| _Currency_       | Select the currency of the displayed price from the dropdown list. The supported currencies include USD, INR, AED, EUR, and SGD. This field appears when you select the _Price Tag_ checkbox.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | No                                                  |
| _Product Value_  | Provide the numerical value representing the original price for the promotional product. This field appears when you select the _Price_ checkbox.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | No                                                  |
| _Discount Value_ | Provide the discount value, which represents the amount deducted from the original price. This field appears when you select the _Price_ checkbox.<br /><br />For example, if the discount value is 25 and the original price is 100, the final price displayed will be $75.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | No                                                  |

5. Click **Preview & Test** to preview the annotated email message.

<Callout icon="📘" theme="info">
  #### **Supported Inboxes**

  Single Image and Carousel annotations are supported only on the Gmail mobile apps (iOS and Android). They are not supported for:

  * Gmail on desktop
  * Users in the EU region (on any platform)
</Callout>

## Image Specification for Promotion Cards

To display promotion cards in an email, ensure that your images meet the following specifications based on the type of promotion card being used:

### For Carousel Layout

* Minimum Cards: You must add two or more promotion cards.
* Target URLs: Each image must have a unique target URL.
* Aspect Ratio Consistency: All images in the carousel must share the same aspect ratio.
* Supported Aspect Ratios: 1.91:1, 4:5, and 1:1

### For Single Image Layout

* Card Limit: Only one promotion card is allowed.
* Supported Aspect Ratio: 1.91:1

# Test Annotation

Create a unique Gmail testing account ending with [promotabtesting@gmail.com](mailto:promotabtesting@gmail.com) for your team. For example, [mycompany.promotabtesting@gmail.com](mailto:mycompanypromotabtesting@gmail.com). This unique account will have a more aggressive email ranking and bundling to make testing easier and faster.

<Callout icon="📘" theme="info">
  #### **Testing Promotion Cards**

  For Promotion Cards to render, Google recommends a campaign with atleast 100 users.
</Callout>

# Troubleshooting

Before troubleshooting a problem, check your account-level settings in your Gmail app. Check that you have enabled the following settings to test the latest experiences in the _Gmail promotions_ tab. The following are the default settings:

* Images: Always show.
* Conversation view: On.
* Enable Bundling of Top Email: On.

The following sections include information about common issues encountered when attempting to test:

### Not seeing email bundles at all

To resolve this issue:

* Check that the device has the latest version of the Gmail app. Refresh your email by pulling down on the screen within the promotions tab.
* Try restarting your device.
* If the issue is still not resolved, try viewing the bundle on another device. For example, a tablet may have a different Gmail version and show the bundle differently.

<Callout icon="📘" theme="info">
  #### **Email Held Up**

  There is a chance your email could be in a holdback group. If none of the measures work, create a new account ending with [promotabtesting@gmail.com](mailto:promotabtesting@gmail.com). For example, create [mycompanypromotabtesting@gmail.com](mailto:mycompanypromotabtesting@gmail.com) and use that new account for testing.
</Callout>

### Email does not show up on the Promotions tab

To resolve this issue:

* Check if the marketing email was sent from the usual subdomain. Sending from less recognized subdomains can confuse the Gmail tab classifier and prevent an email from being placed on the Promotions tab.
* Check that your account has no email filters that send email to the primary tab because annotations are only visible on the Promotions tab.
* Send from different sender subdomains to ensure the email ends up on the correct tab. For more details about the Gmail classifier, refer to [Bulk Senders Guidelines](https://support.google.com/mail/answer/81126).
* If you are using a [promotabtesting@gmail.com](mailto:promotabtesting@gmail.com) account, the first email does not appear on the Promotions tab. Drag the email onto the Promotions tab, and send an email from the same sender address, with a different subject line, to the testing account.

### Cannot see your brand's annotated email in a bundle

To resolve this issue:

* Check if the email is on the Gmail Promotions tab.
* Annotated emails are currently not available for Gmail for Business accounts. Ensure that you are testing on your personal Gmail address.
* Check that the email was not opened or sent on the previous day.
* An email does not populate in a bundle on another device after it is viewed on one device. You must send a new test email to preview.
* Create multiple testing accounts if you want to visualize on multiple devices. One of your team members might open the email, thus making it unavailable in the bundle for the rest of the team.
* Check that the annotation is not past the expiration date.
* Check that you are using the latest version of the Gmail app. Try viewing on another device. For example, a tablet may have a different version of the Gmail app and show email differently.
* Refresh the Gmail app by pulling down the Gmail Promotions tab screen.
* Check that you are not using sensitive categories in the Gmail Promotions tab. For example, adult content or debt collection.

### The email bundle is visible on one device but not on another

To resolve this issue:

* Check that you are viewing from the same email account.
* If the email is opened on one device first, the ranking of the bundle may change on another device.

# Best Practices

Gmail recommends the following to optimize your email annotations.

* **Leverage the Power of Visuals**<br />Gmail has observed improved results when emails feature captivating images that complement the message. Instead of text-only designs, focus on incorporating visually appealing elements. Avoid using images with text that gets cut off or reusing the same visuals across multiple campaigns.
* **Concise Offer Descriptions**<br />Gmail recommends concise and compelling offer descriptions. Avoid lengthy sentences or phrases, such as "Limited Time Offer: 50% Off All Accessories", or "Exclusive Deals on Summer Collection," as they might get clipped and compete with the subject line. Opt for clear, engaging language that encourages recipient engagement without repeating the subject line verbatim.

For more information about annotating your email messages effectively, refer to Google's [Best Practices](https://developers.google.com/gmail/promotab/best-practices).

# FAQs

### Can I see how many users received a product carousel?

Gmail decides when to show the product carousel, so not every person who gets the email will see it. Therefore, there's no definite way to know how many people received the product carousel.

### Why does my promotional message not display the product carousel in the user's inbox?

There are a few reasons why the product carousel might not appear in the Gmail Promotion Tab. Firstly, all the images in the promotion must be of good quality and have the correct aspect ratio. They should mostly be pictures of the product, without too much text or anything inappropriate.

Moreover, Gmail limits the number of product carousels it shows in the _Promotion_ tab. So, if a user receives a lot of emails with product carousels, Gmail might not show all of them.

### What image guidelines should I follow for Email Carousel Annotations?

It is recommended that high-quality, high-resolution product images be used. Try to avoid images with excessive text. The minimum image size is 256 pixels, and the maximum size is 4096 pixels. For the best results, use images with higher pixels.

### What is the minimum number of users required for rendering Promotion Cards?

Google recommends running the campaign with at least 100 users for optimal rendering and visibility.
