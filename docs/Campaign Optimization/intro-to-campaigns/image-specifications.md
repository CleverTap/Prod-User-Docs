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

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Orientation
      </th>

      <th>
        Aspect Ratio
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Landscape
      </td>

      <td>
        16:9
      </td>
    </tr>

    <tr>
      <td>
        Portrait
      </td>

      <td>
        1:1
      </td>
    </tr>
  </tbody>
</Table>

### Media File Sizes

The following media file sizes are supported by iOS: 

<Image title="Screenshot 2020-06-23 at 8.16.22 PM.png" alt={792} width="100%" src="https://files.readme.io/c91b4e2-Screenshot_2020-06-23_at_8.16.22_PM.png" />

## In-App

For in-app, use the following guidelines:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        File Type
      </th>

      <th>
        Maximum Size
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Image
      </td>

      <td>
        500 KB
      </td>
    </tr>

    <tr>
      <td>
        Audio (only for Interstitial)
      </td>

      <td>
        5 MB
      </td>
    </tr>

    <tr>
      <td>
        Video (only for Interstitial)
      </td>

      <td>
        50 MB
      </td>
    </tr>
  </tbody>
</Table>

The supported file formats are JPG, JPEG, PNG, GIF, MP3, and MP4. PNGs convert to JPEG using selected background colors.

### Covers

For covers, the aspect ratio is 2:1.

#### Android

For Android covers, use the following guidelines:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Device Screen
      </th>

      <th>
        Crop Factor
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Android XXXHDPI
      </td>

      <td>
        307px from top and bottom
      </td>
    </tr>

    <tr>
      <td>
        Android HDPI and XXHDPI
      </td>

      <td>
        470px from top and bottom
      </td>
    </tr>

    <tr>
      <td>
        Android - XHDPI
      </td>

      <td>
        563px from top and bottom
      </td>
    </tr>
  </tbody>
</Table>

The following shows the Android devices' crop factor.

![1035](https://files.readme.io/9cd213a-Image_Size_InApp_Cover_Android.png "Image_Size_InApp_Cover_Android.png")

 \####iPhone\
For iPhone covers, use the following guidelines:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Device Screen
      </th>

      <th>
        Crop Factor
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        iPhone X and above
      </td>

      <td>
        None
      </td>
    </tr>

    <tr>
      <td>
        iPhone 5 to 8
      </td>

      <td>
        316px from top and bottom
      </td>
    </tr>

    <tr>
      <td>
        iPhone 4s
      </td>

      <td>
        632px from top and bottom
      </td>
    </tr>
  </tbody>
</Table>

The following shows the iPhone devices' crop factor.

![1359](https://files.readme.io/7818723-Image_Size_InApp_Cover_iOS.png "Image_Size_InApp_Cover_iOS.png")

#### iPad Cover

For iPad covers, use the following guidelines:

* Aspect ratio: 1:1.3
* Crop factor: None

### Interstitial

The supported file types are video, audio, and GIF.

#### Image

The image aspect ratio is 1:1.7812.

![1049](https://files.readme.io/d271eb4-Image_Size_InApp_Interstitial.png "Image_Size_InApp_Interstitial.png")

#### iPad Interstitial

The aspect ratio is 1:1.26.

#### Image with Content

For an image with content, use the following guidelines:

* Aspect ratio: 16:9
* Supported file formats: JPG, JPEG, PNG, GIF, MP3, MP4

PNGs convert to JPEG using selected background colors.

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        File Type
      </th>

      <th>
        Maximum  Size
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Image
      </td>

      <td>
        500 KB
      </td>
    </tr>

    <tr>
      <td>
        Audio
      </td>

      <td>
        5 MB
      </td>
    </tr>

    <tr>
      <td>
        Video
      </td>

      <td>
        50 MB
      </td>
    </tr>
  </tbody>
</Table>

### Half Interstitial 

This section covers specifications for half interstitials options.

#### Image

For an image, use the following guidelines:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Image and Position
      </th>

      <th>
        Aspect Ratio
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Image
      </td>

      <td>
        1:1.3513
      </td>
    </tr>

    <tr>
      <td>
        Header
      </td>

      <td>
        1:1
      </td>
    </tr>

    <tr>
      <td>
        Footer
      </td>

      <td>
        1:1
      </td>
    </tr>
  </tbody>
</Table>

##### iPad

For iPad, the aspect ratio is 1:1.35.

#### Custom HTML

This depends on your custom template. 

### App Inbox

For app inbox, the supported file formats are JPG, JPEG, PNG, GIF, MP3, and MP4.

More aspect ratios include:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Orientation
      </th>

      <th>
        Aspect Ratio
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Portrait
      </td>

      <td>
        1:1
      </td>
    </tr>

    <tr>
      <td>
        Landscape
      </td>

      <td>
        16:9
      </td>
    </tr>
  </tbody>
</Table>

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        File Type
      </th>

      <th>
        Maximum Size
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Image
      </td>

      <td>
        500 KB
      </td>
    </tr>

    <tr>
      <td>
        Audio
      </td>

      <td>
        5 MB
      </td>
    </tr>

    <tr>
      <td>
        Video
      </td>

      <td>
        50 MB
      </td>
    </tr>
  </tbody>
</Table>

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
