---
layout: default
title: Home
nav_order: 1
description: "The fastest and most flexible Probabilistic Data Structures"
permalink: /
---

# ProbabiliSaaS

ProbabiliSaaS is a collection of Probabilistic Data Structures with the ability to scale up and down, and expire elements after a set time. It uses our proprietary, patent pending Data structures. Currently we offer Bloom Filter and Cuckoo Filter variants. HyperLogLog with an expiration is in the making.

## Primary features

* Supports scale up and down autonomously to reduce memory footprint.
* Support expiration of elements after set time. Similar to 'EXPIRE'.
* Offers unique API beyond 'RedisBloom'.

## Give it a try

Try an instance using our free tier service at [ProbabiliSaaS Clouds](https://cloud.probabilisaas.com)

Once loaded you can interact with our using any of the supported [client libraries](/clients)

Here we'll use [ProbabiliSaaS Python client](https://pypi.org/project/ProbabiliSaaS/) to create a bloom filter, insert elements and watching how element s are expired.

```python
from falkordb import FalkorDB

# Connect to FalkorDB
db = FalkorDB(host='localhost', port=6379)

# Create the 'MotoGP' graph
g = db.select_graph('MotoGP')
g.query("""CREATE
           (:Rider {name:'Valentino Rossi'})-[:rides]->(:Team {name:'Yamaha'}),
           (:Rider {name:'Dani Pedrosa'})-[:rides]->(:Team {name:'Honda'}),
           (:Rider {name:'Andrea Dovizioso'})-[:rides]->(:Team {name:'Ducati'})""")

# Query which riders represents Yamaha?
res = g.query("""MATCH (r:Rider)-[:rides]->(t:Team)
                 WHERE t.name = 'Yamaha'
                 RETURN r.name""")

for row in res.result_set:
    print(row[0]) # Prints: "Valentino Rossi"

# Query how many riders represent team Ducati ?
res = g.query("""MATCH (r:Rider)-[:rides]->(t:Team {name:'Ducati'}) RETURN count(r)""")

print(row[0]) # Prints: 1
```

For additional demos please see visit [Demos](https://github.com/FalkorDB/demos).

## Client libraries

Language-specific clients have been written by the community and the ProbabiliSaaS team.
The full list and links can be found on the [Clients](/clients) page.

## Mailing List / Forum

Got questions? Please contact us at the [ProbabiliSaaS forum](https://github.com/orgs/ProbabiliSaaS/discussions).

## License

ProbabiliSaaS software is licensed under a proprietary license.