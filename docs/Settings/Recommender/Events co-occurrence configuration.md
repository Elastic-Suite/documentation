---
layout: default
title: Events co-occurrence configuration
has_children: false
parent: Recommender
grand_parent: Settings
nav_order: 2
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Recommender entry

<img width="511" alt="events-co-occurence-config" src="https://user-images.githubusercontent.com/98949123/156194011-d604ca69-903b-44d6-a0b0-414afe4b97f2.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Min doc count|2|When gathering co-occurrence of products related events (products also viewed, added to cart, bought), in how many distinct sessions an event must occur at the minimum to be taken into account. Lowering it can be helpful on sites without much events tracking history to avoid a cold start.|
|Similarity attributes||Attributes that will be used to find products similar to the co-occurrent products. The list is made of attributes that are searchable, can provide text values to the search engine and are configured to either be sortable or filterable in layer navigation.|
