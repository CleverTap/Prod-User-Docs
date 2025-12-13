---
title: Liquid Tags_WIP
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
Liquid tags offer tremendous flexibility and personalization for your messages. You can create a 'write once use multiple times' message and add multiple variations to it. You can use Liquid tags with the following engagement channels:

  * Email
  * Mobile Push
  * SMS
  * Webhooks
  
Here is a simple example of personalization with a liquid tag: 


[block:code]
{
  "codes": [
    {
      "code": "{% if Profile.PREFERED_LANGUAGE == \"Spanish\" %} \nHola!\n{% elsif Profile.PREFERED_LANGUAGE == \"English\" %}\nHello!\n{% endif %}\n",
      "language": "liquid",
      "name": "Liquid Tag"
    }
  ]
}
[/block]

If the user's preferred language is Spanish, the greeting will appear in Spanish.  
[block:code]
{
  "codes": [
    {
      "code": "Hola!\n",
      "language": "text",
      "name": "Output - Liquid Tag"
    }
  ]
}
[/block]
If the user's preferred language is English, the greeting will appear in English.  
[block:code]
{
  "codes": [
    {
      "code": "Hello!\n",
      "language": "text",
      "name": "Output - Liquid Tag"
    }
  ]
}
[/block]
#Getting Started
You can personalize your messages for [Events](doc:events) and [User Profiles](doc:user-profiles). For example, a user whose language is English (Profile property), or someone who has purchased (Event property) a new shirt.

Let us create a Liquid tag in an email campaign. To create a tag, select the "New email with rich media" template when you create an [email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps). You can use Liquid Tags within this template. 


