---
layout: default
title: Behavioral Optimizer creation - Premium
has_children: false
parent: Optimizers
grand_parent: Search Engine
nav_order: 3
---

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

***

#### Optimizer based on metric (behavioral data)

<img width="533" alt="boost-metric" src="https://user-images.githubusercontent.com/98949123/153369608-aa6d96ec-233c-4ede-b5f6-e540af3dd371.PNG">

**How this works**
This model allows you to apply a dynamic relevance boost that scales proportionally based on real user interactions (behavioral metrics collected by the tracker). 

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Metric | *(Empty)* | Select the specific behavioral metric the boost will be based on. Options include **views** (daily/weekly/total), **sales** (daily/weekly/total), **conversion rates**, and **revenue** (daily/weekly/total). |
| Boost impact | *(Empty)* | Defines the mathematical function used to scale the boost. Options are **Low** (logarithmic), **Medium** (square root), or **High** (linear). |
| Metric value pre-multiplier | *(Empty)* | *(Formerly named "Boost value")*. A constant multiplier applied to the metric's value *before* the Boost Impact function calculates the final score multiplier. |
| Allow negative boost | No | Controls whether products with very low metric values are actively penalized. <br><br>• **No (Recommended):** Products with low metric values (which mathematically result in a score multiplier `< 1`) are safely excluded from the optimizer, preventing them from being artificially pushed down the results page. <br>• **Yes:** Reverts to legacy behavior where a low metric value can mathematically reduce a product's overall relevance score. |

**Calculation Examples**
Assuming you set a **Metric value pre-multiplier of `5`** (formerly named "Boost value"), here is how the final product score multiplier is calculated based on a product's behavioral metric (e.g., total views, sales, etc.):

*   **Low Impact** `log(metric value * pre-multiplier)`: 
    *   Metric = 100 ➔ score multiplied by `log(100 * 5)` = **2.70** 
    *   Metric = 5,000 ➔ score multiplied by `log(5000 * 5)` = **4.40**
    *   Metric = 8,000 ➔ score multiplied by `log(8000 * 5)` = **4.60**

*   **Medium Impact** `√(metric value * pre-multiplier)`: 
    *   Metric = 100 ➔ score multiplied by `√(100 * 5)` = **22.36** 
    *   Metric = 5,000 ➔ score multiplied by `√(5000 * 5)` = **158.11**
    *   Metric = 8,000 ➔ score multiplied by `√(8000 * 5)` = **200**

*   **High Impact** `metric value * pre-multiplier`: 
    *   Metric = 100 ➔ score multiplied by `100 * 5` = **500** 
    *   Metric = 5,000 ➔ score multiplied by `5000 * 5` = **25,000**
    *   Metric = 8,000 ➔ score multiplied by `8000 * 5` = **40,000**
