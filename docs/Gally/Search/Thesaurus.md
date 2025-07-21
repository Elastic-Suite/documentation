---
layout: default
title: Thesaurus
has_children: false
parent: Search
grand_parent: Gally
nav_order: 3
---

It can be accessed under SEARCH menu : SEARCH > Thesaurus.
This entry allows user to manage thesaurus on search.

## Thesaurus grid

At the top of the page, a filter bar is available. User can filter based on every column of the grid (name, thesaurus type, terms, enable, context).

The grid lists all the thessaurus created in Gally :

<img width="1605" height="751" alt="image" src="https://github.com/user-attachments/assets/6d452fed-8d3e-496e-99a7-6d6ce043bce7" />

|Parameter   | Description|
|:-------------|:------|
|Name|Name of the Thesaurus|
|Thesaurus type|The thesaurus is a synonym or an expansion|
|Terms|What terms are used in the thesaurus. For synonyms, terms are listed with a coma separator. For expansions, the reference terms is displayed, then an arrow, and then extended terms separated by comas.|
|Enable|The thesaurus is active or not|
|Context|Scope of the thesaurus. It can be applied to a localized catalog or to a local.|
|Actions|Button "Edit" allowing to access the edition page of the thesaurus.|

A new thesaurus can be created thanks to the button "Create Thesaurus" at the top right of the page.

## Thesaurus edition page

### Common configuration

<img width="358" height="499" alt="image" src="https://github.com/user-attachments/assets/d262c50f-ecca-40fd-a895-82ecc927faef" />

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Name||Name given to the thesaurus|
|Enable|True|Thesaurus is enabled or not|
|Context type||Localized catalog or Locale <p>Localized catalog : The thesaurus will be applied only on the specific selected localized catalog</p> <p>Locale</p>The thesaurus will be applied to all localized catalogs that use the selected local.|
|Localized catalog or Local (according to previous selection)||Selection of the loalized catalog(s) on which the thesaurus will be applied. Thesaurus can be applied to one or several localized catalog(s) or Selection of the locale on which the thesaurus will be applied. Thesaurus can be applied to one or several locale.|
|Thesaurus type||Selection of the thesaurus type : Synonym or Expansion|

### Synonyms

If Thesaurus type = synonym, then following field will be displayed : 

<img width="477" height="295" alt="image" src="https://github.com/user-attachments/assets/c1b56a62-8e5c-48ea-8a95-52b70c76f7be" />

Terms that are synonyms must be listed in the same texfield. Press enter when your term is completed and start typing the next term. In the example above, "phone" and "smartphone" are synonyms, it means that when front user will type "phone" in a search, results for "phone" and "smartphone" will come out and vice versa.
Terms listed in different textfield are not synonym to eachother.

### Expansions

If Thesaurus type = expansion, then following field will be displayed : 

<img width="1039" height="456" alt="image" src="https://github.com/user-attachments/assets/64da070f-6fc2-40a1-b1fc-9b96dcb8be3d" />

Expansion will allow to add separated lists of words that are expansions of a reference terms.
In the example above, "blazer" is the reference term and is extended to "jackets" and "tanks", it means that when front user will type "blazer" in a search, results for "blazer", "jackets" and "tanks" will come out, but if front user search for "jackets", engine will only returns results for "jackets", not for "blazer" or "tanks".




