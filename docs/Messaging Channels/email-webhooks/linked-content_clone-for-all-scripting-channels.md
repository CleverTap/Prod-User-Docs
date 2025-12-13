---
title: Linked Content_Clone for all scripting channels
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
Linked Content gives you the ability to personalize your messages with rich and contextual data that is available outside of the CleverTap platform.  Linked Content helps you to send messages with send-time personalization. 

For example, you deliver food across different geographies and you want to personalize offers to each user based on the weather on their location. The location can come from CleverTap personalization and the weather information can come from a third party API that provides the current weather. If you want to add more information, you can opt for any source such as third-party tools and in-house software to include in your message.

Let us consider a user scenario. You have 3 users, one each in New York - snowing, SanFranciso - cloudy, and Miami - sunny.  You can add conditions in your messages to deliver messages according to the weather and location. So the message will be something like this:

* New York user - The user is probably staying in. You send an offer for ordering piping hot food. 
* San Francisco user - it is a weekend and the user may go out in the evening. You send want an offer for dinner reservations at a nearby restaurant. 
* Miami user - It's always sunny in Miami! So you send an offer for a barbeque restaurant nearby. 

This send-time personalization can help you to cater to end-user requirements at send time and bump your open rates significantly.

> 📘 Note
>
> You can create Linked Content using Liquid Tags. Therefore, before we begin, familiarize yourself with writing [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags). Liquid and Linked Content are available with our [Optimize pack](https://clevertap.com/pricing/).

# Create/Edit API Names

You can get the data for send-time personalization from different APIs. API Names are nicknames that you can assign to the provider APIs. You can call these anywhere in your message so that you do not have to mention the entire API name. For example, you can shorten `http://api.example.com/weather-management/city-weather`  to just `Weather`.

Let us see how to create API Names:

1. Click Settings > Setup > Linked Content. The Linked Content page appears.
2. Click the + Linked Content button to call a new API. To edit, the Linked Content, click the ellipsis menu and click the edit icon. 
3. Enter a name for the API. 

<Image title="Linked_Content_API_Create.png" alt={1163} className="border" width="100%" border={true} src="https://files.readme.io/65c4783-Linked_Content_API_Create.png" />

4. Enter all the relevant details, such as access key and query parameters.

> 📘 Tip
>
> The API parameters are available with the API provider. Refer to their website or contact their support for API details.

5. Click the Test Linked Content link. 
6. Enter the required details to test the API. If the input is correct, you will see a success message. The test response appears in the JSON Response box. Following is an example response:

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

> 📘 Note
>
> The response format is always JSON.

7. You can choose to add each API  Object manually or click Auto-fill objects with the API response. All the objects are listed with their label names. If required, you can change the label names here. 

<Image title="Dynamic_Content_API.png" alt={1192} width="100%" src="https://files.readme.io/8174ccf-Dynamic_Content_API.png" />

8. Click Test and save changes button to save all the API changes. 

# Map APIs

The APIs must be mapped to the campaign from the "What" section.  After the APIs are mapped, you can use them in the message body using [Liquid tags](https://docs.clevertap.com/docs/liquid-tags). Let us create a sample Email campaign using Liquid tags and Linked Content.

1. Create an [Email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps).  
2. Select the "New email with rich media" template. 

> 📘 Note
>
> Linked content is currently available for the Rich media template.

3. From the ["What"](https://docs.clevertap.com/docs/email#section-step-4-define-the-what) section, click the Map to this campaign link. The Map Linked Content window appears. 

<Image title="Linked_Content_map_api_list.png" alt={1398} className="border" border={true} src="https://files.readme.io/6bf525d-Linked_Content_map_api_list.png" />

4. Select your APIs from the list. 

<Image title="Linked_Content_map_api.png" alt={658} className="border" border={true} src="https://files.readme.io/09c93e7-Linked_Content_map_api.png" />

5. Map the API parameters to the user and event properties, or add custom parameters. Here we have mapped the query parameter that fetches location with the profile property "location". What this means is that each of the users is sent an offer based on their location. 

<Image title="Linked_Content_map_api_parameters.png" alt={666} className="border" width="smart" border={true} src="https://files.readme.io/1ecf10d-Linked_Content_map_api_parameters.png" />

6. Save the mapping. 

We are now ready to start writing Linked Content. 

# Write Linked Content

After you have created and saved the APIs, create the linked content for your messages. It is recommended that you familiarize yourself with [Liquid Tags](https://docs.clevertap.com/docs/liquid-tags) before you start writing Linked Content. 

The syntax for writing Linked Content is `Linked.APIName.label`. 

## Use Labels

You can write Linked Content with labels. There are two types of labels that you can use in your Linked Content. 

* Custom Labels - These are labels you can create yourself. For example, password or authorization key.
* System Labels - These default labels that you can use to analyze API responses. 

### Custom Labels

The API response will provide you with a set of object labels. However, if you want additional personalization, then  you can create custom labels during the creation/editing of [APIs](https://docs.clevertap.com/docs/linked-content#section-create-edit-namespaces). These will not be part of the API response.  

### System Labels

These are CleverTap labels that are available by default. You can use them to gauge the health of your API and check whether the responses are received correctly or not. 

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        System Labels
      </th>

      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        raw
      </td>

      <td>
        This is a raw API response.
      </td>
    </tr>

    <tr>
      <td>
        JSON
      </td>

      <td>
        This is the raw response parsed as JSON.
      </td>
    </tr>

    <tr>
      <td>
        http\_status\_code
      </td>

      <td>
        This is the HTTP status code to identify errors such as 404 - not found, 401 - unauthorized, and so on.
      </td>
    </tr>

    <tr>
      <td>
        headers
      </td>

      <td>
        These are response headers.
      </td>
    </tr>
  </tbody>
</Table>

## Arrays in API

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

You can create conditions based on this array. For example, the response above has an array called `restaurants`. This array contains items under it such as id, name, rating. Notice the object `user_rating`. It is a nested object that contains an aggregate rating of the restaurant, rating text from an actual user, number of votes, and so on. You can use the array in the following manner. 

```liquid Array list
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
```

The output will be something like the following text:

```text Output - Array list
Marta has a rating  Excellent
PN Wood Fired Pizza  Excellent
PQR Very Good
&pizza   Good
Leonelli Focacceria e Pasticceria Good
```

## Create Message 

Let us refer to our previous example.  You have 3 users, one each in New York - snowing, SanFranciso - cloudy, and Miami - sunny.  You can add conditions in your messages to deliver messages according to the weather and zip code. So you can plan the message like the following:

* New York user - The user is probably staying in. You send an offer for ordering piping hot food. 
* San Francisco user - The user may go out in the evening. You send an offer for dinner reservations at a nearby restaurant. 
* Miami user - It is always sunny in Miami! So you send an offer for a barbeque restaurant nearby. 

Let us now write personalized Linked Content for your users. 

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

Say you want to add a list of top 5 restaurants in this message. We can add the following in the main message:

```liquid
{% for restaurant in Linked.RestaurantAPI.restaurants_info limit:5%} 
{{restaurant.name}}  {{restaurant.user_rating.rating_text}}
{% endfor %}
```

The final message before you send out the email will look something like the following:

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

Add some personalizations from our editor and send out the email. 

<Image title="linked_content_email_example_split.png" alt={1107} className="border" width="100%" border={true} src="https://files.readme.io/eebe749-linked_content_email_example_split.png" />
