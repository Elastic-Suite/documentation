---
layout: default
title: Configure Tracking in Headless
has_children: false
parent: Installing
grand_parent: ElasticSuite
nav_order: 1
---

## How-To
Elasticsuite tracking mechanism has to be embedded into the frontend application like you would proceed with any other tracking mechanism (like Google Analytics, Tag Commander, etc…).

### Legacy tracking script
You can use the legacy tracking script directly from here : 
2.10.x version : https://github.com/Smile-SA/elasticsuite/blob/2.10.x/src/module-elasticsuite-tracker/view/frontend/web/js/tracking.js
2.11.x version :  https://github.com/Smile-SA/elasticsuite/blob/2.11.x/src/module-elasticsuite-tracker/view/frontend/web/js/tracking.js

This is a vanilla javascript file that should be able to work in any other javascript framework.
This script will add 2 cookies, STUID and STVID. The short term cookie (STUID) will materialize an unique navigation session, the long term one (STVID) will allow to identify the final customer for a long duration and to recognize him when he comes back to the website.

## Configuration
You will have to configure the tracker by using the setConfig({}) method.

This method takes several parameters : 


| Parameter    | Value to put | 
|:-------------|:------------------|
|beaconUrl                              | /elasticsuite/tracker/hit/image/h.png                   |
|endpointUrl (optional but recommended) | \<your backend url\>/rest/V1/elasticsuite-tracker/hit                  |
|sessionConfig.visit_cookie_name        | STUID (don’t change this)                  |
|sessionConfig.visit_cookie_lifetime    |     3600 (don’t change this)              |
|sessionConfig.visitor_cookie_name      |       STVID (don’t change this)            |
|sessionConfig.visitor_cookie_lifetime  |   365 (don’t change this)                |
|sessionConfig.domain                   | \<common domain between the back and the front app\>. <br/> If your store url is www.mysite.com and you api answers on backend.mysite.com, your sessionConfig domain must be set to “mysite.com”.        |
|sessionConfig.path                     |    /               |
|telemetryEnabled|  false               |
|telemetryUrl                           | https://t.elasticsuite.io/track                  |


The beaconUrl and endpointUrl do pretty much the same thing: tell the tracking script where to send the data, but also how : 
- if defined, endpointUrl takes precedence over beaconUrl and the data will be submitted using an Ajax/XmlHttpRequest POST request using our custom Magento REST API endpoint ;
- if only beaconUrl is defined,  the data will be submitted the legacy way by adding to the DOM an <img> HTML tag whose src attribute will be the URL made of beaconUrl and as many URL parameters as necessary

**In a headless theme, we recommend the use of endpointUrl **
- to ease integration (you probably already have the REST endpoint base URL defined somewhere)
- to avoid having to whitelist/setup the beaconUrl URL pattern in your HTTP cache frontend (for instance Fastly) or your SSR config if you have one.

 
**Example**

```javascript
try {
   smileTracker.setConfig(
   {
       beaconUrl: 'https://api.mymagentosite.com/elasticsuite/tracker/hit/image/h.png',
       endpointUrl: 'https://api.mymagentosite.com/rest/V1/elasticsuite-tracker/hit’,
       telemetryEnabled: true,
       telemetryUrl: ‘https://t.elasticsuite.io/track’
       sessionConfig: {
           "visit_cookie_name": "STUID",
           "visit_cookie_lifetime": "3600",
           "visitor_cookie_name": "STVID",
           "visitor_cookie_lifetime": "365",
           "domain": "mymagentosite.com",
           "path": "\/"
        }
   }
   );

// Then we inject the current Magento store. 
// The frontend application should be able to retrieve it.
 smileTracker.addPageVar('store_id', '1');

// By calling sendTag(true) we go through the legacy script then.
 smileTracker.sendTag(true);

} catch (err) {
    ;
}
```

As soon as you have done this, the tracking system is ready to tag your website pages.
You will then have to tag the different pages/rendering events according to the following tagging plan.

Please note that when a call to @smileTracker.sendTag(true)@ is performed, the currently collected tags data are sent to the backend (and on the first call on a given page, some metadata: browser version, resolution, etc) and then disposed of.

