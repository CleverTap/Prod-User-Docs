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
# Introduction 

These are CleverTap recommendations to help you render your messages correctly. While we do specify images on the application window these are a recommendation for each channel to help you find your image sweet spot. 

> 📘 Tip
>
> Content must always be center heavy, otherwise some devices may crop the images from edges. The file size is available on the UI

# Push Notifications

* Supported file types are PNG, JPG, GIF (only iOS).

## Push notifications for Android 

* Aspect ratio: 2:1
* Max size - 40 KB
* Recommended Size - 1080px X 540px
* Supported types - .png, .jpg, .jpeg

## Push notifications for iOS 

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Orientation
      </th>

      <th>
        Aspect Ratio
      </th>

      <th>
        Recommended Size
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

      <td>
        1080px X 608px
      </td>
    </tr>

    <tr>
      <td>
        Portrait
      </td>

      <td>
        1:1
      </td>

      <td>
        720px x 720px
      </td>
    </tr>
  </tbody>
</Table>

<Image title="Screenshot 2020-06-23 at 8.16.22 PM.png" alt={792} src="https://files.readme.io/c91b4e2-Screenshot_2020-06-23_at_8.16.22_PM.png">
  Media sizes supported by iOS
</Image>

## In-APP 

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

Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color)  

### Cover

* Aspect Ratio - 2:1
* Recommended Size for iPhone and Android - Width 1600px Height 3465px 
* Recommended Size for iPad - Width 1600px Height 2134px 

#### Android

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

![1035](https://files.readme.io/9cd213a-Image_Size_InApp_Cover_Android.png "Image_Size_InApp_Cover_Android.png")

 \####iPhone

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
        None \<\<@aditi to verify>>
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

<Image title="Image_Size_InApp_Cover_iOS.png" alt={1359} src="https://files.readme.io/7818723-Image_Size_InApp_Cover_iOS.png">
  iPhone Devices Crop Factor
</Image>

#### **iPad Cover**

Recommended Size - Width 1600px Height 2134px\
Crop Factor - None

![469](https://files.readme.io/1014e66-Image_Size_InApp_Cover_iPAD.png "Image_Size_InApp_Cover_iPAD.png")

### Interstitial

* Supported File type - video, audio, gif
* Recommended size - Width 1600px Height 2850px

#### Image

Aspect ratio: 1 : 1.7812

![1049](https://files.readme.io/d271eb4-Image_Size_InApp_Interstitial.png "Image_Size_InApp_Interstitial.png")

#### iPad Interstial

Recommended Size - Width 1600px Height 2134px\
Crop Factor - None

![362](https://files.readme.io/aec83f8-Image_Size_InApp_Interstitial_iPAD.png "Image_Size_InApp_Interstitial_iPAD.png")

#### Image with Content

* Aspect ratio: 16:9
* Recommended size: {user["Mihir to Provide"]}
* Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 (.png's convert to .jpeg using selected background color).

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

#### Image

Recommended size - {user["Mihir to Provide"]}

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

#### Content

\<\<Mihir is there supposed. to be content here ? Also, can we provide number of lines for content ?>>

Same as image {user["sunil to change presentation"]}

##### iPad

![439](https://files.readme.io/cf64716-Image_Size_InApp_Half_Interstitial_iPad.png "Image_Size_InApp_Half_Interstitial_iPad.png")

#### Custom HTML

This depends on your custom template. 

### App Inbox

Supported file formats - .jpg, .jpeg, .png, .gif, .mp3, .mp4 

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

#### Simple Message

## WhatsApp

\<\<@jay to confirm image sizes>>

## Web Push

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Browser
      </th>

      <th>
        OS
      </th>

      <th>
        Aspect Ratio
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Chrome
      </td>

      <td>
        macOS
      </td>

      <td>
        N/A
      </td>
    </tr>

    <tr>
      <td>
        Chrome
      </td>

      <td>
        Android
      </td>

      <td>
        2:1
      </td>
    </tr>

    <tr>
      <td>
        Chrome
      </td>

      <td>
        Windows
      </td>

      <td>
        360 ≥ x 240
      </td>
    </tr>

    <tr>
      <td>
        Firefox
      </td>

      <td>
        macOS
      </td>

      <td>
        N/A
      </td>
    </tr>

    <tr>
      <td>
        Firefox \<\<@darshan do we support this?>>
      </td>

      <td>
        Windows
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

## Web Popup / Exit intent

Max height - 400px. Width adjusts automatically.

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Browser
      </th>

      <th>
        OS
      </th>

      <th>
        Aspect Ratio
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Chrome
      </td>

      <td>
        macOS
      </td>

      <td>
        N/A
      </td>
    </tr>

    <tr>
      <td>
        Chrome
      </td>

      <td>
        Android
      </td>

      <td>
        2 : 1
      </td>
    </tr>

    <tr>
      <td>
        Chrome
      </td>

      <td>
        Windows
      </td>

      <td>
        360 ≥ x 240
      </td>
    </tr>

    <tr>
      <td>
        Firefox
      </td>

      <td>
        macOS
      </td>

      <td>
        N/A
      </td>
    </tr>
  </tbody>
</Table>
