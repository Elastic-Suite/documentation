---
layout: default
title: Analytics
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 8
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Analytics entry

## Search terms configuration

<img width="479" alt="search-terms-config" src="https://user-images.githubusercontent.com/98949123/156195042-bc04b3a7-3f9d-4c74-a2d7-1f1f927b1614.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Max search terms|100|Maximum number of search terms to display in the search usage report blocks.|

## Pending Events Configuration

<img width="1181" height="253" alt="Image" src="https://github.com/user-attachments/assets/afdc94cb-1ef2-471b-ac1e-2bb7c4a138a3" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Hours before warning | 6 | Defines the maximum allowed age (in hours) for pending tracking events. If events older than this threshold remain stuck in the queue table without being indexed, a warning notification will automatically appear on your Search Usage dashboard to alert you of potential data collection issues. |

## Filters Configuration

<img width="1183" height="397" alt="Image" src="https://github.com/user-attachments/assets/1060e03f-2764-4cfb-8e35-485422c1461e" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Show Customer Group filter | Yes | When enabled, a dropdown filter is added to your Search Usage dashboard, allowing you to easily segment and analyze your search behavioral data by specific Magento customer groups. |
| Show Company filter | Yes | *(Applicable only if your store uses Magento B2B Company features)*. When enabled, a filter is added to the Search Usage dashboard, allowing you to segment and analyze search behavioral data for specific B2B companies. |

