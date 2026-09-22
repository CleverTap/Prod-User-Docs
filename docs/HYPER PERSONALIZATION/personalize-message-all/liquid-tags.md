---
title: Liquid Tags
excerpt: ''
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

Liquid tags offer tremendous flexibility and personalization for your messages. You can create a 'write once use multiple times' message and add multiple variations to it. You can use Liquid tags with the following engagement channels:

* Email
* Mobile Push
* SMS
* Webhooks
* App Inbox
* In-App
* Native Display
* WhatsApp

Here is a simple example of personalization with a liquid tag:

```Text Liquid Tag
{% if Profile.Language == "Spanish" %} 
Hola!
{% elsif Profile.Language == "English" %}
Hello!
{% endif %}
```

If the user's preferred language is Spanish, the greeting will appear in Spanish.

```text Output - Liquid Tag
Hola!
```

If the user's preferred language is English, the greeting will appear in English.

```text Output - Liquid Tag
Hello!
```

<Callout icon="📘" theme="info">
  #### Key Points to Remember

  - Liquid terms are adapted from [shopify's documentation](https://shopify.github.io/liquid/basics/introduction/) for use in CleverTap.  However, CleverTap supports only the terms listed in the document below.
  - When referencing properties, use `Profile.` and `Event.` with capital “P” and “E”, followed by a period.
  - Profile properties are available for all segments. Liquid tags for Event properties are available for live user segments, including Inaction campaigns with a delay greater than 24 hours. If the campaign uses Constant Event Property with a delay greater than 24 hours, `{{Event.*}}` tags fall back to their default values. For more information on using a constant event property, refer to [Constant Event Property](doc:constant-property).
  - The @ Personalization is supported only outside the tags.
</Callout>

# Getting Started

You can personalize your messages for [Events](doc:events) and [User Profiles](doc:user-profiles). For example, a user whose language is English (Profile property), or someone who has purchased (Event property) a new shirt.

Let us create a Liquid tag in an email campaign. To create a tag, select the "New email with rich media" template when you create an [email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps). You can use Liquid Tags within this template.


<Image src="https://files.readme.io/bc6d48d-Select_Rich_Media_Template.png" alt="2878" align="center" caption="Select a Rich Media Template" border={true} />


The Liquid Tags work within the email editor. However, you can also combine the power of HTML with Liquid Tags.  You can paste your HTML code directly in the HTML editor by clicking the Source button and then personalize it with Liquid Tags. For more information, see [Liquid Tags with HTML](https://docs.clevertap.com/docs/liquid-tags#section-liquid-tags-with-htmll)

The liquid terms are adapted from [shopify's documentation](https://shopify.github.io/liquid/basics/introduction/) to  CleverTap. We support only the terms identified in our documentation for a seamless experience.

# Using Tags

You can start creating your message by declaring tags in the campaign editor. You can declare the tags in the following ways:

* For creating message conditions - Conditional tags can help you vary the message for each condition. For example, if your users make a purchase, then send them a coupon with an additional discount for their next purchase. You can create a conditional tag by enclosing the condition within curly braces and a % sign. Start by entering `{%` in the email editor. The closing tag is completed automatically. The syntax for these tags is: `{% if %} {% endif %}`
* For displaying output from a variable - Output tags display the output of a variable. For example, if customer_type is a variable, display all the types of customers such as Platinum, Gold,  and Silver. Start by entering `{{` in the email editor. The closing tag is completed automatically. The syntax for these tags is: `{{customer_type}}`

You can use any of the Profile and Event properties within tags. Just enter `Profile.` or `Event.` in the editor and we will list all the corresponding properties automatically.

<Callout icon="📘" theme="info">
  #### Note

  When selecting properties, the "P" in profile and the "E" in Events must be capitalized and followed with a period ".". Profile properties are available for all segments. Liquid tags for Event properties are only available for live user segments. The "@" personalization is supported only outside the tags.
</Callout>

## Conditional Tags

You can use conditional tags for creating simple or complex conditional statements.  For example, If condition A, then send message 1, else send message 2, else-if message 3. If we were to express this in tags, we can use the user's preferred language as an example.

The following are the conditional tags:

* if
* else
* else-if
* unless
* switch case
* for
* break
* split
* continue
* abort
* limit
* offset
* tablerow
* now

### If

```text If Tag
{% if Profile.Language  == "French"%} 

Bonjour !

{% endif %}
```

### Else/Elseif

You can send messages conditionally to each recipient.

```liquid Else/Elseif Tag
{% if Profile.Language  == "French"%} 

Bonjour !

{% elsif  Profile.Language == "Spanish"%} 

Hola!

{% else %}

Hello!

{% endif %}
```

If the user's preferred language is French, the greeting will appear in French.  If the user's preferred language is Spanish, the greeting will appear in Spanish. However, if the preferred language is not French or Spanish, the greeting will appear in English.

```text Output - Else/Elseif
Hello!
```

You can display different messages based on the value of an Event Property (for example, Requested Product). Here is an example demonstrating the syntax for using Event Properties in Liquid Tags:

```liquid Else/Elseif Tag
{% if Event["Requested Product"] == "Personal Loan" %}
You selected **Personal Loan**. Here's what you need to know about it.
  
{% elsif Event["Requested Product"] == "Car Title Loan" %}
You selected **Car Title Loan**. Let's get started with your application.
  
{% else %}
It seems like we couldn't determine your requested product. Please try again.
{% endif %}
```

### Unless

You can use this tag if a condition is not true. For example, if a user's language is "not" French, then greet with "Hello" in English.

```liquid Unless Tag
{% unless Profile.Language  == "French"%} 

Hello!

{% endunless %}
```

The message display will be as follows:

```text Output - Unless
Hello!
```

### Switch case

You can switch a statement when a variable changes in value.  The `when` statements define the various conditions.<br />For example, you have three types of customers, namely "Gold", "Silver" and everyone else. They are represented by the profile property "customer_type".  You can change the displayed message based on the type of customers.

```liquid Switch case Tag
{% case Profile.customer_type %}
  {% when "Gold" %}
     You are eligible for free lounge access!
  {% when "Silver" %}
     You are eligible for lounge access at only 50% of the cost!
  {% else %}
     Upgrade your membership now for free lounge access!
{% endcase %}
```

```text Output - Switch case
Upgrade your membership now for free lounge access!
```

### for

You can repeat execution in liquid script with the for a loop.

```liquid for Tag
{% for item in hiking.items %}
  {{ item.names | default: "NA"}}
{% endfor %}
```

```text Output - For Tag
flashlight  backpack boots
```

### break

You can stop execution in the liquid script by adding break in a loop.

```liquid Break - Tag
{% for i in (1..10) %}
  {% if i == 7 %}
    {% break %}
  {% else %}
    {{ i | default: "NA" }}
  {% endif %}
{% endfor %}
```

```text Output - Break
1 2 3 4 5 6
```

### split

You can divide a string into an array using the argument as a separator. It converts comma-separated values from a string format to an array.

```text split
{% assign premium = " Customer 1, Customer 2, Customer 3, Customer 4" | split: ", " %}
{% for member in premium %}
  {{ member }}
{% endfor %}
```

`split` displays the following output:

```text Output - split
Customer 1

Customer 2

Customer 3

Customer 4

```

### continue

You can skip the current iteration in a loop with the continue tag.

```liquid continue - Tag
{% for i in (1..10) %}
  {% if i == 7 %}
    {% continue %}
  {% else %}
    {{ i | default: "NA"}}
  {% endif %}
{% endfor %}
```

```text output - continue
1 2 3 4 5 6   8 9 10
```

### abort

This is a CleverTap Tag within Liquid. You can abort sending a message with the abort tag. If a condition is not fulfilled for a user, it is displayed in the campaign reports as `LiquidLogicAborted`.

```liquid abort - Tag
{% if Event.price > 100%}
Thank you for your purchase. Here is a coupon code for you. 
COUPON
{% else %}
{% abort %}
{% endif %}
```

```text output - abort
Thank you for your purchase. Here is a coupon code for you. 
COUPON
```

### limit

You can specify the limit of the for loop with this tag.

```liquid limit - Tag
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array limit:2 %}
  {{ item | default: "NA" }}
{% endfor %}
```

```text output - limit
1 2
```

### offset

You can begin the loop at a specified index.

```liquid offset - Tag
<!-- if array = [1,2,3,4,5,6] -->
{% for item in array offset:2 %}
  {{ item | default: "NA" }}
{% endfor %}
```

```text output - offset
3 4 5 6
```

### tablerow

You can generate an HTML table with this tag. It must be wrapped in opening `<table>` and closing `</table>` HTML tags.

```liquid tablerow - Tag
<table>
{% tablerow product in Profile.multi %}
{{ product | default: "def" }}
{% endtablerow %}
</table>
```

```text output - Tag
<table>
  <tr class="row1">
    <td class="col1">
      Cool Shirt
    </td>
    <td class="col2">
      Alien Poster
    </td>
    <td class="col3">
      Batman Poster
    </td>
    <td class="col4">
      Bullseye Shirt
    </td>
    <td class="col5">
      Another Classic Vinyl
    </td>
    <td class="col6">
      Awesome Jeans
    </td>
  </tr>
</table>
```

### now

Using this tag, you can insert the current date and time in the specified format. Results are returned in IST (Indian Standard Time, UTC+5:30) by default.

```Text now - tag
{{ "now" | date: "%Y-%m-%d %H:%M" }}
```

### date_tz

Using this tag you can format the current timestamp in a specified IANA timezone. Use this filter when your messages need to display time in the recipient's local timezone or a specific regional timezone, regardless of the server timezone.

#### Syntax

```Text syntax
{{ "now" | date_tz: "<format>", "<timezone>" }}
```

#### Parameters

format: A string format for time (same as the standard date filter).

timezone: An IANA timezone string (for example, Asia/Singapore, America/Los_Angeles).

<Callout icon="📘" theme="info">
  ### Note

  Daylight saving time adjustments are handled automatically for time zones that observe Daylight Saving Time (DST).

  The date_tz filter is supported across all channels: Email, Mobile Push, SMS, Webhooks, App Inbox, In-App, and WhatsApp.
</Callout>

For example, you can use multiple date_tz calls within a single message to display time across different timezones simultaneously:

```Text date_tz
Singapore: {{ "now" | date_tz: "%Y-%m-%d %H:%M:%S", "Asia/Singapore" }}
London:    {{ "now" | date_tz: "%Y-%m-%d %H:%M:%S", "Europe/London" }}
New York:  {{ "now" | date_tz: "%H:%M", "America/New_York" }}
Sydney: {{ "now" | date_tz: "%Y-%m-%d %H:%M:%S", "Australia/Sydney" }}
Auckland: {{ "now" | date_tz:"%Y-%m-%d %H:%M:%S", "Pacific/Auckland" }}
```

## Variable Tags

### Assign

You can use the `assign` tag to assign value to a variable. The value of this variable can change based on the defined condition or a range. You can then reuse this variable across your message.

For example, you want to greet a user in French. You create a variable called `LANG`. Now, you can use this variable for all available languages. If the value of the `LANG` variable is French, the greeting is "Bonjour!". The greeting is "Hello!" for all other languages.

```liquid Assign Variable Tag
{% assign LANG = PROFILE.Language %}
{% if LANG == "FRENCH" %}
Bonjour!
{% else %}
Hello!
{% endif %}
```

## Theme Tags

### Raw

You can use the raw tag to display characters used by the tag syntax.

```liquid Raw Tag
{% raw %}{{ 5 | plus: 6 }}{% endraw %} equals 11.
```

```text Output - raw
{{ 5 | plus: 6 }} equals 11.
```

### Comment

You can comment on your code with this tag. It can be notes or description that you want to add to make your code more understandable.

```liquid Comment Tag
{% if Profile.Language  == "French"%} 

{% comment %} This condition is fulfilled only if the value is 
French {% endcomment %}

Bonjour !

{% endif %}
```

```text Output - Comment
Bonjour!
```

## Operators

You can use the following operators to evaluate conditions in your tags.

| Operator     | Description                                            |
| :----------- | :----------------------------------------------------- |
| **==**       | equals                                                 |
| **!=**       | does not equal                                         |
| **>**        | greater than                                           |
| **\<**       | less than                                              |
| **>=**       | greater than or equal to                               |
| **\<=**      | less than or equal to                                  |
| **or**       | logical or. Choose between condition 1 or condition 2. |
| **and**      | logical and. Choose conditions 1 and condition 2       |
| **contains** | check for a string within a string                     |

# Liquid Personalization with Nested Objects

You can personalize campaign messages using nested objects within profile-based and event-based personalization for deeper data granularity in your campaigns. To use nested personalization, ensure that **Nested Object Personalization** is enabled for your account.

**Syntax**

Nested profile and event personalization are supported up to 3 levels. Use the following syntax to configure personalization placeholders:

* Nested Profile Personalization: `{{ Profile.<property_name>.<level_1>.<level_2>.<level_3> | default: "Default" }}`
* Nested Event Personalization: `{{ Event.<property_name>.<level_1>.<level_2>.<level_3> | default: "Default" }}`

When using nested personalization, you must use the Preview & Test option to validate your message before publishing the campaign.

<Callout icon="📘" theme="info">
  #### Supported Channels

  You can use Nested Personalization with the following channels: Email, Mobile Push, SMS, Webhooks, and WhatsApp.
</Callout>

#### Example

Nested personalization is especially useful when your profile or event data is stored in structured objects such as subscription details, order information, travel bookings, or product metadata.

For example, suppose your profile stores subscription information in the following structure:<br />subscription > plan > name

You can reference the plan name using`{{ Profile.subscription.plan.name | default: "your current plan" }}`

**Sample Campaign**

```liquid
Thanks for being a {{ Profile.subscription.plan.name | default: "valued" }} member! Unlock your exclusive benefits today.
```

In this case, the campaign dynamically inserts the exact plan name (for example, Gold or Premium), making the message more contextual and relevant. If the value is unavailable, the default value ensures the message remains natural.

# Liquid Tags with HTML

This section applies only to the email channel.

You can combine your HTML code with Liquid Tags to create beautiful and personalized messages for your users. To do so:

1. Open the message editor and paste your HTML code.
2. Click the ![](https://files.readme.io/651c228-Liquid_tag_icon.png) icon and add your Liquid Tags.


<Image src="https://files.readme.io/e7aa86c-Add_Liquid_tags.png" alt="2876" align="center" caption="Add Liquid Tags" border={true} />


# Linked Content and Liquid Tags in Drag and Drop Editor

Linked Content and Liquid tags are available for the drag-and-drop email editor. This functionality allows customers to design emails and personalize them using dynamic content when they create an [email campaign](https://docs.clevertap.com/docs/email#section-email-campaign-creation-steps).

Perform the following steps to personalize drag and drop editor templates with liquid tags.

1. Select a template.


<Image src="https://files.readme.io/0fc50d2-Select_Media_Template.png" alt="2878" align="center" caption="Select Media Template" border={true} />


2. Click the Row item in _Preview_.


<Image src="https://files.readme.io/b461f6b-2020-07-28_19-19-33_Select_row_item.png" alt="1047" align="center" caption="Select the Row Tab" border={true} />


3. Click _More_ dropdown and select **Customize with Liquid Tags**. The _Personalize messages with Liquid tags and Linked Content_ popup displays.


<Image src="https://files.readme.io/6404ab8-Select_Customize_with_Liquid_Tags.png" alt="2862" align="center" caption="Customize with Liquid Tags" border={true} />


4. Add the liquid script inside the popup.


<Image src="https://files.readme.io/57f0cf4-Add_liquid_script.png" alt="2856" align="center" caption="Add Liquid Script" border={true} />


5. Click **Add**.

# Validate Liquid Tags

When creating a campaign message with Liquid tags, errors appear in real time if the syntax is incorrect. Errors also surface when clicking **Done** on the campaign creation page if the message contains invalid Liquid Tag syntax. You can also use **Preview & Test** in the message editor to validate your message and send test campaigns with personalized values.

Here is an example of how to add Liquid Tags in the message editor:


<Image src="https://files.readme.io/e7aa86c-Add_Liquid_tags.png" alt="Add Liquid Tags" align="center" caption="Message Editor" border={true} />


Here is an example of how CleverTap validates the Liquid Tag syntax from the campaign creation page:


<Image src="https://files.readme.io/0f35bde51577891264842c57d7064bb06d2e0e4608e466c245cf8aa366912050-image.png" alt="Validating the Liquid Tag Syntax" align="center" caption="Validating the Liquid Tag Syntax" border={true} />


# Video Tutorial

You can watch the following video to learn more about Liquid Tags personalization.

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
              src="https://clevertap.portal.trainn.co/share/9vrJTcuXpv8PGXDWIgM32w/embed?autoplay=false"
              frameborder="0"
              webkitallowfullscreen
              mozallowfullscreen
              allowfullscreen
              allow="autoplay; fullscreen"
              style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>
`}</HTMLBlock>
