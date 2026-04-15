---
layout: default
title: Indexing - Bulk Errors
has_children: false
parent: System
grand_parent: ElasticSuite
nav_order: 4
---

## Indexing / Bulk Errors

**Overview**
The Indexing / Bulk Errors dashboard provides a centralized grid to monitor and review errors that may occur during the indexing process when sending data in bulk. Occasionally, certain documents (such as products or categories) might be rejected by the search engine and fail to index. This is typically caused by issues like a faulty custom data source or a Magento attribute containing incorrectly initialized data.

While these errors are traditionally only recorded in the server's Magento logs, this dashboard makes them directly visible within the admin panel. This allows administrators to quickly identify rejected documents and efficiently troubleshoot underlying data issues without needing server access.

You can access this dashboard by navigating to **Smile ElasticSuite > System > Indexing / Bulk Errors** in your Magento admin panel.

### Dashboard Columns

The grid displays detailed information for each recorded indexing error to help you identify the root cause:

| Column | Description |
| :--- | :--- |
| **ID** | The internal system identifier for the recorded error log. |
| **Store Code** | The specific Magento store view code where the indexing error occurred. |
| **Index Identifier** | The target index (e.g., product, category, thesaurus) where the documents were rejected. |
| **Error Type** | The technical classification or type of the indexing error. |
| **Reason** | A detailed explanation or error message returned by the search engine indicating why the failure happened. |
| **Failed doc IDs sample** | A sample list of the specific document IDs (e.g., product IDs or category IDs) that were rejected. |
| **Count** | The total number of documents affected by this specific error. |
| **Created At** | The date and time when the error was initially recorded. |
| **Updated At** | The date and time when the error log was last updated. |

---

### Configuration & Automated Purging

**Enabling or Disabling Logging:**
You can control whether bulk indexing errors are actively logged to this dashboard via the store configuration. To toggle this feature, navigate to:
**Stores > Configuration > Elasticsuite > Base Settings > Indexing / Bulk errors logging > Enable logging of bulk indexing errors**

**Automated Purging:**
To keep the dashboard clean and relevant, the system automatically manages old errors. Please note that for Magento entity-based indices (such as categories and products), **all existing logged errors are purged from the database whenever a full re-index occurs**. This ensures that the grid only displays the most recent indexing issues tied to your current catalog data.
