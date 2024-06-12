---
title: Troubleshooting
has_children: false
parent: ElasticSuite
nav_order: 199
---
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

## How to check if the tracker is working properly.

To be sure that the ElasticSuite tracker is working and collecting data, you should go first to the **Analytics** page.

In this page you should see a various number of events, and they should all look accurate to you.

If you see no events at all, or some events are missing (like 0 "Products added to cart" or 0 "Sales", etc...) , then it's likely that the tracking is not fully working as intended.

In such case, you should go through the following steps.

### Ensure the tracking is enabled.

You should ensure that the Elasticsuite tracking is active (that should be the case) via **Stores > Configuration > Elasticsuite > Tracker > Enabled**.

### Ensure tracking is firing in the front office

When you browse the front-office of your website, you should see calls to either the Elasticsuite tracking pixel, or the Elasticsuite tracking API.

Example of call to the tracking pixel (to be seen as an HTTP call to an image) :

```
https://www.myshop.com/elasticsuite/tracker/hit/image/h.png?page[store_id]=3&page[type][identifier]=catalog_product_view&page[type][label]=Catalog%20Product%20View%20(Any)&page[locale]=fi_FI&page[product][id]=646458&page[product][label]=Nike%20Shoes&page[product][sku]=E66110704&session[uid]=5fa47663-9d64-66bc-11aa-ffecc3f5b3e0&session[vid]=a59b2b7b-af85-1d28-e42e-c0d61f024066&page[site]=myshop.com&page[url]=%2Fnike-shoese66110704&page[title]=Nike%20Shoes&page[referrer][domain]=versionupdatetest.etra.fi&page[referrer][page]=%2F&page[resolution][x]=1920&page[resolution][y]=1053
```

Example of an API call (to be seen as an XHR request to the API) : 

An XHR Request to : https://www.myshop.com/rest/V1/elasticsuite-tracker/hit

With a payload looking like this one : 

```
{
    "eventData": {
        "session": {
            "uid": "c092d9dc-9665-1f82-27f9-7257a95ab95c",
            "vid": "4fdd3f9e-f062-c7cd-8bd1-90e2378e2965"
        },
        "page": {
            "type": {
                "identifier": "catalog_category_view",
                "label": "Catalog Category"
            },
            "category": {
                "id": "MzMwMg==",
                "path": "body-beauty/hair-care/shampoos",
                "label": "Shampoos"
            },
            "product_list": {
                "page_count": "6",
                "product_count": "89",
                "current_page": "1",
                "sort_order": "position",
                "sort_direction": "asc",
                "display_mode": "grid",
                "filters": {
                    "category_uid": "MzMwMg=="
                }
            }
        }
    }
}
```

In both cases, if the payload looks incomplete, check with your system integrator.

### Check that tracking data goes into the proper DB table

The events data is stored in the elasticsuite_tracking_log_event table.

So the next step is to check if this table is properly populated when browsing the website. 

You should see JSON containing the whole event data.

If you see a small json containing only something like "{image : 'h.png'}" and nothing more, you'll need to perform the actions described in [the installation page](https://elastic-suite.github.io/documentation/docs/ElasticSuite/Installing.html?qsdqsdqs#integration-with-magento-cloud-andor-fastly).

### Check that the data is properly fetched from the DB and sent to the Elasticsearch server
The data from this table is unpiled by a cronjob named @elasticsuite_index_log_event@ that is supposed to run every minutes and that will move the events from the DB into the Elasticsearch server.

You should check that this cronjob is enabled and running without issues.


