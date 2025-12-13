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


[block:code]
{
  "codes": [
    {
      "code": "{% case Profile.customer_type %}\n\t\n{% when “Loyal” %}\n\tYou are eligible for 25% discount\n\t{% when “NeedBased” %}\n\t\tYou are eligible for 15% discount\n\t{% when “Wandering” %}\n\t\tYou are eligible for 10% discount\n\t{% when “BargainHunters” %}\n\t\tYou are eligible for 5% discount\n\n{% endcase %}\n",
      "language": "liquid"
    }
  ]
}
[/block]
# Send notifications based on customer city for flights
Give more discounts to customers that are currently based in the city where you operate the flight route (For example, New York City to Las Vegas).

## Liquid Tag 
  * `if, else`
  * `elsif`

## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "{% if Profile.customer_city == “New York City” %}\n\tTake a flight to Las Vegas and earn cashback upto $99 \n{% elsif Profile.customer_city == “Las Vegas” %}\n\tTake a flight to NYC and earn cashback upto $99\n{% else %}\n\tNew flights between New York City and Las Vegas\n\n{% endif %}\n\n",
      "language": "liquid"
    }
  ]
}
[/block]
# Send gift notifications based on customer ratings and credit points
Reward customers with good ratings by sending them gift coupons and motivate the rest of them to buy more to earn gift coupons.

## Liquid Tag 
  * `if, elsif, else`
  * `or, minus`
  
## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "{% if Profile.customer_ratings > 4.5 or Profile.type == “Gold” %}\n{% if Profile.credit_points > 10000 %}\n\tCongrats! You have unlocked a $100 gift coupon. Click to claim.\n{% elsif Profile.credit_points > 5000 %}\n\tCongrats! You have unlocked a $50 gift coupon. Click to claim.\n{% else %}\n\tYou are a {{ 5000 | minus: Profile.credit_points }}  points short to earn a gift coupon. Click to know more.\n{% endif %}\n\n{% else %}\n\tIncrease your Rating to earn a gift coupon. Click to know more.\n\n{% endif %}\n",
      "language": "liquid"
    }
  ]
}
[/block]
# Send top item from a list of items

Add a list of products based on the gender of the user using a list of products that are sorted based on popularity. First prints first product, last prints last product in the list.

## Liquid Tag 
  * `if, else`
  * `first, last`
  * `<!-- --> (comment tags)`

## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "<!-- product_list_men = “Reebok G1, Nike 40, Nike20”  -->\n\t\t<!-- product_list_women = “Prada G1, Nike 40, Nike20”  -->\n\t\t<!-- product_list_common = “Prada J1, Nike 70, Nike20”  -->\n\n{% if Profile.gender == “M” %}\n\tNice deals on {{ product_list_men | first }}\n\n{% elsif Profile.gender == “F” %}\n\tNice deals on {{ product_list_women | first }}\n\n{% else %}\n\tNice deals on {{ product_list_common | first }}\n\n{% endif %}\n",
      "language": "liquid"
    }
  ]
}
[/block]
#  Provide an extra check on maximum and minimum discount values

Send a discount value through `discount.value` and ensure a maximum limit value is sent to the user.

## Liquid Tag 
  * `at_most`
  * `at_least`
## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "Hey! Get discount upto {{ discount.value | at_least: 10 | at_most: 60 }} now!\n\n",
      "language": "liquid"
    }
  ]
}
[/block]
# Use arithmetic operators in message logic

Arithmetic operators can be handy if you want to write simple logic in message personalization, to operate on data values.

## Liquid Tag 
  * `plus, minus`
  * `divided_by, times`
  * `round`
  * `modulo`

## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "Addition {{ 100 | plus: 20 }} \t\t\t// 120\nSubtraction {{ 100 | minus: 20 }}\t\t// 80\nMultiplication {{ 20 | times: 4 }}\t\t// 80\nDivision {{ 100 | divided_by: 4 }}\t\t// 25\nRound {{ 20.4593 | round: 2 }} \t\t// 20.46\nModulo {{ 15 | modulo: 2 }}\t\t\t// 1",
      "language": "liquid"
    }
  ]
}
[/block]
# Remove extra white space from message string
Use this when you want to ensure that your message coupon is free from extra elements such as white spaces, HTML code, newlines, and so on.

## Liquid Tag 
  * `strip, lstrip, rstrip`
  * `strip_html, strip_newlines`

## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "Your coupon: {{ coupon | strip }} \t// Strips white space on left and right side\nYour coupon: {{ coupon | lstrip }}\t// Strips white space only on left side\nYour coupon: {{ coupon | rstrip }}\t// Strips white spacee only on right side\n\nYour coupon: {{ coupon | strip_html }}\t// Removes all html tags from string\nYour coupon: {{ coupon | strip_newlines }}\t// Removes any newlines from string\n",
      "language": "liquid"
    }
  ]
}
[/block]
# String Uppercase and lowercase manipulations
Change the string to completely uppercase, lowercase, or capitalize the first letter.
## Liquid Tag 
  * `upcase`
  * `downcase`
  * `capitalize`
## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "Your coupon: {{ coupon | upcase }} \t\t// Converts string to Uppercase\nYour coupon: {{ coupon | downcase }}\t// Converts string to Lowercase\n\nHi {{ Profile.name | capitalize }} \t\t// Capitalizes first letter of string\n",
      "language": "liquid"
    }
  ]
}
[/block]
# URL Specific encodings

These tags work on URL unsafe characters and convert them to percent encoded characters.

## Liquid Tag 
  * `url_encode`
  * `url_escape`
  * `url_param_escape`

## Sample Script 

[block:code]
{
  "codes": [
    {
      "code": "Visit link: {{ web_link | url_encode }} \t\t// Converts any URL-unsafe characters in a string into percent-encoded characters\n\nVisit link: {{ web_link | url_escape }}\t// Replaces the characters with their escaped variants\n\nVisit link: {{ web_link | url_param_escape }}\t// Replaces the characters with their escaped variants, with ampersand(&) also.\n",
      "language": "liquid"
    }
  ]
}
[/block]
# Set default value using liquid tags

Although this feature is inbuilt in Personalization, you can use this tag to provide a default value in case the value of the parameter is `nil`.

## Liquid Tag 
`default`
## Sample Script 
[block:code]
{
  "codes": [
    {
      "code": "Good morning {{ Profile.name | default: “Valued Customer” }}\n\n",
      "language": "liquid"
    }
  ]
}
[/block]