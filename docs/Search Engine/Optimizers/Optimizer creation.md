---
layout: default
title: Optimizer creation
has_children: false
parent: Optimizers
grand_parent: Search Engine
nav_order: 2
---
## Customizing product Sorting.

ElasticSuite allows you to customize product sorting in several ways :

* Using the Search Optimizers
* Manual sorting of products in a category
* Manual sorting of products for a given search query

### Using the Search Optimizers

It can be accessed under the **Smile ElasticSuite** menu, via the **Optimizers** entry.

You can create, update and delete your search optimizers here.

#### Creating an Optimizer

In this page you have a grid displaying all your optimizers. You can add a new one by clicking on the **Add New Optimizer** button.

You will then be prompted to the optimizer create form containing the following fields :

<img width="290" alt="searchoptimizers_general" src="https://user-images.githubusercontent.com/98949123/153017799-276ead07-6e7c-4593-a358-1cfffe22f272.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Enable optimizer|Yes|	If the optimizer should be enable or not.|
|Store View||The store view for this optimizer. An optimizer can only be assigned to one store view.|
|Model||The model to use for scoring : </br> - **Constant** : to apply a constant score (Details bellow) </br> - **Based on attribute value** : to apply a boost that will be proportional to an attribute value (Details bellow)|
|Optimizer Name||The name of the optimizer.|
|Active From||Start date of the optimizer. Use it for temporary events.|
|Active To||	End date of the optimizer.|
|Request Type||The request to apply the optimizer : </br>- Catalog Product Search : the catalog search results. </br>- Catalog Product Autocomplete : product results in the autocomplete </br>- Category Product View : the catalog navigation. </br>- Quick Order Suggest Search : product results in the quick order suggest search. </br>- Related Products : products in the related product blocks. </br>- Upsell Products : products in the upsell product blocks. </br>- Cross-sell Products : products in the Cross-sell product blocks. </br>- Visitor Products : products in the visitor product blocks.|


