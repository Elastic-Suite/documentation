---
layout: default
title: Recommender types
has_children: false
parent: Recommenders
grand_parent: Merchandize
nav_order: 2
---

The **Recommender type** dashboard is the foundational step for setting up recommendations in Gally. Before you can generate specific product recommendations, you first need to define the structural types of recommendations you want to display on your storefront (such as up-sells, cross-sells, or related products). 

<img width="1434" height="640" alt="image" src="https://github.com/user-attachments/assets/12a04e84-8833-4361-b907-904f56b8acac" />

Once your recommender types are created here, you will be able to configure the actual logic and recommendation rules under the **Auto recommenders** section.

### Managing Recommender Types

The dashboard provides a clear interface to view and organize your existing recommendation categories:

*   **Create Recommender type:** Use the **Create Recommender type** button located at the top right of the screen to add a new type to your system.
*   **Filtering:** You can easily search through your existing types using the **Filter** menu, and reset your current view using the **Clear all** button.

### Grid Columns

The main grid lists all configured recommender types and provides the following information:

| Column | Description |
| :--- | :--- |
| **Name** | The human-readable label of the recommender type (for example, "Default", "Up-sell", or "Cross-sell"). |
| **Code** | The internal, unique technical identifier code used by the system for this type (for example, "default"). |
| **Actions** | Provides a direct **Edit** link allowing you to modify the configuration of the specific recommender type. |

### Creating and Updating a Recommender Type

When creating a new recommender type, you will be presented with a dedicated creation form containing two mandatory fields:

<img width="1427" height="495" alt="image" src="https://github.com/user-attachments/assets/f347132f-a7ac-4b7f-94f2-8d76fc78bf7e" />

*   **Name:** The human-readable label for the recommender type (for example, "Up-sell" or "Cross-sell").
*   **Code:** The unique internal technical identifier used by the system for this type.

To save your new configuration, click the **Create** button at the top right of the screen, or use the **Back** link to return to the previous page without saving.

**Updating an existing type:**
If you need to update a recommender type later via the edit action, you can freely modify its **Name**. However, please keep in mind that the **Code** field is strictly permanent and cannot be updated once the recommender type has been successfully created.



