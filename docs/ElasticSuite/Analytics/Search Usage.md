---
layout: default
title: Search Usage
has_children: false
parent: Analytics
grand_parent: ElasticSuite
---

## Analytics: Search Usage

**Overview**
The Search Usage dashboard provides merchandisers and administrators with comprehensive insights into how users interact with the search engine on your storefront. It allows you to monitor global metrics, identify trending search terms, track conversion rates, and spot areas for catalog improvement (such as fixing common typos or addressing searches that yield no results).

You can access this dashboard by navigating to **Smile ElasticSuite > Analytics > Search Usage** in your Magento admin panel.

<img width="1778" height="819" alt="image" src="https://github.com/user-attachments/assets/05826ac8-dea1-4ca3-aa6d-156c4e29145b" />

### Filtering Data

At the top of the dashboard, you can refine the analytics data using several filters:
*   **Scope:** Filter the data by specific Store Views.
*   **Customer Group:** Filter behavioral data by specific Magento Customer Groups.
*   **Company:** If you are using the Magento B2B module, you can filter the data by specific companies.
*   **Date Range (From / To):** Select the specific time period you want to analyze.

### Global Metrics (KPIs)

The dashboard displays a top-level summary of your storefront's performance based on behavioral data. The available KPIs include:
*   **Searches:** The total number of searches performed.
*   **Page views:** The total number of pages viewed.
*   **Category views:** The number of times category pages were viewed.
*   **Product views:** The number of times product detail pages were viewed.
*   **Products added to cart:** The number of products users added to their carts.
*   **Sales:** The total number of sales events.
*   **Visitors:** The number of unique visitors.
*   **Sessions:** The total number of navigation sessions.
*   **Sessions with search:** The number of sessions where at least one search was performed.
*   **Searches per session:** The average number of searches performed per session.

### Search Terms Data Tables

The dashboard provides detailed tables breaking down specific search term performance. Each table includes metrics for the **Term**, **Sessions**, **Visitors**, **# Results (avg.)**, and **Conv. rate**. The dashboard display is fully optimized to properly handle and display exceptionally long search terms.

*   **Popular search terms:** View what is currently trending and see how often specific search terms lead to a conversion.
*   **Spellchecked search terms:** Identify common spelling mistakes users make so you can proactively fix them using the Thesaurus.
*   **0 results search terms:** Identify search queries that yield no products. This helps you create new synonyms, expansions, or redirects to prevent dead-end user journeys.
*   **AB Testing Campaign:** View performance data comparing sessions and conversion rates for active A/B testing campaigns.

📋 **Exporting Data:** You can easily copy the data from the popular and spellcheck search terms tables to your clipboard. Clicking the export icon allows you to paste the data directly into a spreadsheet application (the data is formatted as TSV - Tab Separated Values).

### Visual Charts

The right side of the dashboard includes visual breakdowns of your search usage:
*   **Sessions:** A pie chart displaying the percentage of sessions *with* a search versus sessions *without* a search.
*   **Spellcheck usage:** A pie chart showing the percentage of exact searches versus spellchecked requests.
*   **Conversion rate:** A bar chart comparing the conversion rates between all sessions, sessions with search, and sessions without search.

***

### System Notifications & Troubleshooting

⚠️ **Pending Events Warning:** If your tracker events storage table contains behavioral events that were created more than 6 hours ago and have not yet been indexed, a warning notification will pop up on this dashboard. This alerts you to potential cronjob or indexing issues that might cause your dashboard data to be incomplete or outdated. *(Note: The 6-hour threshold for this warning can be adjusted in the Store Configuration under Analytics > Pending events configuration)*.

⚠️ **Invalid Behavioral Data Errors:** In certain setups (like custom theme integrations or PWA frontends), data collection may occasionally fail to register unique visitor or session IDs properly. Over time, these invalid events can slow down requests on your behavioral indices and generate 429 errors on your Elasticsearch/OpenSearch server, which will prevent the Search Usage dashboard from loading. You can use the Magento CLI command `elasticsuite:tracker:check-data` to scan for these invalid events, and `elasticsuite:tracker:fix-data` to safely repair them.
