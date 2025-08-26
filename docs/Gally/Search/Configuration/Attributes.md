---
layout: default
title: Attributes
has_children: false
parent: Configuration
grand_parent: Search
---

It can be accessed under SEARCH > Configuration > Attributes. This entry allows user to configure searchable attributes.

At the top of the page, a filter bar is available. User can filter based on attribute code and label. User can also filter on attribute configuration (search weight and used in spellcheck).

The grid with all attributes configured as searchable in Settings > Searchable and filterable attributes are displayed here :

<img width="1577" height="620" alt="image" src="https://github.com/user-attachments/assets/bd6495b7-044d-40cd-b01e-0d2bbee528ce" />

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Attribute code||Attribute code used to identified the attribute|
|Attribute label||Attribute label used to named the attribute|
|Search weight|1|The weight of this attribute in search. Meaning : user can modulate the weight of an attribute in a search. <br/>Eg: Attribute name --> Weight = 8 and Attribute description --> Weight = 3. It means that products that carry the searched request in their name will be placed first then products that carry the searched request in description|
|Used in spellcheck|No|When set to “Yes”, the engine will compute spellchecking on this attribute values. If set to no, engine will only compute exact search on this attribute value.|
|Used for span queries|No|When set to “Yes”, this field is allowed to be used in advanced proximity or word order searches. If set to no, engine will only apply simple searches on this field.|
|Analyzer|Standard|There is 3 possible values. Standard, Reference and Standard_edge_ngram. <p>- Standard : uses the default analyzer, which segments text into words while excluding special characters and stopwords. This analyzer is versatile and suitable for most cases.</p><p>- Reference: This analyzer is used for fields that must match specific values ​​exactly, such as product references or item codes.</p><p>- Standard Edge Ngram : This analyzer splits text into substrings (ngrams) from the beginning of words. For example, the word "dresses" will be split into "d", "dr", "dre", "dres", etc. This allows results to be suggested from the first letters entered, ideal for auto-complete searches.</p>|

Attributes can be selected in the user grid. Once it's the case, an action bar appears allowing to mass edit attributes and change their configuration : 

<img width="1604" height="697" alt="image" src="https://github.com/user-attachments/assets/429a8b7c-09a1-483f-b6f2-c8b3a133824c" />

Every configuration (Search weight, Used in spellcheck, Used for span queries and Analyzer) can be managed in the action bar.
