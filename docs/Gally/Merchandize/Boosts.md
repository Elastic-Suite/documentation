---
layout: default
title: Boosts - Premium
has_children: false
parent: Merchandize
grand_parent: Gally
nav_order: 3
---

It can be accessed under MERCHANDIZE menu : MERCHANDIZE > Boosts.
This entry allows user to manage boosts in product listings (categories, search result pages and autocomplete box).

## Boost grid

At the top of the page, a filter bar is available. User can filter based on every column of the grid (name, model, request type, enable and localized catalog(s)).

The grid lists all the boosts created in Gally : 

![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-grid.png)


|Parameter   | Description|
|:-------------|:------|
|Name|Name of the boost|
|Model|Model of the boost : constant or proportional to an attribute value|
|Request type|The request type(s) on which the boost will be applied. 3 possible values : Category listing, search result and autocomplete. One or several request type can be selected on the same boost.|
|Enable|The boost is enabled or not|
|Localized catalog(s)|The localized catalog(s) on which the boost will be applied. One or several localized catalog can be selected on the same boost.|
|Actions|Button "Edit" allowing to access the edition page of the boost.|

## Boost edition page

### Boost basic edition

The first part of the boost edition page is dedicated to the basic configurations : 

![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-basic-edition.png)
![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-basic-edition2.png)

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Enable |True  |Boost is enabled or not |
|Name |  |Name given to the boost|
|Localized catalog(s)||Selection of the localized catalog(s) on which the boost will be applied. Boost can be applied on one or several localized catalog |
|Request type||Selection of the request type(s) on which the boost will be applied. 3 possible values : Category listing, search result and autocomplete. Boost can be applied on one or several request type|
|Active||Period of time on which the boost will be applied. If those fields are empty, the boost will be applied from now and forever. If "from" is empty, boost will be applied from now and until the date contributed on "to" field. If "to" is empty, boost will be applied from the date contributed on the "from" field and forever |
|Rule engine||This fieldset figures a rule editor where you are able to chose any combination of conditions you want to match. For example : apply boost only on organic cotton products. Attributes available in the rule engine are attributes that have been set as "Use in rule engine" in Settings > Searchable and filterable attributes|


### Boost configuration

This section will allow user to choose the model. According to the model, following configuraiton will be different : 

#### Constant model

![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-conf-constant.png)

With the constant model, the value of the boost will influence the score of the products and change sorting in selected product listings. 
For example a boost value of 30% will multiply the score of the product by 1.3.

It's also possible to deboost a product by selecting a negative value

![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-value.png)

For example : a boost value of -40% will multiply the score of the product by 0.6

#### Proportional to an attribute value model

![boost-grid](https://raw.githubusercontent.com/Elastic-Suite/documentation/refs/heads/master/static/boost-edition-proportional.png)

With the proportional to an attribute value model, the boost will be influenced by the value of the attribute.
Only numerical attributes can be used for this model. 
For example, if the cost attribute is selected for the boost, and the cost of product A is 10€ and cost of product B is 15€, then the score of product B will be higher then product A.

The impact of the boost allows to control the boost value. There is 3 possible impacts :
- Low : use logarithmic formula
- Medium : use square formula
- High : use linear formula

At last, a scale factor can be used to control the score of products.

Calculation is as follow for an example with a weight attribute : 
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


### Boost Preview

At the end of the boost page, user can preview product listings before and after boost application.
First, user has to select the type of request to preview.

In case of "Category navigation" selection, user has to select the category to preview : 

<img width="1032" height="681" alt="image" src="https://github.com/user-attachments/assets/d47e5d54-1d78-48d0-881f-00710c916b2a" />

In case of "Catalog search" or "Autocomplete" selection, user has to type the search term to preview :

<img width="1009" height="317" alt="image" src="https://github.com/user-attachments/assets/110dae44-475d-4ce8-ac7d-bb4b5a8a8094" />

Then, user clicks on "Preview" : 

<img width="1529" height="716" alt="image" src="https://github.com/user-attachments/assets/2346ebdf-e640-49d9-a804-1d3cb2a5f0b1" />

Table has two major parts : 
- Base results which is the product listing before boost application
- Optimized results which is the product listing after boost application

The column "Score" gives the base score and before boost application (for base results section), the calculated score after boost application (for the optimized section).

The column gives the direction of the product after boost application
- <img width="48" height="50" alt="image" src="https://github.com/user-attachments/assets/5848e1d4-c887-4ecd-9ddf-226d66262366" /> : product has gone up
- <img width="46" height="46" alt="image" src="https://github.com/user-attachments/assets/bfb2f8f3-94bd-4102-bcf4-a9e7bf4f8d64" /> : product has gone down
- <img width="49" height="49" alt="image" src="https://github.com/user-attachments/assets/c59102db-d6ab-45e9-972d-e90e289309bf" /> : product didn't change position











