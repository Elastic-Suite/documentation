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
|Model|Constant|The model to use for scoring : <br/> - **Constant** : to apply a constant score (Details bellow) <br/> - **Based on attribute value** : to apply a boost that will be proportional to an attribute value (Details bellow) <br/> - **Based on behavioral data** : to apply a boost that will be proportional to the selected metric (Details bellow)|
|Optimizer Name||The name of the optimizer.|
|Active From||Start date of the optimizer. Use it for temporary events.|
|Active To||	End date of the optimizer.|
|Request Type||The request to apply the optimizer : <br/> - Catalog Product Search : the catalog search results. <br/> - Catalog Product Autocomplete : product results in the autocomplete <br/> - Category Product View : the catalog navigation. <br/> - Quick Order Suggest Search : product results in the quick order suggest search. <br/> - Related Products : products in the related product blocks. <br/> - Upsell Products : products in the upsell product blocks. <br/> - Cross-sell Products : products in the Cross-sell product blocks. <br/> - Visitor Products : products in the visitor product blocks.|

![searchoptimizers_rule](https://user-images.githubusercontent.com/98949123/153025564-244f6818-b090-42cb-b36e-d471f8dfa14a.png)

This fieldset figures a rule editor where you are able to chose any combination of conditions you want to match.

Eg :
* "Color is Blue" to apply a boost on products having the value "Blue" for the "Color" Attribute
* "Only discounted products" to apply a boost on products actually having a special price applied
* "Only in stock products" to display immediately salable products on top of your product list
and so on ...

##### Constant optmizer 

<img width="509" alt="boost-bury" src="https://user-images.githubusercontent.com/98949123/153023601-442ead62-0715-4fa7-8c84-4beeaca0ea05.PNG">

The value given to the optimizer will impact the score of the products in listings.
</br>For example : a value of 10 will multiply by 10% the score of products affected by the boost. As a result, products will go up in affected listing. 
</br>A value of -40 will multiply by -40% the score of products affected by the boost. As a result, products will go down in affected listing.

##### Optimizer based on attribute value

<img width="661" alt="boost-attribute-value" src="https://user-images.githubusercontent.com/98949123/153027839-5e845eeb-1b17-43ac-9803-8d1a09d0dcdb.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Attribute||Select the attribute the boost will based on|
|Boost impact||Low <br/> Medium <br/> High |
|Boost value||Value for the multiplication|

Calculation is as follow : 
<br/>**Low** : log (attribute value * boost value). 
For example : Boost value = 2 
- Attribute weight = 1kg --> product score will be multiplied by log(2*1) = **0,3** 
- Attribute weight = 3kg --> product score will be multiplied by log(2*3) = **0,78**
- Attribute weight = 100kg --> product score will be multiplied by log(2*100) = **2,3**

<br/> **Medium** : &radic; (attribute value * boost value). 
For example : boost value = 2 
- Attribute weight = 1kg --> product score will be multiplied by &radic;(2*1) = **1,99** 
- Attribute weight = 3kg --> product score will be multiplied by &radic;(2*3) = **2,45**
- Attribute weight = 100kg --> product score will be multiplied by &radic;(2*100) = **14,14**

<br/> **High** : attribute value * boost value. 
For example : boost value = 2 
- Attribute weight = 1kg --> product score will be multiplied by 2*1 = **2** 
- Attribute weight = 3kg --> product score will be multiplied by 2*3 = **6**
- Attribute weight = 100kg --> product score will be multiplied by 2*100 = **200**

##### Optimizer based on metric (behavioral)

<img width="533" alt="boost-metric" src="https://user-images.githubusercontent.com/98949123/153369608-aa6d96ec-233c-4ede-b5f6-e540af3dd371.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Metric||Select the metric the boost will based on. Boost can be based on daily views, weekly views, sales, daily sales, weekly sales, conversion rate and daily conversion rate. For every metric, you can select the average metric or the exact number|
|Boost impact||Low <br/> Medium <br/> High |
|Boost value||Value for the multiplication|

Calculation is as follow : 
<br/>**Low** : log (attribute value * boost value). 
For example : Boost value = 5 
- Metric = 100 --> product score will be multiplied by log(5*100) = **2,70** 
- Metric = 5000 --> product score will be multiplied by log(5*5000) = **4,40**
- Metric = 8000 --> product score will be multiplied by log(5*8000) = **4,60**

<br/> **Medium** : &radic; (attribute value * boost value). 
For example : boost value = 5 
- Metric = 100 --> product score will be multiplied by &radic;(5*100) = **22,36** 
- Metric = 5000 --> product score will be multiplied by &radic;(5*5000) = **158,11**
- Metric = 8000 --> product score will be multiplied by &radic;(5*8000) = **200**

<br/> **High** : attribute value * boost value. 
For example : boost value = 5 
- Metric = 100 --> product score will be multiplied by 5*100 = **500** 
- Metric = 5000 --> product score will be multiplied by 5*5000 = **25000**
- Metric = 8000 --> product score will be multiplied by 5*8000 = **40000**
