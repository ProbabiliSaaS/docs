---
title: "ECF.SET"
nav_order: 1
description: >
    Adds elements into filter. Create filter if it does not exist
parent: "Commands"    
---

# ECF.QUERY

Adds elements into filter. Create filter if it does not exist.

Arguments: `Filter name, Parameters, Elements [optional]`

Returns: [Result set](/design/result_structure)

### Queries and Parameterized Queries

The execution plans of queries, both regular and parameterized, are cached (up to [CACHE_SIZE](/configuration#cache_size) unique queries are cached). Therefore, it is recommended to use parameterized queries when executing many queries with the same pattern but different constants.

Query-level timeouts can be set as described in [the configuration section](/configuration#timeout).

#### Command structure

`GRAPH.QUERY filter_name [PARAMS params] ELEMENTS Element [Element ...]`

example:

```sh
ECF.SET user_42 Params 34961249 ELEMENTS towel babylon
```

#### Parametrized query structure:

`GRAPH.QUERY graph_name "CYPHER param=val [param=val ...] query"`

example:

```sh
GRAPH.QUERY us_government "CYPHER state_name='Hawaii' MATCH (p:president)-[:born]->(:state {name:$state_name}) RETURN p"
```

### Query language

The syntax is based on [Cypher](http://www.opencypher.org/). [Most](/cypher/cypher_support) of the language is supported. See [Cypher documentation](/cypher/cypher).