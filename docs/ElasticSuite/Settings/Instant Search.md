---
layout: default
title: Instant Search
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 21
---

<img width="1162" height="684" alt="image" src="https://github.com/user-attachments/assets/40a22a20-950a-460a-864c-e64fa740dde5" />

## Product Autocomplete

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Allow fuzzy queries | Yes | By default, the Instant Search product autocomplete relies on the popular terms data provider and performs strict exact matching. While this ensures fast response times and prevents "results jittering" (results rapidly oscillating between exact and fuzzy matches as the user types), it can lead to zero results for mistyped words. <br><br>Setting this to **Yes** allows the autocomplete engine to fall back to a fuzzy query when no exact popular term match is found. |
| Enable full page cache for suggest | Yes | When enabled, appropriate HTTP cache headers are added to the autocomplete suggestion responses. This allows these queries to be efficiently cached by Full Page Cache (FPC) systems like Varnish, significantly reducing server load. |
| Full page cache TTL | 3600 | Defines the Time-To-Live (TTL) in seconds for the autocomplete suggestion cache. |
| Use Native JS Autocomplete (Fallback Mode) | Yes | **Yes:** Switches the autocomplete from the default React-based component to a vanilla native JavaScript (Web Components) implementation [1]. <br><br>⚠️ *Note: This is a fallback mode designed strictly for instances where you experience JavaScript conflicts, performance issues, or build/delivery problems with the React implementation. It provides core functionality but offers reduced features and styling options. To benefit from this, ensure your `smile/magento2-react` composer package is updated to at least version 16.12.5* [2]. |
| Disable React bundle loading (Fallback Mode) | Yes | *(Only visible/applicable if the Native JS Autocomplete setting above is set to Yes).*<br><br>• **Yes:** Completely disables Magento's attempt to load the React script bundle, preventing potential 404 errors. Use this only if you enabled the fallback mode due to React build difficulties and are absolutely certain no other modules rely on `smile/magento2-react` [1].<br>• **No:** The React JavaScript bundle will still load on all pages, even though the Native JS Autocomplete is being used. |

