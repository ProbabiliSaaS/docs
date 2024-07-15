---
title: "PBF.ADDNX"
nav_order: 2
description: >
    Add an item to a cuckoo filter if the item does not exists
parent: "Bloom Filter"
---

# PBF.ADDNX

Usage: `PBF.ADDNX key item`

The `PBF.ADDNX` command adds an item to a filter if the item does not exists. If a filter does not exist, a new one will be created.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.COUNT PBF 42
(1)
127.0.0.1:6379> PBF.ADDNX PBF 42
(true)
127.0.0.1:6379> PBF.COUNT PBF 42
(1)
127.0.0.1:6379> PBF.ADDNX PBF 42
(false)
127.0.0.1:6379> PBF.COUNT PBF 42
(1)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.COUNT PBF 42
(2)
```