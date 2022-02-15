---
layout: default
title: AB Testing Campaign creation
has_children: false
parent: Optimizer Campaign
grand_parent: AB Testing Campaign
nav_order: 1
---

It can be accessed under the ElasticSuite menu > AB Testing Campaign via the Optimizer Campaign entry.

## Campaign creation

### General configuration

<img width="505" alt="ABtesting-general" src="https://user-images.githubusercontent.com/98949123/153427330-f7cbcf62-68cb-4863-809a-119bc2d57a94.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Name||The name of the campaign|
|Store View||The store view for this AB Testing campaign. AB Testing campaign can only be assigned to one store view.|
|Description||The description of the campaign|
|Start Date||Start date of the campaign|
|End Date||End date of the campaign|

<img width="399" alt="AB-testing-apply-to" src="https://user-images.githubusercontent.com/98949123/153428112-0b6238ed-ac84-43bf-a4b3-02316aacf809.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Request type||**Catalog Product Search** : Apply campaign only to search result listing <br/> **Catalog Product Autocomplete** : Apply campaign only to autocomplete result <br/> **Category Product View** : Apply campaign only to category listing <br/><br/> One, some or all request type can be selected|

<img width="416" alt="customer-segment" src="https://user-images.githubusercontent.com/98949123/153429191-79853f50-30cb-4750-9774-2be7c19d1e63.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Apply to|All customer segments|All customer segments or Selected customer segments <br/> Campaign can only be applied to a specific Magento customer segents|

General configuration must be defined first, and then scenario A and B could be configured :

### Scenario definition

Name and distribution percentage must be given to both of the scenario.
If Scenario A have 60% and Scenario B 40%, it means that 60% of users will see scenario A and 40% of users will see scenario B in front.
For each scenario, 3 possible choices are available :
* Create a new boost
* Create a new boost from existing
* Select no boost at all (it allows to compare a scenario with boost and the other without boost)

<img width="581" alt="AB-testing-scenario" src="https://user-images.githubusercontent.com/98949123/153431742-812fef64-db59-48c5-9fb5-0baa65b2a489.PNG">

| Parameter    | Description |
|:-------------|:------|
|ID|ID of the boost|
|Name|Name of the boost|
|Model|Constant, based on attribute value or based on behavioral data|
|Rule|Detail of the rule used in the boost|
|Action|2 possible actions : <br/> - Edit : open the popup for editing the boost <br/> - Delete : dissociate the boost with the campaign|

### Publish or stop a campaign

Campaign has to be published in order to be activated when start date is reached. Otherwise it will stay on draft mode.

![publish-ab-testing](https://user-images.githubusercontent.com/98949123/154094956-1021f7f4-ecf6-486b-978f-4e48d9c25065.PNG)

If a campaign has to be stoped, a button "stop" is available. Once a campaign is stopped, it is considered completed.

![stop-ab-testing](https://user-images.githubusercontent.com/98949123/154095425-cfbba9c1-bf87-412d-93a0-356f72df7244.PNG)


### Results analytics

<img width="890" alt="result-analytics" src="https://user-images.githubusercontent.com/98949123/154087639-5d2d0546-f889-4cdf-a882-3c0f48147a5f.PNG">

| Parameter     | Description |
|:--------------|:------|
|Total Sessions|How many sessions were exposed to the campaign|
|Sessions A|How many sessions were exposed to scenario A|
|Conv. rate A|Conversion rate for scenario A|
|Sessions B|How many sessions were exposed to scenario B|
|Conv. rate B|Conversion rate for scenario B|
|Significant result|Data collected are sufficient to consider the results significant or not.|


