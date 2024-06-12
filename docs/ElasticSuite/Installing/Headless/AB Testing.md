---
layout: default
title: Configure AB Testing in Headless
has_children: false
parent: Headless
nav_order: 1
---

## Ensure AB Testing is working in Headless mode

On every page (or once by user session) you need to get the AB testing data from the Magento API with these calls :

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

The API will return a json response like :
[{"campaign_id":"3","scenario_id":"A"}]

**Then you need to send these data in every api call to the Magento backend**. 

There are two options to do this:

- You can save this data in a cookie named @AB-CAMPAIGN@ register in the same domain that the magento api call
- You can set a http header named @AB-CAMPAIGN@ on every magento api call
