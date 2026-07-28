---
title: Push Templates
excerpt: Learn how to use push templates in the Content Manager.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview&#x20;

You can create, manage, and reuse push notification templates directly from the Content Manager. Push templates let you define reusable structures for push notifications, which can then be applied across campaigns, journeys, and bulletins, ensuring consistent messaging and faster campaign setup.

To access Push Templates, go to _Content Manager_ > _Templates_ > _Push_. The listing displays all saved push templates for your account.


<Image src="https://files.readme.io/8ce6a3906357e8d96b9ff73ff237e7ce7e49ac089be1967782583302c7a34029-2026-07-27_14-52-49.jpg" alt="Push Templates" align="center" caption="Push Templates" border={true} />


## Create Template

To create a template:

1. Go to _Content Manager_ > _Templates_ > _Push_.

2. Click **Create Template**.

3. On the _Select a template_ screen, select **Layouts** from the left panel. Under _Builders_, choose a template type as follows. You can also select a _Pre-built_ template which features a collection of templates previously created by users and saved to your account's Content Manager.
   - **Standard**: Basic push notification with title and message.
   - **Advanced**: Rich push with expanded content and media.
   - **Auto Carousel**: Automatically cycling image carousel.
   - **Timer**: Push notification with a countdown timer.
   - **Text over Image**: Text overlaid on a full-width image.
   - **Vertical Image with CTA**: Vertical layout with an image and call-to-action button. This layout is released in Private Beta.


<Image src="https://files.readme.io/9f1a469a3caf6506165c8e87c24335b5fc714573d4bc5bef631f37ff881c2820-image.png" alt="Create Template" align="center" caption="Select a Template" border={true} />


4. Fill in the template fields (title, message, image, deep link, and so on) in the push composer. Required fields follow the same validation rules as the push campaign composer. For more information, refer to [Push Editor.](https://docs.clevertap.com/docs/push-editor)
5. Click **Save Template**. After saving, the template appears in the Push listing with its name, type, and creation date.

<Callout icon="📘" theme="info">
  ### Template Names

  Template names can include letters, numbers (0–9), underscores (\_), periods (.), hyphens (-), and spaces. Names must begin with a letter and must be unique.
</Callout>

You can also save the Push Template directly from engagements. In the new push campaign, navigate to the _What_ section. Click **Go to Editor**. Fill in the template fields and click **Save Template**.


<Image src="https://files.readme.io/94e2b0ad8184c634e18fc217f394a5a3731193c3f7021aa07e94588234bd40a7-image.png" align="center" caption="Save Template from Campaign Editor" border={true} />


## Filter Templates

You can filter the Pre-built push templates to narrow down your search.

1. Navigate to _Content > Content Manager > Templates_ > _Push_. Click **Create Template**.


<Image src="https://files.readme.io/09fd1cea5991f58269f0c77cbbc9156b2cc28e51d0e9f1ab76287d39c5185205-2026-07-27_14-31-46.jpg" align="center" caption="Filter Templates" border={true} />


2. Go to the _Pre-built_ template section and click the ![](https://files.readme.io/ac0ed6a-Filter_icon.png) icon. The Filter Campaigns window opens on the left side of the screen. You can filter templates based on the following criteria:

- _Time Period_: Filter and search by the template's creation period.
- _Created by_: Filter and search by the person who created the template.
- _Labels_: Filter and search the template by the assigned label.
- _Type_: Filter and search by the template type: Standard, Advanced, Auto Carousel, Timer, Text over Image, and Vertical Image.

3. Click **Clear Filters** to reset all applied filters.

## Use Push Templates in Campaigns

When creating a push campaign, you can select a saved CMS push template instead of building from scratch:

1. In the new push campaign, navigate to the _What_ section. Click **Go to Editor**.
2. Switch to the **Pre-built** tab to view your saved push templates.
3. Search, filter, or browse to find the right template.


<Image src="https://files.readme.io/15ccc6f47088a8bd05a0776f475881a56f2f492728d40cff3708b3281578d40d-2026-07-27_15-05-18_1.gif" align="center" caption="Use Pre-built Push Templates in Campaigns" border={true} />


4. Select a template. The composer auto-populates with the saved content such as title, message body, media, deep links, and other fields.
5. Edit any fields as needed before sending or scheduling the campaign.

<Callout icon="📘" theme="info">
  ### Note

  Users with read-only access to Templates can view, preview, and apply push templates in campaigns, but cannot modify or save changes back to the Content Manager.
</Callout>

<br />
