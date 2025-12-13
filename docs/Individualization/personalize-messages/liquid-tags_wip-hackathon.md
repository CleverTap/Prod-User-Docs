---
title: Liquid Tags_WIP hackathon
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

Liquid Tags (Replace current doc)\
Overview\
Liquid Tags are a powerful personalization lever for any Marketer, they are used to set up simple expressions that can leverage different User properties & Event properties and give a very personalised content as an output.

Understanding liquid tags\
Each liquid tag starts with a curly brace “\{“, followed by another curly brace or percentage symbol “%” and ends with the same pattern, example - \{\{ Profile.name }} or \{% if Profile.name == “Dave” %}\
The Liquid tag always utilizes a data field to be accessed -\
Profile - This data field accesses the Profile Properties of the User. When applied the liquid tag will either personalize with the property chosen or use the value in the specified expression. Example: Profile.name\
Event - This data field accesses the Event Properties of the Event. When applied the liquid tag will either personalize with the property chosen or use the value in the specified expression. Example: Event.productID\
Linked - This data field accesses the response to any API connected as Linked Content. When applied the liquid tag will either personalize with the response chosen or use the value in the specified expression. Example: Linked.WeatherCity.temperature\
Catalog - This data field accesses the Catalog uploaded for send Time personalisation. When applied the liquid tag will either personalize with the property chosen or use the value in the specified expression. Example: Catalog["Training Demo"].Identity 

Filters over Liquid tags\
All Liquid tags used can have a given set of Filters that can be executed over the data field selected, example all personalisation liquid tags need to have a mandatory default value -\
\{\{ Profile.name | default:"Joe" }}. Here, the value Joe is the default value incase of Profile personalisation where the name doesn’t exist on a User profile.\
Allowed Filters:\
Math Filters - These are basic math operations over an integer or decimal type of values.\
Example: Add or subtract any integer value -\
Input: Hey \{\{ Profile.name }}, Welcome to Shopper’s Pro Club, complete the purchase today to earn 200 points and make your total to \{\{ Profile.points | default: 0 | plus: 200 }}.\
Output: Hey Sunil, Welcome to Shopper’s Pro Club, complete the purchase today to earn 200 points and make your total to 6456.\
String Filters - These are the most commonly used filters to clean up text personalisation, for example if the Username User Property has values which are saved as a mixture of capitals - Sunil, anand, sRuesh; a marketer can standardize this in engagement by using \{\{ Profile.username | default:“there” | capitalize }}. The Output for all the cases would be: Sunil, Anand & Suresh.\
Date Filters - Date filters can be used to convert any DateTime property saved as a User Property or Event Property into any date time format. Example:\
Input: Your order will be delivered by \{\{ Charged.deliverydate | default: “24-May-2021” | date: “'%b, %d” }}\
Output: Your order will be delivered by 24, May

Complete list of Filters available here: [https://shopify.github.io/liquid/basics/introduction/](https://shopify.github.io/liquid/basics/introduction/)

Logical Expressions in Liquid Tag\
Liquid Tags also provide a powerful feature of defining expressions and the content based on the expression evaluation. These expressions can easily be defined within liquid tags by using \{% %} characters. 

Examples of each type of Expression\
Changing content based on logical condition - This a scenario where you’d want to render content based on a certain value, say if the User has more than 2400 points in their wallet, send a 500 additional promo points content or else send 200 additional promo points content\
Input:\
\{% if Profile.walletpoints > 2400 %}\
Purchase today to earn an additional 500 points!\
\{% else %}\
Purchase today to earn an additional 200 points!\
\{% endif %}\
Output:\
If the User had less than 2400 points - Purchase today to earn an additional 200 points!\
Changing content based on unless logical condition - This a scenario where you’d want to render content if the value is not equal to any desired value, say for every Customer Type except Freemium, send out a welcome message stating and exclusive offer\
Input:\
\{% unless Profile.customerType = “Free” %}\
Exclusive offer worth $20! Click to open!\
\{% endunless %}\
Output:\
If the User had the Property set as anything but “Free” - Exclusive offer worth $20! Click to open!\
Changing content based on multiple value conditions - This is a scenario where you’d want to render content based on value, but there can be as many variations as the values possible, say for Gole type customers, Lounge access is free, for Silver type, 50% off on Lounge access for everyone else a default message to upgrade to get discounts on Lounge access.\
Input:\
\{% case Profile.customer\_type %}\
\{% when "Gold" %}\
You are eligible for free lounge access!\
\{% when "Silver" %}\
You are eligible for lounge access at only 50% of the cost!\
\{% else %}\
Upgrade your membership now for free lounge access!\
\{% endcase %}\
Creating multiple blocks of Content from Charged Event - This is a scenario where you’d like to create content blocks based on all items which the User has transacted.\
Input:\
\{% for item in Charged.items %}\
Name: \{\{ item.names }}\
Price: \{\{ item.price }}\
\{% endfor %}\
Output:\
Name: Red shoes\
Price: 100\
Name: Blue shoes\
Price: 200\
Aborting a message on logical condition - This is a scenario where you’d like to abort a message if it fulfills or doesn’t fulfill a condition, say if the added to cart value is less than 100 then abort sending the message.\
Input:\
\{% if Event.amount \<= 100 %}\
\{% abort %}\
\{% else %}\
Your cart is waiting for you!\
\{% endif %}

Using Liquid tags with HTML Email Editor\
HTML Editor gives the leverage to render beautiful email content which was directly crafted in HTML by pasting the HTML on the Editor itself. Liquid Tags can be used in conjunction with the HTML to provide a higher level of personalisation than just simple replacements. Entire blocks of the Email can be manipulated with the contents inside each bolack and the block in itself can be changed.

Step 1:\
Add HTML content to the HTML editor by selecting the Source mode

Step 2:\
Switch back to editor mode from source to add the liquid tags, wherever required

Examples

1. Change the offer Content via Liquid Tags based on Customer Type:

2. Change content block based on logical condition:

3. Change URL based on Liquid Tags:\
   In this case click the Hyper link button on the menu as shown below, the opened popup allows you to personalise the content and the link redirection

4. Personalise image via Liquid tags:\
   This can be achieved by using the Image adder option on the toolbar as shown below - 

Using Liquid tags with Drag and Drop Email Editor\
The Drag and Drop Email Editor is a marketer friendly version, which allows complete capabilities of the HTML editor in a drag and drop fashion. 

Step 1:\
Select the template that needs to use Liquid Tag personalisation

Step 2:\
Add Liquid Tags in the body itself for any text personalisation or use Dynamic Content Block for URL, Email & HTML personalisation\
Text Personalisation:

Dynamic Content Block:

Using Liquid tags with Mobile/SMS/Webhook Editor\
The Liquid Tags can directly be used in all available input fields wherever the Liquid Tag symbol is mentioned. Liquid tags require no special method for invocation, a simple \{\{ or  \{% can invoke them for personalisation.
