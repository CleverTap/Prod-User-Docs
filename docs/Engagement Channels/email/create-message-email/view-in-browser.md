---
title: Add View in Browser Link to Emails
excerpt: >-
  Learn how to add a View in Browser link to your email campaigns so recipients
  can open the email in a web browser, and how to track clicks on it.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The View in Browser feature lets your email recipients open the email in a web browser. This is useful when a recipient's email client does not render the email correctly, or when they want a full-page view of the content.

You can use this option when th&#x65;**&#x20;rendering breaks and content is clipped.** Some email clients strip certain styles or clip long emails such as newsletters and product announcements. The View in Browser link lets recipients open the full, correctly rendered version in a browser instead.

## Add View in Browser Link

Add the link to the body of your email in the campaign template you use.

<Tabs>
  <Tab title="Email with Rich Media">
    1. In the email body editor, place your cursor where you want the link to appear.
    2. Add View in Browser Link using any of the following ways:

       - Using Source Mode: You can add the link directly in source mode using the following HTML tag. Enter your link display text, for example, _View Email in Browser_.&#x20;
         ```html
         <a href="{{ SpecialLink['View In Browser'] | default: '|VIEW IN BROWSER|' }}">View Email in Browser</a>
         ```

       - Using `@` or `  {}  ` icon: Type `@` or click the `{}` icon, then select _Special Links_ from the list.&#x20;


         <Image src="https://files.readme.io/1053832efcc3878fd490a46d0314dee63e57becd36d5ea4e9eb2baa2f4f73954-Add_View_Email_in_Browser_Link_Rich_Media.gif" align="center" caption="Add View in Browser Link Using `@` or `  {}  ` icons" border={true} />


       - Using <img src="https://files.readme.io/bc809c4f2f96cd7e6f2f0a385b7af2d313dc8dcce8b5c9b0949b622547b12ab4-Link_icon.png" valign="middle" height="25"> icon: You can click the icon in the toolbar and add a View in Browser link in your campaign body, as follows:

         1. In the _Display text_ field, enter the link text, for example, `View Email in Browser`.&#x20;
         2. In the URL field, click the  `@` or `  {}  ` icon, then select **Special Links** from the list.
         3. Select _View In Browser_. The URL field populates with the special link.


         <Image src="https://files.readme.io/d2c382084f4b16bfa2e669dfbd0467f267b49de686203eaf90b78edfc3cb9f89-Add_View_in_Browser_Link_Using_Link_Icon.gif" alt="View in Browser addition to the Rich Media Template" align="center" caption="Add View in Browser Link using Link Icon" border={true} />


       The View in Browser link appears in the email body.
  </Tab>

  <Tab title="Email with Drag and Drop">
    1. On the canvas, click the text block where you want the link to appear, for example, a Text or Title block. The text toolbar opens. If the template has no text block, drag one from the CONTENT panel first.
    2. Click the block to open the text toolbar.
    3. In the toolbar, click **More**, then click **Personalized deeplink**. The dialog opens.
    4. In the _Display text_ field, enter the link text, for example, _Open this in Browser_.
    5. In the URL field, click`{}` or `@`, then select _Special Links_ from the list.
    6. Select _View In Browser_ and click **Add**.&#x20;


    <Image src="https://files.readme.io/325b1a79bc039e3712e58463e4cf1727adb19ca2206f2eee76efcc6d76be816c-View_in_Browser_Link_for_Drag__Drop.gif" align="center" caption="Add view in Browser Link for Drag & Drop Editor" border={true} />


    The View in Browser link appears in the text block.
  </Tab>

  <Tab title="Email with Custom HTML & AMP">
    Add the link to both the AMP HTML body and the HTML body. Recipients whose email client supports AMP see the AMP HTML body. All other recipients see the HTML body.

    1. In the AMP HTML Body tab, add a link tag where you want the link to appear, for example, <a href="*|VIEW IN BROWSER|*">View Email in Browser</a>.
    2. Place your cursor between the quotes after `href=`.
    3. Type @, select SpecialLinks, and select View In Browser.&#x20;
    4. Enter you link display text, for example, _Open Email in Browser_.

    Repeat steps _1_ through _4_ in the HTML Body tab.


    <Image src="https://files.readme.io/29cd8a92d5a81accbc6015f32698c1fb7447c8fed43767c63162c79a032d2eff-View_in_Browser_Link_for_AMP_Email.gif" alt="The AMP Template showing the unified View in Browser option" align="center" caption="Add Special Link to View AMP Email Campaign in Browser" border={true} />


    When a recipient clicks the link, the email opens in a new browser tab.


    <Image src="https://files.readme.io/320f65aeb366fc28fc9fe020306868d34425c2b4609ded42f79ea840e9f9e452-View_AMP_Cmapaign_in_Browser.gif" alt="Email opening in a new browser tab after the recipient clicks the View in Browser link" align="center" caption="View Email Campaign In Browser" border={true} />

  </Tab>
</Tabs>

<Callout icon="far fa-circle-info" theme="info">
  #### Send Test Personalization for View in Browser in Web Version

  If the test email uses profile property personalization, the web version shows the same values. In the case of event properties and linked content, it displays the default values set in your personalization tags.
</Callout>

# Tracking and Reporting

