---
title: Content Blocks - Standardize Messaging
excerpt: Learn how to reuse content and standardize your messaging with content blocks.
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

A Content Block is a reusable part of content that can be used across different campaigns. It helps maintain a consistent experience for users as they view a consistent branding tone and colors across your messaging. This messaging can include text, images, or calls to action (CTAs) buttons that you can standardize across messages. Using standard messaging, marketers can maintain a clear tone and style, building trust and consistency in brand communications.

> 📘 Public Beta
>
> This feature is currently a Public Beta Release. If you want access to it, contact your CSM.

Content Blocks also allow marketers to reuse the same content for different campaigns, saving time and effort while matching the brand’s identity. For example, a Content Block can serve as a footer with clickable social media icons for users to follow the brand. Marketers can easily add or remove social media links as needed in a footer, making this change dynamically effective across all campaigns that use this Content Block. For example, if you are a travel app sending messages to users, an update to an email footer about an updated Instagram account can be repeated across footers sent in other campaigns.`

> 📘 Supported Channels
>
> Currently, you can use a content block for [Email campaigns](doc:create-message-email) only. However, only Text Contet Block is supported for [AMP for Email](https://docs.clevertap.com/docs/ampforemail). You can stay tuned to our [Release Notes](https://docs.clevertap.com/docs/whats-new)   and [Changelog](https://developer.clevertap.com/docs/changelog)  about frequent updates and enhancements.

<Image align="center" alt="Standardization with Content Blocks" border={true} caption="Footer Standardization with Content Blocks" src="https://files.readme.io/89622623ff70128b43826e2e2c67459119524f19f1a5bd1f1aef4b07c678d388-image.png" />

# Content Blocks Video Tutorial

Discover the video tutorial for an overview of Content Blocks and a sample use case.

<HTMLBlock>{`
<div style=" position: relative; padding-bottom: 56.25%; height: 0; border-radius: 0; box-shadow: 0 15px 40px rgba(63,58,79,.3); overflow: hidden; min-width:320px"><iframe src="https://clevertap.portal.trainn.co/share/l1E6i5tkUnKL9L5ZGfgQPQ/embed?autoplay=false" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen allow="autoplay; fullscreen" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Content Block Types

There are two types of content blocks:

* Text Content Block - Simple text-based messages mainly to communicate information, updates and so on.
* HTML Content Block -  Engaging, dynamic messages to upsell and quickly engage the users.

You can select a content block based on your messaging requirements, whether you want to send a plain text message or an engaging, colorful message.

## Text Content Block

