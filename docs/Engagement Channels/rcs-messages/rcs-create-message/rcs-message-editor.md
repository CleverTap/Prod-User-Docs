---
title: RCS Message Editor
excerpt: Learn how to use templates to send campaigns through RCS Message Editor
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

The RCS Message Editor in CleverTap allows marketers to create and manage Rich Communication Services (RCS) messages as part of SMS/RCS campaigns. These messages support multimedia content, rich formatting, and interactive buttons, enabling businesses to deliver high-impact communication directly to users' messaging apps.

Templates can be created once and reused across multiple campaigns, improving consistency and reducing setup time.

To access the RCS Message Editor:

1. In the SMS Campaign Builder, go to the **Provider** dropdown, select **Service Provider** for RCS.


<Image src="https://files.readme.io/673259e63b9e14c1c1b924d2b886b044c917653d677612a5aab7e79df18664a8-provider_in_campaign_RCS.png" alt="RCS Provider in Campaigns" align="center" caption="RCS Provider in Campaigns" border={true} />


2. Navigate to the **What** section in the SMS Campaign Builder.
3. Choose a **Message Type** and click **Go to Editor**.


<Image src="https://files.readme.io/7218b693676d558492e8b0c7c0f59764c2bcb5f2d1207676ca15aade0d2d705f-What_section_RCS.png" alt="Go To Editor" align="center" caption="Go To Editor" border={true} />


The RCS Message Template selection screen will appear, where you can create or edit templates for your campaign.

## Template Creation Modes

CleverTap supports two modes for working with RCS templates, based on your telecom carrier and campaign regulations:

### Approved Templates

