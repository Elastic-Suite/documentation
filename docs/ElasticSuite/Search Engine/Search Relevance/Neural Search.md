---
layout: default
title: Neural Search
has_children: false
parent: Search Relevance
grand_parent: Search Engine
nav_order: 4
---

Neural Search leverages vector-based search technology to understand the underlying semantic meaning of a user's query, rather than relying solely on exact keyword matching. By integrating vector search, the engine can significantly improve product discovery and recall, especially for complex queries, typos, or searches that would otherwise lead to a dead end.

## General

<img width="966" height="457" alt="Image" src="https://github.com/user-attachments/assets/06594834-6093-453a-9d3b-ed1e93d790be" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Use vector search as a fallback where there is no search result. | Yes | When set to **Yes**, if a user's search yields a zero-results page using the standard text-based search, the engine will automatically fall back to a vector search query to find semantically relevant products. |
| Use vector search in spellcheck. | Yes | When set to **Yes**, the engine enhances fuzzy (spellchecked) queries by injecting an additional query component based on vector search, improving the accuracy and relevance of typo corrections. |
| Use vector search in exact matches. | No | When set to **Yes**, an additional vector search component is added directly to exact match queries. This can help surface semantically related items alongside the exact keyword matches. |

## Relevance

<img width="978" height="437" alt="Image" src="https://github.com/user-attachments/assets/a7939cb4-112b-4c7a-98ca-c3f482575c75" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| K Value | 100 | Defines the 'k' value used in the k-NN (k-Nearest Neighbors) algorithm. This integer (which must be greater than `0`) determines exactly how many neighboring data points the engine will evaluate to classify and retrieve relevant products for a specific search query. |
| Use Min Score | Yes | Enables or disables the minimum score threshold mechanism specifically for your neural/vector search results. |
| Min Score Value | *(Empty)* | Defines the absolute minimum relevance score a document must achieve to be included in the vector search results. Accepts an integer greater than `0`. Any products with a relevance score lower than this defined value will be completely excluded from the search results. |


