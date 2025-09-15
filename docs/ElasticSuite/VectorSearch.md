---
layout: default
title: Neural Search
has_children: true
parent: ElasticSuite
nav_order: 8
---

## Technical Prerequisites

Before going further, ensure your technical team completed the [pre-requisites](https://elastic-suite.github.io/documentation/docs/ElasticSuite/Installing/NeuralSearch.html).

⚠️ For now, the vector search has only been tested with french and english languages. It might not work properly with other languages (english, spanish, german etc...), and might even need to use language-specific models for some languages, rather than relying on the pre-trained model shipped with Opensearch.

## Installing the module

The module responsible for neural search is `smile/module-elasticsuite-neural-search` and this module is not part of the standard Premium package. You'll need to install it manually prior going further.

## Enabling neural search feature

You can head to **Stores > Configuration > ElasticSuite > Neural Search**

![Sélection_1857](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1857.png)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Enable Neural Search|No|	Set this to "Yes" to enable the neural search feature|
|Model Type|Pre-trained|⚠️ For now, only Pre-Trained models are supported|
|Pretrained Model||A list of pre-trained models available in Opensearch. The default one is recommended.|
|Compute embeddings from a specific store|No|When using a LLM capable of dealing with multiple languages, you can choose to compute the embeddings from a particular store view and use them for all the other languages. That's particularly valuable if you have a store view which is greatly contribued. It can then be used to leverage the data of the other stores.|

## Enabling attributes for Neural Search

Enable the "Use for Vector Search" option on the attributes you plan to use with Neural Search. Refer to the [attribute configuration page](https://elastic-suite.github.io/documentation/docs/ElasticSuite/Filters%20and%20attributes/Global%20configuration.html) to do so.

## Configuring neural search feature

You can head to **ElasticSuite > Search Relevance > Neural Search**

![Sélection_1858](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1858.png)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Use vector search as a fallback when there is no search result.|No|	We recommend to set this to "Yes" to use the neural search as a fallback |
|Use vector search in spellchecked|No|When set to yes, the neural search will be used as part of the spellchecking. We **don't recommend** to use this.|
|Use vector search in exact matches |No|When set to yes, the neural search will be used as part of the exact matching. We **really don't recommend** to use this.|
|K Value|100|We recommend to let this value to the default one.|
|Use Min Score|No|We don't recommend enabling this |
