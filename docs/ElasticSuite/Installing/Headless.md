---
layout: default
title: Installing
has_children: false
parent: Installing
nav_order: 1
---

When working with an Headless Magento app, some additional steps are required for everything to work properly.



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

Then you need to send these data in every api call to magento. There is two options to do this:
You can save this data in a cookie named @AB-CAMPAIGN@ register in the same domain that the magento api call
You can set a http header named @AB-CAMPAIGN@ on every magento api call
