---
title: Remote Config
excerpt: >-
  Learn how you can remotely customize your app experience for segments of your
  user base using variables.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Introduction

CleverTap's Remote Config feature enables you to modify your application's functionality and appearance without mandating users to download an updated version of your application using variables.

Variables are the building blocks of the Remote Config feature. Any element or functionality within your app (such as a CTA text, a new welcome page layout, game difficulty level, and so on) can be defined as a variable that can be controlled remotely via the CleverTap dashboard.

# Key Capabilities of Remote Config

Remote Config allows you to:

- **Deliver customized in-app experiences** for specific segments of your user base. For example, highlight the registration section on your application's home screen for new users.
- **Change elements of your app in real-time** without requiring an update to be pushed to the app stores. For example, switch on a special discount offer and specify the discount percentage for non-paying users (users who have not yet converted).
- **Streamline your messaging campaigns with the in-app user experience** for maximum engagement. For example, switch on a special event in your game via Remote Config for a selected segment and notify the segment about the event via a push and an in-app campaign.
- **Test & release new features securely** with the option to revert back in case of any issues.

# Create Remote Config Variables

**CleverTap Remote Config** offers two ways to set up your variables:

- Create them manually from the Dashboard
- Define them in the code and sync them to the Dashboard

## Create Variables from the Dashboard

Variables can be created from the **Add button** in the Remote Config page.

Each variable requires the following information:

- Name (required)
- Description (optional)
- Value (required)

