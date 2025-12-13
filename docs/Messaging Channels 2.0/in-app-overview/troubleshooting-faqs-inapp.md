---
title: Troubleshooting and FAQs
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
#FAQs 

## Q. I need to send an A/B test and multivariant campaigns. Do I need to update my SDK?
  * No, you do not need an SDK update.
  * You can create a custom HTML campaign for all your variants.
  * You cannot send template campaigns in that case.

## Q. I need to send crisp template campaigns. Do I need to update my SDK?
  * Yes, the new and improved templates only work with SDK version 3.3.0 and above.
  * You cannot send these campaigns on SDK versions below that.

## Q. My partial user base is on an old SDK and the rest are on new. How do I send them the same campaign?
  * To send a campaign, you will have to pick the legacy option.
  * This will open two variants of the campaign.
  * The *New In-App* will send the campaign to users on SDK version 3.3.0 and above.
  * The *Legacy In-App* will send the campaign to users on SDK version 3.2.x and below.
  * This legacy option will be available until March 31, 2019, and will be deprecated after this date.

## Q. When should I use the custom HTML builder?
  * If you have not upgraded to the SDK version 3.3.0 or above, your users will not receive the template-based campaigns. In this case, you will have to use the custom HTML builder.
  * If the templates provided (Cover, Interstitial, etc.) do not meet your business use case, you can create your own HTML.

## Q. How does my image get cropped?
  * We follow the center crop.
  * We scale the image uniformly (maintaining the image's aspect ratio) so that both dimensions (width and height) of the image will be equal to or larger than the corresponding dimension of the phone (minus padding). The image is then centered in the view. 

## Q. What size of media can I use?
  * Image: Less than 500 kb.
  * Audio: Less than 5 Mb.
  * Video: Less than 50 Mb.

## What is the character limit for my message?
[block:parameters]
{
  "data": {
    "h-1": "Title",
    "h-2": "Message",
    "h-0": "Language",
    "0-0": "English",
    "1-0": "Chinese",
    "1-1": "9",
    "1-2": "38",
    "0-1": "30",
    "0-2": "128"
  },
  "cols": 3,
  "rows": 2
}
[/block]
## Q. What is the Time to Live (TTL) for my message?
The default value for TTL is two days. You can define the TTL for a maximum of 28 days.