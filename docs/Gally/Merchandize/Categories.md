---
layout: default
title: Categories
has_children: false
parent: Merchandize
grand_parent: Gally
nav_order: 1
---

It can be accessed under MERCHANDIZE menu : MERCHANDIZE > Categories.
This entry allows user to manage product in categories, configure virtual categories and organize product sorting.

## Scope selection

At the top left of the page, a catalog selector is available.

![image](https://user-images.githubusercontent.com/98949123/211284767-27d50fe2-c897-406c-afd3-d362bbbdb9bc.png)

In this dropdown, all catalogs available in the e-commerce application will be listed. 
If “All catalog” is selected, then configurations will be applied to categories for all scopes.
If a specific catalog is selected, then configurations will be applied to categories only for this specific catalog.

 If user selects a specific catalog, a second dropdown will be displayed. It will allow user to select a specific locale.

![image](https://user-images.githubusercontent.com/98949123/211284831-5497004c-48ec-4496-8319-a69e67817c13.png)

If “All locals” is selected, then configurations will be applied to categories for the specific catalog selected in the first dropdown but applied for all locales within this catalog.
If a specific locale is selected, then configurations will be applied to categories only for the specific catalog selected in the first dropdown and this specific locale.

## Category tree

Category tree(s) is(are) displayed below scope dropdowns : 

![image](https://user-images.githubusercontent.com/98949123/211284921-b7caa6ed-b4e7-453d-95d8-8229240a015f.png)

If scope = All catalogs, all root categories are displayed. According to selected scope, root categories that don’t belong to the selected catalog, will no longer be displayed.

By selecting a category in the tree, corresponding products will be displayed accordingly and configuration will be applied to selected category.

## Category configuration 

Once user selected a category, following configuration will be available : 

![image](https://user-images.githubusercontent.com/98949123/211284999-8b87e336-1ecf-4398-b5ed-a4faec422f05.png)

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Use category name in product search|Yes|If set to yes, when the category name is used in search, then products contained in this category will be displayed as results.|
|Default sorting|Position|Will set the default sorting for products in the category. <br/> Position : products will be sorted according to user’s merchandising (pin products and boost) <br/> Relevance : products will be sorted according to product score <br/> Other sortable attributes : in settings > filterable and searchable attributes, user can set attributes as sortable. All sortable attributes will be available in the dropdown. If selected, product will be sorted according to the selected attribute|
|Virtual attribute|No|If set to yes, category becomes virtual and the rule engine appears : ![image](https://user-images.githubusercontent.com/98949123/211285081-50b745a1-4619-4b29-9f0b-e535306e072d.png)<br/> Products will be placed in the category according to configuration in the rule engine.<br/>Note : Virtual categories configuration is described in a dedicated section.|

All configuration on this page must be saved in order to be effective.

## Product grid
 
Once user selects a category in the category tree, products from this category are displayed in the product grid.

![image](https://user-images.githubusercontent.com/98949123/211290954-46088219-cf6b-42e1-9eda-a646df11ea05.png)

Grid contains following columns :
 
|Selection |Code |Image |Name |Score |Stock |Price |Display |
|:-------------|:------------------|:------|:------|:------|:------|:------|:------|
|Checkbox for selecting products and pin or unpin products (see dedicated section)|Product SKU|Image of the product. The base image is displayed on Gally, other images are not displayed.|Product label|Product score. If boosts are applied on this category listing, score will be affected (detail for boost calculation is described in a dedicated section.|Stock status. 2 possible values : "In stock" or "Out of stock"|Product price|Switcher allowing to display or hide a in front.|

This product grid is a preview area. It means that sorting must be the same then the e-commerce front application.

## Pin and unpin products

User can pin and unpin products at the top of product listing. 
This feature is available only if category default sorting = Position.

Products can be selected in the user grid. Once it's the case, an action bar appears : 

![image](https://user-images.githubusercontent.com/98949123/211294079-1cbf76a6-4769-4f70-ac86-a422949f4c64.png)

If products are selected on the standard grid, products will be pinned at the top products block : 
![image](https://user-images.githubusercontent.com/98949123/212338480-5175f61e-2b79-4208-94b7-b6187a1cacd1.png)

Once products are pinned at the top of product listing, their score no longer manners for sorting them in the product listing. Products are manually placed in this position and will not moove from it.

Products in the top products block can be unpinned. Once products are selected, and action bar appears : 

![image](https://user-images.githubusercontent.com/98949123/212869955-d05bbd05-e4a4-4134-9be1-2c4092e3d68d.png)

By clicking on unpin, products will be placed back in their original position (according to their score).

Configurations must be saved in order to be effective.

