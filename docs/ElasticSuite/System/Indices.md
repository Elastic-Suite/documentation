---
layout: default
title: Indices
has_children: false
parent: System
grand_parent: ElasticSuite
nav_order: 1
---
## System Indices Dashboard

<img width="1780" height="782" alt="indices-status" src="https://github.com/user-attachments/assets/d0190e5b-0e33-4423-b853-bbf6bdf15eb9" />

**Overview**
The Indices dashboard allows you to monitor the status and usage of your Elasticsearch/OpenSearch cluster directly from the Magento Back-Office. It provides a comprehensive grid listing all indices, their sizes, document counts, and routing configurations. From here, you can also easily access any index's specific mapping or settings to troubleshoot search relevance.

You can access this page by navigating to **Smile ElasticSuite > System > Indices**.

### Filtering and Management

At the top of the grid, you have several tools to refine the view and manage your cluster:
*   **Search/Filter:** You can easily filter the grid by searching for either the **Index Title** (exact name) or the **Index Alias**.
*   **Hide External Indices:** You can toggle a filter to hide external indices, allowing you to only display the indices specifically built and managed by ElasticSuite.
*   **Purge Ghost Indices:** A dedicated mass-action button is available at the top of the screen to safely remove all "Ghost" indices at once.

### Indices Grid Columns

| Parameter | Description |
|:----------|:------------|
| **Index Title** | The exact, unique name of the index within Elasticsearch/OpenSearch. |
| **Index Alias** | The alias assigned to the index. This depends on the content type of the indexed data (e.g., `magento2_default_catalog_product`). |
| **Number of documents** | The total number of documents currently stored in the index. |
| **Size** | The physical storage size of the index on your cluster. |
| **Primary Shards** | The number of primary shards configured for this specific index. |
| **Replicas** | The number of replica shards configured for this specific index. |
| **Index Status** | The current operational status of the index. Common statuses include:<br><br>• **Live:** The active index that is currently linked to the alias and serving queries.<br>• **Ghost:** An orphaned index (usually from a failed reindex) that is no longer linked to an alias and is drawing useless resources.<br>• **Closed:** An index that has been explicitly closed in the cluster.<br>• **Unknown:** Displayed if retrieving the index statistics fails. |
| **Action** | Available actions for the specific index. You can click to view its **Mapping** or **Settings**. If the index is flagged as a "Ghost", a **Delete** action will also be available here. |

***

### 💡 Managing Ghost Indices

"Ghost" indices are typically created during a full re-indexing process that failed to complete (due to timeout or errors), leaving behind an orphaned index that is not used but still consumes cluster memory and storage. 

By default, an index is identified as a "Ghost" if it matches the Elasticsuite naming pattern, has no alias, and was created **more than 2 days ago**. 

**Tweaking Ghost Detection:**
If you have fast-indexing catalogs and want to clean up failures quicker, you can adjust the 2-day threshold via **Stores > Configuration > Elasticsuite > Base Settings > Indices Settings > Time for an index to be considered Ghost (in seconds)**.

**Purging Ghosts:**
Once flagged as a Ghost, you can remove them individually via the **Action** column in the grid, or clear all of them simultaneously using the **Remove all ghost indices** button. Alternatively, developers can clear them from the server using the Magento CLI command:
`php bin/magento elasticsuite:indices:purgeghosts`
