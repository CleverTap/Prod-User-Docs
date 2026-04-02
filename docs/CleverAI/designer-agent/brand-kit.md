---
title: Brand Kit
excerpt: Learn how to set up a consolidated Brand Kit in AI Designer Agent.
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

The **Brand Kit** helps ensure consistency across all generated assets, including copy and creative, and serves as a brand governance framework that defines your brand logos, colors, tone, and buttons. Once configured, these settings are automatically applied across AI tools (Designer and Copywriter agents), ensuring a unified branding experience in every campaign.

> 📘 Private Beta
>
> Currently, this feature is released in Private Beta. If you want to access this feature, contact your Customer Success Manager.

The following are the benefits of using a Brand Kit for your assets:

* Ensures automatic application of brand-specific colors, typography, and styles, maintaining a consistent look and feel across all content and visuals.
* Reduces back-and-forth during reviews by enforcing brand rules upfront, ensuring faster approvals and on-brand creative output.
* Scales campaign creation across regions and teams without diluting brand identity.
* Smarter content reuse with Campaign Lookback (for content only), enabling the AI to learn from past campaign tone and messaging patterns.
* Reduced dependency on the Copy and Design teams, enabling faster campaign iterations.

# Accessing Brand Kit

You can access and manage Brand Kits from the Content Manager section of your account. Only users with CMS Brand Kit access can view or edit Brand Kits. Brand Kit permissions are managed through CMS Role-Based Access Control (RBAC) as follows:

| Role Type                                              | Default Access | Description                                                                                                    |
| ------------------------------------------------------ | -------------- | -------------------------------------------------------------------------------------------------------------- |
| Admin                                                  | Read and Write | Full control to create, edit, clone, or delete Brand Kits. Changes apply across all AI tools once published.   |
| System Roles (for example, Admin, Marketing Manager)   | Read-only      | Can view Brand Kits but cannot edit or create new ones.                                                        |
| Custom Roles (for example, Content Executive, Analyst) | Configurable   | Access can be customized based on organizational needs. Admins can enable or restrict Create/Edit permissions. |

## Brand Kit Access in Teams

