---
layout: default
title: Sliders
has_children: false
nav_order: 3
parent: Filters and attributes
---

Elastic Suite allows to display custom attributes with sliders (Price for example).

### Prerequisites

* Attribute values must be exclusively digits
* Attribute must use "Decimal Number" as imput validation, or "price" as input type.

your attribute values must be exclusively digits
you must specify that your attribute is using "Decimal Number" as imput validation, or "price" as input type.

Following will use the attribute "Temperature" as an example.

## Create the attribute

Under Stores > Product > Attributes > create a new attribute

The attribute must be named and Input type must be "Text Field" and Input Validation for store Owner = Decimal Number

![temperature-init](https://user-images.githubusercontent.com/98949123/155737364-835f2ba4-4118-485b-b0af-947152722de8.png)

![decimal-number](https://user-images.githubusercontent.com/98949123/155737381-8ded2b24-90b6-42bf-8486-37cba7b37b93.png)

Next step is to configure the attribute for being filterable in layered navigation and/or in search. 

Back in tab StoreFront properties, a fieldset  **Slider Display Configuration** is available. In this fieldset, the display of your newly created attribute can be configured :

![slider-config](https://user-images.githubusercontent.com/98949123/155738413-a3743414-b144-4e5f-92d5-96fa1aa6faa7.png)

| Parameter    | Default value | Description |
|:-------------|:------------------|:------|
|Display pattern||In this field, a pattern for the slider can be entered. "%s" represents the value. So if "%s °C" is typed, result can be "20 °C".|
|Display precision|0|The number of digits to show for precision when filtering. If set to 0, the slider will only display integer values.|

Once it's done, Attributes values can be contributed for products. A full reindex is needed to see result in frontoffice.

The slider should now be displayed in the Front-Office :

![slider-front](https://user-images.githubusercontent.com/98949123/155739050-90851e63-814c-4dc3-9191-9e8ca039950a.png)

