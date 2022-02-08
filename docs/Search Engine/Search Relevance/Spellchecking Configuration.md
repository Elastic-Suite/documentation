---
layout: default
title: Spellchecking Configuration
has_children: false
parent: Search Relevance
grand_parent: Search Engine
nav_order: 2
---

Spellchecking configuration is editable via a dedicated screen in the back-office.

It can be accessed by going to ELASTICSUITE > Search Engine > Search Relevance > Spellchecking Configuration.

## Search Fuzziness Configuration

Fuzzy queries uses a distance algorithm to calculate matching terms within a specified edit distance related to the current search terms.
This is used to **fix misspelled terms in queries**.

See also the official documentation here : [ElasticSearch Fuzzy Query](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html#query-dsl-fuzzy-query)

![fuziness](https://user-images.githubusercontent.com/98949123/152805108-309b0563-63e6-4dd5-b333-3faebf406b38.PNG)

Parameter                    | Default value  | Description
-----------------------------|----------------|------------
Enable fuzziness             |           Yes  | Set it to "Yes" to enable fuzzy queries to the engine.
Fuzziness value              |           **<br/>Automatic <br/>1 <br/>2**| The maximum edit distance for a fuzzy query. <br/>AUTOMATIC : spellchecking will be ajusted according to word length. <br/>1 : only one edit authorized. <br/>2 : two edits authorized. More informations in [the fuzzy query documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html#_parameters_7).
Fuzziness Prefix Length      |              1 | The number of initial characters that must not be "fuzzified". More informations in [the fuzzy query documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html#_parameters_7).
Fuzziness Max. expansion     |             10 | Maximum number of terms the fuzzy query will expand to. More informations in [the fuzzy query documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-fuzzy-query.html#_parameters_7).

## Phonetic Search Configuration

**This requires the Phonetic Analysis Plugin : [Phonetic Analysis Plugin](https://github.com/elastic/elasticsearch/tree/master/plugins/analysis-phonetic)**

Phonetic search provides a variety of filters that convert tokens to their phonetic representation.

Phonetic search can be also improved with fuzziness. The parameters are used the same way as described above.

Official documentation related to phonetic search : [ElasticSearch Phonetic Search](https://www.elastic.co/guide/en/elasticsearch/plugins/master/analysis-phonetic.html)

![phonetic](https://user-images.githubusercontent.com/98949123/152805685-81c3c31d-2058-4817-89f1-a5feb3496cdd.PNG)

Parameter                             | Default value  | Description
--------------------------------------|----------------|------------
Enable phonetic search                |           Yes  | Set it to "Yes" to enable phonetic search.
