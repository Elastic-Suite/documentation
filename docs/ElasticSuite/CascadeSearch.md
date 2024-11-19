---
layout: default
title: Cascade Search
has_children: true
parent: ElasticSuite
nav_order: 9
---

## Technical Prerequisites

The Cascade Search relies on data collected by the tracking mechanism. If you're not seeing anything under the **ElasticSuite > Search Analytics** screen, it's likely you're having an issue with collecting behavioral data. 

You should head to the Troubleshooting section of this documentation before going further.

## Installing the module

The module responsible for neural search is `smile/module-elasticsuite-cascade-search` and this module is not part of the standard Premium package. You'll need to install it manually prior going further.

## Configuring the Cascade Search

Once the module is installed, you can go to **Stores > Configuration > ElasticSuite > Cascade Search suggestions** 

### General configuration 

Before going further, ensure your technical team completed the [pre-requisites](https://elastic-suite.github.io/documentation/docs/ElasticSuite/Installing/NeuralSearch.html).

![Sélection_1859](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1859.png)

**If you want to enable the cascade search, you will have to set Enabled=yes but also to pick the locales corresponding to the websites you're willing to display cascade suggestions.**

:warning: For now, the cascade search has only been tested with roman languages (french, italian, spanish, etc...). It might not work properly with other languages (english), and especially with languages that rely on word composition (german, dutch, etc...).

### Frontend Configuration

![Sélection_1860](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1860.png)

Here you can configure the number of suggestions displayed and how they should be sorted. 

We recommend to let the "Replace Search Recommendations" parameter to "No".

### Additional Configuration

![Sélection_1861](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1861.png)

The default values are recommended and should rather not be edited.

## Computing the suggestions

Before the suggestions to be shown on the frontend part, you will need to reindex the "ElasticSuite Search Events" and "ElasticSuite Search Suggestions" indices, either by invalidating them through the Magento back-office, or by reindexing them via the command line.

Once you're done with this, suggestions will begin to show in the website frontend.

## Tweaking of the suggestions

Once you're seeing suggestions in the frontend, you can go to the **ElasticSuite > Preview and Manage Suggestions** screen. Here, you'll be able to get the list of suggestions for a given query term, and to fine-tune them by either hiding them globally or for this query only.

![Sélection_1862](https://elastic-suite.github.io/documentation/docs/ElasticSuite/static/Sélection_1862.png)
