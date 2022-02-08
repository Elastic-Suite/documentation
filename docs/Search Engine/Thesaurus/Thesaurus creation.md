---
layout: default
title: Thesaurus creation
has_children: false
parent: Thesaurus
grand_parent: Search Engine
nav_order: 2
---
## Thesaurus Administration

It can be accessed under the Smile ElasticSuite menu, via the Thesaurus entry.

You can create, update and delete your thesauri here.

### Creating a Thesaurus

In this page you have a grid displaying all your thesauri. You can add a new one by clicking on the **Add Thesaurus** button.

First thing you will be prompted on when creating a thesaurus is choosing a type. **Beware, the type can not be modified once the thesaurus is created.**

#### Synonym

<img width="631" alt="configuration-synonym-creation" src="https://user-images.githubusercontent.com/98949123/152959831-bd296d83-a678-404b-8acf-2591e2116432.PNG">

| Parameter    | Description |
|:-------------|:------|
|Thesaurus name|Name the synonym|
|Active|The synonym will be active or not|
|Store|Scope of the synonym. Synonym can only be applied at storeview level.|

Synonyms thesaurus will allow you to add separated lists of words that are synonyms of each other.

![synonyms](https://user-images.githubusercontent.com/98949123/152956847-2e2cb442-7d04-492e-8bb9-c682bae36189.png)

You can add as many list of words as you need. Each list of words has to be **comma-separated**.

In the example above, we have added a synonym between "man" and "men", and also between "woman" and "women".

#### Expansion

<img width="631" alt="configuration-expansion-creation" src="https://user-images.githubusercontent.com/98949123/152960658-111deebf-b7a7-436a-bdf2-d40ff56803f6.PNG">

| Parameter    | Description |
|:-------------|:------|
|Thesaurus name|Name the expansion|
|Active|The expansion will be active or not|
|Store|Scope of the expansion. Expansion can only be applied at storeview level.|

Expansions thesaurus will allow you to add separated lists of words that are expansions of a reference term.

![expansions](https://user-images.githubusercontent.com/98949123/152957001-80d9c359-5d24-4522-962b-da0a0ebe0f32.png)

You can add as many bag of words as you need. Each bag of words has to be **comma-separated**.

In the example above, we have added an expansion from the reference term "sport" to the terms "fitness", "gym" and "running".

### Updating a Thesaurus

You can edit a previously created thesaurus and add or remove some elements (a new synonym list or a new expansion).

### Removing a Thesaurus

You can remove a previously created thesaurus from the grid or by clicking the **Delete Thesaurus** button on the Thesaurus edit page.

## How does it works ?

Given the 2 precedent examples, someone searching for "women sport pants" on the website will trigger the following search queries :

* women sport pants (the base query)
* woman sport pants (based on the women/woman synonym)
* women fitness pants (based on the expansion on "sport")
* women gym pants (based on the expansion on "sport")
* women running pants (based on the expansion on "sport")
* woman fitness pants (based on the women/woman synonym and the expansion on "sport")
* woman gym pants (based on the women/woman synonym and the expansion on "sport")
* woman running pants (based on the women/woman synonym and the expansion on "sport")

The generated "extended queries" will be weighted according to the [Thesaurus configuration](https://elastic-suite.github.io/documentation/docs/Search%20Engine/Search%20Relevance/Thesaurus%20Configuration.html)

NB : Technically speaking, it will only generate one query to the engine, with a boolean structure.