Teams is a separate feature currently available in Private Beta. Team-based Brand Kit access is visible only to accounts where Teams is enabled. When **Teams** is not enabled, all users in the account can view every available Brand Kit. For more information on how Teams works, refer to [Teams Setup](https://docs.clevertap.com/docs/teams-setup).

Refer to the following table for more details:

| **Scenario**                      | **Brand Kits Available** | **Description**                                                                                                                                                                            |
| --------------------------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Team A user**                   | 4 kits                   | Team A has 1 team-specific Brand Kit and there are 3 Brand Kits with all Teams access. The user sees all 4 brand kits.                                                                     |
| **Team B user**                   | 4 kits                   | Team B has 1 team-specific Brand Kit and there are 3 Brand Kits with all Teams access. The user sees all 4 brand kits.                                                                     |
| **Admin (logged in with Team A)** | 4 kits                   | Admins see Brand Kits assigned to the team they’re logged in with (Team A) plus all kits with all Teams access. To view kits assigned to another team, the admin must switch to that team. |

<Callout icon="📘" theme="info">
  **Brand Kit Precedence**

  When generating or editing images or content, the selected Brand Kit always takes precedence over text prompts. If a prompt conflicts with the Brand Kit’s settings (for example, color codes, or tone), AI prioritizes the Brand Kit.

  For example, if your Brand Kit specifies that the phrase “Risk-free” should not be used, even if a user includes it in the prompt, the AI will automatically avoid it in the generated output. This ensures all generated assets stay on-brand and aligned with your company’s approved guidelines.
</Callout>

# Create Brand Kit

Admins and content team members who have access to Brand Kit define elements such as logos, brand colors, button styles, and content guidelines to ensure that every AI-generated asset aligns with your brand identity.

To create a new Brand Kit, perform the following steps:

1. Go to _Content Manager_ > _Brand Kit_ and click **Add Brand Kit**.

<Image align="center" alt="Add Brand Kit" border={true} caption="Add Brand Kit" src="https://files.readme.io/ff5a845b1c5609c09b13c0208e9c02c23ba4279706f9364e99f3915a9471763b-Screenshot_2025-12-03_at_1.12.58PM.png" />

2. Enter the brand details such as _Setup, Content Guidelines, and Image Guidelines_ and click **Create**.

<Image align="center" alt="Create Brand Kit" border={true} caption="Enter Brand Kit Details" src="https://files.readme.io/548eaa09b6a7d5a205a8c05c4ece1c0231da09853628eabe8baae985c62757b9-image.png" width="65% " />

Enter the following Brand Kit details:

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Field
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Description
      </th>

      <th>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **Name**
      </td>

      <td>
        Required
      </td>

      <td>
        The display name for the Brand Kit. It must start with a letter. Supports letters, numbers, underscores, hyphens, parentheses, and spaces (limit: 150 characters).
      </td>

      <td>
        Character Limit: 150
      </td>
    </tr>

    <tr>
      <td>
        **Lock Brand Kit**
      </td>

      <td>
        Optional
      </td>

      <td>
        When enabled, this prevents users from editing brand settings when creating a campaign. Locking ensures brand consistency across global teams and eliminates off-brand variations.
      </td>

      <td>
        * If you want to prevent users from overriding brand settings, you can lock the Brand Kit.
        * When prompts include details that conflict with your Brand Kit, the AI will give precedence to the Brand Kit settings.
        * Only users with Brand Kit access can unlock or update a locked kit.
      </td>
    </tr>

    <tr>
      <td>
        **Campaign Lookback**
      </td>

      <td>
        Optional
      </td>

      <td>
        Determines how far back the AI can reference past campaigns to maintain tone, language, and visual consistency.
      </td>

      <td>
        Options: 3 Months, 6 Months (default), or 1 Year.
      </td>
    </tr>

    <tr>
      <td>
        **Creativity Level**
      </td>

      <td>
        Optional
      </td>

      <td>
        Controls the level of reliance on past campaign references versus creative freshness in AI-generated output. Set it _High_ for more creative experimentation, or _Low_ for outputs that stay tightly within your Brand Kit.
      </td>

      <td>
        * **Low**: Stays very close to your past campaigns.
        * **Medium**: Allows small creative tweaks to add variety.
        * **High**: Provides the AI with the freedom to explore various tones and visuals.
      </td>
    </tr>

    <tr>
      <td>
        **Tone (Brand Tonality)**
      </td>

      <td>
        Optional
      </td>

      <td>
        Defines tone and voice for AI-generated content. Allows multiple tone selections.
      </td>

      <td>
        Up to 3 tones can be selected (for example, Friendly, Professional, Confident).
      </td>
    </tr>

    <tr>
      <td>
        **Instructions (Content Guidelines)**
      </td>

      <td>
        Optional
      </td>

      <td>
        Provides writing and language guidance for AI-generated text.
      </td>

      <td>
        Content and Image Guidelines each have a 500-character limit.

        **Example**: “Use active voice, prefer ‘affordable’ over ‘cheap,’ avoid gendered or racial terms.”
      </td>
    </tr>

    <tr>
      <td>
        **Brand Logos**
      </td>

      <td>
        Optional
      </td>

      <td>
        Add up to 3 logo variations to maintain consistent visual branding.
      </td>

      <td>
        * You can select a file from the **Content Manager**. You can also add images to the content manager from the device storage.
        * **Supported file types**: `.png`, `.jpeg`, `.jpg`, `.pdf` (Max size: 2 MB per file).
      </td>
    </tr>

    <tr>
      <td>
        **Brand Colors**
      </td>

      <td>
        Optional
      </td>

      <td>
        Define up to 5 primary brand colors.
      </td>

      <td>
        Default: White (#FFFFFF). Used as base colors for visuals.
      </td>
    </tr>

    <tr>
      <td>
        **Button Colors**
      </td>

      <td>
        Optional
      </td>

      <td>
        Add up to 3 button colors used in AI-generated creatives.
      </td>

      <td>
        * Default: Black (#000000).
        * Used for CTAs or highlights in campaign visuals.
      </td>
    </tr>

    <tr>
      <td>
        **Instructions (Image Guidelines)**
      </td>

      <td>
        Optional
      </td>

      <td>
        Defines guidance for how visuals should represent the brand.
      </td>

      <td>
        **Example**: “Use minimal design, clean layouts, and product-first focus. Avoid excessive gradients or heavy shadows.”
      </td>
    </tr>
  </tbody>
</Table>

<Callout icon="📘" theme="info">
  **Note**

  * Maximum **10 Brand Kits** can be configured per account.
  * Each Brand Kit is stored at the **account level** and applies across all AI generated content once enabled.
  * Any updates made to a Brand Kit apply automatically across AI Copywriter and Designer Agent once published.
  * Create separate Brand Kits for each brand, region, or business unit. Use clear, meaningful names to help teams quickly identify the right kit when creating campaigns, for example, InstantMart, Insurance, or Ticket Booking.
</Callout>

# Manage Brand Kits

From the **Brand Kit** page, you can:

* View all existing Brand Kits in a list or grid view.
* Edit, rename, or delete kits.
* Duplicate an existing kit to create a variant.

## Edit Brand Kit

To edit an existing Brand Kit, perform the following steps:

1. Click ![](https://files.readme.io/213881709f49a2867e2c7698fc0b3ecf1f750323d98d98a4431a8425b1413af7-ellipses_icon.png) icon and select _Edit_.

<Image align="center" alt="Edit Brand Kit" border={true} caption="Edit Brand Kit Details" src="https://files.readme.io/111ba1fbe586d322e7c3d314792991e6aecfec6f837694d1d0a543b1057f0628-Edit_Brand_Kit.png" width="80% " />

2. Modify the required details and click **Save**.

<Image align="center" alt="Edit Setup" border={true} caption="Edit Brand Kit" src="https://files.readme.io/92e5631734e738d49ea5da226e1ef5da88c46e55c592ec8258f1ca17eb6540f7-image.png" width="65% " />

# Best Practices for Defining Brand Kit Guidelines

Use the Instructions field to clearly express what your brand stands for and how your content should feel. These guidelines enable the AI to select the appropriate tone, wording, and visual direction for all generated content.

Follow these best practices listed below when defining your Brand Kit guidelines:

* Define your brand’s tone and communication style. Describe how your brand should sound and feel (for example, trustworthy, conversational, premium, inspiring, and so on). This helps the AI maintain consistent tonality across all content and imagery.
* Add clear instructions for copy and image generation. The more details you provide, the more accurately the AI can generate brand-aligned content and images.
* Clarify visual intent for images, such as mood, color direction, and overall feel (for example, clean, modern, high-contrast).
* Note any boundaries or must-avoid areas, including regulatory or compliance requirements.

## Sample Instructions

These are example instruction sets you can pre-fill in the Instructions field under _Content Guidelines_ and _Image Guidelines_ in the Brand Kit. This helps AI understand the preferred tone, style, and visual direction of the brand.

| Industry                         | Content Guidelines                                                                                                                                                                    | Image Guidelines                                                                                                                                                           |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Consumer / Retail**            | “Use an active, conversational tone. Highlight benefits and promotions in clear, positive language. Avoid jargon and overpromising. Keep copy brief and easy to scan."                | “Use bright, engaging visuals with product focus. Maintain natural lighting and clean composition. Avoid overly dark or text-heavy designs.”                               |
| **Financial Services / Banking** | “Maintain a professional, confident tone. Use factual, non-exaggerated statements. Avoid words like ‘guaranteed’ or ‘risk-free.’ Ensure all messaging meets regulatory requirements.” | “Use trustworthy, calm visuals — clean design, corporate colors, and professional imagery. Avoid any visuals that may misrepresent returns, outcomes, or endorsements.”    |
| **Healthcare / Pharma**          | “Write in an empathetic, factual tone. Avoid making clinical claims or outcome promises. Ensure all messaging aligns with approved regulatory language.”                              | “Use clean, minimal visuals that focus on care and trust. Avoid imagery suggesting medical results or diagnoses. Prefer healthcare professionals and real people imagery.” |
| **Technology / SaaS / B2B**      | “Maintain a clear, formal tone. Use precise and informative statements that highlight value and reliability. Avoid hyperbolic or casual expressions.”                                 | “Use minimal, professional visuals with abstract or product-based graphics. Keep color palette brand-aligned and consistent. Avoid unlicensed or stock-heavy visuals.”     |
| **Food & Beverage**              | “Use friendly, appetizing language that highlights taste and quality. Avoid unrealistic or exaggerated claims like ‘best ever.’”                                                      | “Use warm, natural lighting and authentic food photography. Keep focus on product quality and freshness. Avoid overly edited or artificial looks.”                         |
| **Gaming / Entertainment**       | “Use an energetic, motivational tone. Highlight rewards or events with excitement, but avoid misleading outcome statements.”                                                          | “Use vibrant, high-contrast visuals with bold elements. Maintain consistent color palettes and avoid off-brand effects.”                                                   |

# FAQs

### Can I edit or clone a Brand Kit later?

Yes. If you have access to edit the Brand Kit, then you can edit all fields or clone a kit to create a new variant with similar settings.

### How many Brand Kits can I create?

You can create up to **10 Brand Kits** per account.

### Can I assign a Brand Kit to multiple teams?

Yes. You can assign it to a single team or make it Global, so all teams can use it. Teams feature is in Private Beta. For more information, refer to Teams.

### What happens if I lock a Brand Kit?

Locking a Brand Kit prevents users from editing or overriding its settings during campaign creation or image generation flow. When unlocked, users can make temporary, campaign-level edits (like adjusting colors or buttons). These changes apply only to that campaign and do not modify the Brand Kit itself. Whether locked or unlocked, Brand Kit settings always take precedence over prompt inputs or AI variations.

### What happens if I try to create something outside the Brand Kit settings?

If a Brand Kit is active, the AI automatically enforces its rules to maintain consistency. If your prompt or request conflicts with Brand Kit specifications (such as using a different color, font, or tone), the AI will prioritize the Brand Kit settings and adjust the output accordingly.
