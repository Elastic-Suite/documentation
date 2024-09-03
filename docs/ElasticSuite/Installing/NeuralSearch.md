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

## Pre-Requisites : OpenSearch cluster configuration & sizing

The knn and neural search operations are costly to proceed and we recommend (as per [the good practices](https://opensearch.org/docs/latest/ml-commons-plugin/cluster-settings/)) to dedicate one ore more nodes of your Opensearch cluster to the ML tasks.

To do so, you must assign the "ml" role to one of your nodes by adding this line in the /etc/opensearch/opensearch.yml configuration file : 

```
node.roles: [ ml ]
```

Please take into account that, by default, Opensearch will only accept to run the "ml" operations on "ml" nodes, and will fail if no node has been tagged with the "ml" role.

If you want to supersede this configuration (because you're running a dev/testing environment), you can check the next chapter.

As said previously, the "ml" operations are costly to proceed, both at indexing time, and at querying time. You need to anticipate this by sizing your OpenSearch server accurately, especially by allocating a correct amount of RAM to the "ml" nodes. This is a process our support team can accompany you with.

## Optional : Single-node configuration

If you plan to run the Neural Search feature on a single-node cluster (which is **not recommended**, but migh be useful for development/testing), you'll have to adapt the configuration of your Opensearch server with the following configuration (on the /etc/opensearch/opensearch.yml) : 

```
plugins.ml_commons.only_run_on_ml_node: false
```
