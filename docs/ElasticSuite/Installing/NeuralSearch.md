---
layout: default
title: Installing and configuring Neural Search module
has_children: false
parent: Installing
grand_parent: ElasticSuite
nav_order: 3
---

## Pre-Requisites : OpenSearch

⚠️ The Neural Search feature is only compatible with OpenSearch >= 2.13. <br/>
⚠️ The Neural Search feature is **NOT** compatible with Elasticsearch.

## Pre-Requisites : OpenSearch configuration

The following plugins must be installed on your Opensearch instance : 

- opensearch-neural-search
- opensearch-ml
- opensearch-knn

## Optional : Single-node configuration

If you plan to run the Neural Search feature on a single-node cluster (which is **not recommended**, but migh be useful for development/testing), you'll have to adapt the configuration of your Opensearch server with the following configuration (on the /etc/opensearch/opensearch.yml) : 

```
plugins.ml_commons.only_run_on_ml_node: false
```
