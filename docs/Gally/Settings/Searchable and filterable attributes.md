---
layout: default
title: Searchable and filterable attributes
has_children: false
parent: Settings
grand_parent: Gally
nav_order: 2
---
It can be accessed under Settings > Searchable and filterable attributes. This entry will allow user to configure each attribute.

At the top of the page, a filter bar is available. User can filter based on attribute code, label and type. User can also filter on attribute configuration (filterable, searchable, sortable and use in rule engine).

The grid with all attributes sent by the e-commerce application are displayed here.
In addition to attribute from the e-commerce data dictionnary, some system attribute are displayed and can't be edited in Gally : 
* image - Base
* id - Id
* sku - SKU
* category - Category
* name - Product Name
* price - Price
* stock - Stock

![image](https://user-images.githubusercontent.com/98949123/212350187-13183472-7d39-467b-b2f4-187f233494fd.png)

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Attribute code||Attribute code used to identified the attribute|
|Attribute label||Attribute label used to named the attribute|
|Attribute type||Type of the attribute (text, integer, select, yes/no...)|
|Filterable|No|Is the attribute filterable in the e-commerce application or not. Meaning : is it going to be displayed as a facet ? If set to yes, attribute is available in SEARCH > Facets grid.|
|Searchable|No|Is the attribute searchable in the e-commerce application or not. Meaning : Is attribute values will be used to compute product search and give results to front user. If set to yes, attribute is available in SEARCH > Configuration > Attributes|
|Sortable|No|Is the attribute sortable in the e-commerce application or not. Meaning : is attribute value will be used as a sorting criteria in product listing. If set to yes, attribute is available in MERCHANDIZE > Categories > DEfault sorting dropdown.|
|Use in rule engine||Is the attribute used in rule engine in Gally admin or not. Meaning : I attribute and its values will be used as conditions in rule engines. If set to yes, attribute is available in every rule engine of Gally admin (virtual category, boosts...)|
