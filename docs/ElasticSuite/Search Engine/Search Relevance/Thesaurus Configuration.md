---
layout: default
title: Thesaurus Configuration
has_children: false
parent: Search Relevance
grand_parent: Search Engine
nav_order: 3
---
It can be accessed under the Smile ElasticSuite menu, via the Search Relevance > Thesaurus configuration entry.

You can manage several parameters here.

## General Configuration

<img width="979" height="553" alt="image" src="https://github.com/user-attachments/assets/ef080d0b-bcc6-47b2-8d5c-bf7996faf40a" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Max Allowed Rewrites | 2 | Defines the maximum number of thesaurus rules applied simultaneously to a single search query to generate alternative queries. This limit applies first to synonym rules, and then to expansion rules.<br><br>*Example:* If set to `2`, each alternative query is built using at most 2 synonym rules and 2 expansion rules. <br><br>⚠️ *Warning:* Be cautious when increasing this value. If you have many rules with long lists of alternative terms, they could combine exponentially and significantly impact search performance. |
| Max Alternative Search Queries | 50 | Defines the absolute maximum number of alternative, rewritten search queries the engine will generate and process for a single user search. <br><br>If you experience "max boolean clauses" errors from your Elasticsearch/OpenSearch cluster, or performance degradation due to a massive volume of active thesaurus rules (or from having stemming enabled for the thesaurus), you should lower this value. *(Note: In older versions, this defaulted to `0`, meaning no limitation).* |

## Synonyms configuration

This panel contains base fulltext configuration settings.

<img width="620" alt="synonyms-configuration" src="https://user-images.githubusercontent.com/98949123/152955763-2a64273a-a06c-43c7-87fa-1abf07a2b498.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Enable synonyms search|Yes|If the engine should generate "extended queries" based on the list of synonyms.|
|Synonyms weight divider|10|The way to calculate documents scores. A value of 10 means the score of documents matched by synonyms will be divided by 10.|

## Query Expansions Configuration

<img width="630" alt="query-expansions-configuration" src="https://user-images.githubusercontent.com/98949123/152955860-a9bae8bb-97ff-468b-b3cf-c248f5b454af.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Enable search expansions|Yes|If the engine should generate "extended queries" baseds on the list of expansion terms.|
|Concepts weight divider|10|The way to calculate documents scores. A value of 10 means the score of documents matched by expansions will be divided by 10.|
