---
layout: default
title: Advanced similarity configuration
has_children: false
parent: Recommender - Premium
grand_parent: Settings
nav_order: 6
---

<img width="988" height="783" alt="image" src="https://github.com/user-attachments/assets/a2485508-4b6d-4a0c-87f6-2e707b5aaf21" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Max Query Terms | 25 | The maximum number of query terms selected for the similarity computation. Increasing this value yields greater accuracy, but at the expense of query execution speed. |
| Min Term Freq | 1 | The minimum term frequency. Words that appear fewer times than this threshold in the input document will be completely ignored. |
| Min Doc Freq | 2 | The minimum document frequency. Words that appear in fewer documents than this threshold across the entire index will be ignored. |
| Max Doc Freq | 2147483647 | The maximum document frequency. Words that appear in more documents than this limit will be ignored. This is highly useful for filtering out extremely frequent words (such as stop words). The default value represents an unbounded limit (Integer.MAX_VALUE). |
| Min Word Length | 0 | The minimum allowed word length. Any term shorter than this value will be ignored during the similarity calculation. |
| Max Word Length | 0 | The maximum allowed word length. Any term longer than this value will be ignored. A default value of `0` means the length is unbounded. |
