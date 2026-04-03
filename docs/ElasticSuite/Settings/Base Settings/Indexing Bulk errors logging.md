---
layout: default
title: Indexing / Bulk errors logging
has_children: false
parent: Base Settings
grand_parent: Settings
nav_order: 3
---

Located under Store > Configuration > ElasticSuite > Base Settings > Indexing / Bulk Errors logging

## Indexing / Bulk Errors Logging

<img width="1195" height="323" alt="image" src="https://github.com/user-attachments/assets/a34d181c-e74e-4da8-ab2d-aacd4685251a" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enable logging of bulk indexing errors | Yes | **Yes:** Errors that occur during bulk indexing operations (such as product or category indexing) are saved to the database [1]. You can review these errors directly in the Magento admin under *Elasticsuite > System > Indexing / Bulk Errors* [1]. This is highly useful for troubleshooting documents that are rejected or fail to index due to incorrectly configured product attributes or faulty custom data sources [1]. <br><br>⚠️ *Note: For Magento entity-based indices (like products and categories), all existing logged errors are automatically purged from the database whenever a full reindex occurs* [2]. |
