---
title: Linked Content_WIP
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
Linked content gives you the ability to personalize your messages with rich and contextual data that is available outside of the CleverTap platform. Linked content helps you to send messages with send-time personalization. 

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather of their location. The location can come from CleverTap personalization and the weather information can come from a third party API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

In a user scenario, you could have three users, one in New York where it is snowing, one in San Francisco where it is cloudy, and one in Miami where it is sunny. You can add conditions in your messages to deliver messages according to the weather and location where the message will be something, such as:

  * New York user - Since this user is probably staying in, you send an offer for ordering piping hot food. 
  * San Francisco user - Since it is the weekend, this user may go out in the evening, so you send an offer for a dinner reservation at a nearby restaurant. 
  * Miami user - Since it is always sunny, you send an offer for a nearby barbecue restaurant. 

This send-time personalization can help you to cater to end-user requirements at send time and bump your open rates significantly.


[block:callout]
{
  "type": "info",
  "body": "You can create *Linked Content* using *Liquid Tags.* For more information, refer to [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags) before you begin.",
  "title": "Note"
}
[/block]
You can use *Linked Content* with the following engagement channels:

  * Email
  * Mobile Push
  * SMS
  * Webhooks

#Create and Edit API Names
You can get the data for send-time personalization from different APIs. API names are nicknames that you can assign to the provider APIs. You can call these anywhere in your message, so that you do not have to mention the entire API name. For example, you can shorten `http://api.example.com/weather-management/city-weather`  to just `Weather`.

The following shows you how to create API names:

1. Select *Settings* > *Setup* > *Linked Content*. The *Linked Content* page displays.
2. Click the **+ Linked Content **button to call a new API. To edit the linked content, click the ellipsis menu, then click the edit icon. 
3. Enter a name for the API. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/65c4783-Linked_Content_API_Create.png",
        "Linked_Content_API_Create.png",
        1163,
        500,
        "#fcfcfc"
      ],
      "border": true,
      "sizing": "full"
    }
  ]
}
[/block]
4. Enter all the relevant details, such as access key and query parameters.

[block:callout]
{
  "type": "info",
  "title": "Tip",
  "body": "The API parameters are available with the API provider. Refer to their website or contact their support for API details."
}
[/block]
5. Click the **Test Linked Content** link. 
6. Enter the required details to test the API. If the input is correct, you will see a success message. The test response appears in the JSON response box. The following is an example response:
[block:code]
{
  "codes": [
    {
      "code": "\n  \"request\": {\n    \"type\": \"City\",\n    \"query\": \"New York, United States of America\",\n    \"language\": \"en\",\n    \"unit\": \"m\"\n  },\n  \"location\": {\n    \"name\": \"New York\",\n    \"country\": \"United States of America\",\n    \"region\": \"New York\",\n    \"lat\": \"40.714\",\n    \"lon\": \"-74.006\",\n    \"timezone_id\": \"America/New_York\",\n    \"localtime\": \"2020-04-22 12:44\",\n    \"localtime_epoch\": 1587559440,\n    \"utc_offset\": \"-4.0\"\n  },\n  \"current\": {\n    \"observation_time\": \"04:44 PM\",\n    \"temperature\": 7,\n    \"weather_code\": 113,\n    \"weather_icons\": [\n      \"http://cdn.worldweatheronline.com/images/wsymbols01_png_64/wsymbol_0001_sunny.png\"\n    ],\n    \"weather_descriptions\": [\n      \"Sunny\"\n    ],\n    \"wind_speed\": 17,\n    \"wind_degree\": 280,\n    \"wind_dir\": \"W\",\n    \"pressure\": 1012,\n    \"precip\": 0,\n    \"humidity\": 28,\n    \"cloudcover\": 0,\n    \"feelslike\": 4,\n    \"uv_index\": 6,\n    \"visibility\": 16,\n    \"is_day\": \"yes\"\n  }\n}",
      "language": "json"
    }
  ]
}
[/block]

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "The response format is always JSON."
}
[/block]
7. You can choose to add each API object manually or click *Auto-fill Objects* with the API response. All the objects are listed with their label names. If required, you can change the label names here. 



