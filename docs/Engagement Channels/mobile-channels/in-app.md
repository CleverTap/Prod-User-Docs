---
title: Legacy In-Apps
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
In-app notifications are popup messages that display to the user while they are within your app. While push notifications are viewed by the user outside the app, in-app notifications are viewed strictly inside the app. 

In-app notifications are great to show contextual messages such as discount offers while the user is within the app, or to communicate with users who have turned off push notifications.

<Image title="image11.png" alt={145} className="border" border={true} src="https://files.readme.io/f1fda84-image11.png" />

# In-App Notification Campaign Creation

## Step 1: Create a New Campaign

To start creating a in-app campaign, first go into “Push” under “Campaigns” on the CleverTap dashboard, then click on “Create New +” on the top-right.

<Image title="image3.png" alt={1280} className="border" border={true} src="https://files.readme.io/2b0f7d6-image3.png" />

## Step 2: Define the Who

The next step would be to indicate the target audience for your in-app campaign. You can target your in-app campaign to a user segment you create on the fly (by clicking on “Create ad-hoc segment”) or use a previously saved user segment (from the list of pre-saved segments shown in the table), as shown below. 

Note that since in-app campaigns are triggered upon live actions within the app, only your live segments will be applicable and thus displayed here.

<Image title="image2.png" alt={1278} className="border" border={true} src="https://files.readme.io/af44325-image2.png" />

If you choose to create an ad-hoc segment, you can now create a live user segment on which to trigger your in-app campaign.

<Image title="image6.png" alt={420} className="border" border={true} src="https://files.readme.io/a2ac529-image6.png" />

On this basis, in the next step, here is how we would set up the “WHO”. For instance, below, we are opting to send this campaign to all users who “Added to Cart”, perhaps as a way to provide them an incentive to transact sooner. You can filter this event by its event properties to segment even more finely to target users who, say, “Added to Cart” where its “Category” = “Books”. 

If needed, you can check the “Limit to users who do this event for the First Time”. This is so that users don’t repeatedly get this incentive every subsequent time they fit the campaign criteria, and in this case, add a book to their cart. 

Finally, you can check the “Filter this stream based on these users’ past behavior/user properties” checkbox to filter this live action-triggered campaign by any past user behavior or user properties.

<Image title="image9.png" alt={394} className="border" border={true} src="https://files.readme.io/057420b-image9.png" />

### Filter by User Properties

Let's say you want to send an in-app notification to people who live in the United States, whose preferred language is English, and who are using version 2 of your app, you can segment your campaign to only reach users who meet this criteria. 

<Image title="screen2.png" alt={1096} className="border" border={true} src="https://files.readme.io/56858b9-screen2.png" />

