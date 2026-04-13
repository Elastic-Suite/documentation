---
layout: default
title: Constant Optimizer creation
has_children: false
parent: Optimizers
grand_parent: Search Engine
nav_order: 2
---
## Customizing Product Sorting

ElasticSuite offers multiple ways to customize the sorting and ranking of your products:

* **Using Search Optimizers:** Dynamically boost or bury products based on specific rules.
* **Manual sorting in categories:** Explicitly define the exact position of products within a specific category.
* **Manual sorting for search queries:** Explicitly define the exact position of products for specific search terms.

### Using the Search Optimizers

You can access the optimizer management grid by navigating to **ElasticSuite > Optimizers** in the Magento admin menu. From here, you can create, update, or delete your search optimizers.

#### Creating an Optimizer

The main page displays a grid of all your existing optimizers. To add a new one, click the **Add New Optimizer** button.

You will then be directed to the optimizer creation form, which contains the following general configuration fields:

<img width="290" alt="searchoptimizers_general" src="https://user-images.githubusercontent.com/98949123/153017799-276ead07-6e7c-4593-a358-1cfffe22f272.PNG">

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enable optimizer | Yes | Toggles whether the optimizer is active and applied to the storefront. |
| Store View | *(Empty)* | Defines the scope of the optimizer. An optimizer can only be assigned to a single store view. |
| Model | Constant | Determines the scoring mechanism used by the optimizer: <br><br>• **Constant:** Applies a fixed score multiplier. <br>• **Based on attribute value:** Applies a dynamic boost proportional to a specific product attribute's value. <br>• **Based on behavioral data:** Applies a dynamic boost proportional to a selected behavioral metric (e.g., views, sales). |
| Optimizer Name | *(Empty)* | The internal name of the optimizer for administration purposes. |
| Active From | *(Empty)* | The start date for the optimizer. Useful for scheduling temporary merchandising events or sales campaigns. |
| Active To | *(Empty)* | The end date for the optimizer. |
| Request Type | *(Empty)* | Defines the specific storefront context where this optimizer will be applied: <br><br>• **Catalog Product Search:** Standard catalog search results page. <br>• **Catalog Product Autocomplete:** Product suggestions in the autocomplete dropdown. <br>• **Category Product View:** Standard catalog category navigation pages. <br>• **Quick Order Suggest Search:** Product results in the quick order suggestion search. <br>• **Related Products:** Products displayed in the "Related Products" blocks. <br>• **Upsell Products:** Products displayed in the "Upsell Products" blocks. <br>• **Cross-sell Products:** Products displayed in the "Cross-sell Products" blocks. <br>• **Visitor Products:** Products displayed in visitor-specific recommendation blocks. |

#### Rule Configuration

![searchoptimizers_rule](https://user-images.githubusercontent.com/98949123/153025564-244f6818-b090-42cb-b36e-d471f8dfa14a.png)

This section features a flexible rule editor allowing you to define the exact conditions products must meet to be affected by the optimizer. 

*Examples of rules you can create:*
* **"Color is Blue"**: Apply a boost exclusively to products where the "Color" attribute is "Blue".
* **"Only discounted products"**: Apply a boost to products currently featuring a special price.
* **"Only in stock products"**: Push immediately salable products to the top of your product lists.

#### Constant Optimizer 

<img width="509" alt="boost-bury" src="https://user-images.githubusercontent.com/98949123/153023601-442ead62-0715-4fa7-8c84-4beeaca0ea05.PNG">

When using the **Constant** model, the percentage value provided acts as a direct multiplier on the base relevance score of the targeted products. 

* **Boosting (Positive Value):** A value of `10%` will multiply the score of the affected products by `1.10`. As a result, these products will rank higher in the affected listings.
* **Burying (Negative Value):** A value of `-40%` will multiply the score of the affected products by `0.60` (calculated as `1 - 0.40`). As a result, these products will rank lower in the affected listings.

#### Optimizer based on attribute value

<img width="661" alt="boost-attribute-value" src="https://user-images.githubusercontent.com/98949123/153027839-5e845eeb-1b17-43ac-9803-8d1a09d0dcdb.PNG">

**How this works**
This model allows you to apply a dynamic relevance boost that scales proportionally based on the numeric value of a specific product attribute (such as weight, margin, or a custom score).

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Attribute | *(Empty)* | Select the specific numeric product attribute the boost will be based on. |
| Boost impact | *(Empty)* | Defines the mathematical function used to scale the boost. Options are **Low** (logarithmic), **Medium** (square root), or **High** (linear). |
| Attribute value pre-multiplier | *(Empty)* | *(Formerly named "Boost value" in older versions).* A constant multiplier applied to the attribute's value *before* the Boost Impact function calculates the final score multiplier. |

**Calculation Examples**
Assuming you set an **Attribute value pre-multiplier of `2`**, here is how the final product score multiplier is calculated based on a product's attribute value (e.g., `weight`):

*   **Low Impact** `log(attribute value * pre-multiplier)`: 
    *   Attribute weight = 1kg ➔ score multiplied by `log(1 * 2)` = **0.30**
    *   Attribute weight = 3kg ➔ score multiplied by `log(3 * 2)` = **0.78**
    *   Attribute weight = 100kg ➔ score multiplied by `log(100 * 2)` = **2.30**

*   **Medium Impact** `√(attribute value * pre-multiplier)`: 
    *   Attribute weight = 1kg ➔ score multiplied by `√(1 * 2)` = **1.41**
    *   Attribute weight = 3kg ➔ score multiplied by `√(3 * 2)` = **2.45**
    *   Attribute weight = 100kg ➔ score multiplied by `√(100 * 2)` = **14.14**

*   **High Impact** `attribute value * pre-multiplier`: 
    *   Attribute weight = 1kg ➔ score multiplied by `1 * 2` = **2** 
    *   Attribute weight = 3kg ➔ score multiplied by `3 * 2` = **6**
    *   Attribute weight = 100kg ➔ score multiplied by `100 * 2` = **200**

