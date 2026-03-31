---
layout: default
title: Explain search and navigation results
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 23
---

<img width="1003" height="208" alt="image" src="https://github.com/user-attachments/assets/779445d2-13a7-407d-83fe-2a0e5dc9bd74" />

## Matches highlights

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| See matches in collector fields | No | When enabled, match highlighting is extended to default collector fields (such as `search` and `spelling`). This allows you to see highlighted matches for searchable attributes that have a search weight of 1. <br><br>⚡ **Warning:** Changing this setting requires a full catalog reindex. <br><br>🚨 **Caution:** Enabling this feature could potentially double the disk space usage of your Elasticsearch/OpenSearch indices. If you have a large catalog or multiple stores, it is highly recommended to test this in a staging environment first to evaluate the storage and performance impact on your infrastructure before deploying to production. |




