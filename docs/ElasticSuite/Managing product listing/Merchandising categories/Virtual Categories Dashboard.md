---
layout: default
title: Virtual Categories Dashboard
has_children: false
parent: Managing product listing
grand_parent: ElasticSuite
nav_order: 4
---

*Note: This feature is available exclusively in **Elasticsuite Premium**.*

## Overview

The Virtual Categories Dashboard provides a dedicated administration screen listing all of your virtual categories in one centralized location. This dashboard gives you quick insights by displaying relevant information and metrics for each virtual category, highlighting alerts if intervention is needed, and providing a direct link to easily go and edit a specific virtual category.

Additionally, this feature enhances the native Magento **Catalog > Categories** tree menu by decorating your virtual categories with the Elasticsuite logo. This visual indicator is designed to help you quickly locate and evaluate your virtual categories mixed within your standard category tree.

<img width="503" height="555" alt="image" src="https://github.com/user-attachments/assets/83cd4dd0-d13e-4e20-b2d9-5cfd2b584126" />

## How to Access

To utilize this feature, ensure the premium composer package `smile/module-elasticsuite-category-monitoring` (which provides the `Smile_ElasticsuiteCategoryMonitoring` module) is installed on your instance.

Once enabled, you can access the dashboard by navigating in your Magento admin menu to:
**Elasticsuite Categories > Virtual Categories Dashboard**

<img width="1711" height="507" alt="image" src="https://github.com/user-attachments/assets/d77ba6f4-e36e-40e1-a52a-b500ba167f4f" />

| Column | Description |
|:-------|:------------|
| **Website** | The Magento website where the virtual category is located. |
| **ID** | The unique internal identifier (ID) of the category. |
| **Name** | The name of the virtual category. |
| **Enabled** | Indicates whether the category is currently active ("Yes" or "No"). |
| **Category path** | The full breadcrumb path of the category within your catalog tree (e.g., `Default Category > Fashion > Sales`). |
| **Number of products** | The current count of products dynamically matching the virtual category's rules. |
| **Alerts** | Displays warnings or notifications if the virtual category requires your attention. |
| **Actions** | Provides a direct **Edit** link to quickly jump to the category configuration page. |
