---
layout: default
title: Terms Recommender - Premium
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 22
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Terms Recommender entry

<img width="1002" height="306" alt="image" src="https://github.com/user-attachments/assets/536cb3d5-17fa-4167-a28e-e6da8577c915" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enable Term Recommendations | Yes | When enabled, the system will generate and display search term recommendations. <br><br>⚠️ *Warning: Enabling this option requires additional processing and may slow down your site's performance.* |
| Term Recommendations Count | 3 | Defines the maximum number of term recommendations that will be displayed to the user. |
| Show Results Count for Each Recommendation | No | When enabled, the system will display the total number of matching products next to each recommended search term. |
| Number of day to take into account | 365 | Determines the historical time window (in days) used to gather data for term recommendations. User sessions older than this threshold will be completely ignored when generating recommendations. |
