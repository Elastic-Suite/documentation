---
layout: default
title: Tracking
has_children: false
parent : Settings
nav_order: 2
---


## Global Configuration

<img width="481" alt="Global-configuration" src="https://user-images.githubusercontent.com/98949123/155968561-e3632adf-34b2-4f63-a173-47970dd31fb2.PNG">

Elasticsuite collects data based on user behaviors on the website.

This data is stored in several Elasticsearch indices and is needed for the following features to work properly : 

- Search Analytics Dashboard (Open Source Version)
- Behavioral Autocomplete (Premium Version)
- Behavioral Optimizers (Premium Version)
- A/B Testing Campaigns (Premium Version)
- Facets Recommender (Premium Version)

| Parameter    | Default value | Description                                                         |
|:-------------|:--------------|:--------------------------------------------------------------------|
|Enabled| Yes           | If the tracking service is enabled.                                 |
|Retention delay| 12            | In months. Tracking data older than this will be removed regularly. |


## Session Configuration

| Parameter    | Default value | Description                                                                   |
|:-------------|:--------------|:------------------------------------------------------------------------------|
|Visit Cookie Name	| STUID         | Visit cookie name, a short-term duration cookie to track visits.              |
|Visit Cookie Lifetime	| 3600          | By default, short-term cookie is one hour.                                    |
|Visitor Cookie Name	| STVID         | Visitor cookie name, a long-term duration cookie to track returning visitors. |
|Visitor Cookie Lifetime	| 365           | By default, long-term cookie is one year.                                     |

## Tracking Anonymization

| Parameter    | Default value | Description                                                                                                                             |
|:-------------|:--------------|:----------------------------------------------------------------------------------------------------------------------------------------|
|Anonymize customer data after a delay.| No            | When enabled, the link between Visitor cookie (anonymous) and Magento Customer (that contains personal data) will be regularly removed. |
