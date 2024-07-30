---
layout: default
title: Extending Instant Search
has_children: false
parent: Extending
grand_parent: ElasticSuite
nav_order: 1
---

This is a quick walkthrough if you plan to extend the React based components used for building the Instant Search module.

Here is the way to go for overriding the Product component of the Instant search, in order to hide the Price Block, but this could be declined to other components as well : 
 
- In the `view/frontend` of a custom module add a directory `react_source`
- Create a `_component.js` file with the following content : `DataProviderComponents['product'] = ProductWithoutPrice;`
- Create a `_imports.js` file with the following content : `import ProductWithoutPrice from 'ProductWithoutPrice';`
- Create a copy of the file `vendor/smile/module-elasticsuite-instant-search/view/frontend/react_source/Product.js` in this directory, name it `ProductWithoutPrice.js`
- This object will inherit the legacy Product object and that's where you'll remove the price block, so the content of the object could be something like the one attached to the ticket.
- Rebuild the react app in order to test it locally yarn dev
- Check that everything works as expected.
 
You can find an example in [this Git repository](https://github.com/Elastic-Suite/extending-instant-search-example) that is hiding the PriceBlock for the products.
 
You can put this module into `app/code/Elasticsuite/Autocomplete` if you want to use it as a base for your local customization.
