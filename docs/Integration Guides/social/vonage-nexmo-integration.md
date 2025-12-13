---
title: '[Internal] WhatsApp Integration Using Vonage (Nexmo)'
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
[block:api-header]
{
  "title": "Overview"
}
[/block]

WhatsApp is a popular messaging channel that allows businesses to communicate with their users in a secure, friendly and interactive manner. WhatsApp’s interaction metrics are superior compared to other platforms (high click-through rates and high response rates to be more specific). Additionally, WhatsApp has over 2 billion + monthly active users in over 100+ Countries.

**Listed below are a few use case scenarios**
1. Send real-time notifications to customers regarding delivery alerts and booking confirmations.
2. Send personalized recommendations about new products, offers, and services through rich media sharing.
3. Delight your customers with reminders about their upcoming bookings.
4. Enable your customer support team to respond to customer queries instantly.

[block:api-header]
{
  "title": "Why Vonage (Nexmo)?"
}
[/block]
Vonage is an award-winning CPaaS (Communications Platform-as-a-Service) provider recognized by leading analysts like Gartner, IDC as leaders in communications services.  
[block:callout]
{
  "type": "info",
  "title": "Note:",
  "body": "Vonage acquired Nexmo in 2016. Since then, Nexmo is a part of Vonage and collectively, the CPaaS platform is now recognized as Vonage. [Learn more](https://www.prnewswire.com/news-releases/vonage-completes-the-acquisition-of-nexmo-advancing-vonages-mission-to-become-the-global-cloud-communications-leader-300279974.html)"
}
[/block]
CleverTap supports WhatsApp messaging through Vonage for WhatsApp Business messaging services. Clevertap has a close integration with Vonage that enables us to send templated messages, receive campaign metrics (sent, delivered, etc.) & leverage the conversation feature.

[block:api-header]
{
  "title": "Prerequisites"
}
[/block]
1. The customer should have a Facebook Business page.
2. The customer should have a Business Manager Account. Business Manager is a Facebook tool that helps you organize and manage your business. 

[Learn more about Facebook Business Manager Account](https://en-gb.facebook.com/business/help/1710077379203657) 

3. The customer should have a new phone number for WhatsApp Business Account creation with Vonage. (Note - The phone number shouldn’t be associated with any other WhatsApp Business provider earlier)

Refer to this [detailed document by Facebook](https://developers.facebook.com/docs/whatsapp/guides/phone-number/#pick-number) to learn more about phone number requirements for WhatsApp Business Account.
 
## Step 1: Fill Clevertap Form
Sales Representative - Sales/CS representative will get the customer to fill CleverTap’s WhatsApp Brand Approval Form.

## Step 2: WABA Account Creation Process Initiation by the Product Manager

The Product Manager needs to: 
1. Reserve an API subkey for the brand on the Vonage dashboard.
2. Create an application for messages in the Vonage dashboard.

## Step 3: Fill up the Vonage form

The Product Manager needs to use the CleverTap form & Vonage WhatsApp dashboard of the brand to fill up the Vonage form
Further, the Product Manager will initiate one email with Vonage to intimate them about the form submission, copying CleverTap’s Sales representative and Customer success manager.
[block:callout]
{
  "type": "info",
  "title": "Note:",
  "body": "This email will keep a track of the entire onboarding journey for the customer. All onboarding updates for the customer needs to be shared on this thread. This will not involve any contract matters and is purely restricted to onboarding updates."
}
[/block]
## Step 4: Contract Signing

* Vonage Team - Vonage will send the contract to the client’s point of contact (POC) to get it signed.
* As soon as the client signs the contract, it will be available for CleverTap’s finance team to sign.

## Step 5: Vonage Onboarding Process

* Vonage team - Once the customer applies for brand approval via CleverTap’s form, the process thereafter can take anywhere between 1-2 weeks, (assuming that there are no other roadblocks on the way). 
* There are a few steps that Vonage carries out as a part of their onboarding process:
  * Jewel notification acceptance and customer’s account verification on Facebook.
  * Spin up the WhatsApp Business Account (perform the OTP verification on the registered number). 
  * Initiate the green tick box for a verified account by Facebook (optional).
 * Templates registration - Note that WhatsApp template approvals take 5-7 working days. 
 * Vonage team - Once the WABA Spin-up is complete, an email is sent to all the stakeholders acknowledging the successful activation process from Vonage’s end.

## Step 6: Configuring WhatsApp Provider Settings on Clevertap Dashboard

* Product Manager - The product manager will configure the Provider details under WhatsApp settings on CleverTap’s Dashboard for the client and inform all the stakeholders about the completion of the process.

## Step 7: Adding Approved Templates in CleverTap Dashboard

*Once a template is approved by Facebook, the client will add the approved templates to CleverTap Dashboard.
  * Settings > Engage > Channels > WhatsApp
   * Select Nexmo from Provider’s Name > Template Tab > “+ Template”
   * Add the template and click Save.

Refer to this document on [How to Configure Message Templates](https://docs.clevertap.com/docs/whatsapp#section-configure-message-templates) for detailed illustration.

# Initial Warm-Up

WhatsApp allows a restricted distribution of messages after initial setup. As customer usage increases, customers are provided with a bigger bracket. This restriction is not on the number of messages sent out but on the number of end-users you are reaching out to. Some indicative tiers are: 

1. Tier 1: Allows your business to send messages to 1K unique customers in a rolling 24-hour period.
2. Tier 2: Allows your business to send messages to 10K unique customers in a rolling 24-hour period.
3. Tier 3: Allows your business to send messages to 100K unique customers in a rolling 24-hour period.

To learn more about the limits and how a customer can transition to the next tier, [refer to this detailed document from Facebook](https://developers.facebook.com/docs/whatsapp/api/rate-limits#messaging).

#Opt-in

It is mandatory for Vonage to get the opt-in consent of the end-user prior to sending them WhatsApp messages. This is usually done at the Vonage’s end.

However, to reflect this in CleverTap Account, the client must get this info for opted-in users from the provider and update profile property *MSG_WhatsApp* for applicable profiles in CleverTap. 

Learn more about [Opting in users into WhatsApp](https://docs.clevertap.com/docs/whatsapp#section-opting-in-users-into-whatsapp) to get detailed information on the process.

To dig deeper, one can also [refer to this document from Facebook for a better understanding](https://developers.facebook.com/docs/whatsapp/guides/opt-in).