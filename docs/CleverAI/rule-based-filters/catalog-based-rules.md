---
title: Catalog-Based Rules
excerpt: >-
  Learn how to create recommendation rules using product catalog attributes and
  conditions.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

A catalog-based rule defines which items from a catalog are eligible for personalization. By applying conditions to catalog attributes such as brand, category, price, or language, a catalog-based rule narrows the pool of items the personalization engine considers. These rules operate solely on item data; they do not factor in user behavior.

Catalog-based rules can be applied to recommendation and catalog send personalization, either to include only matching items or to exclude them from the eligible pool.

# How Catalog-Based Rules Work

Catalog-based rules run before items are retrieved from the catalog. They act as a filter, establishing the eligible item pool that the downstream recommendation engine or catalog send process works with.

When a rule is applied, the personalization engine only fetches or considers items that satisfy the rule's conditions. Items that do not match are never retrieved, regardless of how they would otherwise rank.

## Include vs. Exclude

A catalog-based rule can be applied in one of two modes:

- **Include**: Only items that match the defined conditions enter the eligible pool. Items that do not match are excluded before any personalization logic runs.
- **Exclude**: Items that match the defined conditions are removed from the eligible pool before personalization logic runs. All other items remain eligible.

For example, a catalog rule with the condition `Articles EQ ["Politics"]`:

- **Applied as include**: Recommendation engine only fetches and returns Political articles.
- **Applied as exclude**: Recommendation engine never fetches or returns Political articles, regardless of how those items would otherwise rank.

<Callout icon="📘" theme="info">
  #### Include vs. Exclude at a Glance

  The following table summarizes how each rule type affects the eligible item pool:

  |                | Include                                           | Exclude                                                                |
  | -------------- | ------------------------------------------------- | ---------------------------------------------------------------------- |
  | Catalog Send   | Only matching items are sent                      | Matching items are removed before sending                              |
  | Recommendation | Only matching items enter the recommendation pool | Matching items are dropped before the recommendation engine ranks them |
</Callout>

# Use Cases

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Industry
      </th>

      <th>
        Filter to Recommend Only
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ECommerce
      </td>

      <td>
        - Products from a specific brand (for example, Nike)
        - Items in a specific category (for example, Shoes)
        - Products within a price range
        - Premium or luxury items
        - In-stock or discounted items
        - Items from brands the user has previously purchased
      </td>
    </tr>

    <tr>
      <td>
        Streaming / OTT
      </td>

      <td>
        - Content in a specific language (for example, Hindi)
        - Titles in a specific genre (for example, Drama)
        - Recently released or trending shows
        - Content rated suitable for children
        - Content available in the user's subscription tier
      </td>
    </tr>

    <tr>
      <td>
        Travel
      </td>

      <td>
        - Direct flights
        - Hotels rated 4 stars or above
        - Properties within a specific price range per night
        - Vacation packages that include flights
        - Experiences available in a specific destination
      </td>
    </tr>

    <tr>
      <td>
        Food Delivery
      </td>

      <td>
        - Restaurants that are currently open
        - Dishes tagged as vegetarian or vegan
        - Items within a specific delivery time threshold
        - Restaurants above a minimum rating
        - Items within a price range
      </td>
    </tr>

    <tr>
      <td>
        Gaming
      </td>

      <td>
        - Items available in the in-game store for the user's platform
        - Bundles within a specific coin or gem range
        - New releases in a specific genre
        - Items not already owned by the user
      </td>
    </tr>

    <tr>
      <td>
        EdTech
      </td>

      <td>
        - Courses in a specific language
        - Beginner-level content for new learners
        - Courses that include a certification
        - Content within a specific subject category
      </td>
    </tr>
  </tbody>
</Table>

# Create Catalog-Based Rule

A catalog-based rule is created by selecting a catalog and defining one or more conditions on its attributes. Conditions can be combined using AND or OR logic and nested into groups.

To create a Catalog-based rule, perform the following steps:

1. Go to _Recommendations_ and select the _Catalog-Based Rules_.

2. Click **Create Rule**.

3. Enter the following details:


   <Image src="https://files.readme.io/1214e7f9f240f9982e8c9197d0ebbd4e5894744c399398a22ec05d724b0ccf0e-Configure_Catalog-Based_Rule.png" align="center" caption="Configure Catalog-Based Rule" border={true} />


   <Table align={["left","left"]}>
     <thead>
       <tr>
         <th>
           Field
         </th>

         <th>
           Details
         </th>
       </tr>
     </thead>

     <tbody>
       <tr>
         <td>
           Name
         </td>

         <td>
           Enter a descriptive name that makes the intent of the rule clear. Teams often manage many rules at once, so use names that reflect the specific filter being applied.

           For example, Include Nike Products, Include Men's Premium Footwear, Include New Arrivals, Include Men's Running Products, and so on.

           The maximum number of characters allowed is 255.
         </td>
       </tr>

       <tr>
         <td>
           Description
         </td>

         <td>
           This field is optional. Capture the rule's purpose for anyone reviewing it later. Keep it specific and action-oriented.

           For example, Include all the items in Men's Footwear; restrict recommendations to premium catalog items priced above ₹5,000;

           The maximum number of characters allowed is 1000.
         </td>
       </tr>

       <tr>
         <td>
           Catalog
         </td>

         <td>
           Select the catalog this rule applies to. You can also upload the catalog from here if you have not already.

           Once selected, a product preview table loads automatically, displaying a sample of the catalog's schema, fields such as _color_, _brand_, _category_, _price_, _identity_, _name_, _image_url,_ and \_created_a_t.

           Use this preview to confirm:

           - The correct catalog is selected
           - The catalog schema is visible
           - The attribute you want to filter on (for example, brand) exists in the catalog
         </td>
       </tr>
     </tbody>
   </Table>

