---
title: "PBF.DEL"
nav_order: 4
description: >
    Delete an element from a filter
parent: "Bloom Filter"
---

# PBF.DEL

Usage: `PBF.DEL filter element`

The `PBF.DEL` command delete an element from the filter. If the filter has multiple copies, the oldest copy is removed.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.DEL PBF 42
(false)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.DEL PBF 42
(true)
127.0.0.1:6379> PBF.DEL PBF 42
(false)
```