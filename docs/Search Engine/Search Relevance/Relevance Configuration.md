---
layout: default
title: Relevance Configuration
has_children: false
parent: Search Relevance
grand_parent: Search Engine
nav_order: 1
---

# Fulltext search relevance configuration

Search relevance configuration is editable via a dedicated screen in the back-office.

It can be accessed by going to ELASTICSUITE > Search Engine > Search Relevance > Relevance Configuration.

## Fulltext base settings

This panel contains base fulltext configuration settings.

![fulltext-base-settings](https://user-images.githubusercontent.com/98949123/152519823-f2c48223-b305-457e-815b-2587ca3c75e2.png)

Parameter                    | Default value  | Description
-----------------------------|----------------|------------
Minimum should match         |           100% | The minimum number of terms that should match a fulltext query (except stopwords managed by Cutoff Frequency, see the *CutoffFrequency* part below).<br/> You can look on the [official documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-minimum-should-match.html) for minimum_should_match available values.
Tie breaker                  |              1 | The way to calculate documents scores. <br/> When set to 1, a document score will be the sum of all its fields score.<br/> If set to an arbitrary value of 0.3, document score will be its higher field score **+** the sum of each other fields score * 0.3. <br/><br/> You can refer to [the documentation about tie breaker](https://www.elastic.co/guide/en/elasticsearch/reference/2.2/query-dsl-multi-match-query.html#_literal_tie_breaker_literal).

## Phrase match configuration

Phrase matching enables you to apply a boost on documents that contains *some* of your search terms, in the *same position* relative to each others.

E.g : For the query "the little white horse", we will look for documents matchin "little white", "white horse" or "little white horse".

This feature is based on ElasticSearch Shingle Token Filters, for which you can find more documentation here : [ElasticSearch Shingle Token Filter](https://www.elastic.co/guide/en/elasticsearch/reference/current/analysis-shingle-tokenfilter.html)

![phrasematch-config](https://user-images.githubusercontent.com/98949123/152519954-3514b47c-5fc2-4252-8824-a6212ce976dc.png)

Parameter                    | Default value  | Description
-----------------------------|----------------|------------
Enable boost on phrase match |            Yes | Set to "Yes" to enable phrase match.
Phrase match boost value     |             10 | The boost that will be applied on documents considered as matches.

## Cutoff Frequency

Cutoff Frequency allows specifying an arbitrary frequency where high frequency terms (above the cutoff) are not scored for each query.
This is used as an **automatic stopwords detection** based on their frequency in index.

You can go further with the official documentation here : [ElasticSearch Cutoff Frequency](https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-query.html#query-dsl-match-query-cutoff)

![cutoff-frequency-config](https://user-images.githubusercontent.com/98949123/152519984-93081ffb-ef80-420a-ba0b-16d8d9945e99.png)

Parameter                    | Default value  | Description
-----------------------------|----------------|------------
Cutoff Frequency             |           0.15 | The cutoff frequency value, as a float number between 0 and 1.
