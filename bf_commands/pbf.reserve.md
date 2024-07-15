---
title: "PBF.RESERVE"
nav_order: 900
description: >
    Create a new cuckoo filter
parent: "Bloom Filter"
---

# PBF.RESERVE

Usage: `PBF.RESERVE key capacity [BUCKETSIZE bucketsize] [MAXITERATIONS maxiterations] [EXPANSION expansion]`

The `PBF.RESERVE` creates a new filter using parameters provided by 

## Optional arguments

### BUCKET_SIZE

`BUCKET_SIZE` helps the filter achieve a higher fill rate before becoming full. On the other hand, it increases the error rate.

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