---
layout: default
title: Explain results
has_children: false
parent: Search Engine
---
ElasticSuite allows you to access to the explain and compare page : it will give insights about the search result, the optimizer and product scores.

It can be accessed under the Smile ElasticSuite menu, via the Optimizers entry.

<img width="509" alt="form-explain-result" src="https://user-images.githubusercontent.com/98949123/153380077-f40db411-6e59-43b6-8ee0-f21f1fd5b3d4.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Store view|Default Store View|The storeview where information is needed. Only storeviews can be selected here|
|Request type|Catalog Product Search|Catalog Product Search : will display products of a search result listing <br/> Catalog Product Autocomplete : will display products on the autocomplete <br/> Category Product View : will display products of a category listing|
|Query text (for Catalog Product Search and Catalog Product Autocomplete)||Query for which information is needed|
|Category Preview (for Category Product View)||Dropdown with all categories from the platform. User can select the category for which information is needed|
|Explain||Button explain, by clicking explain and compare is displayed|

![explain-results](https://user-images.githubusercontent.com/98949123/153381927-86c71933-bb1c-4045-8665-36a61b026a9f.png)

| Block    | Description |
|:-------------|:------|
|Synonyms and expansions|If thesaurus are configured on this term, they will be displayed here|
|Optimizers|If optimizers are applied on products from this query, they will be displayed here|
|Product listing|Product listing resulting from this query. For each product, information are displayed (more details bellow)|

<img width="160" alt="explain-results-products" src="https://user-images.githubusercontent.com/98949123/153383086-7ac1ce9b-db62-49a9-b981-0deabbbb2102.png">

| Block    | Description |
|:-------------|:------|
|Locker|The product is manually sorted|
|Green arrow|The product is boost thanks to an optimizer|
|Score|Score of the product resulting from optimizer value|
|Question mark|By clicking, a popup will be displayed for giving more information about the score calculation (more details bellow)|

<img width="703" alt="explain-detail-product" src="https://user-images.githubusercontent.com/98949123/153388237-c0694c32-1c9c-4ac5-b978-c643b1fe3298.PNG">

| Block    | Description |
|:-------------|:------|
|Product information|Product name, SKU, price and stock status|
|Matches|Field : Field indexed <br/> Term : searched <br/> Weight : Weight of the field <br/> Score : Score of the field <br/> ____________________ <br/> **Field matches total** : sum of all the field score <br/> **Boost** : value of the boost. Score of the product is multiplied by this value <br/> **Total** : Field matches total * boost value|

<img width="695" alt="explain-field-explanation" src="https://user-images.githubusercontent.com/98949123/153420502-44fbf2bc-aee8-4b77-a859-53e26a39a82e.png">

This table gives explanation about how fields are working.

<img width="684" alt="explain-indexed-content" src="https://user-images.githubusercontent.com/98949123/153421509-9492b62e-7d04-49d0-bece-47d07cf16ce5.png">

This table gives detail about how product content is indexed.
