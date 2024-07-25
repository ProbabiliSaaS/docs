---
title: "PBF.PARAMS"
nav_order: 800
description: >
    Creates string representation of a filter initialization parameters.
parent: "Bloom Filter"
---

# PBF.PARAMS

Usage: `PBF.PARAMS filter item`

The `PBF.PARAMS` command checks whether an item exists in a filter.

Example:
```
127.0.0.1:6379> PBF.PARAMS CAPACITY 64 PROBABILITY 0.01 TIME_WINDOWS 7 BUCKET_SIZE 4
"JibR15h"
127.0.0.1:6379> PBF.RESERVE PBF JibR15h
"OK"
```