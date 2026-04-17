---
layout: default
title: Facets
has_children: false
parent: Search
grand_parent: Gally
nav_order: 2
---
It can be accessed under SEARCH > Facets. This entry allows user to configure filterable attributes.

At the top of the page, a filter bar is available. User can filter based on attribute code and on attribute configuration (Display, coverage, max size and sort order).

## Configuration level

In the first column on the left, a block allowing to manage configuration level is available : 

![image](https://user-images.githubusercontent.com/98949123/212880377-4118e502-4b6b-4647-a7c1-f9b06bebf3e2.png)

|Level   | Description|
|:-------------|:------|
|Set default values|If user places himself or herself in this level, all configuration will be saved for the whole application, for all categories|
|By category|If user places himself or herself in a specific category level, configuration will only be applied for this specific category. Configuration made on a category level will not be inherited by its subcategories.|

Gally set default values for all configurations : 
* Display = Auto
* Coverage : 90%
* Max size = 10
* Sort order = Result count
* Facet internal logic = OR
* Position = 0

On "General configuration" level, if user changes values of a configuration for an attribute, the content of the field appears in bold and the default value appears below :

<img width="1458" height="350" alt="image" src="https://github.com/user-attachments/assets/a55a4be7-2912-4f2f-ac0a-38aab6da9a3d" />

On a category level, values from "General configuration" are applied by default. If values are different from configuration from General configuration level, then the content of the field appears in bold and the devault value appears below : 

<img width="1463" height="388" alt="image" src="https://github.com/user-attachments/assets/69c14a3b-62e1-41b2-84f4-c2422edbb086" />

At the top of the page in the right, user can switch all configuration to default values. Once it's pressed, all custom configuration will be lost : 

![image](https://user-images.githubusercontent.com/98949123/213145257-0130d834-b6e8-4302-b72a-4866968f394d.png)


## Filterable attribute grid

The grid with all attributes configured as filterable in Settings > Searchable and filterable attributes are displayed here :

<img width="1463" height="522" alt="image" src="https://github.com/user-attachments/assets/dee4b582-d5c5-4e92-a9ab-09796d20e34a" />

|Parameter   | Default value | Description|
|:-------------|:------------------|:------|
|Attribute code||Attribute code used to identified the attribute|
|Display|Auto|It allows to configure how facet is displayed in front. <br/>- Auto : The filter will be displayed according to its coverage rate. This is the standard behavior and will automatically hide filter if it’s not relevant (not covering enough products) for the category. <br/>- Always displayed : The filter will be always displayed and not take the coverage rate into account.<br/>- Always hidden : This filter will never be displayed, even if it could have been relevant.|
|Coverage|90|The minimum coverage rates of results by this attribute.<br/>Example, if set to 90% on the "Brand" attribute, the facet will be displayed only if 90% of the products in the search results or category have the brand attribute contributed.|
|Max size|10|The maximum number of values that will be displayed for this facet. If the attribute features more values than this limit, a "Show more" button will be displayed after the values listing and an autocomplete search box will appear automatically above the values listing.|
|Sort order|Result count|This is how the facet values will be ordered. <br/>- Result count : Will order values according to their number of results (descending). <br/>- Admin sort : Values will be displayed as ordered in attribute's options values. <br/>- Name : Values will be displayed alphabetically (ascending).|
|Facet internal logic|Logical OR|Defines the filtering behavior when a user selects multiple values within this specific facet. <br><br> • **Logical OR** (default): Products matching *any* of the selected values will be displayed (e.g., selecting 'size M' and 'size L' shows products that are either size M OR size L). <br> • **Logical AND**: Only products matching *all* of the selected values will be displayed (e.g., selecting 'blue' and 'red' shows only products that are both blue AND red). |
|Position|0|This configuration allows to sort facets in layered in navigation. Position = 0 --> the facet will be displayed first, then Position = 1, then Position = 2 and so on. <br/> Caution : as the default position is 0, if only one facet is changed from 0 to 1, it will be placed in the last position. If Position is configured, user has to make sure that all facets have a position.|

Attributes can be selected in the user grid. Once it's the case, an action bar appears allowing to mass edit attributes and change their configuration : 

<img width="1496" height="727" alt="image" src="https://github.com/user-attachments/assets/0321cf00-4fdf-4df5-8ae0-516857d398b7" />

Every configuration (Display, Coverage, Max size, Sort order, Facet internal logic, Position) can be managed in the action bar.
