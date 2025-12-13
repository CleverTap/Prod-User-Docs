---
title: Image Specifications WIP do not share
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
#Introduction 

These are CleverTap recommendations to help you render your messages correctly. While we do specify images on the application window these are a recommendation for each channel to help you find your image sweet spot. 
[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "Content must always be center heavy, otherwise some devices may crop the images from edges. The file size is available on the UI"
}
[/block]
#Push Notifications
  * Supported file types are PNG, JPG, GIF (only iOS).


##Push notifications for Android 
  * Aspect ratio: 2:1
  * Max size - 40 KB
  * Recommended Size - 1080px X 540px
  * Supported types - .png, .jpg, .jpeg

##Push notifications for iOS 
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
  "cols": 3,
  "rows": 2
}
[/block]

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
      "caption": "Media sizes supported by iOS"
    }
  ]
}
[/block]
##In-APP 
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
Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color)  

###Cover

  * Aspect Ratio - 2:1
  * Recommended Size for iPhone and Android - Width 1600px Height 3465px 
  * Recommended Size for iPad - Width 1600px Height 2134px 

####Android
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
[block:parameters]
{
  "data": {
    "h-0": "Device Screen",
    "h-1": "Crop Factor",
    "0-1": "None <<@aditi to verify>>",
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
      "caption": "iPhone Devices Crop Factor"
    }
  ]
}
[/block]

####**iPad Cover**
Recommended Size - Width 1600px Height 2134px 
Crop Factor - None

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1014e66-Image_Size_InApp_Cover_iPAD.png",
        "Image_Size_InApp_Cover_iPAD.png",
        469,
        607,
        "#ded1ca"
      ]
    }
  ]
}
[/block]
###Interstitial
  * Supported File type - video, audio, gif
  * Recommended size - Width 1600px Height 2850px

####Image

Aspect ratio: 1 : 1.7812
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
####iPad Interstial
Recommended Size - Width 1600px Height 2134px 
Crop Factor - None
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/aec83f8-Image_Size_InApp_Interstitial_iPAD.png",
        "Image_Size_InApp_Interstitial_iPAD.png",
        362,
        456,
        "#dcd0c9"
      ]
    }
  ]
}
[/block]
####Image with Content
* Aspect ratio: 16:9
* Recommended size: <<Mihir to Provide>>
* Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color).
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

####Image

Recommended size - <<Mihir to Provide>>
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
####Content
<<Mihir is there supposed. to be content here ? Also, can we provide number of lines for content ?>>

Same as image <<sunil to change presentation>>


#####iPad
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/cf64716-Image_Size_InApp_Half_Interstitial_iPad.png",
        "Image_Size_InApp_Half_Interstitial_iPad.png",
        439,
        476,
        "#ebe5e0"
      ]
    }
  ]
}
[/block]
####Custom HTML
This depends on your custom template. 
 
###App Inbox


Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 
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

####Simple Message

##WhatsApp
 
<<@jay to confirm image sizes>>

##Web Push




[block:parameters]
{
  "data": {
    "h-0": "Browser",
    "h-1": "OS",
    "h-2": "Aspect Ratio",
    "0-0": "Chrome",
    "1-0": "Chrome",
    "2-0": "Chrome",
    "0-1": "macOS",
    "1-1": "Android",
    "2-1": "Windows",
    "3-0": "Firefox",
    "3-1": "macOS",
    "0-2": "N/A",
    "1-2": "2:1",
    "2-2": "360 ≥ x 240",
    "3-2": "N/A",
    "4-0": "Firefox <<@darshan do we support this?>>",
    "4-1": "Windows"
  },
  "cols": 3,
  "rows": 5
}
[/block]
##Web Popup / Exit intent


Max height - 400px. Width adjusts automatically.
[block:parameters]
{
  "data": {
    "h-0": "Browser",
    "h-1": "OS",
    "h-2": "Aspect Ratio",
    "0-0": "Chrome",
    "1-0": "Chrome",
    "2-0": "Chrome",
    "3-0": "Firefox",
    "0-1": "macOS",
    "1-1": "Android",
    "2-1": "Windows",
    "3-1": "macOS",
    "0-2": "N/A",
    "1-2": "2 : 1",
    "2-2": "360 ≥ x 240",
    "3-2": "N/A"
  },
  "cols": 3,
  "rows": 4
}
[/block]