CleverTap tracks clicks on the View in Browser link and on the links inside the web version as **Notification Clicked** events. These clicks count toward the **Clicked** metric on the campaign **Stats** page and the [Click Heat Map](doc:email-campaign-stats-heatmap), and appear as **Notification Clicked** events on the user profile.

- **Clicks on View in Browser Link**: The `wzrk_c2a` property of the event holds the URL of the web version, so you can differentiate between these clicks and clicks on other links. For details, refer to [FAQs](doc:view-in-browser#how-do-i-differentiate-between-a-view-in-browser-click-and-a-regular-link-click).
- **Clicks on Links Inside Web Version**: CleverTap counts these clicks toward the main email campaign and records them the same way as clicks on the same links in the email. For more information, refer to [FAQs](doc:view-in-browser#how-do-i-know-whether-recipients-clicked-links-inside-the-web-version-of-the-email).
- **Opening Web Version**: Opening the web version does not record an additional **Notification Viewed** event. It does not count toward the **Viewed** metric on the campaign **Stats** page or appear on the user profile.

<Callout icon="far fa-circle-info" theme="info">
  #### Prerequisites for Tracking

  CleverTap tracks clicks by default. Clicks are not recorded in the following cases:

  - **Tracking Turned OFF for a Link**: You can turn off tracking for an individual link by adding data-track="off" to its `<a>` tag. The link still works in the web version, but CleverTap does not record clicks on it. For more information, refer to [Override Link Tracking](doc:override-link-tracking).
  - **Opted-out of Click Tracking**: Recipients who have opted out of click tracking, CleverTap does not record their clicks on the View in Browser link or on links inside the web version. For more information, refer to [Manage Email Tracking](doc:manage-email-tracking)​.
</Callout>

## FAQs

## How do I differentiate between a View in Browser click and a regular link click?

View in Browser clicks are recorded as **Notification Clicked** events where the `wzrk_c2a` property contains the hosted page URL (for example, `clevertap-pages.com/mails?p=...`). Regular link clicks have the actual destination URL in `wzrk_c2a`. To isolate View in Browser clicks, filter **Notification Clicked** events for the campaign where `wzrk_c2a` contains `clevertap-pages`, or use S3 exports for user-level analysis.&#x20;

The web version URL depends on the region of your account, as follows:

| Dashboard URL                                                                                                       | Region | Web version URL                                |
| ------------------------------------------------------------------------------------------------------------------- | ------ | ---------------------------------------------- |
| [https://eu1.dashboard.clevertap.com/](https://eu1.dashboard.clevertap.com/ "https://eu1.dashboard.clevertap.com/") | eu1    | `https://eu1.clevertap-pages.com/mails?p=...`  |
| [https://in1.dashboard.clevertap.com/](https://in1.dashboard.clevertap.com/)                                        | in1    | `https://in1.clevertap-pages.com/mails?p=...`  |
| [https://us1.dashboard.clevertap.com/](https://us1.dashboard.clevertap.com/)                                        | us1    | `https://us1.clevertap-pages.com/mails?p=...`  |
| [https://sg1.dashboard.clevertap.com/](https://sg1.dashboard.clevertap.com/)                                        | sg1    | `https://sg1.clevertap-pages.com/mails?p=...`  |
| [https://aps3.dashboard.clevertap.com/](https://aps3.dashboard.clevertap.com/)                                      | aps3   | `https://aps3.clevertap-pages.com/mails?p=...` |
| [https://mec1.dashboard.clevertap.com/](https://mec1.dashboard.clevertap.com/)                                      | mec1   | `https://mec1.clevertap-pages.com/mails?p=...` |

### How do I know whether recipients clicked links inside the web version of the email?

CleverTap records clicks on links inside the web version as **Notification Clicked** events, the same as clicks on those links in the email.

To analyze these clicks, filter **Notification Clicked** events for the campaign by the `wzrk_c2a` property from different sections on the dashboard; for example, you can create a funnel to see how many recipients clicked the View in Browser link in the email and then clicked on a specific link from the web version:

1. Go to _Analytics_ > _Funnels_.
2. For step 1, select **Notification Clicked**. Add a property filter where `wzrk_c2a` contains `clevertap-pages.com/mails`, and filter by campaign ID using `wzrk_id`.
3. For step 2, select **Notification Clicked** again. Filter by the same campaign, with `wzrk_c2a` set to the destination URL you want to measure.
4. Click **View Funnel**.

The funnel counts recipients who clicked View in Browser and then clicked the link.

### Does the web version show the same personalization as the email?

Yes, for profile properties, the web version shows the recipient's values for profile properties, Liquid logic based on those properties, and content blocks.&#x20;

Event properties from the triggering event and linked content instead show the default values set in your personalization tags in the web version.

### Why does the web version show different values from the email?

CleverTap renders the web version each time the recipient opens it. If a profile property changes after the email is sent, the web version shows the updated value.

### Do the unsubscribe and email preference center links work in the web version?

Yes, in a campaign send, they work the same as in the email. In a test email and its web version, these links do not unsubscribe the recipient.

### How does the View in Browser link work in a test email?

The web version of a test email shows the same profile property values as the test email. Event properties and linked content display the default values. Clicks on the link are not tracked, and the link expires after 7 days.

### How long is the View in Browser link available?

The View in Browser link is available until the campaign is archived. This applies to running, stopped, and completed campaigns. After a campaign is archived, the link displays a 404 page, including in emails that are already sent.

The View in Browser link in a test email expires after 7 days.
