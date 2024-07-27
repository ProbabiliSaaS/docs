---
title: "FBF.MEXISTS"
nav_order: 11
description: >
    Check if multiple items exist in a filter
parent: "Bloom Filter"
---

# FBF.MEXISTS

Usage: `FBF.MEXISTS filter item`

The `FBF.MEXISTS` command checks whether multiple items exist in a filter.

Example:

```bash
127.0.0.1:6379> FBF.RESERVE FBF CAPACITY 64 ERROR 0.01
(true)
127.0.0.1:6379> FBF.MEXISTS FBF 18 42 1776
1) (false)
2) (false)
3) (false)
127.0.0.1:6379> FBF.MADD FBF 18 42
1) (true)
2) (true)
127.0.0.1:6379> FBF.MEXISTS FBF 18 42 1776
1) (true)
2) (true)
3) (false)
```
