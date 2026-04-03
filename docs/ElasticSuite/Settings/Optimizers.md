---
layout: default
title: Optimizers
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 13
---

Located under Store > Configuration > ElasticSuite > Optimizers

These advanced configuration settings give you deeper control over how ElasticSuite calculates and applies relevance boosts, directly leveraging Elasticsearch's native function score queries.

<img width="1195" height="658" alt="image" src="https://github.com/user-attachments/assets/e09d2603-4e00-4d2c-9ca0-83fce54418b9" />


## Score Mode Configuration

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Score Mode | Multiply | Specifies the `score_mode` used for function score queries. This determines how individual computed scores within the optimizer are combined together. *Tip: For advanced tuning, refer to the official Elasticsearch documentation on Function Score query configuration.* |

## Boost Mode Configuration

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Boost Mode | Multiply | Specifies the `boost_mode` used for function score queries. This dictates exactly how the newly calculated boosted score of each product will be combined with its original base search score. *Tip: For advanced tuning, refer to the official Elasticsearch documentation on Function Score query configuration.* |


