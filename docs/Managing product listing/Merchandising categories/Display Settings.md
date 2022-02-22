---
layout: default
title: Display Settings
has_children: false
parent: Merchandising categories
grand_parent: Managing product listing
nav_order: 1
---

<img width="669" alt="display-settings" src="https://user-images.githubusercontent.com/98949123/155118826-325158df-7911-499d-95e5-494413413b5b.PNG">

Table "Layered Navigation Filters"

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Attribute| | Attributes available for facets in this category|
|Display mode|Auto |Auto : Attribute will be displayed according to configuration made in next columns <br/> Always hidden : Attribute will never be displayed as a facet on this category<br/> Always displayed : Attribute will always be displayed as a facet on this category|
|Facet coverage rate|90|Coverage rate for this facet on this specific category. A number between 0 to 100. For example : 90 means that if 90% or more of products on the category use this attribute then facet is displayed. If less then 90%, facet is not displayed.|
|Facet max. size|10 |Number of facet values to display before proposing the button "display more" and a search bar for searching the value in the facet for front user|
|Sort Order|Result count |- Result count : Will order values according to their number of results (descending). <br/> - Admin sort : Values will be displayed as ordered in attribute's options values in Magento back-office. <br/> - Name : Values will be displayed alphabetically (ascending). <br/> - Relevance : Values will be sorted according to first occurence in product listing|
|Pinned|Unpinned |If an attribute is pinned, then a drag and dropper will be available, and user will be able to drag and drop the attribute in the wanted position. |
