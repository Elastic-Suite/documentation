---
layout: default
title: Telemetry
has_children: false
parent: Settings
nav_order: 3
---
Since releases 2.8.16 2.8.16 and 2.10.9 Elasticsuite is embedding a telemetry tracking mechanism.

That means, starting from this version, we’ll include a completely optional telemetry mechanism to understand how you are using this extension and where to focus our effort in improvement.

On the first launch after the upgrade, you’ll see a lightbox offering you the opportunity to support this effort or not. Deactivation of the telemetry service will have no impact on the quality of the module, which will continue to serve you as always.

![telemetry_popin](https://user-images.githubusercontent.com/98949123/152796487-54b56130-83d6-4186-84e3-1e4926175cc9.png)

##Disable Telemetry
Telemetry can be disabled with 3 clicks by going to **Stores > Configuration > Elasticsuite > Tracking > Telemetry** and setting the _Enable Telemetry_ parameter to No :

![disable-telemetry](https://user-images.githubusercontent.com/98949123/152796825-dfcabfe8-e46b-4d97-b29a-68a76fe33333.png)

##Telemetry data

We want to be completely transparent about what we plan to collect and how, so here is a list of collected informations :

| Name        | Details         | Example |
|:-------------|:------------------|:------|
|**All pages**|
|type.identifier|	type of current page|catalog_category_view, checkout_onepage_success, ...|
|type.label|	label for type of current page|	Catalog Category, Quick Search Form, ...|
|store_id	|store id of the current store	|1|
|locale|	locale of the current store	|fr_FR|
|session.uid|	User id (short-term cookie) of the current session|	8e34df31-0a10-3e87-c28d-9d1ceffe8ce1|
|session.vid|	Visitor id (long-term cookie) of the current session|	d543ef89-6831-7326-6c36-c92288d7db5f|
|customer.age	|Customer Age	|33 * (only applicable when logged-in)|
|customer.gender|	Customer Gender|	male * (only applicable when logged-in)|
|customer.country	|Customer Country	|France * (only applicable when logged-in)|
|customer.state	|Customer State	|Gironde * (only applicable when logged-in)|
|customer.zipcode|	Customer Zip code	|33000 * (only applicable when logged-in)|
|referrer.domain	|Referrer domain	|elasticsuite.io|
|referrer.page|	Referrer page|	https://elasticsuite.io/features|
|url	|Current url	https://myshop/red-shoes.html|
|domain	|Current domain	|myshop.com|
|title|	Current page title	|Nike Red Shoes - Myshop shoes shop|
|resolution.x	|Screen width	|1024|
|resolution.y	|Screen height	|768|
|**CMS Pages**|
|cms.identifier|	identifier of CMS page|	about-us, home, ...|
|cms.title|	title of CMS page|	About us, Homepage, ...|
|**Category Pages**||
|category.id|	numeric id of category|	38|
|category.path|	Category Path (numeric) in Magento|	1/2/138/1256|
|category.label|	Name of the Category|	Shorts|
|category.breadcrumb|	Breadcrumb of the Category|	Men|
|**Search Result Page**|
|search.query	|In search results, the search query|	red shoes|
|search.is_spellchecked|	If the query is spellchecked	|1|
|**Listing pages : Category Pages and Search Result Pages**|
|product_list.page_count|	Page number for product listing	12
|product_list.product_count|	Total number of product in a listing	194
|product_list.current_page|	Current page of a listing	1
|product_list.sort_order|	Sort order of a listing	price
|product_list.sort_direction|	Direction for sort order of a listing	asc
|product_list.display_mode|	Display mode of a listing (grid or list)|	grid|
|product_list.filter|	Applied filter in a listing	|product_list.filters.price=75-501, product_list.filters.manufacturer= 'Salomon|
||Labels of applied filters (not attribute code)|Prix=75-501, Marque=Salomon|
|**Product View page**|
|product.id|	numeric id of a product	|269|
|product.label|	Name of the product	|Nike Red Shoes|
|product.sku|	SKU of the product	|123458ABC|
|product.crosssell.sku	|	
|product.upsell.sku		|
|product.crossell.enabled		|
|product.crossell.enabled		|
|**Order Success page**|
|order.subtotal|	Subtotal of the order	10.0000|
|order.discount_total|	Amount of discount of the order|	10.0000|
|order.shipping_total|	Amount of shipping fees of the order|	10.0000|
|order.grand_total|	Grand total of the order|	10.0000|
|order.shipping_method	|Carrier code of the order|	colissimo_colissimo|
|order.payment_method|	Payment method of the order|	checkmo|
|order.salesrules	|Sales rules applied on the order|	1,36,68|
|order.items.*X*.sku|	SKU of the product ordered	|123458ABC|
|order.items.*X*.product_id|	numeric id of the product ordered|	269|
|order.items.*X*.qty|	qty ordered	|1|
|order.items.*X*.price|	unit price of the product|	10.0000|
|order.items.*X*.row_total|	row total (price * qty) of the ordered product	|10.0000|
|order.items.*X*.label|	Name of the product	|Nike Red Shoes|
|order.items.*X*.salesrules|	Sales rules applied on the ordered product|	1,3|
|order.items.*X*.category_ids|	Category Ids of the ordered product	|1,2,138,1256|


