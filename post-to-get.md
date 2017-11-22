---
layout: default
navigation: 'Elasticsearch Tools'
title: 'post-to-get.py'
description: |
---

```python

import hug
import requests
import json

HOST="http://summadb.summa-project.eu/"

def cors_support(response, *args, **kwargs):
    response.set_header('Access-Control-Allow-Origin', '*')



@hug.post(['/{indexname}/_search',
           '/{indexname}/_msearch',
           '/{indexname}/_mmap'],requires=cors_support)
def mi_search(indexname=None, body=None):
    """ forwards POST to GET """
    print("POST to GET")
    myurl=f"{HOST}{indexname}/_search"
    print(f"Going {myurl}")
    return requests.get(myurl,params={ "source" : json.dumps(body) }).json()


@hug.get(['/{indexname}/_search',
           '/{indexname}/_msearch',
           '/{indexname}/_mmap'],requires=cors_support)
def passthrough(indexname=None,**kwargs) :
    print("INDEXNAME")
    myurl=f"{HOST}{indexname}/_search"
    print(f"Going {myurl}")
    result = requests.get(myurl,params=kwargs)
    try :
        return result.json()
    except  json.decoder.JSONDecodeError :
        return result.content



@hug.get('/{indexname}',requires=cors_support)
def passthrough(indexname=None,**kwargs) :
    myurl=f"{HOST}{indexname}"
    print(f"Going {myurl}")
    return requests.get(myurl,params=kwargs).json()

@hug.get('/{indexname}/{other}',requires=cors_support)
def passthrough_2(indexname=None,other=None,**kwargs) :
    myurl=f"{HOST}{indexname}/{other}"
    print(f"Going {myurl}")
    return requests.get(myurl,params=kwargs).json()

@hug.get('/{indexname}/{other}/{third}',requires=cors_support)
def passthrough_2(indexname=None,other=None,third=None,**kwargs) :
    myurl=f"{HOST}{indexname}/{other}/{third}"
    print(f"Going {myurl}")
    return requests.get(myurl,params=kwargs).json()



```

