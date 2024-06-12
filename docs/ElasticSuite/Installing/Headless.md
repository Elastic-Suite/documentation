---
layout: default
title: Installing
has_children: true
parent: Installing
nav_order: 1
---

When working with an Headless Magento app, some additional steps are required for everything to work properly.

This applies to PWA Studio, Adobe Experience Manager, or any other “from-scratch” frontend application used on top of a Magento application.

## How-To
Elasticsuite tracking mechanism has to be embedded into the frontend application like you would proceed with any other tracking mechanism (like Google Analytics, Tag Commander, etc…).


## AB Test
Integration in headless mode
On every page (or once by user session) you need to get the ab testing data from the Magento api with these calls :

REST:
```
GET /V1/elasticsuite-ab-campaign/hasCampaigns
GET /V1/elasticsuite-ab-campaign/campaigns-scenarios
```

GraphQl:
```
query elasticsuiteAbCampaigns {
   elasticsuiteAbCampaigns {    
```

The api will return a json response like :
[{"campaign_id":"3","scenario_id":"A"}]

Then you need to send these data in every api call to the Magento backend . There are two options to do this:

- You can save this data in a cookie named @AB-CAMPAIGN@ register in the same domain that the magento api call
- You can set a http header named @AB-CAMPAIGN@ on every magento api call
