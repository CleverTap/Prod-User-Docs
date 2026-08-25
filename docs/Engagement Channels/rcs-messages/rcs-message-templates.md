---
title: RCS Message Templates
excerpt: Learn more about setting up and creating RCS Messaging Templates
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

RCS (Rich Communication Services) Message Templates enable businesses to send rich, interactive messages to users, enhancing engagement beyond standard SMS capabilities. These templates support various media types, buttons, and formatting options, allowing for a more dynamic user experience.

Here are the key components that make up an RCS message template.

# Template Components

An RCS message template consists of the following key components:

- **Title**: The headline of the message that appears prominently at the top of the template. It should be concise and engaging to quickly capture the recipient’s attention.
- **Description**:  The main message body where the content of the RCS message is defined. This field provides detailed information to users and can include formatted text such as bold, italics, strikethrough, and emojis to enhance readability and engagement.
- **Buttons**: Interactive elements that allow users to take action directly from the message. RCS templates support up to 10 buttons for Text messages and up to 4 buttons for Rich Card and Carousel templates, enabling businesses to drive customer engagement. The number of buttons rendered in an SMS inbox depends on the device's screen dimensions and UI limitations. Some buttons used in the template may not be visible on certain devices due to these constraints. It is recommended to test templates across different devices to ensure optimal rendering. CleverTap allows six types of buttons in RCS templates:
  - [URL Redirect](doc:rcs-message-templates#url-redirect)
  - [Call Phone Number](doc:rcs-templates#call-phone-number)
  - [Quick Reply](doc:rcs-templates#quick-reply)
  - [Send Location to User](doc:rcs-templates#send-location-to-user)
  - [Get User Location](doc:rcs-templates#get-user-location)
  - [Calendar Event](doc:rcs-templates#calendar-event)

## URL Redirect

A button that redirects users to a specific webpage. Opens a specific URL when tapped, directing users to a landing page, website, or app.


<Image src="https://files.readme.io/4ffa1503d189efeaa24de75b27a679fadde093bd49d2e13c86807855347eadf3-URL_Redirect_RCS.png" align="center" caption="URL Redirect" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **URL Type**: The destination URL (maximum 2,048 characters). For dynamic URLs, use placeholders, for example: `https://example.com/{{1}}`. Choose from the following options:
  - **Static**: Fixed URL entered at the time of template creation.
  - **Dynamic**: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. Uses dynamic parameters, for example: `https://www.clevertap.com/{{1}}`.
  - **CleverTap Link Tracking**: Brands can leverage CleverTap link tracking functionality to monitor details of the user who clicked the URL. The entire URL can be personalized for each user during campaign creation.
- **URL Appearance for Users**: Choose how the URL opens when the user taps the button:
  - **Browser**: Opens the URL in the user's default browser.
  - **Webview**: Opens the URL inside the messaging app. When selected, choose a _Webview Layout_:
    - **Full**: The message is shown throughout the whole screen.
    - **Half**: Opens the URL in a half-screen webview, with the message visible behind it.
    - **Tall**: Opens the URL in a tall webview covering most of the screen, with a portion of the message visible above.
- **Postback**: A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

## Call Phone Number

Initiates a phone call to a specified number, allowing users to contact a business instantly. Users can tap the button to initiate a phone call.


<Image src="https://files.readme.io/22ac81d3143e47cb3848fb69ec0224219156927044f9dbcb9219ca48e90029d9-call_phone_number.png" align="center" caption="Call Phone Number Button" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **Phone number**: The number users will call when they tap the button (maximum 20 characters).
- **Postback**: A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

## Quick Reply

A button that allows users to send predefined responses.


<Image src="https://files.readme.io/70a247404f5801c6016998af5f5f6dd316f742192d732ac418904f21753f9edc-Quick_reply.png" align="center" caption="Quick Reply Button" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **Postback**:  A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

## Send Location to User

Opens a specified location in the user's default map app using the coordinates you provide. Use this to share store addresses, event venues, delivery points, or any fixed geographic location.


<Image src="https://files.readme.io/4f312be82c1c561b3be0bb79763985a2f05c444af31638295c23552b194022f3-send_location_to_user.png" align="center" caption="Send Location to User Button" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **Latitude**: The latitude coordinate of the location. Enter a value between -90 and 90. Supports Liquid tags for personalization — for example, `{{ Profile.latitude }}`.
- **Longitude**: The longitude coordinate of the location. Enter a value between -180 and 180. Supports Liquid tags for personalization — for example, `{{ Profile.longitude }}`.
- **Label**: A display name for the location shown to the user in the map app.
- **Postback**: A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

## Get User Location

Prompts the user to share their current GPS position or select a location from their map app. The shared coordinates are returned to your system as a message reply. Use this to collect delivery addresses, confirm a user's nearest branch, or support location-based personalization.


<Image src="https://files.readme.io/f8a8cf093ecf6b0fa22e18b50004bf7f68a0e8555724201fb4b4236dd7a66088-Get_user_location.png" align="center" caption="Get User Location" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **Postback**: A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

## Calendar Event

Opens the user's default calendar app and pre-fills an event entry. Use this for appointment reminders, product launches, sale events, or any time-bound engagement.


<Image src="https://files.readme.io/5cb92210d11a2fd45f291bf6c865066d153f2fdcfa52a832a973dd7422a967be-calendar_event.png" align="center" caption="Calendar Event Button" border={true} />


- **Button Text**: Enter a label for the button (maximum 25 characters, no special characters).
- **Start Date**: The date the event begins, in MMMM dd, yyyy format.
- **Start Time**: The time the event begins, in mm:hh am/pm format.
- **End Date**: The date the event ends, in MMMM dd, yyyy format.
- **End Time**: The time the event ends, in mm:hh am/pm format.
- **UTC Offset**: The timezone for the event, selected from a dropdown. Defaults to (GMT+05:30) Asia/Kolkata.
- **Event Title**: The name of the calendar event. Supports Liquid tags for personalization.
- **Event Description**: A brief description displayed within the calendar entry. Supports Liquid tags for personalization.
- **Postback**: A button identifier that can be used to track button clicks. The Notification Replied event logs this interaction for analytics.

# Add Message Template

Easily create and manage RCS message templates in CleverTap to streamline your messaging campaigns. These templates are automatically sent to the relevant platforms based on registration. For example, if a template is registered with Vodafone, it will be sent to Vodafone. The status of the template will be updated within 24 hours, and you can track it directly within the dashboard.

To create RCS campaigns for Indian users, you must have pre-approved RCS message templates saved in the CleverTap dashboard. Follow the steps below to add a new message template:

1. Navigate to _Settings_ > _Channels_ > _SMS_ > _SMS Direct_ > _+ Provider_


   <Image src="https://files.readme.io/762fc449942aba1ccfbd894b9456ab9df28f0335b22630cdb0ae3567c18cb545-Set_up_-_RCS.png" alt="Add Provider" align="center" caption="Add Provider" border={true} />


2. In the _Provider Nickname_ select _Infobip RCS Provider_ from the CleverTap dashboard.


   <Image src="https://files.readme.io/da895c9dc2960d00a8be756e9dce30b89bb6393821e9f6476cb90a9bd62ce975-Provider_-_RCS.png" alt="Infobip RCS Provider " align="center" caption="Infobip RCS Provider" border={true} />


3. Select the _Templates_ option and click **+ Template**.


   <Image src="https://files.readme.io/676c7e96d063f681c29b73d2fb7099a1d651016d3378e54cd69e56c898652c8f-Create_Template_-_RCS.png" alt="Create Template" align="center" caption="Create Template" border={true} />


4. Choose the Template Type:

   - [Text  ](doc:rcs-message-templates#text)
   - [Rich Card](doc:rcs-message-templates#rich-card-template)
   - [Carousel](doc:rcs-message-templates#carousel)


     <Image src="https://files.readme.io/41665be20c86c2510f64dbfdd71f72b7609fdc01a610234af1a1d6dcbfee1281-Template_Type_-_RCS.png" alt="Template Type" align="center" caption="Template Type" border={true} />


5. Configure Template Components:
   - **Title**: The headline of the message that appears prominently at the top of the template.
   - **Description**: Enter the main message content.
   - **Buttons**: Add interactive elements to enhance user engagement.

6. Click **Save** to save the template.

## Text

The text template is a simple RCS message format that consists of a plain text message with optional interactive buttons. It allows businesses to send structured messages while incorporating basic text formatting and engagement features. Follow these steps to create a text template:


<Image src="https://files.readme.io/858e0401d0ade895172379f429c1383b6e055a0e5e3f62d82111d941e347072c-Text_Template.png" align="center" caption="Text Template" border={true} />


1. **Template Name**: Enter a name for the template (maximum 20 characters).

> 📘 Naming RCS Templates
>
> Template names and language variants must be unique for each provider configuration. This means that you can use the same template name once for each provider configuration.
>
> For example, if you have multiple provider configurations, such as _Phone\_1, phone\_2_, you can use the same template name once within _Phone\_1 and Phone\_2_.

2. **Message Text**: Enter the text message content (maximum 1000 characters).
   - **For body text formatting**:
     - Adding Emojis: Copy from here and paste in the body.
     - Bold: Add asterisks (\*) at the beginning and end.
     - Italic: Add underscores (\_) at the beginning and end.
     - Strikethrough: Add tilde (\~) at the beginning and end.
     - Monospace: Add three consecutive backticks (\`\`\`) at the beginning and end.
3. **Enable Buttons**:  Click **+** to add buttons to the message (up to 10 buttons). The following button types can be added:
   - [URL Redirect](doc:rcs-message-templates#url-redirect)
   - [Call Phone Number](doc:rcs-templates#call-phone-number)
   - [Quick Reply](doc:rcs-templates#quick-reply)
   - [Send Location to User](doc:rcs-templates#send-location-to-user)
   - [Get User Location](doc:rcs-templates#get-user-location)
   - [Calendar Event](doc:rcs-templates#calendar-event)

## Rich Card Template

A Rich Card Template allow businesses to send RCS messages with images, videos, or other media to enhance engagement.. Rich Cards enhance user engagement by presenting information in an interactive, media-rich format that is more compelling than standard text messages. They are ideal for showcasing products, promotions, event details, and more. Follow the steps below to create a Rich Card template on CleverTap.

1. **Template Name**: Enter a name for the template (maximum 20 characters, only alphanumeric characters and underscores (\_) are allowed.).

2. Choose _Card Size & Layout_ to the layout for how media will be displayed in the message:

   - **Vertical · Right · Short** (Aspect Ratio 3:1): A tall vertical card for displaying prominent visuals, with content aligned to the right.
   - **Vertical · Right · Medium** (Aspect Ratio 2:1): A slightly shorter vertical layout with content aligned to the right.
   - **Horizontal · Left · Medium** (Aspect Ratio 3:4): A horizontal card with the image on the left and text on the right.
   - **Horizontal · Right · Medium** (Aspect Ratio 3:4): A horizontal card with the image on the right and text on the left.


     <Image src="https://files.readme.io/d0662cc5ff0ce10a314f50db6a5a06e9b182ffac7f33ba61dd1d3a3ee0bbb9ca-rich_card_aspect_ratio.png" align="center" caption="Aspect Ratio" border={true} />


3. To configure card _Content_, select the _Media_ type for your Rich Card:

   - Static: The media file is uploaded at the time of template creation and cannot be changed later. Select between _Image_, _Video_, or _PDF_ and click **Upload Media**.

     \ <br />


     <Image src="https://files.readme.io/8830d548d31fad83a7cc9396501ef692a63ac98bbdc41badaa9ba45931e721b0-media_url_type.png" align="center" caption="Static" border={true} />


   - Dynamic: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. For example: `https://www.clevertap.com/{{1}}`. Enter Media URL. \ <br />


     <Image src="https://files.readme.io/340af88035abbb3c12affb00de344bbf76a32a3f76423121bf479b1cb148fdb7-dynamic.png" align="center" caption="Dynamic" border={true} />


- Upload in Campaign: You upload media during campaign creation, but it cannot be personalized per user. Upload media at the campaign level when sending the RCS message. Since CleverTap will register a URL at the time of template creation to provide the flexibility of uploading media URL at the time of campaign creation, personalization will not be available for the URLs at the time of uploading the media while creating a campaign. A pre-determined URL will already be present in the URL field. \ <br />


  <Image src="https://files.readme.io/98584ef7b3fb9186b7ce92ea1e1b26d6d55080c8225714dd673a774f040d4d7d-Upload_in_campaign.png" align="center" caption="Upload in Campaign" border={true} />


4. Add a Thumbnail to provide a preview of the media in the Template. A thumbnail is only applicable for Videos and will be pre-selected automatically. There are three types of media that can be used for the thumbnail.
   - Static: A fixed Video or PDF for the thumbnail. \ <br />


     <Image src="https://files.readme.io/ae6c329c049b4c351ef8a00706c429634fa410167637fe00e6679365710c0cba-static_media_type_rich_card.png" align="center" caption="Static Media for Video with Thumbnail" border={true} />


- Dynamic: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. Select between Image, Video, or PDF and enter the dynamic media URL. For example: `https://www.clevertap.com/{{1}}`. \ <br />


  <Image src="https://files.readme.io/4dd009f5ea9a4d8b508d838b3245931799593de70e0170e67274ec19e480f444-dynamic_media_type_rich_card.png" align="center" caption="Dynamic Media for Video with Thumbnail" border={true} />


- Upload in Campaign: You upload media during campaign creation, but it cannot be personalized per user. Select between _Image_, _Video_, or _PDF_ under _Add Sample Media File_ and click **Upload Media**. Since CleverTap will register a URL at the time of template creation to provide the flexibility of uploading media URL at the time of campaign creation, personalization will not be available for the URLs at the time of uploading the media while creating a campaign. A pre-determined URL will already be present in the URL field. \ <br />


<Image src="https://files.readme.io/89125ce0ac2a8b6dd9d03d7ac31fccb4267b9ee2579d63f42bfc37fa0f48664f-upload_in_campaign_rich_card_with_thumbnail.png" align="center" caption="Upload in Campaign for Video with Thumbnail" border={true} />


5. **Add a Title**: The title will be displayed in bold and can be up to 200 characters long. To add dynamic parameters, use `{{1}}`, `{{2}}`, etc., in sequence, where values will be replaced at runtime.

6. **Add a Description**: Enter the text message content, with a maximum limit of 2000 characters. To add dynamic parameters `{{1}}`, `{{2}}`, etc., for personalization.

   - **For body text formatting**:

     - Adding Emojis: Copy from here and paste in the body.
     - Bold: Add asterisks (\*) at the beginning and end.
     - Italic: Add underscores (\_) at the beginning and end.
     - Strikethrough: Add tilde (\~) at the beginning and end.
     - Monospace: Add three consecutive backticks (\`\`\`) at the beginning and end.


       <Image src="https://files.readme.io/64c41b95d52646629bb3007315a643110bb109b3536a2ee87b7968fcbe7d4883-media_url_type.png" align="center" caption="Title and Description" border={true} />


7. **Enable Buttons**:  Click **+** to add buttons to the message (up to 4 buttons). The following button types can be added:

   - [URL Redirect](doc:rcs-message-templates#url-redirect)
   - [Call Phone Number](doc:rcs-templates#call-phone-number)
   - [Quick Reply](doc:rcs-templates#quick-reply)
   - [Send Location to User](doc:rcs-templates#send-location-to-user)
   - [Get User Location](doc:rcs-templates#get-user-location)
   - [Calendar Event](doc:rcs-templates#calendar-event) \ <br />


     <Image src="https://files.readme.io/a40895751e9b1520cb4a7a84ee8212b4465909443422271ad5a0b134a37ca57a-buttons.png" align="center" caption="Buttons" border={true} />


## Carousel

A Carousel Template is a multi-card format that allows businesses to display multiple Rich Cards within a single message. Users can scroll horizontally through the cards, making it an effective way to showcase multiple products, services, promotions, or event details within a single interaction. Each card in the carousel can contain an image or video, a title, a description, and interactive buttons, enhancing engagement and interactivity.

Follow the steps below to create a Carousel Template on CleverTap. You can add up to 10 cards in the template, with each card containing the following elements:


<Image src="https://files.readme.io/936a4055dd5816d5405b74bd16c2145e33bf4d4d08aff8ca72f2ef8ace6c379f-add_card_in_carousel_template.png" align="center" caption="Add Card in Carousel Template" border={true} />


1. **Template Name**: Enter a name for the template (maximum 20 characters).

2. Choose _Card Size & Layout_ to define the appearance of the Carousel:
   - **Small · Short** (Aspect Ratio 5:4) – A compact card with a shorter image area.
   - **Small · Tall** (Aspect Ratio 4:5) – A compact card with a taller image area.
   - **Medium · Short** (Aspect Ratio 2:1) – A medium-width card with a shorter image area.
   - **Medium · Medium** (Aspect Ratio 4:3) – A medium-width card with a balanced image and content area. \ <br />


     <Image src="https://files.readme.io/0217f9f9e5da9013bd716d31cca2e5960f97a122fc3b9bb82bf4528ed6bc11a1-ASPECT_RATIO_-_CAROUSEL.png" align="center" caption="Aspect Ratio - Carousel Template" border={true} />


3. To configure card _Content_, select the _Media_ type for your Carousel Template:

   - Static: The media file is uploaded at the time of template creation and cannot be changed later. Select between _Image_, _Video_, or _PDF_ and click **Upload Media**. \ <br />


     <Image src="https://files.readme.io/92265cd337d4947574125a912c4fcc303c5cdede3840f5f73c976519fd849fed-Carousel_-_Static_media.png" align="center" caption="Static" border={true} />


   - Dynamic: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. Select between Image, Video, or PDF and enter the dynamic media URL. For example: `https://www.clevertap.com/{{1}}`. \ <br />


     <Image src="https://files.readme.io/78b0d7431da8d66f6d35fee21a44ea665ab2f72a595f23f6710fbf090a305e02-dynamic_-_carousel.png" align="center" caption="Dynamic" border={true} />


   - Upload in Campaign: Select between _Image_, _Video_, or _PDF_ under _Add Sample Media File_ and click **Upload Media**. Since CleverTap will register a URL at the time of template creation to provide the flexibility of uploading media URL at the time of campaign creation, personalization will not be available for the URLs at the time of uploading the media while creating a campaign. A pre-determined URL will already be present in the URL field. \ <br />


     <Image src="https://files.readme.io/cee97fbc4fa3f393c6432bfb6bed278cfb04cb2f789823e54dbdabbb15897408-upload_in_campaign_-_carousel.png" align="center" caption="Upload in Campaign" border={true} />



     <Image src="https://files.readme.io/cdfc80ee5a5b6073a3f88cbdc54728bf1ef9acf79da55a216bf3c8e072bee99a-Upload_in_campaign_-_Carousel_-_RCS.png" alt="Upload in Campaign" align="center" caption="Upload in Campaign" border={true} />


4. Add a Thumbnail to provide a preview of the media in the Template. A thumbnail is only applicable for Videos and will be pre-selected automatically. There are three types of media that can be used for the thumbnail.Static: A fixed image or video for the thumbnail. \ <br />

   -
     <Image src="https://files.readme.io/807cb3df84f5aee4bb8349594e362fb686f6a0177108c7e04fe8a916742a19f5-static_-_carousel_1.png" align="center" caption="Static - thumbnail" border={true} />


   - Dynamic: Brands must provide the URL prefix (URL domain), and the URL suffix can be personalized for each user. For example: `https://www.clevertap.com/{{1}}`. \ <br />


     <Image src="https://files.readme.io/5a2e9ed016ebdbd6868830cd43cc270ed83fdc5d3ec704529b5d0ab39bcbd98b-dynamic_thumbnail_carousel.png" align="center" caption="Dynamic - thumbnail" border={true} />


   - Upload in Campaign: Upload media at the campaign level when sending the RCS message. Since CleverTap will register a URL at the time of template creation to provide the flexibility of uploading media URL at the time of campaign creation, personalization will not be available for the URLs at the time of uploading the media while creating a campaign. \ <br />


     <Image src="https://files.readme.io/bed31f1892108e9ebb4cc32eaa672c534bff64dda06ef477a3e3b66b142e3a4c-upload_in_campaign_thumbnail_-_carousel.png" align="center" caption="Upload in Campaign thumbnail" border={true} />


5. **Add a Title**: The title will be displayed in bold and can be up to 200 characters long.

6. **Add a Description**: Enter the text message content, with a maximum limit of 1000 characters.

   - **For body text formatting**:

     - Adding Emojis: Copy from here and paste in the body.
     - Bold: Add asterisks (\*) at the beginning and end.
     - Italic: Add underscores (\_) at the beginning and end.
     - Strikethrough: Add tilde (\~) at the beginning and end.
     - Monospace: Add three consecutive backticks (\`\`\`) at the beginning and end.\ <br />


       <Image src="https://files.readme.io/a2eae90d9c3f3cc8ec416502299370b7efcfa68aacce12875b748cc22bb45cf0-title_and_description.png" align="center" caption="Title and Description" border={true} />


7. **Card Action**: Click **+** to add buttons to the card (up to 4 buttons per card). The following button types can be added:

   - [URL Redirect](doc:rcs-message-templates#url-redirect)
   - [Call Phone Number](doc:rcs-templates#call-phone-number)
   - [Quick Reply](doc:rcs-templates#quick-reply)
   - [Send Location to User](doc:rcs-templates#send-location-to-user)
   - [Get User Location](doc:rcs-templates#get-user-location)
   - [Calendar Event](doc:rcs-templates#calendar-event) \ <br />


     <Image src="https://files.readme.io/7a7047b7183662823d8adba00d0e6486cfd26ca3e8383a2321b4365dc326ee7a-buttons.png" align="center" caption="Buttons" border={true} />


<br />