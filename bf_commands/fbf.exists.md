---
title: "FBF.EXISTS"
nav_order: 10
description: >
    Check if an item exists in a filter
parent: "Bloom Filter"
---

# FBF.EXISTS

Usage: `FBF.EXISTS filter item`

The `FBF.EXISTS` command checks whether an item exists in a filter.

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