[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8174ccf-Dynamic_Content_API.png",
        "Dynamic_Content_API.png",
        1192,
        1352,
        "#fafafa"
      ],
      "sizing": "smart"
    }
  ]
}
[/block]
8. Click the **Test and save changes** button to save all the API changes. 

#Map APIs
The APIs must be mapped to the campaign from the *What* section. After the APIs are mapped, you can use them in the email body using [liquid tags](https://docs.clevertap.com/docs/liquid-tags). The sample scenario below shows how to create an email campaign using liquid tags and linked content.

1. Create an [email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps).  
2. Select the *New email with rich media* template. 
[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "Linked content is currently available for the rich media template."
}
[/block]
3. From the [What](https://docs.clevertap.com/docs/email#section-step-4-define-the-what) section, click the **Map to campaign** link. The *Map Linked Content* window displays. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6bf525d-Linked_Content_map_api_list.png",
        "Linked_Content_map_api_list.png",
        1398,
        814,
        "#f9f9fb"
      ],
      "border": true
    }
  ]
}
[/block]
4. Select your APIs from the list. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/09c93e7-Linked_Content_map_api.png",
        "Linked_Content_map_api.png",
        658,
        389,
        "#f6f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
5. Map the API parameters to the user and event properties, or add custom parameters. Here, we have mapped the query parameter that fetches location with the profile property *Location*. This means is that each of the users is sent an offer based on their location. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1ecf10d-Linked_Content_map_api_parameters.png",
        "Linked_Content_map_api_parameters.png",
        666,
        442,
        "#f4f4f3"
      ],
      "border": true,
      "sizing": "smart"
    }
  ]
}
[/block]
6. Save the mapping. 

We are now ready to start writing Linked Content. 

#Write Linked Content
After you have created and saved the APIs, create the linked content for your messages. It is recommended that you familiarize yourself with [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags) before you start writing Linked Content. 

The syntax for writing linked content is `Linked.APIName.label`. 

##Use Labels
You can write linked content with labels. There are two types of labels that you can use in your linked content. 

  * Custom Labels - These are labels you can create yourself. For example, password or authorization key.
  * System Labels - These are default labels you can use to analyze API responses. 


