---
layout: default
title: Attributes
has_children: false
parent: Configuration
---

It can be accessed under SEARCH > Configuration > Attributes. This entry allows user to configure searchable attributes.

At the top of the page, a filter bar is available. User can filter based on attribute code and label. User can also filter on attribute configuration (search weight and used in spellcheck).

The grid with all attributes configured as searchable in Settings > Searchable and filterable attributes are displayed here :

![image](https://user-images.githubusercontent.com/98949123/212873305-c3511b6d-b67f-4021-b075-840c0c8e0dad.png)

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Attribute code||Attribute code used to identified the attribute|
|Attribute label||Attribute label used to named the attribute|
|Search weight|1|The weight of this attribute in search. Meaning : user can modulate the weight of an attribute in a search. <br/>Eg: Attribute name --> Weight = 8 and Attribute description --> Weight = 3. It means that products that carry the searched request in their name will be placed first then products that carry the searched request in description|
|Used in spellcheck|Yes|When set to “Yes”, the engine will compute spellchecking on this attribute values. If set to no, engine will only compute exact search on this attribute value.|

Attributes can be selected in the user grid. Once it's the case, an action bar appears allowing to mass edit attributes and change their configuration : 

![image](https://user-images.githubusercontent.com/98949123/212878157-f0ee215a-bad1-4140-b4f5-36a23fba7941.png)

Every configuration (Search weight and Used in spellcheck) can be managed in the action bar.
