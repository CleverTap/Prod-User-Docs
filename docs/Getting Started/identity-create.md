---
title: Identity Creation
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
#Identity Users
Setting an identity will help to identify your users. We recommend that you use the user email as an identity. However, you can also select the user's mobile number or a custom identity.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/390e974-Identity_Start.png",
        "Identity_Start.png",
        1039,
        1130,
        "#fafafb"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]
#Merge Profiles

We recommend that you do not use merge identifiers on the same device. If identifiers are merged on the device, then the profile properties of identifiers' profiles are merged and the different identifiers will not be treated as unique profiles. To avoid this case, on the same device we need to use the onUserLogion method when a new user with another identifier logs in.  However, you can choose to merge identities across devices. 

#Device Identifiers

We recommend that you use ADID (@ankita short desc) and IDFA (@ankita short desc) as device identifiers. You can also choose to use a custom device identifier. (@ankita, why)