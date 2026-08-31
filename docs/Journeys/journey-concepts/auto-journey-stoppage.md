---
title: Journey States
excerpt: >-
  Learn about different Journey States in CleverTap, which provide insights into
  user engagement and behavior throughout their interaction with your
  application.
deprecated: true
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Overview

Journey States in CleverTap refer to the distinct phases a user experiences within an automated Journey. Each state is defined by unique characteristics determining how and when users enter, progress through, or exit the Journey. These states offer valuable insights into user behavior, enabling marketers to monitor engagement and optimize workflow efficiency.

The following table gives a quick overview of key aspects for each journey state:

- User Entry
- User Movement
- Possible Next Actions
- Possible Next States
- Editing Permissions

| State Name     | User Entry                                        | User Movement                                            | Possible Next Actions      | Possible Next States                    | Editing Options                                                                |
| :------------- | :------------------------------------------------ | :------------------------------------------------------- | :------------------------- | :-------------------------------------- | :----------------------------------------------------------------------------- |
| **Draft**      | Not Applicable                                    | Not Applicable                                           | Edit, Save, Publish, Clone | Scheduled, Running                      | Full editing allowed                                                           |
| **Scheduled**  | Not Applicable                                    | Not Applicable                                           | Edit, Clone, Pause, Stop   | Running, Paused, Stopped                | Partial edit (What section).                                                   |
| **Running**    | Users enter the journey as per the entry criteria | Users progress as per the defined flow                   | Edit, Clone, Pause, Stop   | Paused, Stopped, Restricted, Completed  | <li>Partial edit (What section).</li><li>Full edit creates a new version.</li> |
| **Paused**     | No new user entry                                 | Existing users continue to move through the flow         | Edit, Clone, Resume, Stop  | Running, Stopped, Restricted, Completed | <li>Partial edit (What section).</li><li>Full edit creates a new version.</li> |
| **Completed**  | No new user entry                                 | Existing users progress until they exit                  | Edit, Clone, Stop          | Stopped                                 | Full edit creates a new version.                                               |
| **Stopped**    | No new user entry                                 | No further progression; users are exited over 30–60 days | Edit, Clone                | None                                    | Full edit creates a new version.                                               |
| **Restricted** | No new entry                                      | Existing users continue the movement                     | Edit, Stop                 | Stopped                                 | <li>Partial edit (What section).</li><li>Full edit creates a new version.</li> |

# Draft

The Draft State in CleverTap refers to a Journey created but not published. Any unsaved changes in this state may be lost unless explicitly saved. If you have an existing unsaved Journey in the cache and choose to create a new Journey, CleverTap provides the option to either start a fresh Journey or restore the cached Journey for further editing.

If you restore the cached Journey, the most recent version saved in your browser cache loads, enabling you to continue editing from where you stopped. The cache is specific to each user and depends on the web browser, ensuring that only the user who created the Journey can access it while preventing accidental data loss.

The _Created By_ and _Published By_ columns on the Journeys List page identify the users responsible for creating and publishing a journey or its versions. The _Created By_ column shows the user who initially created the journey or its latest draft version, while the _Published By_ column indicates the user who published that specific version. When a draft is published, the journey transitions to the Scheduled or Running state based on its setup. Each version maintains its own creation and publishing metadata to enable accurate version tracking.

<Callout icon="📘" theme="info">
  ### Draft Management

  Only one draft is allowed per Journey entity at any time. Creating a new draft version replaces the existing one.
</Callout>

# Scheduled

The Scheduled state indicates that the journey is set to go live at a later time. In this state, users do not yet qualify for the journey, which becomes active when the scheduled time arrives.

The following table describes the key difference between the Past Behavior and Live Behavior Journeys in the Scheduled state:

