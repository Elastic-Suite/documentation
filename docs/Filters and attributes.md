---
layout: default
title: Filters and attributes
has_children: false
nav_order: 8
---

Magento attributes listing allows ElasticSuite users to configure attribute that will be useful for search and for facets.
Attribute listing can be accessed under the Magento Stores menu > Attributes > Product > Select an attribute
Then under "Storefront properties", configuration for search and facets will be available :

![attributes-configuration](https://user-images.githubusercontent.com/98949123/155306029-8089ce20-01b4-4cdf-87b6-232c6e57ca11.png)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Use for Promo Rule Conditions|No|This is a Magento field, but it's important that this field is set to yes if the attribute is needed in rule engine (virtual categories, virtual attributes, optimizers)|

![attributes-configuration - Copie](https://user-images.githubusercontent.com/98949123/155306388-b798723d-48b1-4723-b4e6-f019c76f715b.png)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Use in Search|No|	If the attribute is used for product search. Eg : Setting it to "Yes" for the "Color" attribute allows to obtain result when searching on "blue hoodie" or "red jacket".|
|Search Weight|1|The weight of this attribute in search.|
|Used in spellcheck|No|When set to "Yes", the engine will compute spellchecking on this attribute values.|
|Display in autocomplete|No|When set to "Yes", values of this attributes will be shown in autocomplete results.|
|Visible in Advanced Search|No|If this attribute can be used on the Advanced Search page.|
|Use in Layered Navigation|No|Set this to "Filterable (with results)" to display this attribute as a search filter (facet) on the Catalog Navigation pages.|
|Use in Search Results Layered Navigation|No|Set this to "Yes" to display this attribute as a search filter (facet) on the Search Result pages.|

NOT DONE 