The variable name is fixed once the variable is created, but you can update the description at any time. For more information, see [Edit a Variable Description.](<doc: remote-config#edit-a-variable-description>) (@murtaza please check)

Variables created through the interface do not have a _default value,_ as do variables synced from code. This means that the value you set in the Dashboard is applied to all users immediately.

To create a Remote Config Variable, go to _Product Experiences > Remote Config_. Click **Add** to add a variable.


<Image src="https://files.readme.io/4961653705d0f4bfcfb71a83afe577cfd204303492bc8412be4ccc728db2cc3b-Screenshot_2025-01-08_at_15.02.22.png" alt="Add Remote Config Variable" align="center" border={true} />


<br />


<Image src="https://files.readme.io/3f5fcfbacffe8059d79809bf2dded48468a810579d8f9abb0113caaaaf553faa-Screenshot_2025-01-08_at_15.03.09.png" alt="Create Remote Config Variable" align="center" border={true} />


> 📘 Creating File Type Variables.
>
> Creating File type Variables are currently not supported to be created from the Dashboard. They must be  synced from the code.

## Define and Sync Variables from Code

To define which elements of your app you want to control, you need to integrate CleverTap SDK and follow the respective developer guide for [Android](https://developer.clevertap.com/docs/android-remote-config)  and [iOS](https://developer.clevertap.com/docs/ios-remote-config) to sync your variables to the dashboard. After doing so, you can start adding override values for your variables from the CleverTap dashboard for all app users or specific segments of your user base.

CleverTap supports creating the following variable data types:

- Number
- String
- Boolean
- File type

> 📘 Prerequisite
>
> To get a complete view of your application’s variables, you must integrate the required CleverTap’s SDK and sync your defined variables with the CleverTap dashboard. After the sync, you must publish the newly-created variables from the _Remote Config page_ of the CleverTap dashboard.

In your app's code, any functionality defined as a variable has a default value or state. For instance, every time you add a new feature, it is initially always hidden with a visibility value of `false`. After syncing the variables to CleverTap, you can view these default values on the _Remote Config_ page. After the initial publish, you can decide whether to override the default values for an existing one or create a new segment and define a new variable value.

The following sections provide information about defining and updating a variable value for a particular segment.

# Manage Remote Config Variables

(Review this entire section @murtaza)

After a variable is created, you can update its description or remove it from the dashboard when it is no longer in use.

## Edit a Variable Description

You can update a variable's description at any time. This is useful when the purpose of a variable changes over time, or when the original description needs more clarity for teammates who join later.

To edit a variable description:

1. Select the required variable from the variable list on the _Remote Config_ page.
2. Open the variable's edit option and update the text in the **Description** field.


<Image src="https://files.readme.io/1306db048642c8ecb4d9c7b2226a59c50eaa264b48894cd74ac2ce75f4d6567e-image.png" alt="Edit a variable description" align="center" caption="Edit Variable Description" border={true} />


3. Save your changes.

> 📘 Note
>
> Only the description can be edited. The variable name (key) remains fixed, because changing the key would affect your App integration with CleverTap.

## Delete a Variable

You can delete variables that are no longer needed directly from the dashboard. Removing unused variables keeps your Remote Config workspace organized and prevents deprecated variables from being selected by mistake when you set up new experiments.

To delete a variable:

1. Go to _Product Experiences_> _Remote Config_.&#x20;
2. Select the required variable from the variable list on the _Remote Config_ page.
3. Open the variable's options and click **Delete**.


<Image src="https://files.readme.io/3b291116649bafb8cea24fcb39436e1cd8de8716adccabe40dd4b4ee1f56dc0f-image.png" alt="Delete a variable" align="center" caption="Delete a variable" border={true} />




> 🚧 Variables in Use Cannot Be Deleted
>
> A variable that is referenced by a live or draft experience cannot be deleted. The system blocks the deletion and indicates where the variable is currently used.&#x20;

## Clone a Variable

Cloning creates a copy of an existing variable under a new name within the same project. This is useful when you want to set up a new experiment that reuses the configuration of an existing variable as a starting point, instead of building it from scratch.

When you clone a variable, the following details are copied:

- Variable type
- Variable values, including the default value and any segment-level values
- Variable description

The approval status, reviewer feedback, and approval history are not copied. The cloned variable starts fresh with no approval history.

To clone a variable:

1. Go to _Product Experiences_> _Remote Config_.&#x20;
2. Select the required variable from the variable list on the _Remote Config_ page.
3. Open the variable's options and click **Clone**.


<Image src="https://files.readme.io/4094f7cb4c16e78c2fee471313cd7bb747ecb5191a4f24f240613ca3fec8a4e2-image.png" alt="Clone a Variable" align="center" caption="Clone a Variable" border={true} />


4. Enter a unique name for the cloned variable and confirm.

> 📘 Note
>
> The cloned variable is always created as a draft and does not go live automatically. You need to publish it from the _Remote Config_ page for the changes to take effect. The name of the clone must be unique within the project. If a variable with that name already exists, the clone is not created.
>
>

# Override Variable Value for New Segment

To override a variable value for a new segment:

1. Search for the required variable from the search bar or select the required variable from the variable list displayed under the Remote Config page.
2. Click **Override** dropdown and scroll down to the end of the list.


<Image src="https://files.readme.io/b46483b-small-New_segment_in_Remote_Config.png" align="center" border={true} />


3. Select _New Segment_ from the dropdown. The _Create New Segment_ popup opens.


<Image src="https://files.readme.io/484e98b-small-Create_new_segment.png" alt="Segment Builder" align="center" border={true} />


4. Enter the criteria for your target audience. Consider the example where your target audience would be users who reside in India and have performed the _Added to cart_ event but did not charge (see figure below).


<Image src="https://files.readme.io/af45e0a-small-Segment_with_Rules.png" alt="Enter Segment Criteria" align="center" border={true} />


5. Toggle ON _Save As_ if you want to save the segment for future use. Keeping the toggle off does not save the segment.
6. Click **Apply** to save the segment. The newly-created segment is now visible under the list of segments on the right side of the screen.

   > 🚧 Remote Config Segments
   >
   > The segments that are created and saved on the Remote Config page can only be seen and reused within that particular page. These segments will not be visible in other areas of the dashboard such as _Segments_ or _Campaigns_. Similarly, any user segments created in the _Segments_ section will not be visible in Remote Config. However, this is only a temporary limitation that will be removed in the future
7. Edit the variable value for the selected segment in the right-side panel and click **Publish**. After you click **Publish**, the variable update is displayed under the _Live_ tab, as shown in the following image:


<Image src="https://files.readme.io/5f9a7a1-small-Published.png" alt="Variables in Published State" align="center" caption="Variables in Published State" border={true} />


(@murtaza please check)

> 📘 Publishing a Single Variable
>
> Publishing applies only to the variable you are working on. When you click **Publish**, only that variable's experience goes live. Any other variables that are still in draft state remain untouched and are not deployed. This allows multiple teams to work on different Remote Config experiences at the same time, and lets you release a finished variable without pushing another team's unfinished configuration.

All the changes you make to the _Remote Config page_ are, by default, saved as a draft and are highlighted in light yellow color in the table, as shown in the following image.  If you want to discard the current draft, click the **Discard** button.


<Image src="https://files.readme.io/eea0fc0-small-Draft_mode_in_remte_config.png" alt="Draft Mode in Remote Config." align="center" caption="Draft Mode in Remote Config" border={true} />


> 📘 Note
>
> The draft in the Remote Config page is shared with all the dashboard users within your app account for everyone to contribute. The changes you make are visible to the rest of the dashboard users.
>
> To avoid overriding or discarding someone else’s changes, verify who made the latest changes to an existing draft from the top right corner of the _Remote Config_ page.

# Override Variable Value for an Existing Segment

To define the variable behavior for an existing segment:

1. Search for the required variable from the search bar or select the required variable from the variable list displayed under the _Remote Config_ page.
2. Select an existing segment from the Override dropdown (for example, a segment of German users) and update the variable value to modify the behavior as required.


<Image src="https://files.readme.io/a6dd6a3-small-Users_in_Germany.png" align="center" border={true} />


3. Click **Publish** to make these changes live on your application.

You can also test your application's variable behavior in the draft version using the _Preview & Test_ feature. For more information, refer to [Preview and Test Remote Config](https://docs.clevertap.com/docs/remote-config#preview-and-test-variables).

> 📘 Key Points to Remember
>
> - The change in variable behavior reflects in the live application only after the draft is published.
>
> {/* CHANGE 4 — added bullet reinforcing single-variable publish in the existing-segment flow, so the behavior is also visible to readers who land here directly. */}
>
> > - Publishing affects only the variable you are editing. Other variables that remain in draft are not deployed.
>
> {/* END CHANGE 4 */}
>
> > - During application startup, CleverTap verifies the user's eligibility for different segments and retrieve the corresponding variables. Later on during the session, it may be necessary to retrieve values if there are any signification milestones in the application where users are expected to transition between segments. For example, if there is a value override for certain variables for the _Paying users_ segment, it would be good to fetch them again at the time of purchase within the app.

# User Profile Personalization

User Profile Personalization is available only for variables of type **String**.

Value personalization is based on **User Properties** and is supported for **String** Variables. This allows you to personalize the Variable Value that will be returned and used by your application based on your users' unique properties.


<Image src="https://files.readme.io/a73244ac51a0d5dd34beb666d4c790f740326da085d6f9e178a83c0b4d6cefa9-Screenshot_2025-01-08_at_14.27.02.png" alt="Step 1" align="center" width="400px" border={true} />


<br />


<Image src="https://files.readme.io/9c065baa43b5df8bc8e56cdd7bcb1c72a37b580cc72f7d6f38c73d067c14af73-Screenshot_2025-01-08_at_14.27.52.png" alt="Step 2" align="center" border={true} />


# Segment Prioritization

When there are multiple segments, and a user meets the criteria for more than one segment, the default segment (All users) is assigned the lowest priority, and the segment that appears at the top of the list is given the highest priority.

Let us consider an example. If a user qualifies for two segments - _Paying Users_ and _All Users_, in this case, the user sees the variable value defined for the _New Users_ segment as shown below.


<Image src="https://files.readme.io/43fb92befa991813c02c9ca366c43496ef5f3dea7cf37b8fb7743be881e466b3-image.png" alt="Multiple Segments" align="center" width="60% " border={true} />


To change the priority, click **Prioritize** and drag and drop the segment to change the priority.


<Image src="https://files.readme.io/51068366f3db442bc351b5a4c63968569727cb346535272d6668724e0ac9f363-image.png" alt="Change Segment Prioritization" align="center" width="60% " border={true} />


# Remote Config Version History

After a Remote Config draft version is published, all the previous live versions are stored along with the following corresponding metadata: created by and the timestamp when the version was published. Each version can be restored when needed. To view the version history and restore a specific version:

1. Navigate to _Published versions_.
2. From the Published version history, select the version of your choice.
3. Click **RESTORE** (see figure below).


<Image src="https://files.readme.io/976c144-Version_history_in_remote_config.gif" align="center" border={true} />


# Preview and Test Variables

For all the variable updates made in the draft mode, you can test their behavior on a device using the _Preview & Test_ feature. By clicking _Preview & Test_, you enable the variable values from your unpublished draft for all profiles marked as test profiles for your app and the associated devices.

> 🚧 Mark Test Profiles
>
> For testing the behavior of variables in draft mode, it is a prerequisite to [mark certain profiles as Test profile](doc:concepts-user-profiles#mark-a-user-profile-as-a-test-profile). It is also imperative for the test profiles to qualify for the specific segment to be able to view the variable changes.
>
> Let us consider the following example to understand this better:
>
> If you make changes to a variable value for a segment of Indian users and want to preview them on your test device, you need to log in to your app on your device with an Indian user profile that is marked as a test profile to qualify for the segment and view the specific changes. Logging in as a user in the US, for instance, will not allow you to see the changes you made.

<br />