With a React-like headless theme based on a rendering loop which acts like a “single page app” and allows for the same browser “page / process” to show different content and perform different actions, you will need to call @smileTracker.sendTag(true)@ each time .


For instance if your theme allows the following actions without any browser refresh/page change: 
- the Homepage has been or is about to be rendered
    - add the Homepage tag
    - call  “smileTracker.sendTag(true); “
- the user performed a search and the REST/GraphQL response for the corresponding request has been rendered into a products list or is about to be rendered
    - add the Search Result page tag
    - call  “smileTracker.sendTag(true); “
- the user clicked on a product to see more details and the PDP has been rendered or is about to be rendered
    -add the Product Page tag
    - call  “smileTracker.sendTag(true); “
etc

Please note it’s important to always have the “true” parameter in the “smileTracker.sendTag(true);“ call, it’s basically what allows the legacy tracking script to send several batches of data in the same browser process.
Otherwise it will think it’s located in a legacy Luma-based Magento theme and will only actually send data the first time the “sendTag” method is called.

→ You would not collect all your users' behavioral events in the frontend !

## Tagging plan
### How to tag
To add tagging on a page, we call the following method : 

```javascript
    try {
            smileTracker.addPageVar('VARIABLE1', VALUE);
            smileTracker.addPageVar('VARIABLE2', VALUE 2);
            etc...
           // and in the end or at some point
           smileTracker.sendTag(true);
        } catch (err) {
        ;
    }
```

### Pages to tag/event

#### Homepage

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier  |    cms_index_index    |
| type.label   | CMS Home Page        |
| cms.identifier    |  Current page URL key    |
| cms.title  |  Current page title |

#### CMS Pages

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier  |    cms_index_index    |
| type.label   | CMS Pages (all)        |
| cms.identifier    |  Current page URL key    |
| cms.title  |  Current page title |

#### Category Page

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier | catalog_category_view   |
| type.label  |  Catalog Category  |
| category.id   |  Numeric id of the category  |
| category.path             |  The 'path' of the category in magento. Exemple 1/2/138/1256  |
| category.label |  The attribute 'name' of the category  |
| product_list.page_count  | Number of pages of the product listing |
| product_list.product_count | Number of products of the current listing |
| product_list.current_page  | Current page of the product listing |
| product_list.sort_order | Current sort order of listing : price, position, etc…  |
| product_list.sort_direction | Direction of the sort order : asc or desc |
| product_list.display_mode | Display mode of the listing (grid or list) not mandatory |

#### Filtered category page
If the user applied some filters to the category, they must be tracked according the following way :

| Variable    | Value | 
|:-------------|:------------------|
|product_list.filters.<attribut> | value |

As an example, on the Tops categories, I filter on brand = Adidas, Nike, price between 75 and 500€, the tracker must sent :
```
           smileTracker.addPageVar('product_list.filters.price', '75-501');
           smileTracker.addPageVar('product_list.filters.manufacturer', 'Nike|Adidas');
```

#### Search Result page
It’s pretty much the same than in category page.

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier | catalogsearch_result_index   |
| type.label  |  Quick Search Form  |
| search.query | The query that has been typed by the user |
| search.is_spellchecked | The value of the @is_spellchecked@ variable coming from the @SearchResultPageInfo@ object result |
| search.query_id   | The value of the @query_id@ variable coming from the @SearchResultPageInfo@ object result |
| product_list.page_count  | Number of pages of the product listing |
| product_list.product_count | Number of products of the current listing |
| product_list.current_page  | Current page of the product listing |
| product_list.sort_order | Current sort order of listing : price, position, etc…  |
| product_list.sort_direction | Direction of the sort order : asc or desc |
| product_list.display_mode | Display mode of the listing (grid or list) not mandatory |

#### Filtered search result page
Exactly the same behavior for filters than on filtered category page.


#### Product Page

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier | catalog_product_view   |
| type.label  |  Catalog Product View (Any)  |
| product.id   | Numerical Id of the product  |
| product.label             |  The attribute "name" of product  |
| product.sku |  The SKU of the product  |


#### Add to cart event
If you send this event, you need to activate the headless mode in elasticsuite configuration in magento backend.

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier | checkout_cart_add   |
| type.label  |  Add Item to Cart  |
| cart.product_id | Numerical Id of the product |

