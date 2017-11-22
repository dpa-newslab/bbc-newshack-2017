---
layout: default
navigation: 'Elasticsearch Tools'
title: 'Elasticsearch Tools'
description: |
---


As a coding journalists, our first impulse is not to code, but to look around for tools that can be plugged together to explore the data and learn from there. 

Due to the restrictions for the #newsHack, none of the tools on this page could be used right off the bat. The hackathon organizers were very forthcoming, completely open to lifting the restrictions as soon as we asked, but it was not possible.

Or suggestion for future hackathons would be to think very hard about this and see why these restrictions are necessary in the first place, and if there is a way around this. 

Specifically, think about:

  - enabling CORS from the start
  - not limiting the API to GET requests (finding other ways to write-protect the Elasticsearch index) 

So below here's what we'd have liked to use. Some of these tools are used for prototypes at the dpa newslab, like [Grafana](https://grafana.com/) and [Facetview](https://github.com/okfn/facetview). The beauty of these tools is that they are almost plug-and-play. After, say, 30 Minutes of configuration you can just explore your Elasticsearch. Below is a reference of those tools - the ones we found and tried and the ones we'd like to explore in the future.

## What we use

|   |Tool| Useful for |
| --- | -----------------------------------:| ------------:|
| <img src="../img/Grafana.png" width="400px">  | [Grafana](https://grafana.com/)   | Everything that has timestamps. Can also visualize a [load of other data sources](http://docs.grafana.org/features/datasources/), like MySQL.|
| <img src="../img/Facet_view.png" width="400px">   | [Facetview](https://github.com/okfn/facetview) | Excellent search engine UI by the Open Knowledge Foundation. Unknown if it is compatible with Elasticsearch 5.x |
| <img src="../img/elasticsearch-head.png" width="400px">   | [Elasticsearch-head](https://github.com/mobz/elasticsearch-head) | Browser Plugin to compose Elasticserarch queries and do other interesting stuff |


## The Future

We've come across some tools that we'd like to explore:

|   |Prospect| Might be useful because |
| --- | -----------------------------------:| ------------:|
| <img src="../img/Searchkit.png" width="400px">   | [SearchKit](http://www.searchkit.co/) | A bunch of `react.js` components to build something on Elasticsearch - and some of us already know `react.js`. |
| <img src="../img/Kibana.png" width="400px">   | [Kibana](https://www.elastic.co/products/kibana) | The original from the guys who brought you Elasticsearch. Maybe they know best ;-) |

