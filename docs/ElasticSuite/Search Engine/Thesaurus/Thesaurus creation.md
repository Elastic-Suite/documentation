---
layout: default
title: Thesaurus creation
has_children: false
parent: Thesaurus
grand_parent: Search Engine
nav_order: 1
---
You can access the Thesaurus administration via the **ElasticSuite > Thesaurus** menu. 

From this grid, you can create, update, and delete your thesauri.

### Creating a Thesaurus

The main page displays a grid of all your existing thesauri. To add a new one, click the **Add Thesaurus** button.

When creating a new thesaurus, the first step is to choose its type. **⚠️ Beware: The type cannot be modified once the thesaurus is created.**

#### Synonym

<img width="631" alt="configuration-synonym-creation" src="https://user-images.githubusercontent.com/98949123/152959831-bd296d83-a678-404b-8acf-2591e2116432.PNG">

| Parameter | Description |
|:----------|:------------|
| Thesaurus name | The internal name for this synonym rule. |
| Active | Toggles whether the synonym rule is enabled or disabled. |
| Store | Defines the scope of the synonym. Thesauri can only be applied at the store view level. |

A **Synonym** thesaurus allows you to create separate lists of words that share the exact same meaning and should be treated identically by the search engine.

<img width="292" height="153" alt="image" src="https://github.com/user-attachments/assets/70763542-00bf-4333-81b3-f32f5c8e34c4" />

You can add as many word lists as you need. The terms in each list must be **comma-separated**. 

*In the example above, we created a synonym relationship between "tank", "t-shirt" and "top".*

#### Expansion

<img width="631" alt="configuration-expansion-creation" src="https://user-images.githubusercontent.com/98949123/152960658-111deebf-b7a7-436a-bdf2-d40ff56803f6.PNG">

| Parameter | Description |
|:----------|:------------|
| Thesaurus name | The internal name for this expansion rule. |
| Active | Toggles whether the expansion rule is enabled or disabled. |
| Store | Defines the scope of the expansion. Thesauri can only be applied at the store view level. |

An **Expansion** thesaurus allows you to define a reference term and associate it with a list of broader or related expansion terms.

![expansions](https://user-images.githubusercontent.com/98949123/152957001-80d9c359-5d24-4522-962b-da0a0ebe0f32.png)

You can add as many groups of words as you need. Each group must be **comma-separated**.

*In the example above, we created an expansion from the core reference term "sport" to the related terms "fitness", "gym", and "running".*

### Updating a Thesaurus

You can edit any previously created thesaurus to add, modify, or remove elements (such as adding a new synonym list or tweaking an expansion).

### Removing a Thesaurus

You can remove a previously created thesaurus directly from the main grid, or by clicking the **Delete Thesaurus** button on the specific Thesaurus edit page.