[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/75cd8d0-Campaigns_Email_Liquid_Tags_Template.png",
        "Campaigns_Email_Liquid_Tags_Template.png",
        1440,
        645,
        "#ebeaed"
      ],
      "caption": "Select a media template",
      "border": true
    }
  ]
}
[/block]
The Liquid Tags work within the email editor. However, you can also combine the power of HTML with Liquid Tags.  You can paste your HTML code directly in the HTML editor by clicking the Source button and then personalize it with Liquid Tags. For more information, see [Liquid Tags with HTML](https://docs.clevertap.com/docs/liquid-tags#section-liquid-tags-with-htmll) 

The liquid terms are adapted from [shopify's documentation](https://shopify.github.io/liquid/basics/introduction/) to  CleverTap. We support only the terms identified in our documentation for a seamless experience.

#Using Tags

You can start creating your message by declaring tags in the campaign editor. You can declare the tags in the following ways: 

  * For creating message conditions - Conditional tags can help you vary the message for each condition. For example, if your users make a purchase, then send them a coupon with an additional discount for their next purchase. You can create a conditional tag by enclosing the condition within curly braces and a % sign. Start by entering `{%` in the email editor. The closing tag is completed automatically. The syntax for these tags is: `{% if %} {% endif %}`
  * For displaying output from a variable - Output tags display the output of a variable. For example, if customer_type is a variable, display all the types of customers such as Platinum, Gold,  and Silver. Start by entering `{{` in the email editor. The closing tag is completed automatically. The syntax for these tags is: `{{customer_type}}`

You can use any of the Profile and Event properties within tags. Just enter `Profile.` or `Event.` in the editor and we will list all the corresponding properties automatically. 

[block:callout]
{
  "type": "info",
  "title": "Note",
  "body": "When selecting properties, the \"P\" in profile and the \"E\" in Events must be capitalized and followed with a period \".\". Profile properties are available for all segments. Liquid tags for Event properties are only available for live user segments. The \"@\" personalization is supported only outside the tags."
}
[/block]

##Conditional Tags

You can use conditional tags for creating simple or complex conditional statements.  For example, If condition A, then send message 1, else send message 2, else-if message 3. If we were to express this in tags, we can use the user's preferred language as an example. 

Following are the conditional tags:
  * if
  * else
  * else-if
  * unless
  * switch case
  * for
   * break
   * continue
   * abort
   * limit
   * reversed
   * offset
   * tablerow


###If

[block:code]
{
  "codes": [
    {
      "code": "{% if Profile.PREFERED_LANGUAGE  == \"French\"%} \n\nBon Jour !\n\n{% endif %}\n",
      "language": "text",
      "name": "If Tag"
    }
  ]
}
[/block]
###Else/Elseif

You can send messages conditionally to each recipient. 
[block:code]
{
  "codes": [
    {
      "code": "{% if Profile.PREFERED_LANGUAGE  == \"French\"%} \n\nBon Jour !\n\n{% elsif  Profile.PREFERED_LANGUAGE  == \"Spanish\"%} \n\nHola!\n\n{% else %}\n\nHello!\n\n{% endif %}\n",
      "language": "liquid",
      "name": "Else/Elseif Tag"
    }
  ]
}
[/block]

If the user's preferred language is French, the greeting will appear in French.  If the user's preferred language is Spanish the greeting will appear in Spanish. However, if the preferred language is anything other than French and Spanish, then the greeting will appear in English. 

[block:code]
{
  "codes": [
    {
      "code": "Hello!\n",
      "language": "text",
      "name": "Output - Else/Elseif"
    }
  ]
}
[/block]

###Unless

You can use this tag if a condition is not true. For example, if a user's language is "not" French, then greet with "Hello" in English. 

[block:code]
{
  "codes": [
    {
      "code": "{% unless Profile.PREFERED_LANGUAGE  == \"French\"%} \n\nHello!\n\n{% endunless %}\n",
      "language": "liquid",
      "name": "Unless Tag"
    }
  ]
}
[/block]
The message display will be as follows:
[block:code]
{
  "codes": [
    {
      "code": "Hello!\n",
      "language": "text",
      "name": "Output - Unless"
    }
  ]
}
[/block]
###Switch case 

You can switch a statement when a variable changes in value.  The `when` statements define the various conditions. 
For example, you have three types of customers, namely "Gold", "Silver" and everyone else. They are represented by the profile property "customer_type".  You can change the displayed message based on the type of customers. 
[block:code]
{
  "codes": [
    {
      "code": "\n\n{% case Profile.customer_type %}\n  {% when \"Gold\" %}\n     You are eligible for free lounge access!\n  {% when \"Silver\" %}\n     You are eligible for lounge access at only 50% of the cost!\n  {% else %}\n     Upgrade your membership now for free lounge access!\n{% endcase %}\n",
      "language": "liquid",
      "name": "Switch case Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "Upgrade your membership now for free lounge access!\n",
      "language": "text",
      "name": "Output - Switch case"
    }
  ]
}
[/block]
###for
You can repeat execution in liquid script with the for a loop.

[block:code]
{
  "codes": [
    {
      "code": "\n{% for item in hiking.items %}\n  {{ item.names }}\n{% endfor %}\n\n",
      "language": "liquid",
      "name": "for Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "flashlight  backpack boots\n\n",
      "language": "text",
      "name": "Output - For Tag"
    }
  ]
}
[/block]
###break
You can stop execution in the liquid script by adding break in a loop.

[block:code]
{
  "codes": [
    {
      "code": "{% for i in (1..10) %}\n  {% if i == 7 %}\n    {% break %}\n  {% else %}\n    {{ i }}\n  {% endif %}\n{% endfor %}",
      "language": "liquid",
      "name": "Break - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "1 2 3 4 5 6 \n\n",
      "language": "text",
      "name": "Output - Break"
    }
  ]
}
[/block]
###continue
You can skip the current iteration in a loop with the continue tag.
[block:code]
{
  "codes": [
    {
      "code": "{% for i in (1..10) %}\n  {% if i == 7 %}\n    {% continue %}\n  {% else %}\n    {{ i }}\n  {% endif %}\n{% endfor %}\n",
      "language": "liquid",
      "name": "continue - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "1 2 3 4 5 6   8 9 10\n\n",
      "language": "text",
      "name": "output - continue"
    }
  ]
}
[/block]

##abort


This is a CleverTap Tag within Liquid. You can abort sending a message with the abort tag. If a condition is not fulfilled for a user, it is displayed in the campaign reports as ``LiquidLogicAborted``.
[block:code]
{
  "codes": [
    {
      "code": "{% if Event.price > 100%}\nThank you for your purchase. Here is a coupon code for you. \nCOUPON\n{% else %}\n{% abort %}\n{% endif %}\n\n",
      "language": "liquid",
      "name": "abort - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "Thank you for your purchase. Here is a coupon code for you. \nCOUPON",
      "language": "text",
      "name": "output - abort"
    }
  ]
}
[/block]

###limit

You can specify the limit the for loop with this tag. 
[block:code]
{
  "codes": [
    {
      "code": "<!-- if array = [1,2,3,4,5,6] -->\n{% for item in array limit:2 %}\n  {{ item }}\n{% endfor %}\n\n",
      "language": "liquid",
      "name": "limit - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "1 2",
      "language": "text",
      "name": "output - limit"
    }
  ]
}
[/block]
###reversed
You can reverse the order of the loop with this tag. Pay special attention to the spelling.
[block:code]
{
  "codes": [
    {
      "code": "<!-- if array = [1,2,3,4,5,6] -->\n{% for item in array reversed %}\n  {{ item }}\n{% endfor %}\n\n",
      "language": "liquid",
      "name": "reversed - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "6 5 4 3 2 1\n\n",
      "language": "text",
      "name": "output - reversed"
    }
  ]
}
[/block]
###offset

You can begin the loop at a specified index.

[block:code]
{
  "codes": [
    {
      "code": "<!-- if array = [1,2,3,4,5,6] -->\n{% for item in array offset:2 %}\n  {{ item }}\n{% endfor %}\n\n",
      "language": "liquid",
      "name": "offset - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "3 4 5 6\n\n",
      "language": "text",
      "name": "output - offset"
    }
  ]
}
[/block]
###tablerow
You can generate an HTML table with this tag. It must be wrapped in opening ```<table>``` and closing ``</table>`` HTML tags. 
[block:code]
{
  "codes": [
    {
      "code": "<table>\n{% tablerow product in collection.products %}\n  {{ product.title }}\n{% endtablerow %}\n</table>",
      "language": "liquid",
      "name": "tablerow - Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "<table>\n  <tr class=\"row1\">\n    <td class=\"col1\">\n      Cool Shirt\n    </td>\n    <td class=\"col2\">\n      Alien Poster\n    </td>\n    <td class=\"col3\">\n      Batman Poster\n    </td>\n    <td class=\"col4\">\n      Bullseye Shirt\n    </td>\n    <td class=\"col5\">\n      Another Classic Vinyl\n    </td>\n    <td class=\"col6\">\n      Awesome Jeans\n    </td>\n  </tr>\n</table>\n\n",
      "language": "text",
      "name": "output - Tag"
    }
  ]
}
[/block]
##Variable Tags

###Assign

You can use the ``assign`` tag to assign value to a variable. The value of this variable can change based on the defined condition or a range. You can then reuse this variable across your message. 

For example, you want to greet a user in French. You create a variable called `LANG`. Now, you can use this variable for all available languages. If the value of the `LANG` variable is French, the greeting is "Bonjour!". The greeting is "Hello!" for all other languages. 
[block:code]
{
  "codes": [
    {
      "code": "\n{% assign LANG = PROFILE.PREFERED_LANGUAGE %}\n{% if LANG == \"FRENCH\" %}\nBonjour!\n{% else %}\nHello!\n{% endif %}\n",
      "language": "liquid",
      "name": "Assign Variable Tag"
    }
  ]
}
[/block]
##Theme Tags

###Raw 
You can use the raw tag to display characters used by the tag syntax. 

[block:code]
{
  "codes": [
    {
      "code": "{% raw %}{{ 5 | plus: 6 }}{% endraw %} equals 11.\n\n",
      "language": "liquid",
      "name": "Raw Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "{{ 5 | plus: 6 }} equals 11.\n\n",
      "language": "text",
      "name": "Output - raw"
    }
  ]
}
[/block]
###Comment
You can comment on your code with this tag. It can be notes or description that you want to add to make your code more understandable. 

[block:code]
{
  "codes": [
    {
      "code": "\n{% if Profile.PREFERED_LANGUAGE  == \"French\"%} \n\n{% comment %} This condition is fulfilled only if the value is \nFrench {% endcomment %}\n\nBonjour !\n\n{% endif %}\n",
      "language": "liquid",
      "name": "Comment Tag"
    }
  ]
}
[/block]

[block:code]
{
  "codes": [
    {
      "code": "Bonjour!\n",
      "language": "text",
      "name": "Output - Comment"
    }
  ]
}
[/block]
##Operators

You can use the following operators to evaluate conditions in your tags. 
[block:parameters]
{
  "data": {
    "0-0": "**==** ",
    "h-0": "Operator",
    "h-1": "Description",
    "0-1": "equals",
    "1-0": "**!=** ",
    "1-1": "does not equal",
    "2-0": "**>** ",
    "2-1": "greater than",
    "3-0": "**<** ",
    "3-1": "less than",
    "4-0": "**>=** ",
    "4-1": "greater than or equal to",
    "5-0": "**<=** ",
    "5-1": "less than or equal to",
    "6-0": "**or** ",
    "6-1": "logical or. Choose between condition 1 or condition 2.",
    "7-0": "**and** ",
    "8-0": "**contains** ",
    "7-1": "logical and. Choose conditions 1 and condition 2",
    "8-1": "check for a string within a string"
  },
  "cols": 2,
  "rows": 9
}
[/block]

#Liquid Tags with HTML

This section applies only to the email channel. 

You can combine your HTML code with Liquid Tags to create beautiful and personalized messages for your users.  

Here is how to do it in three steps: 

1. Click the Source button on the email editor to open the HTML editor. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1cbbd27-Campaign_Email_HTML_editor.png",
        "Campaign_Email_HTML_editor.png",
        1437,
        654,
        "#e9e9eb"
      ],
      "border": true
    }
  ]
}
[/block]
2. Paste your HTML code. 
3. Click the Source button again to open the email editor.  You will see the HTML output. The Liquid Tags work only with the default email editor. 
4. Add your Liquid Tags. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/695cc49-campaigns_email_liquid_editor_example.png",
        "campaigns_email_liquid_editor_example.png",
        1390,
        1083,
        "#eaebf8"
      ],
      "border": false
    }
  ]
}
[/block]
#Linked Content and Liquid Tags in Drag and Drop Editor

