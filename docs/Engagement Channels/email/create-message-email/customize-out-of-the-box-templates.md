---
title: Customize Out-of-the-Box Templates
excerpt: >-
  Learn how to customize Basic and AMP email templates available out-of-the-box
  on the CleverTap dashboard.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

While the entire template is customizable, CleverTap highlights a set of key components you can easily tailor to match your brand and campaign needs. These include logos, banners, CTAs, and theme colors. This section outlines how to modify these core elements, along with reusable code snippets and step-by-step guidance to ensure consistency and ease across your email campaigns.&#x20;

# Customization Options

The following are the key customization options:

* [Replace Logo](doc:customize-out-of-the-box-templates#replace-logo)
* [Replace Background](doc:customize-out-of-the-box-templates#replace-background)
* [Update Banner/Product Images](doc:customize-out-of-the-box-templates#update-bannerproduct-images)
* [Update Call-To-Actions (CTAs)](doc:customize-out-of-the-box-templates#update-call-to-actions-ctas)
* [Update Links in Header/Footer](doc:customize-out-of-the-box-templates#update-links-in-headerfooter)
* [Change Theme or Background Color](doc:customize-out-of-the-box-templates#change-theme-or-background-color)
* [Update Privacy Policy](doc:customize-out-of-the-box-templates#update-privacy-policy)
* [Update Social Media and Download Links](doc:customize-out-of-the-box-templates#update-social-media-links-and-download-links)
* [Countdown Timer (Flash Sale Only)](doc:customize-out-of-the-box-templates#countdown-timer-flash-sale-only)
* [Add or Modify Filters](doc:customize-out-of-the-box-templates#add-or-modify-filters)

## Replace Logo

Displays the brand logo at the top of the email, ensuring immediate brand recognition and consistent visual identity.

### Option 1: Using Source Mode

1. Locate the logo block in your HTML template. The following is a common example:
   ```html
   <td style="text-align: left; vertical-align: middle; padding: 20px">
     <img 
       alt="Logo"
       class="logo"
       src="https://yourdomain.com/logo.png"
       style="display: inline-block; width: 127px; height: 58px; object-fit: cover;" />
   </td>
   ```

2. Replace the `src` value with the URL of your updated brand logo as follows:
   ```html
   src="https://yourdomain.com/path-to-your-logo.png"
   ```

3. Optionally customize:
   * `alt`: Add accessible text such as `"Your Brand Logo"`
   * `width` and `height`: Adjust only if required (default is typically `127px × 58px`)

### Option 2: Using Visual Mode

1. Select the required template in the CleverTap **Email Editor** (for example, under _Create Email > Single Message_).

2. Locate and click the existing logo image in the top section of the email.

3. Choose one of the following image replacement methods:

   * **Upload** a new image file (recommended: PNG or SVG).
   * **Paste the URL where image is hosted** in the **Image URL** field (if available).


   <Image src="https://files.readme.io/ee0f3f1e5b1c453e7e6c07b3a33d9a07aa9bb10d757c40d4ffca334a0ee12c86-Replace_Logo.png" alt="Replace Logo" align="center" width="75% " caption="Replace Logo" border={true} />


4. Click Insert to add the image.

5. Adjust the image size and alignment using the **styling and formatting options**—such as margins, width, and spacing.

6. Click **Add**  and click **Done** in the top-right corner of the editor and preview the email to ensure proper rendering.

<Callout icon="📘" theme="info">
  ### Note

  Ensure to verify logo alignment, spacing, and sizing on both mobile and desktop previews after replacement.
</Callout>

## Replace Background

Sets or replaces the existing background with a custom image of your choice.

### Using Source Mode

1. Locate the `.header-container` property in the HTML code.
   ```css
   .header-container {
     background: transparent url(https://d1qzvqecfo5h8o.cloudfront.net/images/67Z-875-RR7Z/spinn/header-design.png);
     background-size: contain;
     background-repeat: repeat-x;
     background-position: bottom;
     padding-bottom: 18px;
   }
   ```
2. Replace the `background` URL with the link to the new image, in this case, `header-design.png`.

## Update Banner/Product Images

Visually highlights products, offers, or campaigns at the top of the email using a full-width banner image or a product tile grid, depending on the template layout.

### Option 1: Using Source Mode

1. Locate the banner `<img>` tag in your HTML template. For example:
   ```html
   <tr>
     <td align="center">
       <img src="https://yourdomain.com/banner.jpg"
            alt="Promotional Banner"
            style="width: 100%; height: auto;" />
     </td>
   </tr>
   ```

2. Replace the `src` URL with the path to your new banner image.

3. Update the `alt` attribute to provide descriptive alternative text for accessibility and fallback scenarios.

4. Ensure the image meets the following specifications:
   * **Recommended size**: 600px (width) × 400px (height)
   * **Aspect ratio**: 3:2
   * **File formats**: `.jpg`, `.png`, `.gif`
   * **Maximum file size**: Under 1MB

### Option 2: Using Visual Mode

1. Select the required template in the CleverTap **Email Editor**.

2. Click on the existing banner image.

3. Choose one of the following image replacement methods:

   * **Upload** a new image file (recommended: PNG or SVG).
   * **Paste the URL where image is hosted** in the **Image URL** field (if available).


   <Image src="https://files.readme.io/caddfba6fc321ec0d81c6b9028c1c9ad40c7b24616e8409ac25f18b079f6c024-Update_BannerProduct_Images.png" alt="Update Banner/Product Images.png" align="center" width="75% " caption="Update Banner/Product Images.png" border={true} />


4. Click Insert to add the image.

5. Adjust the image size and alignment using the **styling and formatting options**—such as margins, width, and spacing.

6. Click **Add**  and click **Done** in the top-right corner of the editor and preview the email to ensure proper rendering.

<Callout icon="📘" theme="info">
  ### Note

  For templates using grid-based layouts or product tiles, ensure to match the original image dimensions and maintain consistent spacing to ensure the layout remains visually balanced and responsive.
</Callout>

## Update Call-To-Actions (CTAs)

Guides the user to take specific actions within the email, such as clicking a button to redirect the user to a web page, completing a purchase, or viewing more details. You can customize the following elements:

* **Text**: Modify the text within the anchor tag (e.g., "Discover More" → "Shop Now").
* **URL**: Update the `href` attribute with the desired link (e.g., `href="https://your-domain.com"`)
* **Styling**: Adjust the CSS properties to fit your design specifications (for example, background color, padding, text size).

### Option 1: Using Source Mode

1. Locate the CTA section in your HTML template as shown below:
   ```html
   <tr>
     <td style="text-align: center; padding: 20px;">
       <a href="https://your-link.com"
          style="background: #FF5733; padding: 10px 20px; color: #fff; text-decoration: none; font-size: 16px; border-radius: 5px;">
         Shop Now
       </a>
     </td>
   </tr>
   ```

2. Replace the `href` URL with the link where you want to direct the user:
   ```html
   href="https://yourdomain.com/your-action"
   ```

3. Optionally, modify the text of the CTA, such as changing "Shop Now" to "Get Started" or "Claim Your Offer."

4. Adjust the button styling by modifying the CSS within the `<a>` tag (for example, background color, padding, font size, etc.):
   ```html
   style="background: #FF5733; padding: 10px 20px; color: #fff; text-decoration: none; font-size: 16px; border-radius: 5px;"
   ```

### Option 2: Using Visual Mode

1. Open the template in the CleverTap **Email Editor**.

2. Click on the existing CTA button in the email layout.

3. Update the **Display Text** to match your new call to action (for example, _Learn More_, _Shop Now_, and so on).


   <Image src="https://files.readme.io/6f302e2b6f77f9058405ce8b2b1d8a08ab13bbffed52b3ce250ca2a919d9c9a9-Update_Call-to-Action.png" alt="Update CTAs" align="center" width="85% " caption="Update CTAs" border={true} />


4. Enter or update the **Link URL** to point to your desired destination.

5. Click **Add**, then click **Done** in the top-right corner.

6. Preview the email to confirm that the CTA appears and functions correctly across devices.

<Callout icon="📘" theme="info">
  ### Best Practices

  Always make sure the CTAs are clear and actionable, and consider using verbs such as "Buy," "Get Started," "Learn More," or "Shop Now."
</Callout>

## Update Links in Header/Footer

Updates the links in the header or footer sections of the email, such as Privacy Policy, Terms of Service, or any social media or download links, to ensure they direct to the correct URLs.

### Option 1: Using Source Mode

1. **Locate the Header/Footer Section**: Search for the relevant section in your HTML code. The following is a sample code:
   ```html
   <td class="footer" style="text-align: center; padding: 10px; font-size: 12px;">
     <a href="https://your-domain.com/privacy-policy" style="color: #939393; text-decoration: none;">Privacy Policy</a>
   </td>
   ```

2. **Update Link**: Replace the `href` URL with the new destination:
   ```html
   href="https://your-domain.com/new-link"
   ```

3. **Update the Text**: If required, update the link's visible text. For example:
   ```html
   <a href="https://your-domain.com/privacy-policy" style="color: #939393; text-decoration: none;">Terms & Conditions</a>
   ```

4. **Styling Adjustments**: You can adjust the text styles by modifying the `style` attribute (for example, font color, size, and so on).

5. **Save and Preview**: After making changes, ensure to save the file and preview the email to confirm that the links are functional and styled properly.

### Option 2: Using Visual Mode

1. Select the template from the CleverTap dashboard that fits your business requirement.

2. Click the link you want to update in the header or footer section (for example, Unsubscribe link).

3. Update the **Display Text** to reflect your desired action or label.

4. Enter or update the **Link URL** to point to the correct destination.


   <Image src="https://files.readme.io/61f5096178dc9c464e937ded9a7a1b9ca0f2f71a7fa2435ae263bf1510b0505b-Update_Links_in_HeaderFooter.png" alt="Update Links in Header/Footer" align="center" width="75% " caption="Update Links in Header/Footer" border={true} />


5. Click **Apply**, then click **Done** in the top-right corner.

6. Preview the email to confirm that the link appears and functions correctly across devices.

<Callout icon="📘" theme="info">
  ### Header/Footer Links

  * **Unsubscribe Link**: For compliance with regulations such as GDPR and CAN-SPAM, all templates that include an **Unsubscribe** link in the footer must ensure it directs to the correct unsubscribe mechanism.
  * **Social Media Links**: Ensure all social media links, like those for Facebook, Instagram, etc., are up-to-date and lead to your current active profiles.
  * **Dynamic Links**: Some templates, like **Referral** or **Cart Abandonment**, require dynamic links that change based on user activity. Make sure these URLs are generated dynamically by your platform or manually updated.
  * **Call-to-Actions (CTAs)**: Some templates, especially those with **sales**, **product promotions**, or **loyalty rewards**, might have CTAs that need to be consistently checked and updated based on current offers or time-sensitive promotions.
</Callout>

## Change Theme or Background Color

Modifies the background color or overall theme of the email to match your branding or campaign requirements. This ensures a consistent visual experience aligned with your marketing or seasonal themes.

### Using Source Mode

1. Locate the `<table>` tag defining the background color in your HTML code. A typical structure might look like this:
   ```html
   <table style="border-collapse: collapse; width: 100%; max-width: 600px; margin: 0 auto; background: #ffffff;" width="100%" cellspacing="0" cellpadding="0" border="0">
   ```

2. **Update the Background Color**:<br />Replace the existing `background` attribute value with your desired color. For example:
   ```html
   background: #f0f0f0;
   ```

3. **Save and Preview**: After making the changes, save the file and preview the email to ensure the new background color appears correctly across different devices.

## Update Privacy Policy

Ensures that the Privacy Policy link in the email template directs users to the most current and correct Privacy Policy page.

### Option 1: Using Source Mode

1. **Locate the Privacy Policy Link**:<br />Search for the `<a>` tag associated with the Privacy Policy in the footer or header section of your template. The following is a sample code:
   ```html
   <a href="#" class="f-nav-link" style="font-family: 'Poppins', Arial, sans-serif; font-size: 14px; font-weight: 400; line-height: 24px; color: #939393 !important; text-decoration: none;">Privacy Policy</a>
   ```

2. **Update the**`href`**&#x20;URL**:<br />Replace the current `href="#"` with the correct URL for your Privacy Policy page. For example:
   ```html
   href="https://yourdomain.com/privacy-policy"
   ```

3. **Modify Text (Optional)**: You can optionally change the visible text of the link, such as replacing "Privacy Policy" with "Terms & Conditions" if required.

4. **Save and Preview**: After making the changes, save your template and preview it to ensure the Privacy Policy link is working correctly and properly displayed.

### Option 2: Using Visual Mode

1. Open the template in the CleverTap **Email Editor**.

2. Locate the **Privacy Policy link** in the footer (or header) section of the email.

3. Click the link to open the editing toolbar.

4. Update the **Link URL** to point to the correct Privacy Policy page.

5. Optionally, update the **Display Text** if needed (for example, change "Privacy Policy" to "Terms & Conditions").


   <Image src="https://files.readme.io/67f084852c6c76f39130ecea74d93a260c0b57d3d2d351614f8d5fe46352993c-Update_Privacy_Policy.png" alt="Update Privacy Policy" align="center" width="75% " caption="Update Privacy Policy" border={true} />


6. Click **Add**, then click **Done** in the top-right corner of the editor.

7. Preview the email to confirm the link is functional and renders correctly across devices.

## Update Social Media and Download Links

Updates and ensures all social media and download links in your email template direct users to the correct platforms, apps, or resources.

### Option 1: Using Source Mode

1. **Locate the Social Media and Download Sections**:<br />Search for sections in the HTML code related to social media platforms (such as Facebook, Twitter, Instagram, etc.) and download buttons (such as Android or Apple store download links). You may see something like:
   ```html
   <a href="https://your-facebook-link" target="_blank">
     <img src="https://path-to-facebook-icon.png" alt="Facebook" class="social-icon" />
   </a>
   ```

2. **Update the Links**:

   For social media platforms, replace the `href` with the correct URL. For example:

   ```html
   <a href="https://facebook.com/your-page" target="_blank">
     <img src="https://path-to-facebook-icon.png" alt="Facebook" class="social-icon" />
   </a>
   ```

   Similarly, for download links, locate the button or link related to the app download:

   ```html
   <a href="#" class="btn-link" style="margin: 0 10px;">
     <img src="apple-btn.png" alt="Download on Apple" class="btn-img" style="background: #F7F7F7; position: relative; z-index: 1;">
   </a>
   ```

   Update the `href` attribute with the correct download link:

   ```html
   <a href="https://www.apple.com/app-store" class="btn-link" style="margin: 0 10px;">
     <img src="apple-btn.png" alt="Download on Apple" class="btn-img" style="background: #F7F7F7; position: relative; z-index: 1;">
   </a>
   ```

3. **Save and Preview**:<br />After updating the URLs for social media and download links, save the file and preview the email to ensure all links work properly.

### Option 2: Using Visual Mode

1. Select the template from the CleverTap dashboard that fits your business requirement.

2. In the footer section, click on a social media icon (such as Facebook, Instagram, or Twitter).

3. Click the link you want to update and update the **Link URL** to point to your brand’s corresponding social media page.

4. Repeat the process for each social media icon you want to update.


   <Image src="https://files.readme.io/cbc9edf2828c12258b0c5a1da1ad2e0cf8ffbe4061b831de106ff9010c3d48cd-Update_Social_Media_and_Download_Links.png" alt="Update Social Media and Download Links" align="center" width="75% " caption="Update Social Media and Download Links" border={true} />


5. Locate and click on the download link (for example, Android or iOS button) in the footer.

6. Update the **Link URL** to the correct app store page (for example, Google Play Store or Apple App Store).

7. Click **Add** and click **Done** in the top-right corner of the dashboard.

8. **Preview the email** to ensure all links are functional and direct users to the right destinations.

## Countdown Timer (Flash Sale Only)

Adds urgency with a live or static countdown. Use a hosted GIF or PNG and replace the image attribute `src` with the required graphics.

```html
<img src="timer.gif" alt="Countdown Timer" style="width: 100%;" />
```

## Add or Modify Filters

1. Add CTA for the Filter, for example, Kids
   ```html
   <button class="btn typ-secondary"
   [class]="'btn ' + (selectedCategory.value == 'kids' ? '' :
   'typ-secondary')" value="kids"
   on="tap:AMP.setState({selectedCategory: {value: 'kids'}})">
   Kids
   </button>
   2. Add Their Products
   <div class="category category-women" hidden [hidden]="selectedCategory.value !=
   'women'">
   ```
2. Add a list of the products for Kids.

   ```html
   <div class="category category-women" hidden [hidden]="selectedCategory.value !=
   'women'">
   <ul class="product-list">
   <li class="product-item">
   <div class="product-card">
   <div class="img-wrap">
   <!-- Change image src as per your requirements -->
   <amp-img layout="responsive"
   src="https://d1qzvqecfo5h8o.cloudfront.net/images/67Z-875-RR7Z/relevant/women-product-
   1.png"
   alt="Product Image" width="258"
   height="174"></amp-img>
   </div>
   <div class="content-wrap">
   <div class="lhs">
   <h3 class="p-title">Product name</h3>
   </div>
   <div class="rhs">
   <p class="p-amt"><span
   class="rupee">₹</span>1500</p>
   </div>
   </div>
   <p class="p-desc">is simply dummy text of the new age
   fashion industry.</p>
   <a href="https://www.google.co.in/" class="p-link">
   Shop now
   </a>
   </div>
   </li>
   <li class="product-item">
   <div class="product-card">
   <div class="img-wrap">
   <!-- Change image src as per your requirements -->
   <amp-img layout="responsive"
   src="https://d1qzvqecfo5h8o.cloudfront.net/images/67Z-875-RR7Z/relevant/women-product-
   2.png"
   alt="Product Image" width="258"
   height="174"></amp-img>
   </div>
   <div class="content-wrap">
   <div class="lhs">
   <h3 class="p-title">Product name</h3>
   </div>
   <div class="rhs">
   <p class="p-amt"><span
   class="rupee">₹</span>1500</p>
   </div>
   </div>
   <p class="p-desc">is simply dummy text of the new age
   fashion industry.</p>
   <a href="https://www.google.co.in/" class="p-link">
   Shop now
   </a>
   </div>
   </li>
   <li class="product-item">
   <div class="product-card">
   <div class="img-wrap">
   <!-- Change image src as per your requirements -->
   <amp-img layout="responsive"
   src="https://d1qzvqecfo5h8o.cloudfront.net/images/67Z-875-RR7Z/relevant/women-product-
   3.png"
   alt="Product Image" width="258"
   height="174"></amp-img>
   </div>
   <div class="content-wrap">
   <div class="lhs">
   <h3 class="p-title">Product name</h3>
   </div>
   <div class="rhs">
   <p class="p-amt"><span
   class="rupee">₹</span>1500</p>
   </div>
   </div>
   <p class="p-desc">is simply dummy text of the new age
   fashion industry.</p>
   <a href="https://www.google.co.in/" class="p-link">
   Shop now
   </a>
   </div>
   </li>
   <li class="product-item">
   <div class="product-card">
   <div class="img-wrap">
   <!-- Change image src as per your requirements -->
   <amp-img layout="responsive"
   src="https://d1qzvqecfo5h8o.cloudfront.net/images/67Z-875-RR7Z/relevant/women-product-
   4.png"
   alt="Product Image" width="258"
   height="174"></amp-img>
   </div>
   <div class="content-wrap">
   <div class="lhs">
   <h3 class="p-title">Product name</h3>
   </div>
   <div class="rhs">
   <p class="p-amt"><span
   class="rupee">₹</span>1500</p>
   </div>
   </div>
   <p class="p-desc">is simply dummy text of the new age
   fashion industry.</p>
   <a href="https://www.google.co.in/" class="p-link">
   Shop now
   </a>
   </div>
   </li>
   </ul>
   </div>

   ```

   **Output**:


   <Image src="https://files.readme.io/2568bab6a196e7d5593c99ef2d0a2ad9786717bea7519b0f81d93ff7b5f02e46-Output_for_Adding_New_Filter.png" alt="Output for Adding Filter" align="center" width="35% " caption="Output for Adding Filter" border={true} />
