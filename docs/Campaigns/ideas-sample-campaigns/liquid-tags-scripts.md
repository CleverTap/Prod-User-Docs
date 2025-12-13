---
title: Liquid Tags scripts
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
# Overview

These are some use cases that use liquid tags scripts. You can avoid creating too many segments t accomplish the task with liquid scripts.  Liquid tags are much more flexible in terms of usage.

# Send discount based on customer types

Send different discounts based on customer types: loyal, wandering, need-based, or bargain hunters.

## Liquid Tag

`switch statement`

## Sample Script

```liquid
{% case Profile.customer_type %}
	
{% when “Loyal” %}
	You are eligible for 25% discount
	{% when “NeedBased” %}
		You are eligible for 15% discount
	{% when “Wandering” %}
		You are eligible for 10% discount
	{% when “BargainHunters” %}
		You are eligible for 5% discount

{% endcase %}
```

# Send notifications based on customer city for flights

Give more discounts to customers that are currently based in the city where you operate the flight route (For example, New York City to Las Vegas).

## Liquid Tag

* `if, else`
* `elsif`

## Sample Script

```liquid
{% if Profile.customer_city == “New York City” %}
	Take a flight to Las Vegas and earn cashback upto $99 
{% elsif Profile.customer_city == “Las Vegas” %}
	Take a flight to NYC and earn cashback upto $99
{% else %}
	New flights between New York City and Las Vegas

{% endif %}
```

# Send gift notifications based on customer ratings and credit points

Reward customers with good ratings by sending them gift coupons and motivate the rest of them to buy more to earn gift coupons.

## Liquid Tag

* `if, elsif, else`
* `or, minus`

## Sample Script

```liquid
{% if Profile.customer_ratings > 4.5 or Profile.type == “Gold” %}
{% if Profile.credit_points > 10000 %}
	Congrats! You have unlocked a $100 gift coupon. Click to claim.
{% elsif Profile.credit_points > 5000 %}
	Congrats! You have unlocked a $50 gift coupon. Click to claim.
{% else %}
	You are a {{ 5000 | minus: Profile.credit_points }}  points short to earn a gift coupon. Click to know more.
{% endif %}

{% else %}
	Increase your Rating to earn a gift coupon. Click to know more.

{% endif %}
```

# Send top item from a list of items

Add a list of products based on the gender of the user using a list of products that are sorted based on popularity. First prints first product, last prints last product in the list.

## Liquid Tag

* `if, else`
* `first, last`
* `<!-- --> (comment tags)`

## Sample Script

```liquid
<!-- product_list_men = “Reebok G1, Nike 40, Nike20”  -->
		<!-- product_list_women = “Prada G1, Nike 40, Nike20”  -->
		<!-- product_list_common = “Prada J1, Nike 70, Nike20”  -->

{% if Profile.gender == “M” %}
	Nice deals on {{ product_list_men | first }}

{% elsif Profile.gender == “F” %}
	Nice deals on {{ product_list_women | first }}

{% else %}
	Nice deals on {{ product_list_common | first }}

{% endif %}
```

# Provide an extra check on maximum and minimum discount values

Send a discount value through `discount.value` and ensure a maximum limit value is sent to the user.

## Liquid Tag

* `at_most`
* `at_least`

## Sample Script

```liquid
Hey! Get discount upto {{ discount.value | at_least: 10 | at_most: 60 }} now!
```

# Use arithmetic operators in message logic

Arithmetic operators can be handy if you want to write simple logic in message personalization, to operate on data values.

## Liquid Tag

* `plus, minus`
* `divided_by, times`
* `round`
* `modulo`

## Sample Script

```liquid
Addition {{ 100 | plus: 20 }} 			// 120
Subtraction {{ 100 | minus: 20 }}		// 80
Multiplication {{ 20 | times: 4 }}		// 80
Division {{ 100 | divided_by: 4 }}		// 25
Round {{ 20.4593 | round: 2 }} 		// 20.46
Modulo {{ 15 | modulo: 2 }}			// 1
```

# Remove extra white space from message string

Use this when you want to ensure that your message coupon is free from extra elements such as white spaces, HTML code, newlines, and so on.

## Liquid Tag

* `strip, lstrip, rstrip`
* `strip_html, strip_newlines`

## Sample Script

```liquid
Your coupon: {{ coupon | strip }} 	// Strips white space on left and right side
Your coupon: {{ coupon | lstrip }}	// Strips white space only on left side
Your coupon: {{ coupon | rstrip }}	// Strips white spacee only on right side

Your coupon: {{ coupon | strip_html }}	// Removes all html tags from string
Your coupon: {{ coupon | strip_newlines }}	// Removes any newlines from string
```

# String Uppercase and lowercase manipulations

Change the string to completely uppercase, lowercase, or capitalize the first letter.

## Liquid Tag

* `upcase`
* `downcase`
* `capitalize`

## Sample Script

```liquid
Your coupon: {{ coupon | upcase }} 		// Converts string to Uppercase
Your coupon: {{ coupon | downcase }}	// Converts string to Lowercase

Hi {{ Profile.name | capitalize }} 		// Capitalizes first letter of string
```

# URL Specific encodings

These tags work on URL unsafe characters and convert them to percent encoded characters.

## Liquid Tag

* `url_encode`
* `url_escape`
* `url_param_escape`

## Sample Script

```liquid
Visit link: {{ web_link | url_encode }} 		// Converts any URL-unsafe characters in a string into percent-encoded characters

Visit link: {{ web_link | url_escape }}	// Replaces the characters with their escaped variants

Visit link: {{ web_link | url_param_escape }}	// Replaces the characters with their escaped variants, with ampersand(&) also.
```

# Set default value using liquid tags

Although this feature is inbuilt in Personalization, you can use this tag to provide a default value in case the value of the parameter is `nil`.

## Liquid Tag

`default`

## Sample Script

```liquid
Good morning {{ Profile.name | default: “Valued Customer” }}
```
