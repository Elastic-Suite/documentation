---
layout: default
title: Elasticsearch Client
has_children: false
parent: Base Settings
grand_parent: Settings
---

<img width="504" alt="base-settings" src="https://user-images.githubusercontent.com/98949123/155967436-1b226fc7-fc0f-453d-9fea-1e30d6987d40.PNG">

Parameter                          | Default value  | Description
-----------------------------------|----------------|------------
ElasticSearch Servers List         | localhost:9200 | This a comma-separated list of servers in the [host]:[port] format where you should indicate all your ElasticSearch nodes. E.g. : "es-node1.fqdn:9200, es-node2.fqdn:9200".
Use HTTPS                          |             No | Enable this parameter if you want to access to your Elasticsearch server through https.
Enable basic HTTP authentication   |             No | Enable this one if your Elasticsearch server uses basic HTTP authentication
Basic HTTP authentication user     |          empty | If you are using HTTP authentication, set your user auth in this field.
Basic HTTP authentication password |          empty | If you are using HTTP authentication, set your user password in this field.
Enable debug mode                  |             No | When this parameter is set to "Yes", the module produces logs through the Magento logging system.
Server connection timeout          |             1  | In seconds, the default timeout used when querying the server.
