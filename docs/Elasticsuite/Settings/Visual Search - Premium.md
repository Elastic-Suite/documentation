---
layout: default
title: Visual Search - Premium
has_children: false
parent: Settings
nav_order: 7
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Visual Search

<img width="481" alt="miscellaneous-footer-settings" src="https://user-images.githubusercontent.com/98949123/156195865-63602680-1828-48e4-9a7a-1716ff8d4d33.PNG">

| Parameter | Default value | Description                                                                                                                                                                                                                                   |
|:----------|:--------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Url       | empty         | The external Visual Search API url provided by the Elasticsuite team                                                                                                                                                                          |
| Allowed extensions (comma separated)       | jpg,jpeg      | The supported file formats that can be used for Visual Search                                                                                                                                                                                 |
| Maximum size (kb)       | 100           | The maximum image size that can be used for Visual Search                                                                                                                                                                                     |
| Optimal resized width (px)       | 640           | The resize size of images that are used for Visual Search (depends on the API)                                                                                                                                                                |
| Api Terms Mapping       | empty         | A mapping of terms returned by the Visual Search API. The API will return one term per product, and the returned terms will not be translated, so if you are having multiple store views, you'll need to map the terms in all languages here. |
