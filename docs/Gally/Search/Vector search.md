---
layout: default
title: Vector search
has_children: false
parent: Search
grand_parent: Gally
nav_order: 4
---

It can be accessed under SEARCH menu : SEARCH > Vector search.
This entry allows user to configure vector search.

## Attribute configuration

All attributes available in Gally are displayed in the vector search grid.

<img width="1417" height="703" alt="image" src="https://github.com/user-attachments/assets/5b29d166-e68b-4314-b1f9-59a19365ed99" />


|Parameter   | Description|
|:-------------|:------|
|Attribute label|Label of the attribute|
|Vectorisable|Is the attribute used in the vector search. If switch to yes, a prompt can be written on this attribute|
|Position|Determines the order in the final prompt|
|Prompt|Defines how the attribute will be included in the sentence used for search vectorization|

<img width="1262" height="303" alt="image" src="https://github.com/user-attachments/assets/140acb90-efa5-4b21-91ce-9cfaa9e6dfea" />

In the example above, The "Product Name" attribute is set to position 1 with the prompt: "The product name is %s" and the "Color" attribute is set to position 2 with the prompt: "and its color is %s"
These are combined into a single sentence based on their positions, resulting in the final prompt used for vector search: "The product name is %s and its color is %s"
This sentence will be filled with the actual attribute values for each product. The %s placeholders are replaced with the respective attribute values during search indexing.