###Custom Labels
The API response will provide you with a set of object labels. However, if you want additional personalization, you can create custom labels during the creation and editing of [APIs](https://docs.clevertap.com/docs/linked-content#section-create-edit-namespaces). These will not be part of the API response.  

###System Labels

These are CleverTap labels that are available by default. You can use them to gauge the health of your API and check whether the responses are received correctly or not. 
[block:parameters]
{
  "data": {
    "0-0": "raw",
    "0-1": "This is a raw API response.",
    "1-0": "JSON",
    "1-1": "This is the raw response parsed as JSON.",
    "2-0": "http_status_code",
    "3-0": "headers",
    "2-1": "This is the HTTP status code to identify errors, such as, 404 (not found), 401 (unauthorized), and so on.",
    "3-1": "These are response headers.",
    "h-1": "Description",
    "h-0": "System Labels"
  },
  "cols": 2,
  "rows": 4
}
[/block]

##Arrays in API

The response from an API may have arrays with nested JSON. 
[block:code]
{
  "codes": [
    {
      "code": "\"restaurants_info\": [\n    { \n        \"id\": \"16769241\",\n        \"name\": \"Junior's Restaurant\",\n        \"user_rating\": {\n            \"aggregate_rating\": \"4.7\",\n            \"rating_text\": \"Excellent\",\n            \"votes\": \"538\"\n     }      \n    },\n  \n    {\n        \"id\": \"16763460\",\n        \"name\": \"Cookshop\",\n        \"user_rating\": {\n           \"aggregate_rating\": \"4.6\",\n           \"rating_text\": \"Excellent\",\n           \"votes\": \"252\"\n        }\n    }\n]",
      "language": "json",
      "name": "Example Response"
    }
  ]
}
[/block]
You can create conditions based on this array. For example, the response above has an array called ``restaurants``. This array contains items under it such as id, name, rating. Notice the object ``user_rating``. It is a nested object that contains an aggregate rating of the restaurant, rating text from an actual user, number of votes, and so on. You can use the array in the following manner:

[block:code]
{
  "codes": [
    {
      "code": "{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} \n{{restaurant.name}}  {{restaurant.user_rating.rating_text}}\n{% endfor %}\n\n",
      "language": "liquid",
      "name": "Array list"
    }
  ]
}
[/block]
The output will be something similar to the following text:
[block:code]
{
  "codes": [
    {
      "code": "\nMarta has a rating  Excellent\nPN Wood Fired Pizza  Excellent\nPQR Very Good\n&pizza   Good\nLeonelli Focacceria e Pasticceria Good",
      "language": "text",
      "name": "Output - Array list"
    }
  ]
}
[/block]
##Create Message 
In our previous user scenario, you have three users, one in New York where it is snowing, one in San Francisco where it is cloudy, and one in Miami where it is sunny. You can add conditions in your messages to deliver messages according to the weather and zip code. So, you can plan the following message:

  * New York user - Since this user is probably staying in, you send an offer for ordering piping hot food. 
  * San Francisco user - Since it is the weekend, this user may go out in the evening, so you send an offer for a dinner reservation at a nearby restaurant. 
  * Miami user - Since it is always sunny, you send an offer for a nearby barbecue restaurant. 

The following is how a written personalized linked content for your users may look like:
[block:code]
{
  "codes": [
    {
      "code": "Hi {{ Profile.name | default:\"there!\" }},\n\n{% if Linked.cityBasedWeather.temp > 30 %}\nIt is a bright sunny day in {{ Profile.location | default:\"your city\" }}. How about a barbeque today?\n\n\n{% elsif Linked.cityBasedWeather.temp < 10 %}\nIt is indeed cold today in {{ Profile.location | default:\"your city\" }}!! Time for some hot pizza!\n{% else %}\nIt has  been a while in {{ Profile.location | default:\"your city\" }}. Order something exotic!\n{% endif %}",
      "language": "liquid"
    }
  ]
}
[/block]
If you want to add a list of the top 5 restaurants in this message, you can add the following in the main message:

[block:code]
{
  "codes": [
    {
      "code": "{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} \n{{restaurant.name}}  {{restaurant.user_rating.rating_text}}\n{% endfor %}\n\n\n",
      "language": "liquid"
    }
  ]
}
[/block]
The final message before you send out the email may look like the following:

[block:code]
{
  "codes": [
    {
      "code": "Hi {{ Profile.name | default:\"there!\" }},\n\n{% if Linked.cityBasedWeather.temp > 30 %}\nIt is a bright sunny day in {{ Profile.location | default:\"your city\" }}. How about a barbeque today?\n\nUse the coupon code (BARBQ).\nThese are the top 5 restaurants near you:\n{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} \n{{restaurant.name}}  {{restaurant.user_rating.rating_text}}\n{% endfor %}\n\n\n{% elsif Linked.cityBasedWeather.temp < 10 %}\nIt is indeed cold today in {{ Profile.location | default:\"your city\" }}!! \nTime for some hot pizza!\n                                         \nUse the coupon code (PIZZA). These are the top 5 restaurants near you:\n{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} \n{{restaurant.name}}  {{restaurant.user_rating.rating_text}}\n{% endfor %}\n                                          \n{% else %}\n                                          \nIt has  been a while in {{ Profile.location | default:\"your city\" }}. \nOrder something exotic!\n                                          \nUse the coupon code (EXOTIC).These are the top 5 restaurants near you:           {% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} \n{{restaurant.name}}  {{restaurant.user_rating.rating_text}}\n{% endfor %}\n                                          \n{% endif %}\n\n\n                                          \n                                          ",
      "language": "liquid"
    }
  ]
}
[/block]
Add some personalizations from our editor, then send out the email. For additional information on how to personalize your email, refer to [Email Editor](doc:email-editor). 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/eebe749-linked_content_email_example_split.png",
        "linked_content_email_example_split.png",
        1107,
        1997,
        "#9e9b9e"
      ],
      "sizing": "full",
      "border": true
    }
  ]
}
[/block]