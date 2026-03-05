---
title: 'Funnels vs. Flows: Finding the Best Fit'
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

Funnels are actionable since you can create campaigns or journeys for drop-off users from funnels. On the other hand, flows is a sunburst chart that represents successive steps in a user’s journey.

# When to Select Funnels or Flows

Flows are used when you can take multiple parallel paths before a defined goal and funnels when the path is defined.

Funnels are useful to check the number of users that are progressing towards the set goal and also retain the users dropping off in this process. You can create campaigns and journeys for all the users and the users who dropped off.  

# Event in Funnels or Flows

Flows can have repeated steps because it provides the order of events performed by the user. For example, a user performed *App Launched* event three times in quick succession and the *Product Viewed* event two times, then the Flows are displayed as:

*App Launched > App Launched > App Launched > Product Viewed > Product Viewed*

<Image title="View Events in Funnels or Flows" alt={896} align="center" border={true} src="https://files.readme.io/b49f3c9-Flows_events.png">
  View Events in Funnels or Flows
</Image>

Funnels display the movement of users. Therefore, a user event is counted only once even if it is repeated. For example, *App Launched* and *Product Viewed* will be two steps even if the user repeats one or both events.

<Image title="Select Percentage or Count to View Events" alt={1168} align="center" border={true} src="https://files.readme.io/1f24c87-Funnel_Dropoff.png">
  View Percentage or Count of Events
</Image>
