---
title: Image Specifications
excerpt: ''
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

These are CleverTap recommendations to help you render your messages correctly. While we specify image sizes on the application window, these are recommendations for each channel to help your image find a sweet spot.

> 📘 Content Tip
>
> The content must always be center-heavy. If not, some devices may crop the images from the edges. The file size is available on the user interface.

# Push Notifications

The supported file types are PNG, JPG, and GIF (only iOS).

## Android Push Notifications

For Android, use the following guidelines:

* Aspect ratio: 2:1
* Maximum size: 40 KB
* Supported types: PNG, JPG, and JPEG

## iOS Push Notifications

For iOS push notifications, use the following guidelines:

| Orientation | Aspect Ratio |
| :---------- | :----------- |
| Landscape   | 16:9         |
| Portrait    | 1:1          |

### Media File Sizes

The following media file sizes are supported by iOS:

<Image align="center" alt={792} border={true} caption="Media File Sizes Supported by iOS" title="Media file sizes supported by iOS" src="https://files.readme.io/c91b4e2-Screenshot_2020-06-23_at_8.16.22_PM.png" width="100%" />

## In-App

For in-app, use the following guidelines:

| File Type                     | Maximum Size |
| :---------------------------- | :----------- |
| Image                         | 500 KB       |
| GIF (only for Interstitial)   | 500 KB       |
| Audio (only for Interstitial) | 5 MB         |
| Video (only for Interstitial) | 50 MB        |

The supported file formats are JPG, JPEG, PNG, GIF, MP3, and MP4. PNGs convert to JPEG using selected background colors.

> 📘 Video Messages
>
> When adding video messages to In-App, ensure an audio track is always present.  
> If required, insert a blank audio track to the video.

### Covers

For covers, the aspect ratio is 2:1.

#### Android

For Android covers, use the following guidelines:

| Device Screen           | Crop Factor               |
| :---------------------- | :------------------------ |
| Android XXXHDPI         | 307px from top and bottom |
| Android HDPI and XXHDPI | 470px from top and bottom |
| Android - XHDPI         | 563px from top and bottom |

The following shows the Android devices' crop factor.

<Image align="center" alt={1035} border={true} caption="Android Devices' Crop Factor" title="Android devices' crop factor" src="https://files.readme.io/9cd213a-Image_Size_InApp_Cover_Android.png" />

#### iPhone

For iPhone covers, use the following guidelines:

| Device Screen      | Crop Factor               |
| :----------------- | :------------------------ |
| iPhone X and above | None                      |
| iPhone 5 to 8      | 316px from top and bottom |
| iPhone 4s          | 632px from top and bottom |

The following shows the iPhone devices' crop factor.

<Image align="center" alt={1359} border={true} caption="iPhone Devices' Crop Factor" title="iPhone devices' crop factor" src="https://files.readme.io/7818723-Image_Size_InApp_Cover_iOS.png" />

#### iPad Cover

For iPad covers, use the following guidelines:

* Aspect ratio: 1:1.3
* Crop factor: None

### Interstitial

The supported file types are video, audio, and GIF.

#### Image

The image aspect ratio is 1:1.7812.

<Image align="center" alt={1049} border={true} caption="Image Aspect Ratio" title="Image Aspect Ration" src="https://files.readme.io/d271eb4-Image_Size_InApp_Interstitial.png" />

#### iPad Interstitial

The aspect ratio is 1:1.26.

#### Image with Content

For an image with content, use the following guidelines:

* Aspect ratio: 16:9
* Supported file formats: JPG, JPEG, PNG, GIF, MP3, MP4

PNGs convert to JPEG using selected background colors.

| File Type | Maximum  Size |
| :-------- | :------------ |
| Image     | 500 KB        |
| GIF       | 500 KB        |
| Audio     | 5 MB          |
| Video     | 50 MB         |

### Half Interstitial

This section covers specifications for half interstitial options.

#### Image

For an image, use the following guidelines:

| Image and Position | Aspect Ratio |
| :----------------- | :----------- |
| Image              | 1.30:1       |
| Header             | 1:1          |
| Footer             | 1:1          |

##### iPad

For iPad, the aspect ratio is 1:1.35.

### Custom HTML

This depends on your custom template. You can also add images, GIFs, and videos to your HTML code.

## App Inbox

The supported file formats for App Inbox are JPG, JPEG, PNG, GIF, MP3, and MP4.

More aspect ratios include:

| Orientation | Aspect Ratio |
| :---------- | :----------- |
| Portrait    | 1:1          |
| Landscape   | 16:9         |

| File Type | Maximum Size |
| :-------- | :----------- |
| Image     | 500 KB       |
| GIF       | 500 KB       |
| Audio     | 5 MB         |
| Video     | 50 MB        |

> 📘 Video Messages
>
> When adding video messages to App Inbox, ensure an audio track is always present. If required, insert a blank audio track to the video.

## Web Push

For web push, the aspect ratio is 2:1.

### Supported Browsers

We support the following browsers:

* Chrome
* Firefox
* Safari

## Web Pop-up/Exit Intent

For web pop-up and exit intent, use the following guidelines:

* Aspect ratio: 1.12:1
* Maximum height: 400px

The aspect ratio remains constant. While the image width is 80% of the overall container, the width adjusts automatically.

## WhatsApp

| Media Type | File Size | Mime type        | Recommended Aspect Ratio |
| :--------- | :-------- | :--------------- | :----------------------- |
| Images     | 500 KB    | .png, .jpg, jpeg | 1.91:1                   |
| Videos     | 2MB       | .mp4             | 1.91:1                   |
| Document   | 2MB       | .pdf             | NA                       |
