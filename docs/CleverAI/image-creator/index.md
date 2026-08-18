---
title: Image Creator
excerpt: >-
  Learn how configuring brand colors, tone, and content guidelines once helps
  you create on-brand AI-generated assets, every time.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Image Creator helps you instantly create, edit, or refine images for your campaigns, all within CleverTap, without the need for external design tools. It combines advanced AI capabilities with your [Brand Kit](https://docs.clevertap.com/docs/brand-kit) to generate on-brand, campaign-ready visuals quickly and efficiently. This makes it easier for teams to design creative images directly in the campaign editor, reducing dependency on design teams and accelerating go-to-market time.

<Callout icon="📘" theme="info">
  ### Availability

  Image Creator is available in Pro and Ultimate plans. To access this feature, contact your Customer Success Manager.
</Callout>

With Image Creator, you can do the following:

- Save time creating campaigns by generating campaign banners, promotional visuals, or lifestyle images directly in the campaign builder.
- Maintain brand consistency at scale by automatically applying your Brand Kit, colors, logo, and visual style, across all campaign images.
- Reduce dependency on design teams by generating campaign-ready images on demand.
- Produce multiple visual variations for A/B testing.
- Refining and editing an existing image concept (for example, adjusting mood, style, or elements) without starting from scratch.

# Learn How Image Creator Works

The feature is embedded within the campaign editor, next to image upload fields, such as **Expanded Image** or **Large Icon**. You can use it to:

- Create new images from scratch using descriptive prompts.
- Edit or refine existing visuals with prompts.

The Image Creator automatically applies your Brand Kit to ensure every generated image aligns with your brand colors, styles, and tone.

<Callout icon="📘" theme="info">
  #### Brand Kit Application

  The latest created Brand Kit is automatically selected and applied to your image, even if you don’t manually choose one.

  If only one Brand Kit exists, it is applied by default. If multiple kits are available, the most recently created one is auto-selected.
</Callout>

# Supported Channels

Image Creator supports the following channels:

- Push
- SMS
- Email
- Whatsapp
- Web channels
- Native Display
- App Inbox
- InApp

## Generate Image Using Prompt

Before you use Image Creator, ensure that your account's [Brand Kit](https://docs.clevertap.com/docs/brand-kit) is configured with your brand's visual identity (colors, logo, and imagery style), so generated images stay on-brand.

<Callout icon="📘" theme="info">
  ### Note

  The process differs slightly depending on the channel. The steps below use Push as the example. For channel-specific fields and behavior, refer to Supported Channels.&#x20;
</Callout>

To generate an image using prompts:

1. Open your **Push Notification** campaign editor.
2. For Android, click **![](https://files.readme.io/935fb6454c1119d8ecbbcb60baaa21dd7d7fbd62688f5c4fc3a5590b17a9c46e-Clever_AI_icon.png)CleverAI** for the _Expanded image_ or _Large icon_ fields. For iOS, click **![](https://files.readme.io/de594698e41f816505d7fb2148204b4ce6f2f581d952289e89b9d9022fe5015d-Clever_AI_icon.png)CleverAI** in the _Rich media_ field.


<Image src="https://files.readme.io/39436023d3464470ff80f91a5a23aca057f06a89fa3481ad0f3f32bc3f678a8c-2026-08-12_14-15-02.jpg" alt="AI Image Generator for Push Notification" align="center" caption="Image Creator for Push Notification" border={true} />


3. Click **Generate Image**. The _Generate Image_ window opens.


<Image src="https://files.readme.io/74f18fb31de8a3b4e279030917574e593e550c36050e1a63a373c4298c65dcb3-2026-08-12_14-12-49.jpg" align="center" caption="Generate Image" border={true} />


4. Apply a Brand Kit to ensure brand consistency, and customize the [Image Settings](https://docs.clevertap.com/docs/designer-agent#image-settings) to align with your campaign goals.
5. Describe the image you want in the prompt field at the bottom. For example, refer to the sample image below for an OTT platform to promote an upcoming Premier League football match:


<Image src="https://files.readme.io/8ceefe7bdab2ac89acbb678c4545e306b149170945e8257a959012ee8008458b-36f39a978330cfb65027a4ea70fe248e359d668dcfbef99f7303472a5ae48bc2-new_prompt.jpg" alt="Generate Image" align="center" caption="Image Generated Using Text to Image Option" border={true} />


6. Click **Generate**. Review the generated image, then click **Insert** to add it to your campaign.
7. After inserting the image, you can edit or refine the image directly within the editor:
   - Enter follow-up prompts in the same chat thread to refine the image.
   - To edit an existing image, go to the Message Editor, click **Upload**, and select the image. Click ![](https://files.readme.io/3dd08bfdc757b30950b16c701f01b8970b5ddec566c161e93cb3c1081ee73e60-Edit_icon.png) and describe the change you want to make (for example, Change CTA text from "Claim Now" to “Claim Fast”).&#x20;
   - Each refinement creates a new version saved in your Threads history, allowing you to revisit or reuse past iterations.


<Image src="https://files.readme.io/4a9e41575f33527ed58fe3c384553b65495b1feded65ba20df439f8a32c7ca69-2026-08-12_14-45-53_1.gif" alt="Edit Generated Image" align="center" caption="Edit Generated Image" border={true} />


<Callout icon="📘" theme="info">
  #### Why detailed prompts matter?

  The Image Creator relies on the clarity of your description to produce accurate, high-quality visuals. The more specific you are about theme, colors, layout, or mood, the better the output will align with your campaign goals. Include contextual details (like event name, offer type, or brand tone) for best results. For more information, refer [Generate On-Brand Images with Effective Prompts](https://docs.clevertap.com/docs/effective-prompts-for-ai-designer-agent).
</Callout>

## Generate Using Reference Image

To generate an image using a reference image, perform the following steps:

1. Open your Push Notification campaign editor.
2. Go to the Message Editor, click **Upload** to upload the image, and select the image. Click **Edit**.


<Image src="https://files.readme.io/5130f8ca30e871fa16f3600547fdd771a654e99ac31ae2f1217ee6116505045d-2026-08-12_14-51-56.jpg" alt="Edit Image" align="center" caption="Edit Image" border={true} />


3. Click ![](https://files.readme.io/7c39b5787600b7ac069bc4f2f78a6f3f0304bd3c3cc04eef082aa945c714fdf8-Plus_Icon.png) to select the reference image from CMS.


<Image src="https://files.readme.io/f66e3fc98940dc37ea9e2f7ae522d6bfa93e3519a6dd01987e5a17cd70a429f1-2026-08-12_14-12-49.jpg" align="center" caption="Add files" border={true} />


4. In the prompt field, describe the updates or new campaign details you want to apply.  Once you select an image, you can:
   - **Change text**: For example, update offer amounts, taglines, or call-to-action text.
   - **Change background**: Modify colors, replace backgrounds, or adjust contrast for seasonal themes.
   - **Replace visual elements**: Swap product photos, icons, or logos.
   - **Adjust layout**: Realign elements, add or remove visual sections, or reposition branding.
   - **Add highlights or effects**: Emphasize key offers or add simple visual effects, such as a glow or drop shadows. For example, if you want to use 30% Off banner as a reference and update it for Holi with bright color accents and festive treats.

5) Click **Brand Kit** to view or switch to another kit if needed.
6) Click **Generate**. It analyzes your reference image and applies the prompt instructions you provide. A new image is generated that maintains the layout and design consistency of your requirements.
7) Review the generated image and click **Insert** to add it to your campaign.

## Use Secondary Image to Update Primary Image

Upload an existing image as a reference. Clever.AI uses its layout, style, and color palette to create a fresh visual. You can use this method when you want to: refresh a past campaign creative, maintain a consistent look and feel across offers, and make quick adaptations for regional or seasonal variations.

This helps with the following:

- Retains brand tone and design balance.
- Reduces turnaround for variant creation.

To generate an image using this method, perform the following steps:

1. Open your Push Notification campaign editor.
2. For Android, click **![](https://files.readme.io/935fb6454c1119d8ecbbcb60baaa21dd7d7fbd62688f5c4fc3a5590b17a9c46e-Clever_AI_icon.png)CleverAI** for the _Expanded image_ or _Large icon_ fields. For iOS, click **![](https://files.readme.io/de594698e41f816505d7fb2148204b4ce6f2f581d952289e89b9d9022fe5015d-Clever_AI_icon.png)CleverAI** for the _Rich media_ field.
3. Click **Generate Image**. The Generate Image window opens.
4. Click ![](https://files.readme.io/7c39b5787600b7ac069bc4f2f78a6f3f0304bd3c3cc04eef082aa945c714fdf8-Plus_Icon.png) to upload the following.
   - Primary Image: The creative you want to update.
   - Secondary Image: The visual reference that defines your desired color tone, layout, or design.
5. In the prompt field, describe how you want to adapt or align the primary image to match the secondary one.


<Image src="https://files.readme.io/879aae0c5629396861b0d7d09d4684d616f8ca0ab45eac0938ddc2a6d5ab87b1-2025-11-23_17-21-52_1.gif" alt="Use Secondary Image to Update Primary Image" align="center" caption="Use Secondary Image to Update Primary Image" border={true} />


Refer to the following example prompt:

> Use the Christmas Sale banner as the primary image and the Diwali Sale banner as the secondary reference.<br />Match the Christmas image’s composition, color palette, and text placement to the Diwali banner’s warm, festive layout.<br />Replace the background gradient with rich gold tones, add warm lighting, and include subtle decorative elements like stars or ribbons.<br />Headline: “Celebrate the Season with Style”<br />Subheadline: “Up to 50% Off on Fashion & Accessories.”<br />CTA: “Shop Now” in a red or gold rounded button.

6. Click **Brand Kit** to apply your brand’s predefined colors, tones, and layout.
7. Click **Generate**. It analyzes both images and adjusts the primary to match the secondary in tone, layout, and design style.
8. Review the generated image in the preview panel and click **Insert** to add it to your campaign. To make refinements, use follow-up prompts.

# Brand Kit and Image Settings&#x20;

Image Creator gives you the options to adjust and filter your generated image. The Image Settings menu lets you adjust your file format, and Brand Kit lets you apply brand styling to your generated image.&#x20;


<Image src="https://files.readme.io/736883e6e97d997c34b45127d0a8d351498cd7783d7a2c7319e8a410be12b83f-2026-08-12_14-12-49.jpg" align="center" caption="Filters and Brand Kit" border={true} />


## Brand Kit

Click on Brand Kit to view your brand’s style, button colors, brand colors, and so on, for your image. Click **Apply to this Thread**. You can also select other kits or configure a custom kit for the current image. The applied Brand Kit ensures that all generated visuals remain consistent with your brand identity.


<Image src="https://files.readme.io/5e1e525eaf13bb6e9af34630d47fea6b0be2c1e30232ed6b2d07bf5b325b2648-2026-08-12_14-26-21.jpg" align="center" caption="Brand Kits" border={true} />


<Callout icon="📘" theme="info">
  #### **Note**

  - Locked kits cannot be edited within the campaign flow.
  - Any changes made to BrandKit through campaign flow only apply to the **current thread**.
  - If a prompt conflicts with Brand Kit settings (for example, brand colors or tone), the AI automatically follows the Brand Kit settings to maintain consistency.
</Callout>

For more information on setting up and using brand kits, refer to <Anchor target="_blank" href="https://docs.clevertap.com/docs/brand-kit">Brand Kit</Anchor>.

## Image Settings

Click ![](https://files.readme.io/bdbfd957c9ccc6dff7284d71450e4414281705ac5d8337c238198a6d7cc896ee-Image_Settings_Icon.png) to open Image Settings. Here, you can:

- Select the _File format_ between JPEG or PNG.
- View the Aspect ratio and size, which are auto-selected and non-editable. The aspect ratio and size are automatically aligned with Push OS specifications (for example, 1:1 for Large Icon and 3:2 for Expanded Image) to ensure compatibility.


<Image src="https://files.readme.io/99abaabfa308ea1d21c6d938ce819e61db6f0995d9f8faa2b1edb846ef221058-2026-08-12_14-24-38.jpg" alt="Image Studio" align="center" caption="Image Settings" border={true} />


# Manage Generated Images

All AI-generated images can be accessed via [Threads](https://docs.clevertap.com/docs/designer-agent#threads) and [AI Images Folder](https://docs.clevertap.com/docs/designer-agent#ai-images-folder).

## Threads

Once you start generating images, CleverTap automatically saves your sessions under the Threads ![](https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png) tab. Each session is stored as a thread, which captures your prompts, refinements, and generated outputs, helping you resume from where you left off without losing context.


<Image src="https://files.readme.io/664b73f20a3b9b2baab4fcf6abb38fe00bbb212239b5eced4a6913079bea77a1-2026-08-12_14-27-35.jpg" alt="All Threads" align="center" caption="All Threads" border={true} />


### How Threads Work

Threads are scoped to your **Account**, **Agent**, and **User**, ensuring that your history remains personalized and relevant. All threads for your account appear in the **All Threads** popup. A thread becomes the context for your next generation, allowing Clever.AI to remember your prior visual style, brand preferences, or edits. They are not tied to specific campaigns; they persist across multiple campaigns for seamless continuity.

If multiple users from the same account use AI tools:

- Each user sees only their own threads and the latest image generation session that they have participated in.
- Threads are separate for Segmentation, Analytics, Image Creator, and Scribe, even under the same account.

### Manage Threads

From the **All Threads** view, you can:

- Reopen an older thread to continue generating or editing images using the same context.
- Review and compare multiple image versions created during that session.
- Restore or reuse previously generated images without regenerating them.

<Callout icon="💡" theme="default">
  ### **Tip**

  For subsequent edits, you need not restart a session. You can type your next instruction directly in the chat. For example: _“Make the background blue and add a 50% OFF badge in the corner.”_ The AI will update the existing image while maintaining your brand styling and earlier visual tone.
</Callout>

## AI Images Folder

All AI-generated images are automatically stored in your _CMS_, under the **AI Images** folder for your account. This allows you to reuse, manage, or download previously created visuals without needing to regenerate them.


<Image src="https://files.readme.io/e11b078ebf2be9b89f11911847723625a7f51dc11bb2c7f37600a4ba7499ee22-2026-02-12_14-07-06.png" alt="AI Generated Images Folder" align="center" caption="AI Images Folder" border={true} />


<Callout icon="📘" theme="info">
  #### **Note**

  The AI Images folder is system-managed and cannot be renamed, moved, or deleted. Images stored in this folder can be download and reused in campaigns, but cannot be renamed or moved to a different folder.
</Callout>

# Best Practices for Writing Prompts

The following best practices will help you with writing more detailed prompts:

- Be **specific** and include theme, tone, and visual intent.<br />_Example: “Create a modern app promo banner with minimalist icons.”_
- Add **context**; specify what the image is for (for example, offer, product launch, festival).
- Use your **brand kit** for visual alignment.
- Don’t write one-liners. A prompt like “banner” or “sale” gives the AI too little to work with — resulting in generic, off-brand images.
- Describe the scene, emotion, and layout you want to see.<br />_Example: “Create a 1:1 In-App image for a festive Diwali campaign with maroon and gold tones, decorative lamps, and a bold ‘Shop Now’ button in brand colors.”_
- Review and refine your prompt if the output doesn’t match your intent.

The Image Creator relies on the clarity of your description to produce accurate, high-quality visuals. The more specific you are about theme, colors, layout, and mood, the better the output aligns with your campaign goals.

For more information, refer to [Generate On-Brand Images with Effective Prompts](https://docs.clevertap.com/docs/effective-prompts-for-ai-designer-agent).

<Callout icon="📘" theme="info">
  #### **Image Generation Limit**

  AI image generation is capped at 100 images per account per month. The quota refreshes monthly and applies across all users within the account. Once the limit is reached, image generation will be disabled until the next reset.&#x20;

  To increase the cap for image generation after limit is reached, contact your Customer Success Manager.
</Callout>

# Additional Resources

For more information, refer to the following resources:

- [Generate On-Brand Images with Effective Prompts](https://docs.clevertap.com/docs/effective-prompts-for-ai-designer-agent)
- [Brand Kit](https://docs.clevertap.com/docs/brand-kit)
- [Image Creator: FAQs](doc:faqs-4)
- [CleverTap Terms & Disclaimer](doc:clevertap-aienabled-feature-disclaimer-terms)&#x20;
