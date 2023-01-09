---
layout: default
title: Categories
has_children: false
parent: Merchandize
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

| Parameter   | Default value | Description |
|:-------------|:------------------|:------|
|Use category name in product search|Yes|If set to yes, when the category name is used in search, then products contained in this category will be displayed as results.|
|Default sorting|Position|Will set the default sorting for products in the category. 
Position : products will be sorted according to user’s merchandising (pin products and boost)
Relevance : products will be sorted according to product score
Other sortable attributes : in settings > filterable and searchable attributes, user can set attributes as sortable. All sortable attributes will be available in the dropdown. If selected, product will be sorted according to the selected attribute|
|Virtual attribute|No|If set to yes, category becomes virtual and the rule engine appears : ![image](https://user-images.githubusercontent.com/98949123/211285081-50b745a1-4619-4b29-9f0b-e535306e072d.png)
Products will be placed in the category according to configuration in the rule engine.|

All configuration on this page must be saved in order to be effective.