Linked Content and Liquid tags are available for the drag-and-drop email editor. This functionality allows customers to design emails and personalize them using dynamic content when they create an [email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps).

Perform the following steps to personalize drag and drop editor templates with liquid tags.

1. Select a template.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e404d9c-2020-07-28_18-55-48_Select_template.png",
        "2020-07-28_18-55-48_Select template.png",
        1098,
        781,
        "#eaebed"
      ]
    }
  ]
}
[/block]
2. Click on a *Row* item in *Preview*.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b461f6b-2020-07-28_19-19-33_Select_row_item.png",
        "2020-07-28_19-19-33_Select row item.png",
        1047,
        557,
        "#a3a5a7"
      ]
    }
  ]
}
[/block]
3. Select **Add display content** in the right pane.
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e695382-2020-07-28_19-15-27_Content_editor.png",
        "2020-07-28_19-15-27 Content editor.png",
        1054,
        533,
        "#bfbfc0"
      ]
    }
  ]
}
[/block]
4. Add the liquid script inside the personalized text box.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/7850f33-2020-07-28_19-25-41_add_personalized_message..png",
        "2020-07-28_19-25-41_add personalized message..png",
        1082,
        758,
        "#777779"
      ]
    }
  ]
}
[/block]
5. Click **Save**.