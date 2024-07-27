---
title: "FBF.MADD"
nav_order: 5
description: >
    Add an item to a filter
parent: "Bloom Filter"
---

# FBF.MADD

Usage: `FBF.MADD key item`

The `FBF.MADD` command adds multiple items to a filter. If a filter does not exist, a new one will be created.

Example:

```bash
127.0.0.1:6379> FBF.RESERVE FBF CAPACITY 64 ERROR 0.01
(true)
127.0.0.1:6379> FBF.EXISTS FBF 42
(false)
127.0.0.1:6379> FBF.MADD FBF 42
(true)
127.0.0.1:6379> FBF.EXISTS FBF 42
(true)
```
