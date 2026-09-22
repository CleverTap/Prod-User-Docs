---
title: Linked Content
excerpt: Learn more about dynamic messaging with Linked Content.
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

Linked content allows you to personalize your messages with rich and contextual data that is available outside of the CleverTap platform. It helps you send messages with send-time personalization.

For example, you deliver food across different geographies, and you want to personalize offers to each user based on the weather of their location. The location can come from CleverTap personalization, and the weather information can come from a third-party API that provides the current weather. If you want to add more information, you can opt for any source, such as third-party tools and in-house software, to include in your message.

In a user scenario, you could have three users: one in New York, where it is snowing; one in San Francisco, where it is cloudy; and one in Miami, where it is sunny. You can add conditions in your messages to deliver messages according to the weather and location where the message will be something, such as:

* New York user - Since this user is probably staying in a cold region, you can send an offer to order piping hot food.
* San Francisco user - Since it is the weekend, this user may go out in the evening, so you send an offer for a dinner reservation at a nearby restaurant.
* Miami user - Since it is always sunny, you send an offer for a nearby barbeque restaurant.

This send-time personalization can help you cater to end-user requirements at send time and significantly increase your open rates.

<Callout icon="📘" theme="info">
  #### Note

  You can create _Linked Content_ using _Liquid Tags._ For more information, refer to [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags) before you begin.
</Callout>

You can use _Linked Content_ with the following engagement channels:

* Email
* Mobile Push
* SMS
* Webhooks
* WhatsApp
* Native Display

# Video Tutorial

You can watch the following video to learn more about Linked Content personalization.

