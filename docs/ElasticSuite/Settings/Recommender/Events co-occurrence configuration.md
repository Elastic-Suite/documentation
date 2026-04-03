---
layout: default
title: Events co-occurrence configuration
has_children: false
parent: Recommender - Premium
grand_parent: Settings
nav_order: 5
---

Located under Store > Configuration > ElasticSuite > Recommender > Events co-occurence configuration

<img width="1008" height="775" alt="image" src="https://github.com/user-attachments/assets/e449efe9-9933-4796-8983-59d87e36c398" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Minimum sessions count | 2 | Defines the minimum number of unique user sessions required for a related event (e.g., "products also viewed", "added to cart", or "bought") to be considered a valid co-occurrence. Lowering this threshold can be helpful to prevent a "cold start" on websites with limited tracking history. |
| Similarity attributes | [List of eligible attributes]* | Specifies which product attributes the recommendation engine uses to find items similar to the co-occurring products. <br><br>*\*Note: This multi-select list is dynamically populated with attributes that are searchable, provide text values to the search engine, and are configured as either sortable or filterable in layered navigation.* |
| Similarity Minimum Should Match | 30% | Defines the "Minimum Should Match" (MSM) threshold used for the full-text similarity request. If you select multiple similarity attributes and want to ensure all of them are taken into account, you should configure a value in the format of `N<30%` or `N<80%` (where `N` represents the total number of selected attributes), keeping in mind that each attribute might contribute at least one term. |