The table below lists all the different ways you can segment your audience for an in-app notification campaign based on their user profile properties.

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
        Geography
      </td>

      <td>
        User's coarse location. Filters include Country, Region, and City. CleverTap's SDK can automatically detect this from the user's IP address.
      </td>

      <td>
        Country = United States\
        State = California\
        City = San Francisco
      </td>
    </tr>

    <tr>
      <td>
        Geography Radius
      </td>

      <td>
        User's exact location. You can select a city, and then define the target radius. You can also select multiple cities. You can send this information using CleverTap's SDK. Please see the [iOS](https://developer.clevertap.com/docs/ios#section-send-location-information-to-clevertap) and [Android](https://developer.clevertap.com/docs/android#section-manually-updating-user-location) developer guides for more information.
      </td>

      <td>
        Locations = San Francisco, USA; Paris, France
      </td>
    </tr>

    <tr>
      <td>
        App Fields
      </td>

      <td>
        App Fields filters include App Version, Device Make, Device Model, OS Version, and CleverTap SDK Version. This information is sent by CleverTap's SDK for each device that has your app. This means a single user can have multiple devices associated with their user profile.
      </td>

      <td>
        App Version = 2
      </td>
    </tr>
  </tbody>
</Table>

## Step 3: Define the When

In the next step, the “WHEN”, you can set the campaign up to start immediately, or at a later time. If it is a limited-time incentive, you might want to end the in-app popup at a particular end date and time. If always relevant, you can specify that the campaign should never end. 

However, if you change your mind later, you can always stop the campaign by clicking on the red “stop” icon next to the campaign in the main in-app campaigns page. You can set campaign frequency here, as well, by specifying any specific days of the week and times of the day you would like for it to display. 

Finally, you can specify how often users receive the campaign: Bypass global campaign limits by checking the ‘Exclude from campaign limits’ radio button, or send once per session, once per day, or just once per user for the entire duration of the campaign.

<Image title="image14.png" alt={736} className="border" border={true} src="https://files.readme.io/a45a571-image14.png" />

## Step 4: Define the What

In the next step, you can build out the look of your in-app campaign. You must specify which mobile OSes the in-app campaign displays on: Android, iOS, and/or Windows. 

You must also specify in-app campaign layout by choosing any of the options shown at the very top: Interstitial, Cover, Half-Interstitial, Sticky Header, or Sticky Footer. With our built-in in-app campaign builder, you can drag and drop text and button elements, specify background colors and overlay, or even “Reset” if you would like to start over. The background may also be a custom, publicly-hosted image URL of yours. 

You also have the option to use your own custom HTML by clicking on the ‘Custom’ option below. You can include a close button for your in-app campaign by checking the corresponding checkbox. 

<Image title="image4.png" alt={1280} className="border" border={true} src="https://files.readme.io/fb5f2c7-image4.png" />

In-app campaigns support all screen sizes and orientations. Images are scaled or skewed and aligned to the best size and orientation at the time of delivery. 

> 📘 Recommendations
>
> 1. Use images with aspect ratio 2:1, smaller than 150KB in size and in .jpg or .png formats.
> 2. Provide sizes in % as opposed to pixels as the same image gets rendered across different screen sizes
> 3. Test the image rendering on multiple device sizes to ensure highest quality of InApp campaign delivery

The table below lists the optimal image sizes for various mobile in-app popup layouts.

<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th>
        Type
      </th>

      <th>
        Aspect Ratio
      </th>

      <th>
        Sample Image Sizes
      </th>

      <th>
        Image Size Relative to Screen Size
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Interstitial
      </td>

      <td>
        1:1.8
      </td>

      <td>
        **4x: 1040 x 1840 (optimal)**




        2x: 520 x 920




        1x: 260 x 460
      </td>

      <td>
        85% of the viewport height




        and 90% of the viewport width.
      </td>
    </tr>

    <tr>
      <td>
        Cover
      </td>

      <td>
        1:2
      </td>

      <td>
        **4x: 1280 x 2560 (optimal)**




        2x: 640 x 1280




        1x: 320 x 640
      </td>

      <td>
        100% of viewport height and 100% of viewport width.
      </td>
    </tr>

    <tr>
      <td>
        Half-Interstitial
      </td>

      <td>
        1:1
      </td>

      <td>
        **4x: 1040 x 1040 (optimal)**




        2x: 520 x 520




        1x: 260 x 260
      </td>

      <td>
        50% of the viewport height




        and 90% of the viewport width.
      </td>
    </tr>

    <tr>
      <td>
        Sticky Header
      </td>

      <td>
        2.1:1
      </td>

      <td>
        **4x:1280 x 600 (optimal)**




        2x: 640 x 300




        1x: 320 x 150
      </td>

      <td>
        30% of the device height and 100% of the device width.
      </td>
    </tr>

    <tr>
      <td>
        Sticky Footer
      </td>

      <td>
        2.1:1
      </td>

      <td>
        **4x:1280 x 600 (optimal)**




        2x: 640 x 300




        1x: 320 x 150
      </td>

      <td>
        30% of the device height and 100% of the device width.
      </td>
    </tr>
  </tbody>
</Table>

You can edit the text and look of the text within your campaign. Text content can be personalized for every user based on specific user property or event property values (dynamic replacements). See User Profiles to learn more about user profile properties and events. To invoke the personalization menu, type @ in the title or the text fields while typing out the content:

<Image title="image8.png" alt={1272} className="border" border={true} src="https://files.readme.io/88ca421-image8.png" />

You can edit the button text and click action (upon click, either close the in-app popup, or open a specified call-to-action link) as shown below.

<Image title="image13.png" alt={1287} className="border" border={true} src="https://files.readme.io/0eb9945-image13.png" />

## Step 5: Test & Schedule Campaign

Then, you can “Preview on phone” to see what the in-app popup will look like on your mobile device. For this, you will receive a push notification that directs you to open your app and preview the in-app popup, since the popup can only be previewed within your app.

Finally, once you’re satisfied with the look of your in-app campaign, you can “Continue to Overview” to view a summary of your in-app campaign, and then “Schedule notification” once you’re all set.

<Image title="image12.png" alt={1298} className="border" border={true} src="https://files.readme.io/d87d07f-image12.png" />

# Viewing In-App Campaign Stats

Once the campaign has gone out, you can view its stats by going into “In-app” under “Campaigns” on the CleverTap dashboard and clicking on the campaign of interest to see its impressions (views), clicks, conversions, and revenue from conversions (if applicable).

<Image title="image7.png" alt={1296} className="border" border={true} src="https://files.readme.io/6bfc088-image7.png" />
