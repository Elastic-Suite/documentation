---
layout: default
title: Virtual categories
has_children: false
parent: Managing product listing
grand_parent: ElasticSuite
nav_order: 3
---
## Virtual Categories Configuration

You can access this feature by navigating to the Magento **Catalog** menu > **Categories** > Select a category in the tree > expand the **"Products in Category"** section.

A category can be created specifically to be a virtual category, or an already existing standard category can be switched to virtual. **Note:** If you switch an existing category, all products that were previously manually placed into this category will be removed from it.

To begin, toggle the **"Virtual Category"** switcher to **Yes**. A rule engine will then appear, allowing you to build the dynamic conditions for this virtual category.

![virtual-category](https://user-images.githubusercontent.com/98949123/155300177-8f1a150d-0915-41f4-8fa0-3048cc29bb70.PNG)

### Configuration Parameters

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Virtual Category | No | Toggles whether the category operates as a virtual category. |
| Virtual Category Root | Default Category | Allows you to choose a base category to map the virtual category on. The products inside the virtual category will be contextualized relative to this root category, and the layered navigation facets displayed on the Front-Office will reflect this context. |
| Generate Virtual Category Root Subtree | No | When enabled, the category filter for this virtual category will automatically generate a subtree based on the **Virtual Category Root**. *For example, if your root is "Default Category", users browsing this virtual category will be able to filter among its children categories (like "Men" and "Women")*. |
| Virtual rule | *(Empty)* | The rule engine allows you to configure the specific product conditions associated with this virtual category. You can use a single rule or a complex combination of rules. |

### Rule Engine Capabilities

The rule engine offers extensive flexibility to define which products belong in your virtual category:
*   **Standard Attributes:** You can filter by standard catalog attributes. For instance, when using the `SKU` attribute, you can configure the rule to use either exact matching or a "contains" match.
*   **Special Attributes:** You can create dynamic rules based on time-sensitive criteria or stock, such as:
    *   **Days since the creation date of the product** (e.g., dynamically display products created in the last 30 days).
    *   **Days since the update date of the product**.
    *   **Stock quantity and searchable content**.
*   **Undefined Values:** The engine fully supports the "is undefined" operator for all types of attributes, allowing you to catch products missing specific data.
*   **Alphabetical Sorting:** If you have attributes with long lists of options (like brands), you can force alphabetical sorting of attribute options in the rule engine via **Stores > Configuration > Elasticsuite > Catalog Search > Catalog Rules Configuration**.

### Previews & Sorting

All preview and manual sorting functionalities available for standard categories are fully supported for virtual categories as well. You can drag and drop products in the preview grid to pin them to specific positions. You can also define product positions and blacklists at the store view level.

---

### Important Notes
*   **Disabled Root Categories:** By default, if the category you selected as the "Virtual Category Root" is disabled (or if a disabled category is used in your virtual rules), the virtual category will be forced to display zero products. You can manage this behavior via **Stores > Configuration > Elasticsuite > Catalog Search > Catalog Search Configuration > Force zero results for disabled categories**.
*   **Monitoring Virtual Categories:** If you are using Elasticsuite Premium, you can use the **Virtual Categories Dashboard** to view, manage, and monitor all your virtual categories from a single centralized grid.
