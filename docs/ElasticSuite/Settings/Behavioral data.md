---
layout: default
title: Behavioral data
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 19
---

Located under Store > Configuration > ElasticSuite > Behavioral data

<img width="1003" height="435" alt="image" src="https://github.com/user-attachments/assets/b403f3fe-c7a4-4872-b2c7-d41af96fa2b3" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enabled | Yes | When enabled, the system collects behavioral data from your tracker indices during product reindexing. This allows the Behavioral Optimizers to dynamically boost products based on real user interactions (such as views, sales, and cart additions). Additionally, this per-product behavioral data becomes visible within the "Explain results" panel for debugging relevance. |
| Use weekly stats | Yes | When enabled, the engine will compute and store behavioral data on a weekly basis in addition to the standard daily tracking. |
| Daily From | 30 | Defines the maximum time window (in days) to be considered when calculating daily behavioral data. Accepts an integer between `7` and `100`. |
| Weekly From | 60 | Defines the maximum time window (in days) to be considered when calculating weekly behavioral data. Accepts an integer between `28` and `365`. |
