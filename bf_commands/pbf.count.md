---
title: "PBF.COUNT"
nav_order: 3
description: >
    Count item insertions into a filter
parent: "Bloom Filter"
---

# PBF.COUNT

Usage: `PBF.COUNT item element`

The `PBF.COUNT` command returns a count of how many times an item has been added to a cuckoo filter, with results within the error rate.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.COUNT PBF 42
(integer) 1
```