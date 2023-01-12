---
layout: default
title: Category level
has_children: false
nav_order: 2
parent: Filters and attributes
grand_parent: ElasticSuite
---

ElasticSuite allows to customize layered navigation configuration of each category.

It can be access under the Display Settings tab on a category edit page.

Under this tab, a new entry called Layered Navigation Filters is available.

Please note this entry only appear on existing categories. The Layered Navigation Filters entry will not be displayed when creating a category.

![facet-by-category](https://user-images.githubusercontent.com/98949123/155732918-8e611431-8be2-4245-a5e5-46b572c74ed2.png)

The grid will allow to customize filterable attributes for the current category.

## Manage filter position

The first main thing is that it's possible to change the position of each filter. By default, each filter is using the global position value which has been defined inside Stores > Attributes > Product page.

Here, it's possible to reorganize them so they will fit better with this category.

This is useful if the store is selling a large variety of products : "Author" and "Theme" attributes will be set on top for books related categories, but they have no sense on DVD related categories.

To reorder the filters just click on the Pinned switch on the right column : the filter will be moved on top of the list.

Then pinned items can be reorganized via drag-and-drop to perfectly fit the ordering that suits the best for this category.

When an item is unpinned, it will take back its original position.

![pin-move-filter](https://user-images.githubusercontent.com/98949123/155734055-a774213e-4fed-4227-a0d3-74d74a594f27.gif)

## Manage filter display

The way filters are displayed in this specific category can also be configured here.

The default value of each fields are the one that have been set for this attribute in the admin configuration.

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Drag and dropper||Only displayed if the attribute is pinned|
|Display Mode|Auto|This is how the filter will be displayed. <br/> - Auto : The filter will be displayed according to its coverage rate. This is the standard behavior and will automatically hide filter if it's not relevant (not covering enough products) for the category. <br/> - Always displayed : The filter will be always displayed and not take the coverage rate into account. <br/> - Always hidden : This filter will never be displayed in this category, even if it could have been relevant.|
|Facet coverage rate|Attribute global value|This can be edited in combination with Display Mode : auto to widen or reduce the minimum coverage rate for an attribute on the current category. <br/> The minimum coverage rates of results by this attribute. <br/> Example, if set to 90% on the "Brand" attribute, the facet will be displayed only if 90% of the products in the search results or category have a brand.|
|Facet max. size|Attribute global value|The maximum number of values that will be displayed for this facet. If the attribute features more values than this limit, a Show more button will be displayed after the values listing and an autocomplete search box will appear automatically above the values listing.|
|Facet sort order|Attribute global value|This is how the facet values will be ordered. <br/> Result count : Will order values according to their number of results (descending). <br/>Admin sort : Values will be displayed as ordered in attribute's options values in Magento back-office. <br/>Name : Values will be displayed alphabetically (ascending). <br/>Relevance : Values are displayed by relevance.|
|Pinned|Unpinned|See above|

