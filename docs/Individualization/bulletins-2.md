---
title: Bulletins_WIP hackathon
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
REVIEW EXISTING LIVE PAGE AND ASSESS WHAT INFO CAN BE INCORPORATED FROM THE HACKATHON COPY.

Bulletins
Use Case (E-Commerce) - Price Drop (Single Product) How-to
Step 1: Define your business event and event properties

If you are unsure of the properties to add, you should include those event properties basis which you would want to map interest (Product ID and Product Name in the e.g. below) or  you want to personalize your communication (title, body, deeplink, etc) in the WHAT section is what you should usually list down. Press Enter to add a business event property.

Business Event Name: Price Drop
Business Event Properties: 
Product Name/ID
Brand Name
Title
Body
Deeplink
Image


[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Important points to note here
Once you save this Business Event - you can not REMOVE any of the properties - you can only ADD. 
When firing the API call (for the business event) you will need to ensure that all your properties are listed - else you will get an error message. 
The keys are all case-sensitive.
Step 2(Optional): Set a goal

Set the goal that you want the user to achieve. This could be Charged (product ID) for a Price Drop or Back in stock use case for e-commerce or Video Watched(Show ID/Episode ID) for an OTT.

Important points to note here

The GOAL that you set for your Business event works differently than a conversion event on a campaign.
While in a normal campaign - the conversion event is considered AFTER the PN is fired.
In the case of Bulletins the GOAL will be checked on the user's profile PREEMPTIVELY - and he will be accordingly excluded from the Bulletin.

Goal achieved users and bulletin qualified users are calculated independently. We later subtract the goal set from the bulletin set. Save the goal and move on to creating an interest segment

Step 3: Define Interest Segment
Now in this segment you will choose to map the Business Event Property basis which you want to send out the Bulletins. 
For an OTT this would be Genre or Show ID or Actor, etc and for an E-commerce it would be product ID/ Name.

You will map it to a user’s event. For OTT this event would be Video Watched. Select an event property from the dropdown menu. The value of the property needs to match the business event property. This is important to ensure that you create the correct Interest Segments. 
[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Points to note here:

You can use a User property as well instead of Event but again the rule applies that you need to ensure the values in these keys should match. 
You can add additional event property filters as well to the single event. So say for e.g. for an E-Commerce platform there is a price drop on all Adidas shoes and you want to reach out to all those who have viewed an adidas shoe. But currently in your event: Product Viewed - we generally see brands pass brand name and category seperately. You would do the following:
User Event 1
Product Viewed (filter by Brand: Adidas)
match the value of property CATEGORY with CATEGORY. 
This would basically create an interest segment of all those users who did a product view where Brand was Adidas. 

Step 4: Create a message
Let us break it down into two options:

Option 1: I want to create one static message and that goes out always whenever I fire an API call. 
In this case you would create a normal message (title/body/image/deep link etc). This is like you would do for any campaign of any type. 


[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Option 2: I want to change Title/Message/Deep Link/ Image URL every time I fire the business event according to the product. Can this be done?

The answer is yes. If you scroll back to when we created the Business Event Properties, we had added the following:  title, body, deeplink, image with the business event. We will treat them as the name suggests, individually as a Personalization for your message. After this you can go ahead and complete the create message steps as done regularly. This ends all work required from the dashboard end. See screenshot below:

[block:image]
{
  "images": [
    {
      "image": []
    }
  ]
}
[/block]
Step 5: Raise API for Business Event


{
    "business_event" : "Price Drop",
    "name" : "Adidas Men’s Originals",
    "properties" : {
        "Product ID" : "123456”,
        “Brand Name”: “CleverTap”
        "title":"PRICE DROP on CleverTap Men’s Tee",
        "body":"Available for only 399, shop now!",
        "deeplink":"https://www.clevertap.com/",
        "Image": "https://images.clevertap.jpg"
    },
    "when": "now",
    "c-by" : "admin@clevertap.com"
}




Important Points to Note:

C-BY needs to be an ADMIN on the CT dashboard
All the Business Event properties need to be in the payload or else you will get an error message for the same. 
Event keys are limited to 120 characters and property values are limited to 512 bytes. 
The channels supported with bulletins are only Push, Email, SMS, web push as other channels require online actions and will not be triggered by API events.
Global campaign limits apply to bulletins by default.
CleverTap only supports the string data type for mapped property values.

Use Case (OTT) - New GOT Episode How-to
Repeat the steps to implement the use case above, the business event example is listed below.

Business Event Name: New Episode
Business Event Properties: 
Show Name
Genre
title
body
deeplink
image

Interest Segment defined:
Time frame: Last 30 days
From segment: All Users
Business event property: Show Name
User event 1
Video Viewed
Show Name equals $$Show Name$$


Raise a Business Event via API


{
    "business_event" : "New Episode",
    "name" : "Game of Thrones Episode",
    "properties" : {
        "Show Name" : "Game Of Thrones”,
        “Genre”: “Drama”
        "title":"New Game of Thrones episode out!",
        "body":"Watch now to find out who dies today",
        "deeplink":"https://www.clevertap.com/",
        "image": "https://images.got.jpg
    },
    "when": "now",
    "c-by" : "admin@clevertap.com"
}