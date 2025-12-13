---
title: Regex_Campaign_redesign_WIP
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

Regex is a feature that provides the capability to create a campaign that includes or excludes users who visit specific pages on your website. 

> 📘 Regex Explained
>
> Regex is an abbreviation for the term regular expression which defines a search pattern for a string. The pattern can be a single character, multiple characters, or an expression with characters describing the pattern. 
>
> Following are some Regex examples: 
>
> * "." matches any character.
> * "ABC" matches ABC.
> * "A|B" matches A or B.

## Use Case

For example, if you have a travel booking site, you can create a campaign that targets users who are searching for flights between San Francisco and Los Angeles. When a user searches for flights from San Francisco (SFO) to Los Angeles (LAX) on your website, the URL follows this pattern: *[https://www.example.com/flights/SFO/LAX](https://www.example.com/flights/SFO/LAX)*. Using the Regex below, you can identify users who visited that URL and include them in a campaign.

```text Regex
.*(SFO|LAX).*
```

# Feature Guide

When creating a campaign or a journey in CleverTap that targets web users, you can use the Regex feature to define who receives the campaign based on pages the user did or did not visit. 

@DK/PM: COULDN'T FIND REGEX UNDER THE WHO OF THE NEW UI. CAN YOU PLEASE HELP WITH THE SCREENSHOT? WE MOST LIKELY NEED TO REWRITE THE STEPS AS WELL. PLEASE ADVISE. THANKS.

<Image title="regex2.png" alt={900} className="border" border={true} src="https://files.readme.io/8a70f69-regex2.png" />

If you want to include users who visited a page that matches the Regex, select the *matches regex* option. If you want to exclude those users, select the *does not match regex* option.

If there is only one page that needs to be matched or not matched for a campaign, then you can use the options *contains* or *does not contain*.

# Examples

The following table shows more examples:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Regex
      </th>

      <th>
        Notes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        .
      </td>

      <td>
        Matches any character.
      </td>
    </tr>

    <tr>
      <td>
        example text
      </td>

      <td>
        Matches exactly. For example: "example text".
      </td>
    </tr>

    <tr>
      <td>
        example\s+text
      </td>

      <td>
        Matches the word "example" followed by one or more whitespace characters followed by the word "text". For example: "example   text".
      </td>
    </tr>

    <tr>
      <td>
        A|B
      </td>

      <td>
        Matches A or B.
      </td>
    </tr>
  </tbody>
</Table>

# Regex Verification

You can use [Regex101.com](https://regex101.com/) to build and test your Regex.
