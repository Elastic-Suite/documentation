---
layout: default
title: Cascade Search suggestions
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 24
---

Located under Store > Configuration > ElasticSuite > Cascade Search suggestions

The Cascade Search module leverages your behavioral data to suggest finer, more specific popular search terms to your users. This allows them to easily navigate from a very broad, vague search query to the exact item type they might be looking for. 

## General

<img width="1152" height="495" alt="image" src="https://github.com/user-attachments/assets/2994bed1-f2a8-46d1-802a-2498c271b46b" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Supported locales | [List of available locales]* | Acts as an additional safeguard. Even if the Cascade Search feature is enabled for a given store view, it will only be active if that store's locale is explicitly selected in this list. This prevents you from accidentally enabling the feature on complex languages that haven't been properly tested or officially supported yet. <br><br>*\*Note: While this feature can work with many languages, it is optimized out-of-the-box for common Romance languages (such as French, Spanish, Italian, Portuguese) and English*. |
| Enabled | Yes | Enables or disables the Cascade Search suggestions feature for your store. |

## Frontend

<img width="1155" height="854" alt="image" src="https://github.com/user-attachments/assets/1fc2cd9e-e5a7-44a7-8f22-cbac13a6a8e3" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Replace Search Recommendations | No | If set to **Yes** on a Luma or Hÿva-based theme, the module will inject its suggestions directly into the native Magento Advanced Search Recommendations block, rather than displaying its own standalone block with product images. |
| Max Size | 5 | Defines the maximum number of search suggestions that will be displayed to the user at one time. |
| Sort Suggestions by | Popularity (recommended) | Determines the default sort order for the suggested terms. You can choose to rank them either by their overall **Popularity** (descending) or by the **Number of matching products** (descending). |
| Hide existing query | Yes | Controls whether the user's original search term is repeated inside the newly suggested terms.<br><br>• **Yes:** Hides the original term to keep suggestions concise. *(Example: If a user searches for "top", suggestions will simply read: "blouse", "tank", "yoga".)*<br>• **No:** Retains the original term. *(Example: "top blouse", "top tank", "yoga top".)* |
| Display when filters are applied | No | *(Applicable to Luma-based themes).* When enabled, the cascade suggestions block remains visible even after a user applies layered navigation filters on the search results page. <br><br>⚠️ *Note: Clicking on any of the suggestions will automatically reset all currently applied filters.* |
| Display on all results pages | No | Determines visibility across paginated results.<br><br>• **No:** Suggestions will strictly appear only on the first page of the search results.<br>• **Yes:** Suggestions will be displayed continuously, regardless of the current results page. |
| Enable independent cache | Yes | When enabled, the suggestions block utilizes its own specific cache mechanism (in addition to the standard Full Page Cache) which is shared among sufficiently similar search terms to improve performance. |
| Cache TTL | 3600 | Defines the Time-To-Live (TTL) in seconds for the independent suggestions cache. The default value is `3600` (1 hour). |

## Indexing

<img width="1165" height="488" alt="image" src="https://github.com/user-attachments/assets/dd421eaf-6988-47bf-b2c3-3b9824375389" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Use all search events | Yes | If set to **Yes**, the module will pull existing search events from all available historical behavioral data to comprehensively build search suggestions. <br><br>⚠️ *Note: This process can take a significantly long time. Regardless of your choice here, the corresponding "Elasticsuite Search Events" indexer will only rebuild the data if it is explicitly flagged as invalid (showing a "Reindexing Required" status label).* |
| Maximum depth to collect suggestions for | 10 | Defines the maximum "depth" (number of significant terms) in a search query that the engine will process. For example, the query "blue dress" has a depth of two terms. The query "the blue dress" also has a depth of two, because words like "the" are considered non-significant stop words. |
| Maximum searches to collect per depth | 5000 | Defines the maximum number of unique search queries the system will collect for each specific depth/term count. The absolute maximum allowed value is `10000`. |
| Minimum search events | 5 | Defines the minimum number of times a specific search query must have been performed by users before it can be considered a valid potential suggestion. |
