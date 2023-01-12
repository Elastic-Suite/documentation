---
layout: default
title: Virtual categories
has_children: false
parent: Managing product listing
grand_parent: ElasticSuite
nav_order: 3
---
It can be accessed under the Magento Catalog menu > Categories > Select a category in the tree > heading "Products in Category"

A category can be created to purposely be a virtual category or an already existing category can be switched to virtual. In that case, all products that have been placed in this category will be deleted from it.

First, the switcher "Virtual Category" has to be set to Yes, and then a rule engine will allow user to build the conditions for this virtual category : 

![virtual-category](https://user-images.githubusercontent.com/98949123/155300177-8f1a150d-0915-41f4-8fa0-3048cc29bb70.PNG)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Virtual Category|No|If set to yes, Category becomes a virtual category|
|Virtual Category Root|Default Category|This field allows to choose a category to map the virtual category on. Virtual category products will be contextualized related to this category. The facets displayed in Front-Office will too.|
|Virtual rule||The rule engine allows to configure rule to associate with this virtual category. It can be one rule or a combination of rules.|

All previews and sorting functionnalities available on standard categories will be available for virtual categories too.
