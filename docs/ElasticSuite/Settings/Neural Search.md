---
layout: default
title: Neural Search
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 10
---

Neural Search enhances your catalog search by using advanced machine learning models (Large Language Models) to understand the semantic meaning and context of a user's query, rather than just relying on exact keyword matches. The settings below allow you to configure how the engine generates and manages the vector embeddings required for this semantic search capability.

## General Configuration

<img width="963" height="741" alt="Image" src="https://github.com/user-attachments/assets/2d9c7e05-5c61-4d64-b2fb-fae4b4b0fe1f" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enable Neural Search | Yes | Controls whether the Neural Search capabilities are active for your store. |
| Model Type | Pre-Trained | Defines the hosting location and type of the language model used to generate your catalog's embeddings. Available options are **Pre-Trained**, **Local**, or **Remote**. |
| Pretrained Model | huggingface/sentence-transformers/all-distilroberta-v1 | Specifies the exact pre-trained model used by the engine to compute vector embeddings. |
| Compute embeddings from a specific store | Yes | **Yes:** Allows you to compute embeddings from one primary store view and apply them across all other language store views. This is highly recommended if you are using a multi-lingual LLM and have one particular store view with exceptionally rich, high-quality content. It leverages your best data to power search across all stores.<br><br>**No:** Embeddings are computed independently for each individual store view. |
| Source Store for embeddings | Default Store View | *(Only applies if the setting above is set to Yes).* Select the specific store view to act as your primary data source for computing embeddings. You should select the store view that has the most comprehensive and highest-quality catalog data. |