For carriers where template approval is required, RCS templates must be [created](doc:rcs-setup#create-template) and submitted in advance. Once approved:

- Template content and button fields are locked.
- Only dynamic placeholder values (e.g., `{{1}}`, `{{2}}`) can be filled at the campaign level.
- This ensures compliance with telecom regulations.

When using an approved template in the editor, you will see fields pre-filled with static content or placeholders. CleverTap supports two modes for working with RCS templates, depending on your region and the regulatory requirements enforced by telecom carriers and campaign compliance guidelines. Your role is to supply the appropriate values for those placeholders during campaign setup.

### Free-form Templates

For carriers where template approval is not required, you can build templates directly in the editor. These templates allow full flexibility:

- You define all text, media, button behavior, and placeholders.
- There are no locked fields.

This documentation explains every component clearly to support both workflows.

## RCS Template Types

CleverTap provides three types of RCS templates. Each supports text, personalization through placeholders, and interactive buttons.

### [Text Template](doc:rcs-message-editor#text-template-1)

A simple, text-only format. Useful for alerts, reminders, and announcements.

### [Rich Card Template](doc:rcs-message-editor#rich-card-template-1)

A more visual format that allows an image, video, or PDF, along with a title, body text, and buttons.

### [Carousel Template](doc:rcs-message-editor#carousel-template-1)

A scrollable format featuring multiple rich cards. Each card can contain its own media, title, body, and buttons.

Each template supports up to 10 buttons for Text messages and up to 4 buttons per card for Rich Card and Carousel templates. These buttons can open a URL, dial a number, send a quick reply, share a location, request a location, or create a calendar event. The way you configure these buttons depends on whether you are working with an approved or free-form template.Button Types in RCS Messages

Buttons allow users to interact with your message. All three template types: **Text**, **Rich Card**, and **Carousel** support the same button types (URL Redirect, Call Phone Number, Quick Reply, Send Location to User, Get User Location, and Calendar Event). The difference lies in how the content is organized and how fields behave for different types of users.

- [URL Redirect](doc:rcs-message-editor#url-redirect-button)
- [Call Phone Number](doc:rcs-message-editor#call-phone-number-button)
- [Quick Reply](doc:rcs-message-editor#quick-reply-button)
- [Send Location to User](doc:rcs-message-editor#send-location-to-user-button)
- [Get User Location](doc:rcs-message-editor#get-user-location-button)
- [Calendar Event](doc:rcs-message-editor#calendar-event-button)

Each button includes specific fields that must be configured. Depending on your template type, these fields may be locked (approved templates) or editable (free-form templates).

### URL Redirect Button

This button opens a web page when tapped. There are three configurations:

<Tabs>
  <Tab title="Static URL">
  A fixed link for all users, used to direct all recipients to a general landing page.

  * **Button Text**: The label shown on the button (for example, "Visit Website").
    * Approved templates: Pre-filled and not editable.
    * Free-form templates: Enter a clear, actionable label.
  * **URL**: The destination web link (for example, `https://example.com/sale`).
    * Approved templates: Predefined and locked.
    * Free-form templates: Enter the full URL manually.
  * **Postback**: A value triggered when the button is clicked, used for tracking clicks or triggering automation.
    * Approved templates: Predefined.
    * Free-form templates: Enter a value such as `static_sale_click`.
  </Tab>
  <Tab title="Dynamic URL">
  A personalized link that varies per recipient, used to redirect users to their own dashboard, cart, or offer page.

  * **Button Text**: The clickable label (for example, "View My Offer").
    * Approved templates: Pre-filled and locked.
    * Free-form templates: Enter manually.
  * **URL**: Constructed from a fixed prefix and a dynamic suffix (for example, `https://example.com/user/{{user_id}}`).
    * Approved templates: The prefix is fixed; the suffix is entered during campaign setup.
    * Free-form templates: Define both parts using personalization tokens.
  * **Postback**: Used to identify which user clicked the button.
    * Free-form templates: Enter a value such as `dynamic_offer_click_{{user_id}}`.
  </Tab>
  <Tab title="Link Tracking">
  A URL configured with tracking parameters to measure engagement, used to track user clicks and optimize campaigns.

  * **Button Text**: The visible label (for example, "Learn More").
    * Approved templates: Pre-filled and locked.
    * Free-form templates: Enter a descriptive label.
  * **URL**: A tracking-enabled link (for example, `https://example.com?utm_source=rcs`).
    * Approved templates: Locked.
    * Free-form templates: Input manually.
  * **Postback**: A value used to log the click action.
    * Free-form templates: Use values such as `link_tracking_click_offer`.
  </Tab>
</Tabs>

### Call Phone Number Button

This button opens the user's phone app with a predefined phone number.

**Use Case**: Let users immediately contact your sales, support, or service team.

- **Button Text**: The label on the button (e.g., "Call us now").
  - Approved templates: Predefined.
  - Free-form templates: Enter a clear and direct label.

- **Phone Number**: The number to be dialed. Enter the number with the country code (e.g., `+919999999999`).
  - Approved templates: Predefined and uneditable.
  - Free-form templates: Enter the number manually with the country code.

- **Postback**: Triggers a log when the button is tapped, indicating that a call was initiated.
  - Free-form templates: Enter a value such as `call_support`.

### Quick Reply Button

This button sends a short, predefined response back to your system when the user taps it.

**Use Case**: Collect fast, structured responses (e.g., “Yes”, “No”, “Remind me later”).

- **Button Text**: The visible text on the button (e.g., "Yes, I'm interested").
  - Approved templates: Predefined.
  - Free-form templates: Enter this manually.

- **Reply Text**: The message content sent back to your system (can be the same as the button text or different).
  - Free-form templates: Define this clearly (e.g., `"Reply Text": "User is interested"`).

- **Postback**: Helps you identify which quick reply the user selected.
  - Free-form templates: Enter a unique identifier (e.g., `interest_yes_reply`).

### Send Location to User Button

This button opens a specified location in the user's default map app using the coordinates you provide. Use this to share store addresses, event venues, delivery points, or any fixed geographic location.

**Use Case**: Share your nearest store, event venue, or delivery drop-off point with users.

- **Button Text**: The label on the button (e.g., "Find our store").
  - Approved templates: Predefined.
  - Free-form templates: Enter a clear and direct label.

- **Latitude**: The latitude coordinate of the location. Enter a value between -90 and 90 (e.g., `19.0760`).
  - Approved templates: Predefined and uneditable.
  - Free-form templates: Enter the latitude value manually.

- **Longitude**: The longitude coordinate of the location. Enter a value between -180 and 180 (e.g., `72.8777`).
  - Approved templates: Predefined and uneditable.
  - Free-form templates: Enter the longitude value manually.

- **Label**: A display name for the location shown to the user in the map app (e.g., `CleverTap Mumbai Office`).
  - Approved templates: Predefined.
  - Free-form templates: Enter a descriptive location name.

- **Postback**: Triggers a log when the button is tapped.
  - Free-form templates: Enter a value such as `send_location_store`.

### Get User Location Button

This button prompts the user to share their current GPS position or select a location from their map app. The shared coordinates are returned to your system as a message reply.

**Use Case**: Collect delivery addresses, confirm a user's nearest branch, or support location-based personalization.

- **Button Text**: The label on the button (e.g., "Share your location").
  - Approved templates: Predefined.
  - Free-form templates: Enter a clear and direct label.

- **Postback**: Triggers a log when the button is tapped.
  - Free-form templates: Enter a value such as `get_user_location`.

### Calendar Event Button

This button opens the user's default calendar app and pre-fills an event entry. Use this for appointment reminders, product launches, sale events, or any time-bound engagement.

**Use Case**: Help users save important dates directly to their calendar without leaving the message.

- **Button Text**: The label on the button (e.g., "Save the date").
  - Approved templates: Predefined.
  - Free-form templates: Enter a clear and direct label.

- **Start Date**: The date the event begins, in MMMM dd, yyyy format (e.g., `June 20, 2026`).
  - Free-form templates: Enter or select the date using the date picker.

- **Start Time**: The time the event begins, in mm:hh am/pm format (e.g., `10:00 AM`).
  - Free-form templates: Enter or select the time using the time picker.

- **End Date**: The date the event ends, in MMMM dd, yyyy format (e.g., `June 20, 2026`).
  - Free-form templates: Enter or select the date using the date picker.

- **End Time**: The time the event ends, in mm:hh am/pm format (e.g., `11:00 AM`).
  - Free-form templates: Enter or select the time using the time picker.

- **UTC Offset**: The timezone for the event, selected from a dropdown. Defaults to (GMT+05:30) Asia/Kolkata.
  - Free-form templates: Select the appropriate timezone from the dropdown.

- **Event Title**: The name of the calendar event (e.g., `CleverTap Sale Begins`).
  - Free-form templates: Enter a clear and descriptive event name.

- **Event Description**: A brief description displayed within the calendar entry (e.g., `Don't miss our biggest sale of the year`).
  - Free-form templates: Enter a short description of the event.

- **Postback**: Triggers a log when the button is tapped.
  - Free-form templates: Enter a value such as `calendar_event_sale`.

## Template Types

Now that you understand how buttons work and how their fields behave depending on your template type, the next step is to configure the structure of the RCS message itself using templates. Templates define how the message appears, text-only, rich content, or multiple scrollable cards, and they determine where your buttons and dynamic content appear.

All three template types: **Text**, **Rich Card**, and **Carousel** support the same button types (URL Redirect, Dialer, Quick Reply). The difference lies in how the content is organized and how fields behave for different types of users.

Depending on your region or setup, you may be using:

- **Approved Templates**: Created in advance and submitted for approval. Most content fields are locked, and only dynamic values (e.g., `{{1}}`) can be updated in the campaign.
- **Free-form Templates**: Created directly in the RCS Message Editor with full control over layout, text, media, and button configuration.

### Text Template

The Text template allows you to send a simple message with optional buttons. It does not support media and is best suited for short messages or alerts.

**Use Cases**:

This template is ideal for transaction updates or informational messages that require no media and need quick delivery.

- Account notifications or payment reminders
- Quick updates without images

**Supported Features**:

The Text template offers basic personalization and interactivity while maintaining a lightweight format.

- Media: Not supported
- Buttons: Up to 10 buttons. Supported types include URL Redirect, Call Phone Number, Quick Reply, Send Location to User, Get User Location, and Calendar Event.
- Personalization: Yes, using placeholders like `{{1}}`, `{{2}}`

#### Message Text

This is the main body of the message that users will receive. Depending on your template type, you may either customize the full content or provide values for predefined placeholders.

- **Approved Templates**:
  - The message content is pre-filled and cannot be changed.
  - You can only fill in values for dynamic fields like `{{1}}`, `{{2}}`.
  - Example: If the message is `Hi {{1}}, your order for {{2}} has shipped`, you can only enter values like `{{1}} = "Alex"`, `{{2}} = "Shoes"`.
- **Free-form Templates**:
  - You can enter the full text message manually.
  - Use placeholders for dynamic values if needed (e.g., `{{}}`, `{{product_name}}`).
  - RCS supports basic formatting such as **bold** and _italics_, where available.

#### Custom Key-Value Pairs

Custom key-value pairs let you dynamically replace placeholders in your message with actual values at the campaign level.

- Used to provide values for placeholders dynamically.
- **Preset Key**: Select a predefined placeholder name (e.g., `{{user_name}}`)
- **Value Field**: Input the actual value to replace it (e.g., `Emma`)
- **Add KV Pair Button**: Lets you add additional key-value pairs

#### Buttons

All six button types are supported. For more on button behavior and setup, refer to the [Button Types](doc:rcs-message-editor#button-types-in-rcs-messages) section.

- **Approved Templates**: Buttons are predefined and locked; you can only enter values for dynamic parts, such as a URL suffix.
- **Free-form Templates**: You define each button completely, including type, label, destination, and postback.

### Rich Card Template

Rich Cards add media, titles, and longer body messages to your campaign, along with interactive buttons. They provide a more visual format to drive engagement.

**Use Cases**:

Use Rich Cards when you want to combine images or video with text to better highlight offers, products, or updates.

- Promotions or discount offers
- Product spotlights or new feature announcements
- Event reminders with RSVP buttons

**Supported Features**:

This template supports multimedia content and personalization, making it ideal for marketing or promotional use cases.

- Media: Yes (image, video, or PDF)
- Buttons: Up to 4 buttons. Supported types include URL Redirect, Call Phone Number, Quick Reply, Send Location to User, Get User Location, and Calendar Event.
- Personalization: Yes, in both Title and Body

#### Template Name

The template name helps identify the message in your dashboard and is either pre-set or defined during creation.

- **Approved Templates**: The name is pre-filled during approval and cannot be changed.
- **Free-form Templates**: Enter a unique name to identify the template in the dashboard.

#### Media URL

This is the main image, video, or PDF shown in the Rich Card. It helps visually reinforce your message.

- **Approved Templates**:

The media URL is either fixed or partially dynamic, depending on how the template was created and approved.

- May include a static URL or a predefined prefix with a dynamic suffix.
- Example: `https://cdn.example.com/images/{{image_id}}`
- **Free-form Templates**:

You can provide a direct URL for media. Dynamic URLs are also supported for personalized content.

- Enter a complete image or video URL manually.
- Optionally, use dynamic values to personalize the media source.

#### Thumbnail URL (if supported)

The thumbnail is an optional smaller image shown as a preview or fallback in certain layouts or devices. A thumbnail is only applicable for Videos and will be pre-selected automatically.

- A smaller image shown as a preview or fallback.
- Can be uploaded or added via URL.
- Example: `https://www.placeholder.com/images/india/festivalsale/genericimg3`

#### Title

The title appears prominently above the message body and can contain personalization tokens.

- **Approved Templates**:
  - Title is pre-defined and may include placeholders (e.g., `Hello {{1}}`).
  - You can only provide values for the placeholders.
- **Free-form Templates**:
  - You enter the full title.
  - Add placeholders where personalization is needed.

#### Body

The message body provides additional context or detail beneath the title and supports dynamic content.

- **Approved Templates**:
  - The body is pre-filled with placeholder syntax (e.g., `Hi {{1}}, your order for {{2}} is confirmed`).
  - You provide only the placeholder values during campaign setup.
- **Free-form Templates**:
  - Write the full message body manually.
  - Use placeholders to insert dynamic content such as names or order details.

#### Buttons

All six button types are supported. For more on button behavior and setup, refer to the [Button Types](doc:rcs-message-editor#button-types-in-rcs-messages) section.

- **Approved Templates**: Buttons are predefined and locked; you can only enter values for dynamic parts, such as a URL suffix.
- **Free-form Templates**: You define each button completely, including type, label, destination, and postback.

### Carousel Template

Carousel templates allow you to create a scrollable series of rich cards, each with its own content and buttons. Each card functions independently and can present a unique product, category, or option.

**Use Cases**

Carousel templates are ideal for showcasing multiple products, services, or promotions within a single message.

- Product or service galleries
- Multi-offer campaigns
- Feature comparisons

**Supported Features**

This template supports multimedia content and personalization on each card, making it ideal for multi-product or multi-offer campaigns. The following features are supported in the Carousel template:

- Media: Yes (image, video, or PDF per card)
- Buttons: Up to 4 buttons per card. Supported types include URL Redirect, Call Phone Number, Quick Reply, Send Location to User, Get User Location, and Calendar Event.
- Personalization: Yes (individually on each card)

#### Media per Card

Configure the media for each card depending on your template type.

- **Approved Templates:&#x20;**
  - Image, video, or PDF URLs are either static or partially dynamic.

  - You may only enter suffixes or dynamic parts if supported.
- **Free-form Templates**:
  - Provide the full URL or upload media for each card.
  - You can use dynamic media for personalization.

#### Thumbnail per Card

A thumbnail is only applicable for Videos and will be pre-selected automatically.

- A smaller image shown as a preview (optional).
- Can be uploaded or provided via URL.
- Supported in both template modes, depending on configuration.

#### Title per Card

Configure the title for each card depending on your template type.

- **Approved Templates**:
  - Pre-filled with placeholder structure (e.g., `{{1}}`)
  - Only placeholder values are editable
- **Free-form Templates**:
  - You write the full title for each card
  - Placeholders can be added for dynamic personalization

#### Description per Card

Configure the description for each card depending on your template type.

- **Approved Templates**:
  - The body is locked and uses placeholders
  - You only fill in dynamic values during campaign setup
- **Free-form Templates**:
  - You create the full message
  - Add dynamic placeholders as needed

#### Buttons per Card

All six button types are supported. For more on button behavior and setup, refer to the [Button Types](doc:rcs-message-editor#button-types-in-rcs-messages) section.

- **Approved Templates**: Buttons are predefined and locked; you can only enter values for dynamic parts, such as a URL suffix.
- **Free-form Templates**: You define each button completely, including type, label, destination, and postback.

<br />