| **Feature**                | **Past Behavior Setup**                                                                                         | **Live Behavior Setup**                                                                                   |
| -------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Qualification Criteria** | Based on **past actions** or **custom lists**.                                                                  | Based on **real-time user actions** or **inactivity**.                                                    |
| **Entry Timing**           | **At a fixed time**.                                                                                            | **At a fixed time**.                                                                                      |
| **Trigger Type**           | Static triggers based on predefined events.                                                                     | Dynamic triggers that act as soon as the criteria are met.                                                |
| **Use Case Focus**         | Re-engagement or follow-ups based on past activities (for example, targeting users who checked out last month). | Real-time engagement or retention campaigns (for example, sending a real-time cart abandonment reminder). |

If the journey is stopped while in the Scheduled state, it will not go live, and no users will qualify for the journey.

## Editing Journey in Scheduled State

To edit a scheduled journey, click the ![](https://files.readme.io/8f45b08c7f55c17da382ee310aa5def046dab2b3d740a837ce8e39e61ea57240-Edit_icon.png) icon. In this state, you can only do limited edits to the _What_ section of engagement nodes, such as message content, providers, and manual distribution percentages.

# Running

The Running state indicates that the journey is active, and the users execute actions as defined. In this state, users enter the Journey as they qualify and progress through it according to the flow after qualifying (refer to the following GIF).


<Image src="https://files.readme.io/5aa5ea778cb2e4c2a73b283535a56b64413f776a1ca3379792ba2b4766364f3b-Running.gif" alt="User Entry and Movement in Running State" align="center" caption="User Entry and Movement in Running State" border={true} />


As users move through the Journey nodes (for example, receiving a message, meeting a condition, or dropping off), the stats are updated immediately in the dashboard. The date range selection in the calendar widget directly influences the Node stats. Consider an example where the Journey running from January 1 to January 10 sends push notifications to users. On January 5, you use the calendar widget to filter data for January 1–January 4. The Node stats update to reflect only the number of users who entered, dropped off, or converted during that time frame. Always ensure you are analyzing the correct time frame. For nodes with scheduled actions (for example, if a campaign is scheduled to run after two days), stats are updated only when those actions are triggered.

## Editing Journey in Running State

You can edit the _What_ section of engagement nodes, such as message content, provider configuration, or manual distribution settings, without creating a new version. You must create a new version to modify other journey aspects (for example, entry criteria, goal logic, and journey structure).

Once you publish a new version, you can:

- **Stop the older version**, if you want all users to move to the new version immediately
- **Mark the old version Restricted** if you want to allow existing users to continue moving through it. The new users who meet the updated entry criteria are routed into the new version of the journey.

# Paused

The Paused state indicates that already qualified users or users who have entered the journey continue to advance through the journey. However, no new users qualify for the journey until it resumes (refer to the following GIF). For example, consider a Journey targeting users who abandon their cart without completing a purchase within 30 minutes. If you pause the Journey, users who are already qualified continue to progress and receive notifications as per the Journey setup, such as receiving a discount after 24 hours. However, new users who meet the criteria during the pause do not enter. Once the Journey resumes, new users qualify again based on the cart abandonment trigger. Existing user progress remains unaffected by the paused period.


<Image src="https://files.readme.io/8f53f43f6d2bf593957d3fd51ab66753c3d0a36009497ab9f6a31af58422c7c9-Paused.gif" alt="User Entry and Movement in Paused State" align="center" caption="User Entry and Movement in Paused State" border={true} />


## Editing Journey in Paused State

While updates to the What section, such as message content or provider settings, are still allowed without versioning, any structural changes require you to create a new draft version. This includes edits to nodes, paths, goals, and qualification logic.

When you publish the new version, CleverTap prompts you to choose how to handle the paused version:

- **Stop the older version**, if you want all users to move to the new version immediately
- **Mark the old version Restricted** if you want to allow existing users to continue moving through it. The new users who meet the updated entry criteria are routed into the new version of the journey. Once you move the older journey to Restricted, it cannot be resumed.

<Callout icon="📘" theme="info">
  ### Note

  Only one version of a journey can be in the Paused/Running state at a time.
</Callout>

# Stopped

The Stopped state indicates that the journey has been permanently deactivated. Users currently in the journey do not progress further, and actions are halted.


<Image src="https://files.readme.io/d37e56e4b883fcc1cbf6eaf85b1ba34bb3f4c462b274b7f6528058564920684b-Stopped.gif" alt="User Entry and Movement in Stopped State" align="center" caption="User Entry and Movement in Stopped State" border={true} />


## Automatic Journey Stoppage

CleverTap can automatically identify and stop journeys that are in the Completed State, that is, when no new users can enter, and all existing users have exited. This helps maintain performance and optimize system resources.

**Journey moves to a Completed State when the user entry for the journey finishes**, based on its configuration. This can happen in the following scenarios:

- The journey is configured as a One-Time Entry journey.
- The journey is a recurring PBS journey with a defined entry end date.
- The journey is a Live journey with a defined end date.

In all these cases, once the entry closes, no new users can qualify for the journey.

### Criteria for Automatic Journey Stoppage

A journey in the Completed state becomes eligible for automatic stoppage when all users who entered the journey have fully exited it. This means:

- All users have exited the journey:
  - Either they met the goal
  - They timeout of the journey
  - They exited the journey via Force exit
  - No new users are entering the journey
- There are no users currently active in any journey node.
- No pending scheduled actions remain for any user.

Once these conditions are met, CleverTap automatically transitions the journey from **Completed** to **Stopped**, ensuring completed journeys no longer occupy active processing slots.

Journeys that stop automatically behave the same as those that are stopped manually; no new users can enter, and existing users exit over time.

## Editing Journey in Stopped State

You can make changes to a stopped journey by creating a new draft version. This allows you to modify all aspects of the journey, including nodes, paths, goals, and qualification criteria.

Once the new version is published, it becomes the active version of the journey. The stopped version remains inactive; users do not progress, and no new users qualify for it. Any users still present in the journey are exited automatically within 30 to 60 days.

# Completed

The Completed state signifies that the user entry is marked complete. The already qualified users continue to progress and exit the journey once they have timed out (refer to the following GIF).


<Image src="https://files.readme.io/854ba478e8cd88e48cda04e1e449cbf26cf26ebb353e680b83dbebbf24a8125e-Completed.gif" alt="User Entry and Movement in Completed State" align="center" caption="User Entry and Movement in Completed State" border={true} />


## Editing Journey in Completed State

You can make changes to a Journey in the Completed State by creating a new draft version. This includes updates to nodes, paths, goals, and entry criteria. When you publish the new version, you will be prompted to choose how the completed version should be handled:

Once you publish a new version, you can:

- **Force exit from version**, if you want all users to move to the new version immediately
- **Keep moving in version** if you want to allow existing users to continue moving through it. The new users who meet the updated entry criteria are routed into the new version of the journey.


<Image src="https://files.readme.io/b18a8d5c4aea555b1672fe3ac6404078cb7e21f819b8cd894e9dece8b2b35cf2-Edit_a_Journey_in_Completed_State.png" alt="Edit a Journey in Completed State" align="center" caption="Edit a Journey in Completed State" border={true} />


# Restricted

The Restricted state indicates that the journey version is no longer accepting new users, but users who have already qualified will continue to progress through the journey. This is a system-driven state that is applied when a new version of the journey is published and the previous version is not stopped, but retained to support in-progress users.

For example, consider a running journey that you edit and publish as a new version. If you choose not to stop the previous version, it enters the Restricted state. In this state, the journey flow remains active only for users already inside the journey; no new users will be able to enter.


<Image src="https://files.readme.io/6ed85c1e970478e35469e9dd240d3f26c4babbd9935d531e4d75b55f112f338c-Restricted_state_-_Static_New_Journey.png" alt="User Entry and Movement in Restricted State " align="center" width="90% " caption="User Entry and Movement in Restricted State" border={true} />


A version in the Restricted state cannot be made active again. This state exists solely to ensure continuity for users already in the journey, while new users are directed to the latest active version.

## Editing Journey in Restricted State

Journey in the Restricted state supports limited edits to the _What_ section. To edit the journey beyond the What section, select _Full editing_ to create a new version. This initiates a new draft version. Once published, the older version remains restricted, and only the new version will remain active.
