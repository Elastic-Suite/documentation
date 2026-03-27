---
layout: default
title: Catalog Search
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 6
---

<img width="506" alt="catalog-search-configuration" src="https://user-images.githubusercontent.com/98949123/155971312-a6bf21f8-9bad-4a38-ad6f-80dc00751b67.PNG">

| Parameter    |Default value| Description |
|:-------------|:------|:------|
|Category Name Weight|1|The search weight of category names when used in fulltext search.|
|Redirect to product page if only one result|Yes|If set to yes, the user will be redirected to the product page, if there is only one product matching a given search query|
|Use URL Rewrites for Category Filter in category navigation|Yes|If set to yes, users are redirected (and all filters are reset) to the chosen category page when they use the category filter in layered navigation.|
|Expanded facets|3|Number of facets to display expanded by default.|
|Enable adaptive slider|No|If enabled, when necessary to support the presence of outlier values in the navigation context (for instance, a very high price amidst a majority of low prices), the price slider behavior changes so that the middle of the slider range corresponds to the median price instead of the price at the middle of the range.|
| Enable indexing child product SKU in dedicated subfield | No | Controls how SKUs of composite products (e.g., configurable or bundle products) are indexed. <br><br>**Yes:** Child product SKUs are indexed in a completely separate field, ensuring the main `sku` field strictly contains the parent's SKU. This prevents child SKUs from being merged into the parent's data, which is highly recommended to avoid confusion when building SKU-based widgets.<br>**No:** Child SKUs are merged with the parent SKU. |
| Enable indexing discount on child products | No | Enable this setting if your catalog utilizes configurable products where child variants have different prices and independent discount rules. This ensures the search engine accurately indexes and reflects these specific child-level discounts. |
| Ignore manual positions of out of stock products | No | If your store is configured to display out-of-stock products on the frontend, setting this to **Yes** ensures that any product manually pinned to a specific position (either in a category or for a specific search query) will automatically lose its pinned position and stop being pushed to the top when it goes out of stock. |
| Force zero results for disabled categories | Yes | **Yes:** Ensures that if a Virtual Category uses a disabled category as its root, or specifically references a disabled category within its attribute rules, it will strictly return an empty result. <br><br>⚠️ *Warning: Modifying this setting will automatically clear your entire category query cache.* |
| Text scoring algorithm for collector fields | Default | Defines the relevance scoring model (or "similarity") applied to special Elasticsuite collector fields (like the `search` and `spelling` fields, which aggregate data from multiple searchable attributes). <br><br>• **Default:** Applies the standard algorithm that rewards term frequency (e.g., a product containing the word "dress" 3 times in its data will score higher than a product containing it only once). <br>• **Boolean:** Applies a strict boolean model where multiple occurrences do not increase the score. A product with the word "dress" 3 times will receive the exact same score as a product with "dress" only once. |
