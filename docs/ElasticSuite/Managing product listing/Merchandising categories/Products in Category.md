---
layout: default
title: Products in Category
has_children: false
parent: Merchandising categories
grand_parent: Managing product listing
nav_order: 2
---
It can be accessed under the catalog menu > category > select the category in the tree > Expand "products in Category".
These functionnalities can be used both for standard categories and virtual categories.

![product-in-category1](https://user-images.githubusercontent.com/98949123/154659268-28bab1a1-d313-44cd-96d4-1239b1eac7f7.PNG)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Virtual Category|No|Switch the category to virtual (for more details, see Virtual category section)|
|Ajouter/Supprimer des produits (Add/Delete products)||This button is only displayed for standard categories. <br/> Opens a popup where products can be selected in the grid or by searching product by SKU and be added to the category|
|Display potentially applied optimizers||Allows to open the optimizer grid that are applied to products of this category|
|Default Product Listing Sort By|Position|4 possible options : <br/> - Position : products are sorted according to position given by boosts, drag and drop... <br/> - Product name : products are ordered in alphabetical order based on their name <br/> - Price : products are sorted according to ascending price <br/> - Performance : Products that have the best performance are sorted first|

![product-listing-category](https://user-images.githubusercontent.com/98949123/154704869-3330dd89-574a-4ef4-af17-d68061a571bc.PNG)

| Parameter    | Description |
|:-------------|:------|
|Refine search|Allows to search for products within this category|
|Clear product positions|Sort products according to automatic sorting. All manual sorting will be lost|
|Drag and dropper|Allows to move product manually in the category. This action is possible only on products in "Manual sort" mode|
|Show/hider|Allows to hide or show a product on front. If hidden, products will not be displayed in front, but will stay in the category|
|Green/red tag|If green : product has been viewed this week. Tooltip is displayed in mousehover and gives the number of views this week for this product <br/> If red : product has not been viewed this week|
|Switcher automatic or manual sort mode|If Automatic sort : product will be sorted according to sorting configuration and boosts. <br/> If Manual sorting : product is pinged to this position and can be dragged and droped to another position (only among products that are on manual mode)|

When you display out of stock products in the frontend, it can be annoying that a product manually positioned in a category or for a search query be still displayed at the configured position when it is no longer in stock.
A new setting named “Ignore manual positions of out of stock products” available in “Stores > Configuration > Elasticsuite > Catalog Search > Catalog Search Configuration” can now prevent this situation.

![image](https://github.com/Elastic-Suite/documentation/assets/98949123/7aeca0ce-4f81-4335-8640-6609b07d32c5)



