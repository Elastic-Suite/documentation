---
layout: default
title: Indices Settings
has_children: false
parent: Base Settings
grand_parent: Settings
---

<img width="478" alt="indices-settings" src="https://user-images.githubusercontent.com/98949123/155967887-09927aa3-f83b-455d-9b85-21981edb8dfa.PNG">

Parameter                    | Default value           | Description
-----------------------------|-------------------------|------------
Indices alias name           |                magento2 | The default alias put by the module on Magento's related indices. <br/><br/> An alias per store and entity type will be generated with the following format : [indices_alias_name]\_[store_code]\_[entity_type]. <br/><br/> E.g. : magento2_default_catalog_product.
Indices name pattern         | {{YYYYMMdd}}_{{HHmmss}} | The horodated pattern used when creating new index.<br/><br/> An index name per store and entity type, based on the horodated pattern, will be generated with the following format : [indices_alias_name]\_[store_code]\_[entity_type]\_[horodated_pattern]. <br/><br/> The E.g. : magento2_default_catalog_product_20160304_094708.
Number of shards per index   |                       1 | The number of shards per index. A shard is a single Lucene instance and they are distributed by ElasticSearch amongst all nodes in the cluster. <br/><br/> You can see the Shard definition on the [ElasticSearch glossary](https://www.elastic.co/guide/en/elasticsearch/reference/current/glossary.html#glossary-shard) for more informations.
Number of replicas per index |                       0 | The number of replicas shards per index. Main purposes of replica shards is for failover : if the node holding a primary shard dies, a replica is promoted to the role of primary. <br/><br/> You can read more about Replica Shards on the [ElasticSearch documentation](https://www.elastic.co/guide/en/elasticsearch/guide/current/replica-shards.html).
