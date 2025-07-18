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




