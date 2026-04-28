---
layout: default
title: Healthcheck
has_children: false
parent: System
grand_parent: ElasticSuite
nav_order: 2
---

## System Healthcheck

<img width="1791" height="540" alt="image" src="https://github.com/user-attachments/assets/af57ae23-6755-471a-aac8-bf85f7e35f24" />

**Overview**
The Healthcheck dashboard provides a centralized monitoring screen that actively evaluates the configuration and overall health of your Elasticsuite installation. Introduced to consolidate previous Magento admin system notifications, this page helps you quickly identify misconfigurations, synchronization issues, or optimization opportunities within your search engine and cluster.

You can access this dashboard by navigating to **Smile ElasticSuite > System > Healthcheck** in your Magento admin panel.

**Admin Menu Alerts:** To ensure issues do not go unnoticed, a notification badge decorates the Elasticsuite admin menu, allowing you to immediately see how many checks are currently failing without having to open the page.

### Dashboard Columns

The dashboard grid displays the results of various system validations, organized by the following columns:

| Column | Description |
|:-------|:------------|
| **Identifier** | The internal system code for the specific health check. |
| **Description** | A human-readable explanation of what is being evaluated. If a check fails, this column will provide actionable advice or direct links to resolve the issue. |
| **Status** | Indicates the current result of the check (typically **PASSED** or **FAILED**). |
| **Severity** | If a check fails, this column displays color-coded criticality levels (such as **CRITICAL**) to help you prioritize which issues need immediate intervention. |

---

### Available Health Checks

The system continuously runs a variety of checks covering core engine settings, catalog configurations, tracking data, and premium add-ons. Common checks you will see include:

#### Core Engine & Cluster Checks
*   **search_engine_config_check:** Verifies that Magento is correctly configured to use Elasticsuite as its primary search engine.
*   **primary_shards_config_check:** Ensures that the number of primary shards is properly configured for your Elasticsearch/OpenSearch cluster.
*   **replicas_config_check:** Ensures that the number of replica shards is properly configured.
*   **ghost_indices_check:** Scans your cluster to verify there are no "ghost" (orphaned) indices consuming unnecessary resources.

#### Catalog & Frontend Configuration
*   **category_is_anchor_config_check:** Confirms that all categories in your catalog are correctly configured as "anchor" categories. Elasticsuite relies on anchor categories to properly display a category's own products alongside products associated with its subcategories.
*   **hyva_compatibility_check:** If your storefront utilizes the Hyvä theme, this checks that all specific frontend requirements and compatibility modules are fulfilled.

#### Behavioral Data Tracking
*   **tracker_pending_events:** Monitors the behavioral tracker queue to ensure that events (like views and sales) are being regularly indexed as expected. 
*   **invalid_tracker_events:** Scans for malformed tracker events (e.g., missing unique visitor or session IDs) that were stopped from being put into your behavioral indices to prevent performance or data collection issues.

#### Package & License Validation
*   **packages_version_check:** *(Premium only)* Verifies that all Elasticsuite Premium packages installed on your instance perfectly match the version of the core `smile/elasticsuite` package, preventing compatibility errors.
*   **premium_client_id_checker:** *(Premium only)* Validates that your Elasticsuite Premium Client ID is correctly configured according to your onboarding license terms.
*   **recommender_similarity_attr_check:** *(Premium only)* Ensures that the Recommender module is properly configured with valid similarity attributes.

