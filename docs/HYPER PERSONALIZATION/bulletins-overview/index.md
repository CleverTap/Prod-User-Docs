---
title: Bulletins
excerpt: >-
  Learn how to use Bulletins to send personalized messages to interested users
  each time a business event occurs.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Overview

Bulletins automatically send personalized messages to interested users each time a business event occurs, such as a new episode release, an album launch, or a product restock.

Many businesses announce the same kind of event again and again, with only the details changing. For example, a streaming app announces new seasons for hundreds of shows, and a music app announces new albums for thousands of artists. Creating a campaign for each announcement takes time and does not scale. With Bulletins, you create the setup once, and CleverTap handles each announcement.

Each time your system raises a business event, CleverTap identifies users who have shown interest in that specific show, artist, or product and sends them a message. For example, when a new season of a series launches, CleverTap sends the message only to users who watched that series recently.

With Bulletins, you can:

- Define business events that describe what happens in your business, with properties that identify each one, such as the series name.
- Decide who counts as interested by matching a business event property to user events or user properties.
- Add several campaigns to one bulletin so a single business event reaches users via Push notification, Web push, Email, and SMS.
- Personalize each message with the properties that your system sends with the business event.
- Monitor how each business event performs, including conversions and delivery errors.

## How Bulletins Work

A bulletin connects what happens in your business to users who have shown interest. Three parts make this work.

- **Business event**: An action or update on your side that can affect user engagement, such as a new episode release. A business event carries properties that describe the item, such as the series name.
- **Bulletin**: Names the business event, defines which users can receive the message, and states which business event property to match against user behavior.
- **Campaigns**: The messages the bulletin sends. Each campaign uses one channel.

The following example shows the flow for a streaming app:

1. You create a business event named _New Season Launched_ with the property `series name`.
2. You create a bulletin that qualifies users who watched a series at least 10 times in the last 30 days, and you match the series name of the business event to the series name in their viewing events.
3. You add a push campaign to the bulletin and publish it.
4. Your content team launches a new season of a series. Your backend raises the New Season Launched business event with the series name.
5. CleverTap identifies users whose viewing history matches the series name and sends each active campaign in the bulletin to them.
6. The next time another series launches a season, your backend raises the same business event with a different series name. The same bulletin reaches a different audience, and you create no new campaign.

The match between the business event property and user behavior determines the audience each time.

## Use Cases

Use Bulletins when you send the same type of message repeatedly, and the audience depends on what the message is about. The following table lists common use cases:

| Use Case                                                       | Business Event      | Business Event Property | Users Who Qualify                                                           |
| -------------------------------------------------------------- | ------------------- | ----------------------- | --------------------------------------------------------------------------- |
| **Streaming:** announce a new season or episode                | New Season Launched | `series_name`           | Users who watched the series several times in the last 30 days              |
| **Music:&#x20;**&#x61;nnounce a new album                      | Album Released      | `artist_name`           | Users who played songs by the artist several times in the last 30 days      |
| **Retail:&#x20;**&#x61;nnounce that a product is back in stock | Back in Stock       | `product_category`      | Users who viewed products in the category several times in the last 30 days |
| **Sports:** announce that a match is about to start            | Match Started       | `team_name`             | Users whose Favorite Team user property equals the team name                |

For each use case, you create one bulletin. Each time the business event occurs, your system sends the property value, and CleverTap selects the audience and sends the message. You do not create a separate campaign for each series, artist, product category, or team.

## Prerequisites

Confirm the following before you create a bulletin.

- Bulletins are enabled for your account. When enabled, the Bulletins item in the left navigation opens a page containing the Bulletins and Business Events sections.
- You have write access to Bulletins. Users without write access see a limited-access message and cannot create or modify bulletins.
- Your app already sends the user events and user properties that you want to use to find interested users. For example, to find users who watched a series, your app must send a viewing event with a series property.

## Next Steps

- Create a business event, raise it, and monitor it. For more information, refer to [Create Business Events](doc:create-business-events).
- Create a bulletin and add campaigns to it. For more information, refer to [Create Bulletins](doc:create-bulletins).