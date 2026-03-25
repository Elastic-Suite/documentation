---
layout: default
title: Autocomplete
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 5
---

## Max Size for section in the autocomplete box

<img width="506" alt="autocomplete-configuration" src="https://user-images.githubusercontent.com/98949123/155970323-b820d955-f670-4cc1-82f0-51dfd4e3d7e9.PNG">

| Parameter    |Default value| Description |
|:-------------|:------|:------|
|Popular Term Autocomplete - Max size|3|Maximum number of popular search terms to display in autocomplete results.|
|Product Autocomplete - Max size|5|Maximum number of products to display in autocomplete results.|
|Product Attributes Autocomplete - Max size|3|Maximum number of attributes values to display in autocomplete results.|
|Category Autocomplete - Max size|3|Maximum number of categories to display in autocomplete results.|

## Advanced Settings

To leverage user behavioral patterns and improve performance, Elasticsuite historically relies on Popular Search Terms to populate the autocomplete results. 

When a user types a partial word (e.g., `comp`), the engine first looks for suggested popular search terms (e.g., `computer`, `peach computer`, `computer for kids`). It then uses these expanded terms to find matching products and categories, discarding the original `comp` input. If no popular search terms are found, the engine falls back to searching for the exact raw input (`comp`), which may yield zero results unless you have configured specific attributes with the `standard_edge_ngram` analyzer.

The settings below give you fine-grained control over this "extension" mechanism, allowing you to disable it entirely, limit its scope, or force the engine to always include the user's raw input.

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Use suggested search terms to fetch results | Yes | **Yes (Legacy behavior):** The autocomplete will use expanded popular search terms to find products and categories. <br>**No:** Autocomplete results will be based strictly on the user's raw input exactly as typed (e.g., `comp`), without trying to expand it. |
| Always use the user raw input for suggestions | No | **No (Legacy behavior):** The raw typed input is only used as a fallback if no matching popular terms are found. <br>**Yes:** The raw input is *always* used alongside the suggested terms. For example, if a user types `comp` and `computer` is suggested, the engine will display products matching either `comp` OR `computer`. |
| Limit the amount of suggested search terms used | No | **No (Legacy behavior):** All retrieved popular search terms are used to fetch autocomplete results. <br>**Yes:** Unlocks the ability to restrict the number of suggested terms used (configured in the field below). |
| Maximum number of popular search terms to use | 5 | *(Only applies if the limitation above is set to Yes)*. Defines the maximum number of suggested search terms used to fetch product and category results. **Note:** Setting a value greater than the "Max Size" defined in your general "Popular Term Autocomplete" settings will have no effect. |
| No extension for actual popular search terms | No | **Yes:** Discards the extension mechanism if the user types a complete word that is already a known popular term. For example, if the user finishes typing `computer`, the engine will only search for `computer`, explicitly ignoring longer variations like `peach computer` or `computer for kids`. |








