---
layout: default
title: Indices Mapping
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 4
---

<img width="478" alt="indices-mapping" src="https://user-images.githubusercontent.com/98949123/155969671-bf1f51d0-bfc6-459e-8b07-c059e45be53f.PNG">

This configuration allow to associate index names (in Elasticsearch) with indexer keys (in Magento).

This is used to determine "rebuilding" indices and indices managed by Elasticsuite in the Indices page.

| Parameter    | Description                                                                                        |
|:-------------|:---------------------------------------------------------------------------------------------------|
|Indexer key| The indexer key, as defined by Magento indexer.xml files. Eg : "elasticsuite_categories_fulltext"  |
|Index name| The index name, as defined by Elasticsuite elasticsuite_indices.xml files. Eg : "catalog_category" |
|Action| Delete : delete the index association                                                              |
|Button "Add mapping of index"| Add a new line for a new association                                                               |
