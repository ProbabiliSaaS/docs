---
title: "FBF.ADD"
nav_order: 4
description: >
    Add an item to a filter
parent: "Bloom Filter"
---

# FBF.ADD

Usage: `FBF.ADD key item`

The `FBF.ADD` command adds an item to a filter. If a filter does not exist, a new one will be created.

Example:

```bash
127.0.0.1:6379> FBF.RESERVE FBF CAPACITY 64 ERROR 0.01
(true)
127.0.0.1:6379> FBF.EXISTS FBF 42
(false)
127.0.0.1:6379> FBF.ADD FBF 42
(true)
127.0.0.1:6379> FBF.EXISTS FBF 42
(true)
```