<HTMLBlock>{`
<div
              style="
                position: relative;
                padding-bottom: 56.25%;
                height: 0;
                border-radius: 0;
                box-shadow: 0 15px 40px rgba(63,58,79,.3);
                overflow: hidden;
                min-width:320px"><iframe
              src="https://clevertap.portal.trainn.co/share/7TS9XZhkIYJhZzaiEiuq0w/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>

# Create Linked Content

You can get the data for send-time personalization from different APIs. API names are nicknames that you can assign to the provider APIs. You can call these anywhere in your message so that you do not have to mention the entire API name. For example, if the API fetches the weather information for a particular city. You can shorten the API endpoint URL   `http://api.example.com/weather-management/city-weather`  to just `Weather` as the API name. You can also [personalize the API endpoint URL](doc:linked-content-url-personalization#personalize-linked-content-url).

To. create API names:

1. Select _Settings_ > _Setup_ > _Linked Content_. The _Linked Content_ page displays.
2. Click the **+ Linked Content** button to call a new API. To edit the linked content, click the ellipsis menu, then click the edit icon.
3. Enter a name for the API.


<Image src="https://files.readme.io/65c4783-Linked_Content_API_Create.png" alt="1163" align="center" width="smart" caption="Create API Names" border={true} />


4. Enter all the relevant details, such as the access key and query parameters.

<Callout icon="📘" theme="info">
  #### Tip

  The API parameters are available with the API provider. Refer to their website or contact their support for API details.
</Callout>

5. Click the **Test Linked Content** link.
6. Enter the required details to test the API. If the input is correct, you will see a success message. The test response appears in the JSON response box. The following is an example response for the API name you entered:

```json
"request": {
    "type": "City",
    "query": "New York, United States of America",
    "language": "en",
    "unit": "m"
  },
  "location": {
    "name": "New York",
    "country": "United States of America",
    "region": "New York",
    "lat": "40.714",
    "lon": "-74.006",
    "timezone_id": "America/New_York",
    "localtime": "2020-04-22 12:44",
    "localtime_epoch": 1587559440,
    "utc_offset": "-4.0"
  },
  "current": {
    "observation_time": "04:44 PM",
    "temperature": 7,
    "weather_code": 113,
    "weather_icons": [
      "http://cdn.worldweatheronline.com/images/wsymbols01_png_64/wsymbol_0001_sunny.png"
    ],
    "weather_descriptions": [
      "Sunny"
    ],
    "wind_speed": 17,
    "wind_degree": 280,
    "wind_dir": "W",
    "pressure": 1012,
    "precip": 0,
    "humidity": 28,
    "cloudcover": 0,
    "feelslike": 4,
    "uv_index": 6,
    "visibility": 16,
    "is_day": "yes"
  }
}
```

<Callout icon="📘" theme="info">
  #### Note

  The response format is always JSON.
</Callout>

7. You can choose to add each API object manually or click _Auto-fill Objects_ with the API response. All the objects are listed with their label names. If required, you can change the label names here. These labels are available at the time of campaign creation.


<Image src="https://files.readme.io/8174ccf-Dynamic_Content_API.png" alt="1192" align="center" width="smart" caption="Add API Objects" border={true} />


8. Click **Test and save changes** to save all the API changes.

<Callout icon="📘" theme="info">
  #### Encoding Error

  If you encounter encoding errors in your API response due to non-English characters, add the `charset=utf-8` parameter to your endpoint.


  <Image src="https://files.readme.io/cc268ec-image.png" align="center" width="75% " border={true} />

</Callout>

# Personalize Linked Content URL

You can dynamically generate URLs that contain parameters based on the user's preferences or interactions. For example, if there is an API that fetches information for a particular city. Instead of setting up multiple Linked Content endpoint URLs to fetch weather updates from different locations, we can set up a single endpoint URL by personalizing the endpoint URL. In this case, the endpoint URL will be as follows: `https://api.example.com/weather-management?location-name={{locname}}&location-weather={{locweather}}`


<Image src="https://files.readme.io/7dab31c-Example_for_Linked_Content_URL_Personalization.png" alt="Example for Linked Content URL Personalization" align="center" caption="Example for Linked Content URL Personalization" border={true} />


The endpoint URL consists of the following parameters:

* **Path Parameter**: These parameters help specify variable parts of the URL path, allowing APIs to target specific resources or actions dynamically based on the values provided within the URL path itself. Path parameter, when present in the endpoint URL, becomes a mandatory parameter. So, you can include the path parameter as shown in the following image:


<Image src="https://files.readme.io/1c6e77f-Example_for_Path_Parameters.png" alt="Path Parameter Example" align="center" caption="Path Parameter Example" border={true} />


* **Query Parameters**: Query parameters are key-value pairs appended to the end of a URL that provides additional information to an API endpoint. They are used to modify the behavior or content returned by the server. Query parameters are separated from the base URL by a question mark (?), and multiple parameters are separated by an ampersand (&). If we refer to the following image, the query parameters will be: `articletopic` and `user`.


<Image src="https://files.readme.io/70cddc9-image.png" alt="Query Parameters Example" align="center" caption="Query Parameters Example" border={true} />


In the above image, only the values are personalized in the query parameters. You can even personalize the keys in the query parameters. For example, a user is accessing a movie recommendation API, and the API allows for personalized queries based on the user's preferences and location. In this case, the endpoint URL can be `https://movie-recommendation-api.com/recommendations?{{genrename}}={{genre}}&{{location}}={{place}}`. So, the keys and values change based on user input or data stored in a user profile, allowing the API to deliver personalized recommendations tailored to the individual's genre preference and location.


<Image src="https://files.readme.io/2fab433-Personalize_Both_Keys_and_Values_in_Query_Parameters.png" alt="Personalize Both Keys and Values in Query Parameters" align="center" caption="Personalize Both Keys and Values in Query Parameters" border={true} />


# Linked Content Request Body Personalization

In addition to personalizing URLs, Linked Content also supports dynamic personalization of the request body. This is especially useful for POST APIs that require user-specific details, such as identity, eligibility, or category, to be sent as part of the payload.

Currently, body personalization for Linked Content is available for the following channels: Push, Email, Web Push, Webhook, and Native Display.

### Example

Consider an OTT platform wants to fetch personalized content recommendations based on:

- The user’s region and language (passed in the URL), and
- The user’s subscription plan and viewing preferences (passed in the request body).

**Linked Content Endpoint URL**

```
[https://movie-recommendation-api.com/recommendations?\{\{genrename}}=\{\{genre}}&\{\{location}}=\{\{place}}](https://movie-recommendation-api.com/recommendations?\{\{genrename}}=\{\{genre}}&\{\{location}}=\{\{place}})
```

**Request Body with Linked Content Placeholders**

```json
{
  "userId": "{{identity}}",
  "subscriptionPlan": "{{Profile.plan_type}}",
  "preferredGenre": "{{Profile.favorite_genre}}"
}
```

When the request is sent, Linked Content automatically replaces these placeholders with real user data. The OTT recommendation service then uses this personalized payload to return content that is relevant to each viewer.

<Callout icon="📘" theme="info">
  #### Note

  - For inaction campaigns with a delay greater than 24 hours, event personalization is available when the campaign is configured for multiple occurrences. Each message is personalized with the event properties of the respective triggering event. For more information on using a constant event property, refer to [Constant Event Property](doc:constant-property).
  - For single-occurrence inaction campaigns with a delay greater than 24 hours, event personalization is not supported and default values are used.
  - The following personalization inputs are supported when used inside the Linked Content body:
    - Profile Properties
    - Identity
    - Campaign ID
    - Event Personalization
    - External Trigger Properties
    - Send Test Personalization (in Push)
</Callout>

# Map APIs

The APIs must be mapped to the campaign from the _What_ section. After the APIs are mapped, you can use them in the email body using [liquid tags](https://docs.clevertap.com/docs/liquid-tags). The sample scenario below shows how to create an email campaign using liquid tags and linked content.

1. [Create an Email Campaign](https://docs.clevertap.com/docs/create-message-email).
2. Select the _New email with rich media_ template.
3. From the [What](https://docs.clevertap.com/docs/email#section-step-4-define-the-what) section, click ![](https://files.readme.io/d946c02-personalization_icon.png) icon. The _Personalization Setup_ window displays.


<Image src="https://files.readme.io/17bef81-Click_Personalization_icon.png" alt="2876" align="center" caption="Create Personalized Email" border={true} />


4. Select your APIs from the list under the _Linked Content_ tab.


<Image src="https://files.readme.io/e1a6472-Linked_Content.png" alt="1896" align="center" caption="Select APIs from Linked Content" border={true} />


5. Map the API parameters to the user and event properties, or add custom parameters. Here, we map the query parameter that fetches weather information based on the user location with the help of the profile property _Location_. This means that each user is sent an offer based on their location.


<Image src="https://files.readme.io/6011741-Map_Linked_Content.png" alt="1898" align="center" width="smart" caption="Map Linked Content" border={true} />


<Callout icon="📘" theme="info">
  ### Mapping Custom Fields

  You can also use liquid tags for personalization when mapping customer properties for an External Trigger Campaign. You can access this feature only if you have External Trigger enabled for your account.


  <Image src="https://files.readme.io/1bcf690-Mapping_Custom_Fields.gif" alt="Mapping Custom Fields Using Liquid Tags" align="center" caption="Mapping Custom Fields Using Liquid Tags" border={true} />

</Callout>

6. Click **Apply** to save the mapping.

We are now ready to start writing Linked Content.

# Use Labels

You can write linked content with labels. There are two types of labels that you can use in your linked content.

* Custom Labels - These are labels you can create yourself. For example, a password or authorization key.
* System Labels - These are default labels you can use to analyze API responses.

## Custom Labels

The API response will provide you with a set of object labels. However, if you want additional personalization, you can create custom labels during the creation and editing of [APIs](https://docs.clevertap.com/docs/linked-content#section-create-edit-namespaces). These will not be part of the API response.

## System Labels

These are CleverTap labels that are available by default. You can use them to gauge the health of your API and check whether the responses are received correctly.

| System Labels    | Description                                                                                               |
| :--------------- | :-------------------------------------------------------------------------------------------------------- |
| raw              | This is a raw API response.                                                                               |
| JSON             | This is the raw response parsed as JSON.                                                                  |
| http_status_code | This is the HTTP status code to identify errors, such as, 404 (not found), 401 (unauthorized), and so on. |
| headers          | These are response headers.                                                                               |

# Arrays in API

The response from an API may have arrays with nested JSON.

```json Example Response
"restaurants_info": [
    { 
        "id": "16769241",
        "name": "Junior's Restaurant",
        "user_rating": {
            "aggregate_rating": "4.7",
            "rating_text": "Excellent",
            "votes": "538"
     }      
    },
  
    {
        "id": "16763460",
        "name": "Cookshop",
        "user_rating": {
           "aggregate_rating": "4.6",
           "rating_text": "Excellent",
           "votes": "252"
        }
    }
]
```

You can create conditions based on this array. For example, the response above has an array called `restaurants`. This array contains items under it such as id, name, rating. Notice the object `user_rating`. It is a nested object that contains an aggregate rating of the restaurant, rating text from an actual user, number of votes, and so on. You can use the array in the following manner:

```liquid Array list
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
```

The output will be something similar to the following text:

```text Output - Array list
Marta has a rating  Excellent
PN Wood Fired Pizza  Excellent
PQR Very Good
&pizza   Good
Leonelli Focacceria e Pasticceria Good
```

# Create Message

After you have created and saved the APIs, use the linked content in your campaigns. It is recommended that you familiarize yourself with [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags) before you start writing Linked Content.<br />The syntax for writing linked content is `Linked.APIName.label`. In our previous user scenario, we had three users, one in New York, where it was snowing, one in San Francisco, where it was cloudy, and one in Miami, where it was sunny. You can add conditions in your messages to deliver messages according to the weather and zip code. So, you can plan the following message:

* New York user - Since this user is probably staying in, you send an offer for ordering piping hot food.
* San Francisco user - Since it is the weekend, this user may go out in the evening, so you send an offer for a dinner reservation at a nearby restaurant.
* Miami user - Since it is always sunny, you send an offer for a nearby barbecue restaurant.

The following is what a written personalized linked content for your users may look like:

```liquid
Hi {{ Profile.name | default:"there!" }},

{% if Linked.cityBasedWeather.temp > 30 %}
It is a bright sunny day in {{ Profile.location | default:"your city" }}. How about a barbeque today?


{% elsif Linked.cityBasedWeather.temp < 10 %}
It is indeed cold today in {{ Profile.location | default:"your city" }}!! Time for some hot pizza!
{% else %}
It has  been a while in {{ Profile.location | default:"your city" }}. Order something exotic!
{% endif %}
```

If you want to add a list of the top 5 restaurants in this message, you can add the following in the main message:

```liquid
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
```

The final message before you send out the email may look like the following:

```liquid
Hi {{ Profile.name | default:"there!" }},

{% if Linked.cityBasedWeather.temp > 30 %}
It is a bright sunny day in {{ Profile.location | default:"your city" }}. How about a barbeque today?

Use the coupon code (BARBQ).
These are the top 5 restaurants near you:
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}


{% elsif Linked.cityBasedWeather.temp < 10 %}
It is indeed cold today in {{ Profile.location | default:"your city" }}!! 
Time for some hot pizza!
                                         
Use the coupon code (PIZZA). These are the top 5 restaurants near you:
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
                                          
{% else %}
                                          
It has  been a while in {{ Profile.location | default:"your city" }}. 
Order something exotic!
                                          
Use the coupon code (EXOTIC).These are the top 5 restaurants near you:           {% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
                                          
{% endif %}
```

Add some personalizations from our editor, then send out the email. For additional information on how to personalize your email, refer to [Create an Email Campaign](https://docs.clevertap.com/docs/create-message-email).


<Image src="https://files.readme.io/eebe749-linked_content_email_example_split.png" alt="1107" align="center" width="60% " caption="Create an Email Campaign using Linked Content" border={true} />


# Using Personalization in Linked Content Response

<Callout icon="📘" theme="info">
  ### Private Beta

  This feature is released in Private Beta. If you want to access this feature, contact your Customer Success Manager.
</Callout>

CleverTap supports personalization in Linked Content, allowing you to dynamically replace personalization placeholders with user-specific values. This ensures messages are customized before delivery, even for translated or localized content.

With this feature, you can send highly targeted messages across multiple languages using profile attributes and event properties, improving user engagement and relevance.

## Supported and Unsupported Variables

### Supported Variables

You can personalize Linked Content responses using the following placeholders with Liquid syntax:

- Profile attributes: `{{Profile.name}}`, `{{Profile.accounttype}}`
- Event properties: `{{Event["offerPercentage"]}}` (supported for live campaigns and for inaction campaigns with a delay greater than 24 hours configured for multiple occurrences)
- Campaign ID: `{{Campaign.campaignId}}`
- External Trigger values: `{{ExternalTrigger.somekey}}`
- Identity: `{{Profile.Identity}}`

### Unsupported Variables

- Event properties are supported in Inaction campaigns with a delay greater than 24 hours.&#x20;
- If the campaign uses Constant Event Property with a delay greater than 24 hours, \`{{Event.*}}\` tags fall back to their default value when the campaign is configured for a single occurrence. For multiple occurrences, event personalization is supported and resolves to the properties of each triggering event. For more information on using a constant event property, refer to [Constant Event Property](doc:constant-property).
- Catalog and recommendation variables fall back to default values.
- As @ Personalization is not supported, any variable prefixed with @ (for example, @Profile - Name) is not parsed, that is, the variable is not replaced with a value.
- Messages with invalid Liquid syntax are flagged as errors to prevent delivery with unresolved placeholders.

## Syntax

Use the following syntax to configure personalization placeholders in Linked Content responses:

* Profile Personalization: `{{Profile.name | default:"Name"}}`
* Event Personalization: `{{Event["offerPercentage"] | default:"0"}}`
* Campaign ID Personalization: `{{Campaign.campaignId | default:"0_0"}}`
* External Trigger: `{{ExternalTrigger.somekey | default:"def"}}`
* Identity: `{{Profile.Identity | default:"idFail"}}`

***

## Use Case: Translating Personalized Messages Across Languages

Learn how to use personalization for translated messages.

### Scenario

A bank customer in Germany receives notifications from his bank about promotional offers. The English version of the final notification delivered to the user is as follows:

```Text Output
Hi John! Now you can earn up to €50 in your savings account.
```

However, when the message is translated into German using Linked Content, it displays as follows:

```
Hallo {{Profile.name | default:"Namefailed"}}! Jetzt kannst du bis zu {{Profile.currency | default:"Currency"}} {{Event["offerPercentage"] | default:"0"}} in dein {{Profile.accounttype | default:"Account"}} Konto verdienen.
```

### Solution

When using message translation, personalized parameters such as \{\{\}\} placeholders often remain unchanged in translated messages and notifications. This results in the German version of the message not being fully personalized when delivered to the user.

With this feature, CleverTap dynamically resolves all placeholders within translated content before the message is delivered, ensuring a fully personalized experience in the user's preferred language.

### How it works

This is how the above-mentioned use case is achieved:

1. When the bank sends him the same promotional message, Linked Content fetches the German message from the translation service.
2. All personalization placeholders are dynamically replaced using real-time user data, such as `Profile.name, Event["offerPercentage"]`, and so on.
3. If a placeholder is invalid or unsupported (for example, prefixed with @), it is either left as-is or flagged as an error.
4. The fully personalized message is delivered in the user’s preferred language, here, German:

```Text Output
Hallo John! Jetzt kannst du bis zu €50 in dein Sparkonto verdienen.
```

This use case can be extended for further personalization using Liquid setup, or through API-based translations.

<Callout icon="📘" theme="info">
  ### Key Consideration

  * Resolving personalization placeholders adds processing time, which may slightly delay message delivery compared to standard notifications.
  * No changes are required in the campaign setup process.
</Callout>

This ensures that personalization works seamlessly across multiple languages, improving engagement and user experience.

# FAQs

### Do you retry if the linked content API fails to give a successful payload?

We do not retry if the linked content API fails to give a successful payload.

### How much time do you wait to fetch the API response?

We wait **five** seconds to fetch the API response.
