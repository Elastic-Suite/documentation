---
layout: default
title: Neural Search
has_children: true
parent: ElasticSuite
nav_order: 8
---

## Prerequisites

Before going further, ensure your technical team completed the [pre-requisites](https://elastic-suite.github.io/documentation/docs/ElasticSuite/Installing/NeuralSearch.html).

## Enabling vector search feature

You can head to **Stores > Configuration > ElasticSuite > Neural Search**

![Sélection_1857](https://github.com/user-attachments/assets/5493fa35-b2b7-447d-92a4-39dc4e354f36)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Enable Neural Search|No|	Set this to "Yes" to enable the neural search feature|
|Model Type|Pre-trained|⚠️ For now, only Pre-Trained models are supported|
|Pretrained Model||A list of pre-trained models available in Opensearch. The default one is recommended.|
|Compute embeddings from a specific store|No|When using a LLM capable of dealing with multiple languages, you can choose to compute the embeddings from a particular store view and use them for all the other languages. That's particularly valuable if you have a store view which is greatly contribued. It can then be used to leverage the data of the other stores.|
