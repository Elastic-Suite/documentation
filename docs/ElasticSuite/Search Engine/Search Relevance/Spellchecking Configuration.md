---
layout: default
title: Spellchecking Configuration
has_children: false
parent: Search Relevance
grand_parent: Search Engine
nav_order: 2
---

Spellchecking configuration is editable via a dedicated screen in the back-office.

It can be accessed by going to ELASTICSUITE > Search Engine > Search Relevance > Spellchecking Configuration.

## Search Fuzziness Configuration

Fuzzy queries uses a distance algorithm to calculate matching terms within a specified edit distance related to the current search terms.
This is used to **fix misspelled terms in queries**.

See also the official documentation here : [ElasticSearch Fuzzy Query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html#query-dsl-fuzzy-query)

<img width="978" height="668" alt="image" src="https://github.com/user-attachments/assets/ac690f23-c131-4a33-bb00-5f20c6a1765b" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enable Fuzziness | Yes | Enables or disables the fuzzy search mechanism globally. When enabled, the search engine will attempt to find matches for misspelled words. |
| Use default Minimum Should Match | Yes | When set to **Yes**, fuzzy queries will automatically inherit the global `Minimum Should Match` value defined under **Relevance Configuration > Fulltext Base Settings**. |
| Fuzziness Value | Automatic | Defines the maximum edit distance (the number of single-character changes needed to correct the word) allowed for a match.<br><br>• **Automatic (AUTO):** The engine dynamically determines the allowed edit distance based on the length of the search term (highly recommended).<br>• **1 or 2:** Forces a strict, hardcoded edit distance regardless of word length. |
| Fuzziness Prefix Length | 1 | Specifies the number of initial characters in a search term that *must* match exactly before fuzziness is applied. Accepts an integer `≥ 0`. A value of `1` means the first letter of the word must always be correct. |
| Max Expansion | 10 | Defines the absolute maximum number of alternative spelling variations the engine will generate and evaluate for a given misspelled word. Accepts an integer `≥ 0`. Keeping this number reasonably low helps maintain fast search performance. |

## Phonetic Search Configuration

**This requires the Phonetic Analysis Plugin : [Phonetic Analysis Plugin](https://github.com/elastic/elasticsearch/tree/master/plugins/analysis-phonetic)**

Phonetic search provides a variety of filters that convert tokens to their phonetic representation.

Phonetic search can be also improved with fuzziness. The parameters are used the same way as described above.

Official documentation related to phonetic search : [ElasticSearch Phonetic Search](https://www.elastic.co/guide/en/elasticsearch/plugins/master/analysis-phonetic.html)

![phonetic](https://user-images.githubusercontent.com/98949123/152805685-81c3c31d-2058-4817-89f1-a5feb3496cdd.PNG)

Parameter                             | Default value  | Description
--------------------------------------|----------------|------------
Enable phonetic search                |           Yes  | Set it to "Yes" to enable phonetic search.

## Term Vectors Configuration

<img width="979" height="581" alt="image" src="https://github.com/user-attachments/assets/e365c761-a224-4f0a-be84-2d6bf24814fa" />

These settings enhance how the search engine processes complex product references (like SKUs) and partial search terms during the pre-analysis step. By adjusting how term vectors are evaluated, you can significantly improve matching accuracy and recall when using specific analyzers, such as the reference or edge ngram analyzers.

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
|Use all tokens from term vectors | No |Instructs the engine to take into account all tokens from the term vectors response, instead of just one token per position. This is particularly useful for improving SKU and complex reference matching. |
|Use reference analyzer in term vectors | No |Includes the `reference` collector field (which contains all searchable fields using the `reference` analyzer) when performing the term vectors request. Highly recommended for accurate SKU/reference matching. |
|Use edge ngram analyzer in term vectors | No |Includes the `edge_ngram` collector field (which contains all searchable fields using an analyzer with an edge ngram component, like `standard_edge_ngram`) when performing the term vectors request. This is especially useful for triggering exact matching on partial search terms (e.g., matching "scre" exactly to "screen") that are only present in fields using an edge ngram component. |