This is a Text-based Content Block you can reuse for your messaging requirements. It is useful when you want to create a message quickly. The [Inline personalization](https://docs.clevertap.com/docs/personalize-message-all#inline-personalization) includes only profile personalization.

> 📘 Text Block Specifications
>
> Currently, we support up to 500 characters in a content block.

Here is a sample of a personalized Text Content Block that encourages the user to upgrade the plan for an OTT app. The [Conditional Tags](doc:liquid-tags#conditional-tags) help deliver the message based on the current subscription plan of the user:

<Image align="center" alt="Sample Text Content Block" border={true} caption="Sample Content Block - Text" src="https://files.readme.io/42281df9b000b3b1bc70ec90ad727c7cce69bf65cb887f408478cc9e519b430a-image.png" />

## HTML Content Block

The HTML Content Block allows you to create visually appealing and dynamic messages, allowing you to import and paste your HTML code. The HTML code helps design and customize your message’s layout, style, and interactivity, helping you deliver a more engaging experience for your audience.

Here is a sample HTML Content Block that nudges the user to upgrade the plan for an OTT app. The [Conditional Tags](doc:liquid-tags#conditional-tags) help deliver the message based on the current subscription plan of the user:

<Image align="center" alt="Sample HTML Content Block" border={true} caption="Sample Content Block -  HTML" src="https://files.readme.io/c94ed28109426e3a91754c428c8b474d8e24cb16ed4ad6894fdf156694e645db-image.png" />

# Create Content Blocks

You can create Content Blocks from the CleverTap Dashboard.

> 📘 Content Blocks Via API
>
> You can also create and manage your Content Blocks via the CleverTap [Content Blocks API](https://developer.clevertap.com/docs/content-blocks-api) when you want to update or create Content Blocks at scale.

Follow the steps to create a content block:

1. Go to _Content Manager_ > _Content Blocks_.

<Image align="center" alt="Create a Content Block" border={true} caption="Create a Content Block" src="https://files.readme.io/a9f13e16ffcf9b9f8561cc02a6a5744fb167a2be2704c902b6b29a4ea98c6292-image.png" />

2. Click **New** and select the type of _Content Block_ [Content Block](doc:content-blocks#content-block-types).
3. Select the type of Content Block, that is, Text or HTML.

<Image align="center" alt="Content Block Editor" border={true} caption="Content Block Editor" src="https://files.readme.io/a94c81ea360432f27cbdaafe8bd37214d191265536bc33cca545d3ece87e433a-image.png" />

3. From the editor, click **\{\{}}**  to use [inline personalization](https://docs.clevertap.com/docs/personalize-message-all#inline-personalization) and [Conditional Tags](https://docs.clevertap.com/docs/liquid-tags) to personalize the _Content Block_.
4. Click **Preview** to preview the content block.

<Image align="center" alt="Preview content block" border={true} caption="Preview Content Block" src="https://files.readme.io/d4862eae25783ab2d1facd6210a58e93c59bed9a9f2c8cc864681ff955e80b85-image.png" />

4. Click **Save** to save your _Content Block_.
5. Enter a name for your Content Block.

> 📘 Content Block Name
>
> Content Block names can include letters, numbers (0-9), underscores (_), periods (.), hyphens (-), and spaces. The name must begin with a letter. Additionally, the Content Block name must be unique.

4. From the list of labels, select the appropriate labels to organize and identify your content block.
5. Click **Done**.

## Preview Content Block

You can preview the Content Blocks from the Content Blocks page or during the Content Block creation process.

To preview a content block:

1. Go to _Content Manager_ > _Content Blocks_.
2. Select a Content Block and double-click to preview it.

The content block displays information such as name, label, and so on.

<Image align="center" alt="Content Block Preview" border={true} caption="Content Block Preview" src="https://files.readme.io/9b4a67b0830157d3afc2ac1c06ff6067005ae32c7642cdba3a9d2a7f312428ed-image.png" />

# Use Content Block (in a campaign)

Currently, you can use a content block only in [Email campaigns](doc:create-message-email) to standardize and reuse content in email messaging. Follow these steps to use a content block:

1. From the dashboard, select _Campaigns_.
2. Click **+ Campaign**.
3. From the _Messaging Channels_ list, select the Email messaging channel—the Campaign page displays.
4. From the _What_ section on the Campaign page, select the message type and click **Go To Editor**.
5. Select any template from the _Basic Templates_ tab.
6. In the editor, enter _\{\{_  to add the content block.  Select the content block from the list.

<Image align="center" alt="Add a Content Block" border={true} caption="Add a Content Block" src="https://files.readme.io/00b42b58ae892077e4ed213d986414a5d21c8658542e9e833b968f88ead7647d-image.png" />

7. Continue with the campaign creation flow.

## Personalization in Liquid Tags

When creating a campaign, you can further personalize content using content blocks with the help of Liquid Tag personalization. For example, you can email users tempting offers based on their food preferences. Using Liquid Tags, you can add multiple Content Blocks for each cuisine to ensure that end users receive the relevant menu options and images in their emails. Follow these steps to add liquid tags to content blocks:

1. Select the message type from the _What_ section on the Campaign page and click **Go To Editor**.
2. Select any _drag and drop_ template from the _Basic Templates_ tab.
3. Drag and drop a text block and double-click it to display the formatting options:
4. Select _Customize with Liquid tags_ from the _More_ list in the toolbar.

<Image align="center" alt="Customize Text Block with Liquid Tags" border={true} caption="Customize Text Block Liquid Tags" src="https://files.readme.io/46c8e6115ee531ecb87300772d00a449df8712559463a73cb4f2456165bbf202-image.png" />

5. Click the **\{\{}}** icon and select the required _Content Blocks_.

<Image align="center" alt="Personalization list with {{}}" border={true} caption="Personalization list with \{\{}}" src="https://files.readme.io/c3de482967c79bbe16b5123abf33a246e77b8d3b32349f5e8fa886d16946d49b-image.png" />

> 📘 Enhance Personalization
>
> You can combine Content Blocks with additional personalization options provided by Clevertap. Click the **\{\{}}** icon to explore more personalization for your messaging.

6. Add conditions based on your requirements using Liquid Tags.

<Image align="center" alt="Add multiple content blocks with liquid tags" border={true} caption="Add Multiple Content Blocks with Liquid Tags" src="https://files.readme.io/0376c188ca78af9d7ea171932f960b4361d46607711b1836d41cced236870896-image.png" />

7. After adding the content, click **Add** to add the Content Block.

Preview the message and verify the content before sending it. The content will be displayed.

<Image align="center" alt="Content Block Display in Email" border={true} caption="Content Block Rendered" src="https://files.readme.io/937f04c2ee11a2238cc5fae846461244065adf25f06628cfc2f4d78577d786b0-image.png" />

# Content Block Considerations

Check for the following considerations to optimally use Content Blocks in your messaging campaigns.

## Content Block Specification

Before proceeding with creating content blocks, it is advisable carefully to review the specifications and considerations.

| Content Block Element | Specification                                                                                                                                                                            |
| :-------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name/Rename           | Names can include letters, numbers (0-9), underscores (_), periods (.), hyphens (-), and spaces. The name must begin with a letter. Additionally, the content block name must be unique. |
| Content Size          | Maximum of 50kB (kilobyte) for HTML Content Block. Up to 500 characters for Text Content Block.                                                                                          |
| Supported Channels    | Content Blocks can currently be used only in the email channel.                                                                                                                          |
| Deletion              | Deleting content blocks is currently not supported.                                                                                                                                      |

## Content Block Operations

You can edit, rename, and label the Content Blocks from the Content Block card. Follow these steps to manage the content blocks:

1. Go to _Content Manager_ > _Content Blocks_.
2. Click the **Content Block card** to perform various operations.

<Image align="center" alt="Content Block Operations" border={true} caption="Content Block Operations" src="https://files.readme.io/31c51346a270c91bd031646d40244881b4ba45b6f1db097b431bf0454747bdd2-image.png" />

3. Select from the following options:

* _Edit_: Select to edit the content block.
* _Rename_: Select to rename the folder.
* _Label_: Select to apply a label to the content block. It will help further identify or search the Content Block.

## Supported Personalization

Before using Content Blocks, refer to these essential guidelines for supported personalization. These help you understand which personalization types are supported and how to use them effectively in your campaigns.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Personalization Type
      </th>

      <th>
        Supported  
        (Yes/No)
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Inline Personalization
      </td>

      <td>
        Yes
      </td>

      <td>
        You can use profile attributes.
      </td>
    </tr>

    <tr>
      <td>
        Conditional Tags
      </td>

      <td>
        Yes
      </td>

      <td>
        You can create a _write once use multiple times_ message by adding conditional variations based on user attributes or behavior. For more information, refer to <Anchor label="Liquid Tags" target="_blank" href="doc:liquid-tags">Liquid Tags</Anchor>.
      </td>
    </tr>

    <tr>
      <td>
        Event
      </td>

      <td>
        Yes
      </td>

      <td>
        You can add event personalization tags.
        **Note**: Event Personalization for Content Blocks is currently in **Private Beta**.
      </td>
    </tr>

    <tr>
      <td>
        Reminders
      </td>

      <td>
        Yes
      </td>

      <td>
        You can add reminder personalization tags.  
        **Note**: Reminder personalization for Content Blocks is currently in **Private Beta**.
      </td>
    </tr>

    <tr>
      <td>
        Campaign
      </td>

      <td>
        Yes
      </td>

      <td>
        You can use campaign-level personalization attributes in Content Blocks.
      </td>
    </tr>

    <tr>
      <td>
        Linked Content
      </td>

      <td>
        No
      </td>

      <td>
        * <br />
      </td>
    </tr>

    <tr>
      <td>
        Catalog Send-Time
      </td>

      <td>
        No
      </td>

      <td>
        * <br />
      </td>
    </tr>
  </tbody>
</Table>

### Personalize Content Blocks Using Event Personalization

You can use event-based personalization in Content Blocks across campaigns and journeys. Event tags resolve automatically based on the associated user event data.

To add event-based personalization in an email Content Block, perform the following steps:

1. Open the Content Block you want to edit (HTML or Text).
2. Type the event tag, ensuring the correct syntax is used.
3. Preview or test send to verify the tag.
4. Publish the campaign.

<Image align="center" border={true} caption="Event Personalization" src="https://files.readme.io/b5269510850372301c8a54f43c746a3464a6093c259c135698f05afe59ffe5d0-2026-01-02_15-28-44_1.gif" />

### Syntax

Tags must be typed exactly as required. Use the following format to insert event-based values:

```liquid
{{Event[“CT Source“] | default:”default”}}
{{Event.experiment | default:”default”}} 
```

CleverTap validates that the Content Block’s event matches the event used in the campaign's trigger criteria (Who section). Any mismatches are automatically blocked during campaign publishing.

### Example

You want to personalize the campaign based on the series they have previously watched. In this case, you can use both profile and event-based personalization.

```text Sample Campaign Message
Hello {{ Profile.name | default: "User" }},
You watched {{ Event.SeriesName | default: "your favorite series" }}
```

If either property is missing for the user in the CleverTap dashboard, the default values are rendered. This ensures the message displays correctly and does not disrupt personalization. The following is the rendered output if defaults are used:

```Text Output with Default Values
Hello User,  
You watched your favorite series
```

### Personalize Content Blocks Using Reminder Personalization

To add reminder-based personalization in a Content Block:

1. Create or open a Content Block (HTML or Text).
2. Add reminder personalization tags, ensuring the correct syntax is used.
3. Save the Content Block once validation passes.
4. Insert the Content Block into a reminder campaign. For more information, refer to <Anchor label="Create Campaign using Reminders" target="_blank" href="https://docs.clevertap.com/docs/reminders#create-campaign-using-reminders">Create Campaign using Reminders</Anchor>.
5. Publish the campaign.

<Image align="center" border={true} caption="Reminder Personalization" src="https://files.readme.io/bcd06fb0a69e340306c0833f956a4d844e36b723b39a600ff5ee7c9b56e8896e-2026-01-02_15-25-00_1.gif" />

### Syntax

Tags must be typed exactly as required. Use the following format to insert reminder-based values:

```liquid
{{ Reminder.<reminder_entity>.<property_name> | default: "<fallback_value>" }}
```

### Example

You want to remind users about an upcoming flight booking. Use a Content Block to personalize the reminder message with reminder-specific properties such as the booking date and seat number.

If a reminder property is unavailable for a user, the default value is used so the reminder message renders correctly.

```html Sample Reminder Message
Your flight is scheduled on {{ Reminder.flight_booking.date | default: "your upcoming travel date" }}.
Seat number: {{ Reminder.flight_booking.seat_number | default: "to be assigned" }}
```

The following is the rendered output if defaults are used:

```Text Output with Default Values
Your flight is scheduled on your upcoming travel date.
Seat number: to be assigned
```

<Callout icon="⚠️" theme="warn">
  #### Note

  * **Event matching**:
    * Check that the event used for personalization in the Content Block is the same as the event selected in the trigger criteria of the event-triggered campaign.
    * A Content Block can be used in a reminder campaign only if the reminder entity in the block matches the reminder entity selected in the campaign.
  * **No mixed personalization**: Reminder (`Reminder.*`) and event (`Event.*`) tags cannot be used in the same Content Block.
  * **Single reminder entity**: A Content Block can reference only one reminder entity. For example, `Reminder.flight_booking` and `Reminder.hotel_booking` cannot be used together in the same block.
  * **Nested blocks**:
    * For event personalization, the event used in a nested Content Block must be the same as the event in the parent Content Block. For example, if `App Launched` is used in the parent block, it must also be used in the nested block.
    * For reminder personalization, both the parent and nested Content Blocks must reference the same reminder entity. For example, if the parent block uses `Reminder.flight_booking`, the nested child block must also use `Reminder.flight_booking` (for example, `Reminder.flight_booking.seat_number`). Blocks with different reminder entities cannot be nested.
  * **Validation:**
    * While typing in the email editor, only compatible Content Blocks appear in the dropdown:
      * Blocks with matching event personalization
      * Blocks without personalization
    * In reminder campaigns, the dropdown shows:
      * Blocks with matching reminder personalization
      * Blocks without personalization
        Blocks with event personalization or a different reminder entity are hidden.
</Callout>

# Use Cases for Content Block

Content Blocks can be used in various ways to enhance communication across campaigns. From displaying personalized offers to embedding interactive elements such as forms or buttons, these versatile blocks ensure your messages are engaging and consistent. The following are some use cases where Content Blocks can effectively streamline your marketing efforts.

## Multi-Language Support

Here is a simple example of personalization with a liquid tag for multi-language support. An OTT app offers subscription or membership plans tailored to the user's region and displayed in their preferred language.

```liquid Content Block using Liqud Tags

{% if Profile.PREFERED_LANGUAGE == "Spanish" %}
  Elige tu plan: Plan Básico por €5/mes o Plan Premium por €15/mes.
{% elsif Profile.PREFERED_LANGUAGE == "Italian" %}
  Scegli il tuo piano: Piano Base per €5/mese o Piano Premium per €15/mese.
{% else %}
  Choose your plan: Basic Plan for $5/month or Premium Plan for $15/month.
{% endif %}

```

If the user's preferred language is Spanish, the greeting will appear in Spanish.

```text Output - Spanish
Elige tu plan: Plan Básico por €5/mes o Plan Premium por €15/mes.
```

The greeting will appear in English if the user prefers English.

```text Output - English
Choose your plan: Basic Plan for $5/month or Premium Plan for $15/month.
```

## Update Footer

You can change the footer in a running campaign to reflect new content. For example, a footer displays icons for various social media such as _TikTok_, _Facebook_, _WhatsApp_, and _Instagram_. You can change the footer in the outgoing messages by removing or adding icons in this footer. Once you change the icons, the change will be reflected in all outgoing messaging.

<Image align="center" alt="HTML Code for Footer" border={true} caption="HTML Code for Footer" src="https://files.readme.io/669b9b25ec2da9c3e5360bc694538dc3d9098be24596dbadc230a617ef54f845-HTML_code_for_footer.jpg" />

You can edit the HTML to remove or add an icon.

<Image align="center" alt="Footer Content Block with X and Facebook" border={true} caption="Footer without Instagram" src="https://files.readme.io/c9b7536b14f5594b55b4fc9cb7782bf2af37234cdb8ff74b03bfe9c40e4ab633-2024-11-11_18-20-20.jpg" />

The following is an example of an updated footer. Once the footer is updated, all campaigns using this Content Block will display the updated icons in the outgoing messages.

<Image align="center" alt="Footer content block with X , FB , and Google" border={true} caption="Footer with Instagram" src="https://files.readme.io/72e98e0eba6fdbfbe66b8e3dff9af113e891ab6e97bae511ccd2ec11a79af57b-2024-11-11_18-16-47.jpg" />
