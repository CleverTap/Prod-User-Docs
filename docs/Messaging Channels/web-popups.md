---
title: Web Popups
excerpt: ver 1.2
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

Web notifications are popup messages that are displayed on desktop or mobile websites.

CleverTap web notifications are displayed in either of the following ways:

* On the footer of your site; available for desktop and mobile websites.
* Before the user exits your site; known as exit intent web popups that are available only for desktop.

> 🚧 Prerequisite
>
> The prerequisite to set up web popup campaigns is to integrate your website with the CleverTap JavaScript plugin. For more information, refer to [Web](https://developer.clevertap.com/docs/web) in the developer documentation.

# Web Popup

Web popups provide the capability to send quick alerts, offers, or how-to byte-sized content to your users using our built-in web popup builder or your own custom HTML templates. The *Web Popup* feature makes it easy to set up web popup campaigns for all your users or specific user segments. 

These segments are created based on either of the following ways:

* User action on one of your webpages
* User visiting one of your specific webpages
* User visiting your website via an external ad referral
* User visits to a number of webpages

After sending the campaign, you can view detailed reports on how many messages were sent, how many users converted as a result, and so on.

# Web Exit Intent

CleverTap’s web exit intent popups help with encouraging subscriptions or gathering information from users before they leave your website. CleverTap’s rich segmentation offers the ability to display time-sensitive, relevant, and personalized web popup campaigns on a large scale. 

# Web Popup Campaign Creation

This section shows how to create a web popup campaign

## Create a New Campaign

To start creating a web popup campaign:

1. Navigate to *Campaigns*. 
2. Click on the **+Campaign** button.
3. Select *Web Popup* under the *Messaging Channels* list. 

<Image title="Screenshot 2021-08-03 at 12.30.42 PM.png" alt={818} width="smart" src="https://files.readme.io/b14acff-Screenshot_2021-08-03_at_12.30.42_PM.png" />

The campaign page displays.

<Image title="Web_pop_up_Editor_main.png" alt={1100} className="border" width="80%" border={true} src="https://files.readme.io/4bf6219-Web_pop_up_Editor_main.png" />

Once all the sections are defined, you can publish the campaign.

## Start Campaign

The *Start here* section displays the setup information. 

**Goal:** You can track your campaign conversion by setting up a goal. Setting a goal allows you to measure your campaign effectively against what you want to achieve in the campaign. This selection is optional.

The campaign goal can be as generic or as specific as you want. It can answer questions from *How many users were influenced for purchasing an X amount?* to *How many first-time visitors purchased red shoes worth a minimum of X amount and blue jackets worth a minimum of Y amount?*". 

Create focused conversions using event properties.  For more information on event properties, see [Events]\(doc: events). 

Define the conversion period by selecting the *Funnel Conversion Time*. 

<Image title="Push_notification_set_goal_track_conversion.png" alt={919} className="border" border={true} src="https://files.readme.io/4fbbeb2-Push_notification_set_goal_track_conversion.png" />

## Define the Who

You must indicate the target audience for your Web Popup campaign. You can target your Web Popup campaign to a new user segment by clicking on the **Target segment** section. Here, you can create a new ad-hoc segment or use a previously saved user segment from the *segment* list. 

<Image title="campaign_Who_Live_segment.png" alt={964} className="border" border={true} src="https://files.readme.io/a92d833-campaign_Who_Live_segment.png" />

Campaigns can be configured based on the following types of user interactions:

* Single action: User performs an action on one of your web pages.
* Page visit: User visits a particular web page on your website.
* Page referral: User visits your website via an external ad referral URL.
* Page count: Number of your web pages a user has visited so far in their session.

### Ad-hoc Segment

If you want to create an ad-hoc segment, you can define a target segment by leveraging the action properties and additional filters for your Web Popup campaign. You can create the target audience on the basis of past user behavior and/or user properties, or live (ongoing) user behavior (the latter is useful to send out real-time, triggered Web Popup campaigns).

For instance, you can create a live *Inaction within time* campaign that targets users as soon as they add a product to their cart but do not finish transacting within 10 minutes; the golden window within which most users transact on iOS and Android app platforms.

Based on the data, you can then set up the *Who* by choosing to send this campaign to all users who qualify or just a portion of the users who qualify under *Estimated reach*. 

### Deliver Action Based Web Popup Notifications

You can trigger a Web Popup message based on an action. Users receive Web Popup notifications when they perform an action in the app instead of waiting for the next app launch. This makes notifications more contextual and increases conversion. 

### Filter by User Properties

Using the *With user properties* filter in the *Who* section, you can segment your campaign to only reach users who meet specific criteria. 

For example, you can send a Web Popup notification to English-speaking female users who live in the United States. 

The following table explains the various property types:

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Property Type
      </th>

      <th>
        Description
      </th>

      <th>
        Example
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        User Properties
      </td>

      <td>
        Custom [user profile properties](https://docs.clevertap.com/docs/user-profiles#section-user-profile-data-model) that you define and send to CleverTap.
      </td>

      <td>
        Customer Type = Platinum
      </td>
    </tr>

    <tr>
      <td>
        Demographics
      </td>

      <td>
        Demographics filters include *Age* and *Gender*.
      </td>

      <td>
        Age = 25 to 40 years\
        Gender = Female
      </td>
    </tr>

    <tr>
      <td>
        Geography
      </td>

      <td>
        User's coarse location. Filters include *Country*, *Region*, and *City*. CleverTap's SDK can automatically detect this from the user's IP address.
      </td>

      <td>
        Country = United States\
        State = California\
        City = San Francisco
      </td>
    </tr>

    <tr>
      <td>
        Reachability
      </td>

      <td>
        Reachability filters include *Has email address*, *Has phone number*, *Unsubscribed email*, and *Unsubscribed SMS*.
      </td>

      <td>
        Unsubscribed email = No
      </td>
    </tr>
  </tbody>
</Table>

To know more about what segments can be used, see [Segments](doc:segments).

### Constant event property

You can also hold a property constant across the selected events.  For more information, see [Constant Event Property](doc:constant-property). 

### Control Group

You can define the control group to compare and measure the results of your campaign. For more information on control groups, see [Control Groups]\(doc:control-groups.

![1107](https://files.readme.io/a739a68-campaign_control_group_targeting_cap.png "campaign_control_group_targeting_cap.png")

### Targeting Cap

This section explains the campaign creation flow when you are determining who to send your message to. Under the *Estimated Reach* section, select the option to limit the delivery of the messages to a specified number.

Sometimes, you want to send a message to only a subset of the qualifying audience (*Target Reach*) for a campaign or avoid sending it if the number of qualified users exceed the specified number.

For instance, on a limited offer where you want to send a fixed number of coupon codes to distribute.\
If the total reach for your campaign exceeds the number of coupon codes you can distribute, you can limit the number of users who will receive the message to exactly the number of coupons you want to distribute.

![406](https://files.readme.io/3aa9241-subset_image.png "subset_image.png")

For triggered campaigns based on live user segments, the qualified users receive a message until the total quantity specified is delivered after which the campaign ends. We randomly select the users who receive the message for campaigns based on *Past Behavior Segments*.

The campaign limits can also be configured as follows: 

* Limit the number of users for each day, for *Best Time*, *User-Timezone*, and *Triggered* campaigns.
* Limit the number of users for each run of a campaign, for *Fixed Time* or *Recurring* campaigns.
* Prevent sending out unwanted campaigns. A campaign does not run if the number of qualified users exceeds the safety limit. The campaign creator receives an email alert for further action. 

> 👍 Safety Check Example
>
> A customer has a budget for distributing 1,000 discount coupons but the qualified user count is 10,000. If you select the safety check, the campaign does not run and prevents the sender from spending over budget.

## Define the What

Now, you can set up the *What* which is the Web Popup campaign content.

Click *Go To Editor* to create your message. 

![1048](https://files.readme.io/8a73e71-Webhook_what_without_options.png "Webhook_what_without_options.png")

The *Create Web Popup Message* window displays.

## Template Selection.

CleverTap supports three types of templates for Web popup creation - *Basic*, *Ratings*, and *Custom HTML.*

1. Basic Templates

At a high level, one can choose from three styles of popup layouts available under Basic Templates:

* **Box** - It's a small popup that can be placed at the desired corners of the browser window.
* **Banner**- It's a wide horizontal popup that can be either placed at the top or bottom of the browser window.
* **Interstitial** - It's a center-aligned popup particularly used for driving better engagements.

2. Custom HTML Templates

Users have a choice to customize their popup's appearance for the Box, Banner, and Interstitial templates. One simply needs to insert the custom HTML scripts for the respective template layout in the HTML editor.

3. Ratings Template

Marketers can now create feedback-related popups (Interstitials only) for their website users using the *Ratings Template*. Refer to the image below for a sample user rating popup.

![1206](https://files.readme.io/a18e4dd-Screenshot_2021-08-25_at_5.57.15_PM.png "Screenshot 2021-08-25 at 5.57.15 PM.png")

Marketers get the complete flexibility to explicitly define the rating scale, its shape (Star, Heart, Emojis), labels, and the overall content of the popup. One can also choose to add a comment box to get accurate user feedback/comments. Besides, additional customizations such as the background color of the notification, text color, and the color of the rating scale are also possible.

### Tracking Events

Whenever a user submits the feedback form, the **Rating Submitted** event is triggered. This event includes properties such as *User Rating, Input Type, Comment*.\
Refer to the table below for a better understanding of the event properties.

<Table align={["left","left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Event Name
      </th>

      <th>
        Properties
      </th>

      <th>
        Data Type
      </th>

      <th>
        Sample Value
      </th>

      <th>
        Comments
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Rating Submitted
      </td>

      <td>
        User Rating
      </td>

      <td>
        Number
      </td>

      <td>
        3
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Input Type
      </td>

      <td>
        String
      </td>

      <td>
        Rating
      </td>

      <td>

      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Comment
      </td>

      <td>
        String
      </td>

      <td>
        Awesome product
      </td>

      <td>
        512 characters limit
      </td>
    </tr>

    <tr>
      <td>

      </td>

      <td>
        Campaign Id
      </td>

      <td>
        String
      </td>

      <td>
        17654
      </td>

      <td>

      </td>
    </tr>
  </tbody>
</Table>

The event details can then be tracked from the Analytics dashboard.

## Analysis of Data Captured using Ratings Template

1. When a user submits a rating by clicking on Submit button on the Web popup, a Rating Submitted event is triggered.
2. This event is available across the CleverTap platform. It helps in creating targeted segments for users to engage them on various channels based on their rating feedback. 
3. This event can also be used in Analytics for the analysis of data captured through the **Ratings** campaigns. 

Listed below are the steps to perform analysis for some of the key metrics:

1. To view the *Trend* for the number of ratings submitted and Frequency histogram:

* Go to *Analytics > Events*. 
* From the event dropdown, search for *Rating Submitted* event and click on **View details**.
* Under the *Trends & Properties* tab, one can view the trend for the number of ratings submitted on a Daily, Weekly, and Monthly basis.
* Select Event property as *Ratings* to get a histogram view of the rating scale.

2. To analyze the Average Rating trends

* Go to *Analytics > Trends*
* Select the *Rating Submitted event* > *+Summarize by* “User Rating” property and click on **View Trend**
* Navigate to the *Properties* tab and select *Average of property value* from the *View* dropdown. 
* You can also analyze the trend of Average Rating on a Daily, Weekly, and Monthly basis.

> 📘 Pinning Reports to Dashboards
>
> One can also pin the reports or specific trend charts to a custom dashboard using the pin icon available at the extreme right for monitoring the data at regular intervals.

## Define the When

![1962](https://files.readme.io/211ef85-Screenshot_2021-08-06_at_7.40.16_PM.png "Screenshot 2021-08-06 at 7.40.16 PM.png")

Set up the *When* to define the campaign schedule.

If it is a limited-time incentive, you might want to end the web popup at a particular date and time. On the other hand, if it is always relevant, you can specify that the campaign never ends; however, if you change your mind later, you can always stop the campaign by clicking on the *Stop campaign* icon next to the campaign on the main web popup Campaigns page.

In addition, you can even specify a minor delay so that the web popup is displayed a few minutes after the user does the trigger action for the campaign to give them time to apply the payment offer. You can also set campaign frequency by specifying any specific days of the week and times of the day you would like for it to be inactive.

Finally, you can specify how often users receive the campaign: Bypass global campaign limits by checking the Exclude from campaign limits radio button or choose the appropriate cadence on how often to send your campaign.

# Define a Custom Callback

Using the following custom callback functions, you can control the look, feel, and location of your web popup.

You need to explicitly call `clevertap.raiseNotificationViewed();` and `clevertap.raiseNotificationClicked();` to ensure that notification views and clicks are tracked on CleverTap.

To define the callback and raise the clicked and viewed events, you need to add the following snippet to the JavaScript embed code comprising your CleverTap web integration:

```javascript
clevertap.notificationCallback = function(msg){
      // Raise the notification viewed and clicked events in the callback
      clevertap.raiseNotificationViewed();
      console.log(JSON.stringify(msg));// Your custom rendering implementation here
      var $button = jQuery("<button></button>");// Element on whose click you want to raise the notification clicked event
      $button.click(function(){
         clevertap.raiseNotificationClicked();
      });
};
```

The message will be in the following format:

```json
{
    "msgContent": {
        "title": "hello title!",
        "description": “hello message!"
    },
    "msgId": "1439796272_20160219",
    "kv": {
        "key1":"value1",
        "key2":"value2"
    }
}
```

*msgId* contains the campaign ID and the date-stamp so that you can programmatically decide whether to display the notification. **kv** contains the custom key-value pairs.

# Viewing Web Popup Campaign Stats

Once the campaign has been sent, you can view its statistics from the dashboard by clicking on **Campaigns**, then selecting the desired campaign to view its total impressions, clicks, conversions, and revenue from conversions (if applicable).
