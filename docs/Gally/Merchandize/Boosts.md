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
<img width="1595" height="750" alt="image" src="https://github.com/user-attachments/assets/c53bfc66-8233-41a4-bf3c-f005e058cb57" />

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

<img width="757" height="592" alt="image" src="https://github.com/user-attachments/assets/91ec1bf9-c19e-469c-a4fe-e9b6d4ffde23" />
<img width="864" height="381" alt="image" src="https://github.com/user-attachments/assets/e7629476-a3ce-4f99-bf1a-74c181f02b73" />


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

<img width="484" height="276" alt="image" src="https://github.com/user-attachments/assets/8a11b60e-8041-4712-a296-f7d08f5bdf91" />

With the constant model, the value of the boost will influence the score of the products and change sorting in selected product listings. 
For example a boost value of 30% will multiply the score of the product by 1.3.

It's also possible to deboost a product by selecting a negative value

<img width="417" height="95" alt="image" src="https://github.com/user-attachments/assets/86cd0d3a-5cfc-400c-a35b-f27130111d94" />

For example : a boost value of -40% will multiply the score of the product by 0.6

#### Proportional to an attribute value model

<img width="338" height="492" alt="image" src="https://github.com/user-attachments/assets/1b77fd99-a8e7-48b1-8bea-3b223a13d8dc" />

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









