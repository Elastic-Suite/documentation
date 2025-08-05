---
layout: default
title: Results
has_children: false
parent: Analyze
nav_order: 1
---

It can be accessed under ANALYZE menu : ANALYZE > Results. This entry allows user to access to the explain results feature.
The explain feature allows to test a query and understand how document' score is calculated.

First user needs to select the scope where he/she wants to study the query's results : 
<img width="569" height="236" alt="image" src="https://github.com/user-attachments/assets/a74e9f4c-f0c4-4b3f-b0f6-4053ccf04d15" />

Once it's done, user will select the type of query in the dropdown "Request type" :

<img width="550" height="125" alt="image" src="https://github.com/user-attachments/assets/ef86ede5-e9b3-43f8-b0eb-bbc8c5b9ccdf" />


## Explain search queries

When Request type = Search results is selected, then next step is to give the term that need to be explained : 

<img width="1109" height="161" alt="image" src="https://github.com/user-attachments/assets/dcfd165d-ecdd-4ae6-9f25-f6c8a4a33566" />

### Product grid

Then user can press "Explain", results for this queries will appear exactly as displayed in the frontoffice. Following details are available : 

|Parameter   | Description|
|:-------------|:------|
|Code|Code of the product|
|Image|Image of the product|
|Name|Name of the product|
|Score|Final score of the product + Boost multiplier applied on the initial score of the product + Number of boosts applied on this product for this query|
|Stock|Stock status of the product|
|Price|Price of the product|

### Product detailed popup

User can click on a product to open a popup where details are displayed : 

<img width="986" height="769" alt="image" src="https://github.com/user-attachments/assets/20fd9e70-bb63-4655-92fd-43d49b9dc78b" />

| Parameter    | Description |
|:-------------|:------|
|Product information|Product name, code, price and stock status|
|Matches|Field : Field indexed <br/> Term : searched <br/> Weight : Weight of the field <br/> Score : Score of the field <br/> ____________________ <br/> **Total score** : sum of all the field score <br/> **Score after application of the boosts** : Field matches total * boost value|

The second section of the popup gives detail about how product content is indexed : 

<img width="966" height="748" alt="image" src="https://github.com/user-attachments/assets/8ff6f9fe-1d8b-4436-94a8-89c3ebc1ac7a" />

| Parameter    | Description |
|:-------------|:------|
|Field|Name of the field|
|Source|Content of the field|

## Explain category queries

When Request type = Category listing is selected, then next step is to select the category that need to be explained : 

<img width="873" height="445" alt="image" src="https://github.com/user-attachments/assets/3fff0f0b-2323-4bdf-aa9b-d7446bb8af19" />

Then user can press "Explain", products of this category will appear exactly as displayed in the frontoffice. 
Product grid and popup content are the same then below, except all information about score calculation before boost application is not relevant for categories.

