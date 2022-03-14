---
layout: default
title: General
has_children: false
parent: Recommender
grand_parent: Settings
nav_order: 1
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Recommender entry

<img width="514" alt="recommender-general" src="https://user-images.githubusercontent.com/98949123/156156551-a51cf777-31de-4d0a-913c-3fc2666685b0.PNG">

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Exclude from recommendations any product already bought by the visitor|Yes|If set to yes, products already bought by user will not be displayed on recommenders product blocks. Applies only to automated recommendations and not to manually selected products. Exclusion duration is set on following field.|
|Product bought exclusion window size as a number of days|90|For instance "90" will mean no product bought by the visitor in the past 90 days will be recommended. 0 means no time restriction at all : no product ever bought by the visitor will be recommended to him. Be careful that this setting impact is heavily dependent on the tracker "Retention delay" and "Visitor Cookie Lifetime" parameters.|
|Prevent defaulting to whole catalog|Yes|In some conditions, there might not be any event yet (searches, views, sales, ...) for a product (e.g. for a new product) and so not constraint on the recommendation request for that product. If set to Yes, this will prevent such a recommendation request to be executed and no products will be shown. If set to No, the request would end up displaying generic products picked from the whole catalog.|
|Maximum Number of Products in Related Products List|6|Maximum number of products to display in the block for related products|
|Show Related Products|- Both Selected and Event-Based|Both Selected and Event-Based : Both manually selected products and event-based products will be placed in the related product block. Manual products will be up in the listing, and Event-based products will be placed next. <br/> - Selected Only : Only manually selected product will be displayed in the related product block --> behavioral data is deactivated for this block.<br/>- Event-Based Only : On event-based products will be displayed in the related product block --> even if products are manually selected, they will be ignored|
|Exclude composite (bundle, grouped, configurable) from Related Products List|No|If set to yes, no configurable, grouped or bundle products will be displayed in the related product block.|
|Maximum Number of Products in Cross-Sell Products List|6|Maximum number of products to display in the block for cross-sell products|
|Show Cross-Sell Products|Both Selected and Event-Based|- Both Selected and Event-Based : Both manually selected products and event-based products will be placed in the Cross-Sell product block. Manual products will be up in the listing, and Event-based products will be placed next. <br/> - Selected Only : Only manually selected product will be displayed in the Cross-Sell product block --> behavioral data is deactivated for this block.<br/>- Event-Based Only : On event-based products will be displayed in the Cross-Sell product block --> even if products are manually selected, they will be ignored|
|Maximum Number of Products in Upsell Products List|6|Maximum number of products to display in the block for Upsell products|
|Show Upsell Products|Both Selected and Event-Based|- Both Selected and Event-Based : Both manually selected products and event-based products will be placed in the Upsell product block. Manual products will be up in the listing, and Event-based products will be placed next. <br/> - Selected Only : Only manually selected product will be displayed in the Upsell product block --> behavioral data is deactivated for this block.<br/>- Event-Based Only : On event-based products will be displayed in the Upsell product block --> even if products are manually selected, they will be ignored|
|Allow native complement of manually selected upsell products|Yes|If set to Yes, will dispatch the native event which ensures that any bundle product the current product appears in is added to the manual upsell products selection. This will of course potentially restrict the size of the automated recommendations.|
|Force Higher Price for Upsell Products|No|If set to Yes, will ensure that products automatically recommended based on past tracked events have a higher price than the base product. This has no impact on the manually configured upsell products.|