4. Click the <img src="https://files.readme.io/c4f873524de0d8e26fc44f0d8c04f4588d27734c3cbf3d26f88c392aad283952-Refresh_icon.png" valign="middle" height="30"> icon next to the catalog dropdown to reload the preview if needed.

5. Define filter conditions to evaluate a catalog attribute against a value using an operator, thereby refining product recommendations. Only items that satisfy the defined conditions are passed to the recommendation strategy. For more information, refer to _Define Filter Conditions_.

## Define Filter Conditions

Filter conditions are the core of a catalog-based rule. Each condition evaluates a catalog attribute against a value using an operator. Only items that meet the defined criteria are passed to the recommendation strategy.

To add a condition, select a catalog attribute, choose an operator, and enter a value. You can add multiple conditions and combine them using AND or OR logic. Conditions can also be nested into groups for more complex filtering.

The following operators are supported:&#x20;

| Operator | Type               | Description              | Value format                                   |
| -------- | ------------------ | ------------------------ | ---------------------------------------------- |
| EQ       | Text / categorical | Equals                   | List of values, for example, \["Men", "Women"] |
| NE       | Text / categorical | Does not equal           | List of values                                 |
| CNT      | Text / categorical | Contains                 | List of values                                 |
| DNCNT    | Text / categorical | Does not contain         | List of values                                 |
| GT       | Numeric            | Greater than             | Single number, for example, 100                |
| GTE      | Numeric            | Greater than or equal to | Single number                                  |
| LT       | Numeric            | Less than                | Single number                                  |
| LTE      | Numeric            | Less than or equal to    | Single number                                  |
| BET      | Numeric            | Between                  | Two-element list, for example \[10, 50]        |
| INL      | Any                | Is null                  | true                                           |
| SWITH    | Text               | Starts with              | String, for example, "Nike"                    |
| EWITH    | Text               | Ends with                | String                                         |

# Manage Catalog-Based Rules

The Catalog-Based Rules list page is the central place to view, search, filter, and manage all rules in your account.

Each rule in the table displays the following columns by default:


<Image src="https://files.readme.io/07f5923db8f5f0a1bfa35d10abd4684c2f985a1d49d3fe51696ac17c20bb934f-Catalog-Based_Rules_List_Page.png" align="center" caption="Catalog-Based Rule Listing Page" border={true} />


| Column             | Description                                                                                                                                                                                                |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Rule Name          | The name of the rule and its unique ID. Click the copy icon to copy the ID.                                                                                                                                |
| Created On         | The date the rule was created.                                                                                                                                                                             |
| Created By         | The identifier of the user who created the rule.                                                                                                                                                           |
| Updated On         | The date the rule was last modified.                                                                                                                                                                       |
| Active engagements | The number of active engagements currently using this rule. A rule with one or more active engagements cannot be deleted. To delete the rule, first remove it from or stop all engagements referencing it. |

From the rules list, you can perform the following actions on any rule:

- **Edit:** Modify the rule name, description, catalog, or filter conditions.
- **Clone:** Create a copy of an existing rule. Use this to duplicate a rule's configuration as a starting point for a new one.
- **Delete:** Remove one or more rules. Select the rules you want to remove and confirm deletion. Deleted rules are removed permanently.

<Callout icon="📘" theme="info">
  #### Note

  Rules that are actively used by one or more strategies cannot be deleted until they are removed from those strategies.
</Callout>

### Search Rules

Use the search bar at the top of the list to find rules by name. This is particularly useful when managing a large number of rules.

### Filter Rules

Click the \<img src="\[[https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png](https://files.readme.io/b99f7538b9e4ccb533891cc739702136b98e89af650357bf641143f6467967aa-Filter_icon.png)]\([https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png](https://files.readme.io/a973e47e78d9cb32bf7c2372bc46d90fdb6f8eb16dd6ebaa77a63c2b385438c8-Threads_icon.png))" valign="middle" height="20”> icon to open the Filters panel. Filters help narrow the list to rules that match specific criteria.

The following filters are available:


<Image src="https://files.readme.io/5431ea209efab8f5683f3355300eaeec30a797fb9edac40ba4958125de3c788e-Filter_Catalog-Based_Rules.gif" align="center" caption="Filter Catalog-Based Rules from List Page" border={true} />


- **Time Period**: Filters rules by the date they were created or last updated. Select a preset range or define a custom date range using the date picker.
- **Created By**: Filters rules by the team member who created them. Click _Select user_ to choose one or more users from the list.

### Edit Columns

Click the ![](https://files.readme.io/8de2c03feeb395252701620d658cff05d1f864dc0714d5f6cf91c33585ede102-Edit_Columns_icon.png) icon to open the _Edit Columns_ panel. This lets you choose which columns appear in the rules table and reorder them to match your workflow.


<Image src="https://files.readme.io/f7040117388609659e8825ca8f6e914efb91e1e1e65ef5dd5e401bd5efb2bf38-Edit_Columns.gif" align="center" caption="Edit Columns" border={true} />


The following columns can be shown or hidden:

- Created On
- Created By
- Updated On
- Active Strategies

The Rule Name column is always visible and cannot be hidden.

Toggle each column on or off to show or hide it. Drag rows using the handle on the left to reorder columns. Once done, click **Apply Changes** to save. To restore the default column layout, click **Reset**.
