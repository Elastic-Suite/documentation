---
layout: default
title: Auto recommenders
has_children: false
parent: Recommenders
grand_parent: Merchandize
nav_order: 1
---

Once you have defined your Recommender types, you can use the **Auto recommender** dashboard to create and manage the actual recommendation rules. This feature allows you to dynamically suggest specific "Target" products based on the "Source" products a customer is currently viewing or interacting with.

### Auto Recommender Dashboard

<img width="1597" height="455" alt="image" src="https://github.com/user-attachments/assets/8178185a-8b3a-4a38-94e7-422e1cb46a17" />

The main grid provides a clear overview of all your active and inactive recommendation rules. From here, you can:

*   **Create an Auto recommender:** Use the **Create Auto recommender** button at the top right of the screen to build a new rule.
*   **Filter & Search:** Use the **Filter** menu to easily find specific rules, and reset the view using the **Clear all** button.
*   **Manage rules:** The grid lists key information for each rule, including its Name, Priority, Enable status, the Localized catalog(s) it applies to, and the specific Recommender Type it is **Applied to**. You can click the **Edit** link in the Actions column to modify an existing rule.

### Creating and Updating an Auto Recommender

When you create or edit an auto recommender, you will configure its behavior through a detailed form separated into general settings and rule engines.

#### General Settings

<img width="1018" height="670" alt="image" src="https://github.com/user-attachments/assets/4307d567-3682-4ded-a6ac-c47947bbd366" />

*   **Enable:** A toggle switch to quickly activate or deactivate the rule on your storefront.
*   **Name:** A mandatory, human-readable label for your rule (for example, "Tops and Bottoms").
*   **Localized catalog(s):** A multi-select field allowing you to define exactly which catalogs and store views this recommendation applies to.
*   **Applied to:** This mandatory dropdown links your rule to a structural **Recommender type** (such as the "Default", "Up-sell", or "Cross-sell" types you created previously).
*   **Active (From / To):** Date pickers allowing you to schedule time-bound recommendation campaigns.
*   **Priority:** A mandatory numeric value. If multiple auto recommenders match a given product context, the system will use this priority score to determine which rule takes precedence.

#### Rule Engines

<img width="1014" height="596" alt="image" src="https://github.com/user-attachments/assets/804005da-52cd-42bc-943e-0e11c4b08dfb" />

The core logic of your recommendations is built using two distinct visual condition builders:

*   **Source rule engine:** This defines the *triggering context*. You build conditions here to identify the product the user is currently looking at. 
    *   *Example: Set a condition where `Category is equal to Bottoms`. The rule will only trigger when a user views pants, shorts, etc.*
*   **Target rule engine:** This defines the *recommended products*. You build conditions here to determine which items will be pulled from your catalog and displayed to the user.
    *   *Example: Set a condition where `Category is equal to Tops`. The system will fetch shirts, jackets, etc., to recommend.*

Both the Source and Target engines allow you to combine complex criteria, giving you the flexibility to require that **all** conditions are true, or that **any** conditions are true, ensuring highly relevant cross-merchandising.

