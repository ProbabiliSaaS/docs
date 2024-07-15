---
title: "PBF.ADD"
nav_order: 1
description: >
    Add an element to a filter
parent: "Bloom Filter"
---

# PBF.ADD

Usage: `PBF.ADD key item`

The `PBF.ADD` command adds an item to a filter. If a filter does not exist, a new one will be created.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.EXISTS PBF 42
(false)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.EXISTS PBF 42
(true)
```