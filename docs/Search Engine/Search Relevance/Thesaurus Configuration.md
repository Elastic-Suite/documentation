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

<img width="620" alt="general-configuration-thesaurus" src="https://user-images.githubusercontent.com/98949123/152954833-fb7b00b8-9158-438f-9097-9bfed58d6949.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Max Allowed Rewrites|2  |How many rewrites authorized on a search. For example : 1. Only one rewrites according to a thesaurus will be authorized in a search query|

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
