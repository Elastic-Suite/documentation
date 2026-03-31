---
layout: default
title: Behavioral autocomplete
has_children: false
parent: Settings
grand_parent: ElasticSuite
nav_order: 18
---

It can be accessed under the Stores menu > Configuration > ElasticSuite entry > Behavioral autocomplete entry

## Trend Based Autocomplete

<img width="479" alt="behavioral-autocomplete" src="https://user-images.githubusercontent.com/98949123/156197639-258b50a7-ce42-4251-8bac-e650fadb551d.PNG">

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| Enabled | Yes | Determines how popular search terms are surfaced in the autocomplete dropdown. <br><br>• **Yes:** Suggests *trending* search terms (terms gaining recent popularity). <br>• **No:** Suggests search terms with the highest *overall historical usage*. <br><br>⚠️ *Note: Elasticsuite's behavioral tracking must be enabled and actively collecting data for either of these options to function.* |

## Tweaks

<img width="1011" height="228" alt="image" src="https://github.com/user-attachments/assets/9f3dba2d-d85f-4db1-9f84-f365a76e3ded" />

| Parameter | Default value | Description |
|:----------|:--------------|:------------|
| [Experimental] Show raw search terms | No | Controls how accented characters are displayed in autocomplete suggestions. <br><br>• **Yes:** Displays popular search terms exactly as users typed them (in their most popular "raw" form) rather than a basic, "ASCII-folded" standardized form [1]. This is highly recommended for languages that utilize accents and diacritics. <br>• **No (Default):** Displays the standardized, unaccented form. <br><br>*Example:* If French users frequently search for "boîte à thé", the default legacy behavior strips the accents and suggests "boite a the". Enabling this setting ensures the correctly accented "boîte à thé" is displayed [1]. <br><br>⚠️ *Note: Because this setting relies on raw user input, enabling it means the autocomplete might occasionally display uppercase or mixed-case search terms.* |

