---
title: Regex
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
# Overview

Regex is a feature that enables you to create a campaign that includes or excludes users who visit specific pages on your website. 
[block:callout]
{
  "type": "info",
  "body": "Regex is an abbreviation for the term regular expression, which defines a search pattern for a string. The pattern can be a single character, multiple characters, or an expression with characters describing the pattern. \n\nHere are some Regex examples: \n* \".\" matches any character.\n* \"ABC\" matches ABC.\n* \"A|B\" matches A or B.",
  "title": "Regex Explained"
}
[/block]
For example, let's say you have a travel booking site, and want to create a campaign that targets users who are searching for flights between San Francisco and Los Angeles. When a user searches for flights from San Francisco (SFO) to Los Angeles (LAX) on your website, the URL follow this pattern: https://www.example.com/flights/SFO/LAX. Using the Regex below, you can identify users who visited that URL and include them in a campaign.
[block:code]
{
  "codes": [
    {
      "code": ".*(SFO|LAX).*",
      "language": "text",
      "name": "Regex"
    }
  ]
}
[/block]
# Feature Guide

When creating a campaign in CleverTap that targets web users, you can use the Regex feature to define who will receive the campaign based on pages the user did or did not visit. 
[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a70f69-regex2.png",
        "regex2.png",
        900,
        400,
        "#f5f8fb"
      ],
      "border": true
    }
  ]
}
[/block]
If you want to include users who visited a page that matches the Regex, select the **matches regex** option. If you want to exclude those users, select the **does not match regex** option.

If there is only one page that needs to be matched or not matched for a campaign, then you can just use the options **contains** or **does not contain**.

# Examples
[block:parameters]
{
  "data": {
    "h-0": "Regex",
    "h-1": "Notes",
    "0-0": ".",
    "1-0": "example text",
    "2-0": "example\\s+text",
    "1-1": "Matches exactly. For example: \"example text\".",
    "2-1": "Matches the word \"example\" followed by one or more whitespace characters followed by the word \"text\". For example: \"example   text\".",
    "0-1": "Matches any character.",
    "3-0": "A|B",
    "3-1": "Matches A or B."
  },
  "cols": 2,
  "rows": 4
}
[/block]
# Regex Verification

You can use [Regex101.com](https://regex101.com/) to build and test your Regex.