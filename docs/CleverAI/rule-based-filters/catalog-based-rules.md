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

Catalog-based rules run before items are retrieved from the catalog. They act as a pre-fetch filter, establishing the eligible item pool that the downstream recommendation engine or catalog send process works with.

When a rule is applied, the personalization engine only fetches or considers items that satisfy the rule's conditions. Items that do not match are never retrieved, regardless of how they would otherwise rank.

## Include vs. Exclude

A catalog-based rule can be applied in one of two modes:

* **Include**: Only items that match the defined conditions enter the eligible pool. Items that do not match are excluded before any personalization logic runs.
* **Exclude**: Items that match the defined conditions are removed from the eligible pool before personalization logic runs. All other items remain eligible.

For example, a catalog rule with the condition `Articles EQ ["Politics"]`:

* **Applied as include**: Recommendation engine only fetches and returns Political articles.
* **Applied as exclude**: Recommendation engine never fetches or returns Political articles, regardless of how those items would otherwise rank.

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
        Use Cases
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ECommerce
      </td>

      <td>
        * Recommend only Nike products
        * Recommend only items in the Shoes category
        * Recommend only products under a specific price range
        * Recommend only premium or luxury items
        * Recommend only in-stock or discounted items
        * Recommend only items from brands the user has previously purchased
      </td>
    </tr>

    <tr>
      <td>
        Streaming/OTT Platform
      </td>

      <td>
        * Recommend only Hindi-language content
        * Recommend only drama titles
        * Recommend only recently released or trending shows
        * Recommend only content rated suitable for children
        * Recommend only content available in the user's subscription tier
      </td>
    </tr>

    <tr>
      <td>
        Travel
      </td>

      <td>
        * Recommend only direct flights
        * Recommend only hotels with a rating of 4 stars or above
        * Recommend only properties within a specific price range per night
        * Recommend only vacation packages that include flights
        * Recommend only experiences available in a specific destination
      </td>
    </tr>

    <tr>
      <td>
        Food Delivery
      </td>

      <td>
        * Recommend only restaurants that are currently open
        * Recommend only dishes tagged as vegetarian or vegan
        * Recommend only items under a specific delivery time threshold
        * Recommend only restaurants with a minimum rating
        * Recommend only items within a price range
      </td>
    </tr>

    <tr>
      <td>
        Gaming
      </td>

      <td>
        * Recommend only items available in the in-game store for the user's platform
        * Recommend only bundles within a specific coin or gem range
        * Recommend only new releases in a specific genre
        * Recommend only items not already owned by the user
      </td>
    </tr>

    <tr>
      <td>
        EdTech
      </td>

      <td>
        * Recommend only courses in a specific language
        * Recommend only beginner-level content for new learners
        * Recommend only courses with a certification
        * Recommend only content within a specific subject category
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

   <Image align="center" border={true} caption="Configure Catalog-Based Rule" src="https://files.readme.io/c9b0ad6012520e54b2073e0f103ff7cf36efd84d0332ac441a1520092b4dccff-Configure_Catalog-Based_Rules.png" />

   <br />

   <Table align={["left","left","left"]}>
     <thead>
       <tr>
         <th>
           Field
         </th>

         <th>
           Details
         </th>

         <th>

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

         <td>

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

         <td>

         </td>
       </tr>

       <tr>
         <td>
           Catalog
         </td>

         <td>
           Select the catalog this rule applies to. You can also upload the catalog from here if you have not already.

           Once selected, a product preview table loads automatically, displaying a sample of the catalog's schema, fields such as _color_, _brand_, _category_, _price_, _identity_, _name_, _image_url,_ and, _created_a_t.

           Use this preview to confirm:

           * The correct catalog is selected
           * The catalog schema is visible
           * The attribute you want to filter on (for example, brand) exists in the catalog
         </td>

         <td>

         </td>
       </tr>
     </tbody>
   </Table>

   <br />