#### Checkout success

| Variable    | Value | 
|:-------------|:------------------|
| type.identifier | checkout_onepage_success   |
| type.label  | One Page Checkout Success  |
| order.subtotal  | Subtotal of the order, Ex 10.0000  |
| order.discount_total  | Total discount of the order. Ex 10.0000  |
| order.shipping_total  | Shipping amount of the order. Ex 10.0000  |
| order.grand_total  | Grand total of the order. Ex 10.0000  |
| order.shipping_method  | Carrier code of the order, Ex 'flatrate_flatrate", 'colissimo_colissmo', etc...  |
| order.payment_method  | Payment method used for the order. Ex 'checkmo'  |
| order.salesrules  | Sales rules applied on the order. Ex '1,3,68' not mandatory  |
| order.items.*X*.sku  | The SKU of the product  |
| order.items.*X*.product_id  | The numerical ID of the product  |
| order.items.*X*.qty  | Quantity ordered  |
| order.items.*X*.price  | Unit price of the product  |
| order.items.*X*.row_total  | Row total for the product  |
| order.items.*X*.label  | The “name” attribute of the product  |
| order.items.*X*.salesrules  | Sales rules applied to the product. Ex ‘1,12,4’. not mandatory  |
| order.items.*X*.category_ids  | Categories the product belongs to, comma-separated.  |

Exemple :

```javascript
   <!--
    try {
            smileTracker.addPageVar('type.identifier', 'checkout_onepage_success');
            smileTracker.addPageVar('type.label', 'One Page Checkout Success');
            smileTracker.addPageVar('order.subtotal', '0.0000');
            smileTracker.addPageVar('order.discount_total', '0.0000');
            smileTracker.addPageVar('order.shipping_total', '10.0000');
            smileTracker.addPageVar('order.grand_total', '10.0000');
            smileTracker.addPageVar('order.shipping_method', 'flatrate_flatrate');
            smileTracker.addPageVar('order.payment_method', 'checkmo');
            smileTracker.addPageVar('order.salesrules', '');
            smileTracker.addPageVar('order.items.0.sku', 'DYFIT00641 153 cm');
            smileTracker.addPageVar('order.items.0.product_id', '1806');
            smileTracker.addPageVar('order.items.0.qty', '1.0000');
            smileTracker.addPageVar('order.items.0.price', '0.0000');
            smileTracker.addPageVar('order.items.0.row_total', '0.0000');
            smileTracker.addPageVar('order.items.0.label', 'Dna Ski');
            smileTracker.addPageVar('order.items.0.salesrules', '');
            smileTracker.addPageVar('order.items.0.category_ids', '153,1424,1257');
            smileTracker.addPageVar('order.items.2.sku', 'MILL03853-XL');
            smileTracker.addPageVar('order.items.2.product_id', '436');
            smileTracker.addPageVar('order.items.2.qty', '1.0000');
            smileTracker.addPageVar('order.items.2.price', '0.0000');
            smileTracker.addPageVar('order.items.2.row_total', '0.0000');
            smileTracker.addPageVar('order.items.2.label', 'ELEVATION S GTX JACKET M ABYSS/ORION BLUE');
            smileTracker.addPageVar('order.items.2.salesrules', '');
            smileTracker.addPageVar('order.items.2.category_ids', '507,247,1627');
            smileTracker.sendTag(true);
        } catch (err) {
        ;
    }
    //→
```

## AB Campaign

If you are using Elasticsuite Premium, you will need to add campaign data in the tracking data of **every pages** if one or several campaigns are active on your website:

| Variable    | Value | 
|:-------------|:------------------|
|ab_campaign.*X*.id | Id of the campaign |
|ab_campaign.*X*.scenario | Scenario assign to this visitor for this campaign |

You can find all this data in the @AB-CAMPAIGN@ cookie (the cookie will exist only if at least one campaign is active) if you have the Magento cookies on your front or via the following  API:
Rest:

```
GET /V1/elasticsuite-ab-campaign/hasCampaigns
GET /V1/elasticsuite-ab-campaign/campaigns-scenarios
```

GraphQl:
```
query elasticsuiteAbCampaigns {
   elasticsuiteAbCampaigns {    
       campaign_id    
       scenario_id  
   }
}
```
