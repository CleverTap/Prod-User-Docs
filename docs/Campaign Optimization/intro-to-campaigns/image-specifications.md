---
title: Image Specifications
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
#Overview 

These are CleverTap recommendations to help you render your messages correctly. While we specify image sizes on the application window, these are recommendations for each channel to help your image find a sweet spot. 
[block:callout]
{
  "type": "info",
  "title": "Content Tip",
  "body": "The content must always be center-heavy. If not, some devices may crop the images from the edges. The file size is available on the user interface."
}
[/block]
#Push Notifications
The supported file types are PNG, JPG, and GIF (only iOS).

##Android Push Notifications 
For Android, use the following guidelines:
  * Aspect ratio: 2:1
  * Maximum size: 40 KB
  * Supported types: PNG, JPG, and JPEG

##iOS Push Notifications 
For iOS push notifications, use the following guidelines:
[block:parameters]
{
  "data": {
    "h-0": "Orientation",
    "h-1": "Aspect Ratio",
    "h-2": "Recommended Size",
    "0-0": "Landscape",
    "1-0": "Portrait",
    "0-1": "16:9",
    "1-1": "1:1",
    "0-2": "1080px X 608px",
    "1-2": "720px x 720px"
  },
  "cols": 2,
  "rows": 2
}
[/block]
###Media File Sizes
The following media file sizes are supported by iOS: 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/c91b4e2-Screenshot_2020-06-23_at_8.16.22_PM.png",
        "Screenshot 2020-06-23 at 8.16.22 PM.png",
        792,
        528,
        "#fafbfc"
      ],
      "caption": "",
      "sizing": "full",
      "border": false
    }
  ]
}
[/block]
##In-App
For in-app, use the following guidelines:
[block:parameters]
{
  "data": {
    "h-0": "File Type",
    "h-1": "Maximum Size",
    "0-0": "Image",
    "1-0": "Audio (only for Interstitial)",
    "2-0": "Video (only for Interstitial)",
    "0-1": "500 KB",
    "1-1": "5 MB",
    "2-1": "50 MB"
  },
  "cols": 2,
  "rows": 3
}
[/block]
The supported file formats are JPG, JPEG, PNG, GIF, MP3, and MP4. PNGs convert to JPEG using selected background colors.

###Covers

For covers, the aspect ratio is 2:1.

####Android
For Android covers, use the following guidelines:
[block:parameters]
{
  "data": {
    "h-0": "Device Screen",
    "h-1": "Crop Factor",
    "0-0": "Android XXXHDPI",
    "1-0": "Android HDPI and XXHDPI",
    "1-1": "470px from top and bottom",
    "0-1": "307px from top and bottom",
    "2-0": "Android - XHDPI",
    "2-1": "563px from top and bottom"
  },
  "cols": 2,
  "rows": 3
}
[/block]
The following shows the Android devices' crop factor.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9cd213a-Image_Size_InApp_Cover_Android.png",
        "Image_Size_InApp_Cover_Android.png",
        1035,
        694,
        "#e2beba"
      ]
    }
  ]
}
[/block]
 ####iPhone
For iPhone covers, use the following guidelines:
[block:parameters]
{
  "data": {
    "h-0": "Device Screen",
    "h-1": "Crop Factor",
    "0-1": "None",
    "0-0": "iPhone X and above",
    "1-0": "iPhone 5 to 8",
    "1-1": "316px from top and bottom",
    "2-1": "632px from top and bottom",
    "2-0": "iPhone 4s"
  },
  "cols": 2,
  "rows": 3
}
[/block]
The following shows the iPhone devices' crop factor.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7818723-Image_Size_InApp_Cover_iOS.png",
        "Image_Size_InApp_Cover_iOS.png",
        1359,
        899,
        "#e3c8c2"
      ],
      "caption": ""
    }
  ]
}
[/block]

####iPad Cover
For iPad covers, use the following guidelines:
  * Aspect ratio: 1:1.3
  * Crop factor: None

###Interstitial
The supported file types are video, audio, and GIF.

####Image
The image aspect ratio is 1:1.7812.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d271eb4-Image_Size_InApp_Interstitial.png",
        "Image_Size_InApp_Interstitial.png",
        1049,
        596,
        "#e1d2cd"
      ]
    }
  ]
}
[/block]
####iPad Interstitial
The aspect ratio is 1:1.26.

####Image with Content
For an image with content, use the following guidelines:
* Aspect ratio: 16:9
* Supported file formats: JPG, JPEG, PNG, GIF, MP3, MP4

PNGs convert to JPEG using selected background colors.
[block:parameters]
{
  "data": {
    "h-0": "File Type",
    "h-1": "Maximum  Size",
    "0-0": "Image",
    "0-1": "500 KB",
    "1-0": "Audio",
    "1-1": "5 MB",
    "2-0": "Video",
    "2-1": "50 MB"
  },
  "cols": 2,
  "rows": 3
}
[/block]
###Half Interstitial 

This section covers specifications for half interstitials options.

####Image
For an image, use the following guidelines:
[block:parameters]
{
  "data": {
    "0-0": "Image",
    "1-0": "Header",
    "2-0": "Footer",
    "h-1": "Aspect Ratio",
    "h-0": "Image and Position",
    "0-1": "1:1.3513",
    "1-1": "1:1",
    "2-1": "1:1"
  },
  "cols": 2,
  "rows": 3
}
[/block]

#####iPad
For iPad, the aspect ratio is 1:1.35.

####Custom HTML
This depends on your custom template. 
 
###App Inbox
For app inbox, the supported file formats are JPG, JPEG, PNG, GIF, MP3, and MP4.

More aspect ratios include:
[block:parameters]
{
  "data": {
    "h-0": "Orientation",
    "h-1": "Aspect Ratio",
    "0-0": "Portrait",
    "0-1": "1:1",
    "1-0": "Landscape",
    "1-1": "16:9"
  },
  "cols": 2,
  "rows": 2
}
[/block]

[block:parameters]
{
  "data": {
    "h-0": "File Type",
    "h-1": "Maximum Size",
    "0-0": "Image",
    "0-1": "500 KB",
    "1-0": "Audio",
    "2-0": "Video",
    "2-1": "50 MB",
    "1-1": "5 MB"
  },
  "cols": 2,
  "rows": 3
}
[/block]

##Web Push
For web push, the aspect ratio is 2:1. 

###Supported Browsers
We support the following browsers:
  * Chrome 
  * Firefox
  * Safari 

##Web Pop-up/Exit Intent
For web pop-up and exit intent, use the following guidelines:
  * Aspect ratio: 1.12:1 
  * Maximum height: 400px 

The aspect ratio remains constant. While the image width is 80% of the overall container, the width adjusts automatically.