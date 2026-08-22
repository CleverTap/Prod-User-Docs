---
title: Troubleshooting & FAQs
excerpt: Explore troubleshooting tips and FAQs for Facebook Audiences
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Here’s a concise guide of troubleshooting tips and frequently asked questions to help you address common issues with Facebook Audiences.

### What happens if I open an old draft or clone an older Facebook campaign?

When you open an old draft or clone a previously created Facebook campaign, it will open using the new default setup:

* The default ad account will be selected in the **Set Up** step.
* The **first audience** under the selected ad account will be preselected in the **What** section.
* The **Who** section (target users) will remain unchanged.\
  Since the campaign workflow has been updated, we strongly recommend **reviewing all campaign details** before publishing to ensure everything is configured as expected.

### Can I publish a campaign that uses the old Facebook campaign structure?

No, you cannot publish campaigns using the old structure. Before it can be published, you must update it to align with the new format.

### What happens when I open an older Facebook campaign in Completed, Scheduled, or Recurring state?

CleverTap maintains legacy compatibility for viewing data from older campaigns, but editing limitations apply.

* The *Campaign Overview* page will continue to display as expected.
* The *Stats* page will display data using the old structure for consistency and historical accuracy.
* No edits can be published unless the campaign is updated to the new structure.

### Can I use an old Facebook campaign node in a Journey?

No. You cannot publish a Journey that includes a Facebook campaign node built using the old structure. The system will block the publish action until the node is updated to the new structure.

> 📘 Note
>
> To check if a Facebook campaign node is using an outdated structure, try opening it in the Journey builder. If the node requires an update, the interface will prompt you to reconfigure it before proceeding.

### What happens to the Facebook campaign node in Journeys that use the old structure?

The **Facebook Node** in the **What** section of the Journey will be reset. You must reconfigure it using the latest campaign structure to proceed.

### Why am I seeing the error "Connect to Business Manager to create this audience"?

This error appears when your **ad account is not connected to a Business Manager**, which is now a Facebook requirement for creating or editing **Custom Audiences**.

To resolve the issue:

* Go to [Business Settings](https://business.facebook.com/latest/settings/ad_accounts).
* Under Accounts, click Ad Accounts.

  <Image alt="Add Ad Accounts to Business Manager" align="center" src="https://files.readme.io/9100bef3774c8a43db8ca98f55ba752692e46ca1ec677a8a39a86c8674efe9ee-image.png">
    Add Ad Accounts to Business Manager
  </Image>
* Click + Add, and choose one of:
  * Add Ad Account (permanently move it into Business Manager — must be the owner).
  * Request Access to an Ad Account (if it's owned by someone else).
  * Create a New Ad Account (new accounts are automatically managed via Business Manager).

> 🚧 Note: Once an ad account is added to a Business Manager, it cannot be removed or moved elsewhere.

**Common reasons you may not be able to add an ad account:**

* The ad account is already owned by another Business Manager.You've already added a personal ad account (only one allowed).\
  You've reached the limit of 5 ad accounts in your Business Manager. This limit increases with your ad spend.

### Why are my Custom Audiences not populating or failing?

* You haven’t accepted the Custom Audiences [Terms of Service](https://business.facebook.com/ads/manage/customaudiences/tos/) — this is mandatory, and missing approval can block audience creation.
* User Setting up Ad Accounts in CleverTap lacked admin permission of Facebook ad account.
* Tip: Reauthenticate integrations and ensure correct roles in the ad account

### Minimum audience size requirement for Lookalike Audiences?

Seed data must contain at least 1000 users in a single country, though Facebook recommends 5000–10,000 for accuracy. 

### How long for synced audiences to show up?

It may take 6–48 hours for audiences to appear in your destination platform after syncing.

### What user data can I sync?

Facebook allows email, phone, name, ad ids etc., while CleverTap only uses email or phone numbers only.

### What is match rate?

Match rate = (matched audience size) ÷ (uploaded audience size). A high match rate means more of your users are found and targeted on Facebook

### Why is my match rate low (e.g., 20–30%)?

* Facebook users may use different emails or phone numbers than your list.
* Privacy changes (iOS 14+, GDPR/CCPA) limit available identifiers.
* Missing required identifiers: Facebook can match up to 15 types, but you are exporting only few. 
* Poor data hygiene: internal formatting or incorrect data reduces matching

### How to improve match rate?

* Add more identifiers: first/last name, city, zip, DOB, advertiser IDs .
* Clean and normalize data before upload (remove punctuation, correct casing) .
* Use data enrichment or append services for missing info.

### How can Facebook’s audience be bigger than my uploaded file?

* When uploading identifiers (email, phone, Facebook IDs), you might send multiple identifiers for the same user. Facebook may match these to different accounts, resulting in a higher audience count than rows in your file.
* If you’ve synced the same user list via different CleverTap campaigns or even other sources , Facebook might merge audiences—so overlapping identities can inflate the final count.
* Facebook often estimates or rounds audience sizes, which may cause it to display a slightly higher number than the actual matches

### Why is my audience smaller than the uploaded list?

* Invalid or unmatched records are dropped—e.g. wrong formatting, duplicates, or users not on FB.
* Some users may not have updated identifiers or may not be active FB users.
* In the case of website audiences, only visitors with identifiable Meta cookies/device combos are included