4. Click the <Image border={true} src="https://files.readme.io/c4f873524de0d8e26fc44f0d8c04f4588d27734c3cbf3d26f88c392aad283952-Refresh_icon.png" className="border" /> icon next to the catalog dropdown to reload the preview if needed.
5. Define filter conditions to evaluate a catalog attribute against a value using an operator to refine product recommendations. Only items that satisfy the defined conditions are passed to the recommendation strategy. For more information, refer to [Define Filter Conditions](doc:catalog-based-rules#define-filter-conditions).

## Define Filter Conditions

Filter conditions are the core of a catalog-based rule. Each condition evaluates a catalog attribute against a value using an operator. Only items that meet the defined criteria are passed to the recommendation strategy.

To add a condition, select a catalog attribute, choose an operator, and enter a value. You can add multiple conditions and combine them using AND or OR logic. Conditions can also be nested into groups for more complex filtering.

The following operators are supported:

| Operator | Type               | Description              | Value format                                  |
| -------- | ------------------ | ------------------------ | --------------------------------------------- |
| EQ       | Text / categorical | Equals                   | List of values, for example, ["Men", "Women"] |
| NE       | Text / categorical | Does not equal           | List of values                                |
| CNT      | Text / categorical | Contains                 | List of values                                |
| DNCNT    | Text / categorical | Does not contain         | List of values                                |
| GT       | Numeric            | Greater than             | Single number, for example, 100               |
| GTE      | Numeric            | Greater than or equal to | Single number                                 |
| LT       | Numeric            | Less than                | Single number                                 |
| LTE      | Numeric            | Less than or equal to    | Single number                                 |
| BET      | Numeric            | Between                  | Two-element list, for example [10, 50]        |
| INL      | Any                | Is null                  | true                                          |
| SWITH    | Text               | Starts with              | String, for example, "Nike"                   |
| EWITH    | Text               | Ends with                | String                                        |

# Manage Catalog-Based Rules

The Catalog-Based Rules list page is the central place to view, search, filter, and manage all rules in your account.

Each rule in the table displays the following columns by default:

<Image align="center" border={true} caption="Catalog-Based Rule Listing Page" src="https://files.readme.io/07f5923db8f5f0a1bfa35d10abd4684c2f985a1d49d3fe51696ac17c20bb934f-Catalog-Based_Rules_List_Page.png" />

| Column             | Description                                                                                                                               |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Rule Name          | The name of the rule and its unique ID. Click the copy icon to copy the ID.                                                               |
| Created On         | The date the rule was created.                                                                                                            |
| Created By         | The identifier of the user who created the rule.                                                                                          |
| Updated On         | The date the rule was last modified.                                                                                                      |
| Active engagements | The number of engagements currently using this rule either as part of catalog send tie personalisation or recommendation personalization. |

From the rules list, you can perform the following actions on any rule:

* **Edit:** Modify the rule's name, description, catalog, or filter conditions.
* **Clone:** Create a copy of an existing rule. Use this to duplicate a rule's configuration as a starting point for a new one.
* **Delete:** Remove one or more rules. Select the rules you want to remove and confirm deletion. Deleted rules are removed permanently.

<Callout icon="📘" theme="info">
  #### Note

  Rules that are actively used by one or more strategies cannot be deleted until they are removed from those strategies.
</Callout>

### Search Rules

Use the search bar at the top of the list to find rules by name. This is particularly useful when managing a large number of rules.

### Filter Rules

Click the <Image border={true} src="https://files.readme.io/b99f7538b9e4ccb533891cc739702136b98e89af650357bf641143f6467967aa-Filter_icon.png" className="border" /> icon to open the Filters panel. Filters help narrow the list to rules that match specific criteria.

The following filters are available:

<Image align="center" border={true} caption="Filter Catalog-Based Rules from List Page" src="https://files.readme.io/5431ea209efab8f5683f3355300eaeec30a797fb9edac40ba4958125de3c788e-Filter_Catalog-Based_Rules.gif" />

* **Time Period**: Filters rules by the date they were created or last updated. Select a preset range or define a custom date range using the date picker.
* **Created By**: Filters rules by the team member who created them. Click _Select user_ to choose one or more users from the list.

### Edit Columns

Click the ![](https://files.readme.io/8de2c03feeb395252701620d658cff05d1f864dc0714d5f6cf91c33585ede102-Edit_Columns_icon.png) icon to open the _Edit Columns_ panel. This lets you choose which columns appear in the rules table and reorder them to match your workflow.

<Image align="center" border={true} caption="Edit Columns" src="https://files.readme.io/f7040117388609659e8825ca8f6e914efb91e1e1e65ef5dd5e401bd5efb2bf38-Edit_Columns.gif" />

The following columns can be shown or hidden:

* Created On
* Created By
* Updated On
* Active Strategies

The Rule Name column is always visible and cannot be hidden.

Toggle each column on or off to show or hide it. Drag rows using the handle on the left to reorder columns. Once done, click **Apply Changes** to save. To restore the default column layout, click **Reset**.
