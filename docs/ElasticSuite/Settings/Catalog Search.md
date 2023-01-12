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
