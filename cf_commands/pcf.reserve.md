---
title: "PCF.RESERVE"
nav_order: 900
description: >
    Create a new cuckoo filter
parent: "Cuckoo Filter"
---

# PCF.RESERVE

Usage: `PCF.RESERVE key capacity [BUCKETSIZE bucketsize] [MAXITERATIONS maxiterations] [EXPANSION expansion]`

The `PCF.RESERVE` creates a new filter using parameters provided by 

## Optional arguments

### BUCKET_SIZE

`BUCKET_SIZE` helps the filter achieve a higher fill rate before becoming full. On the other hand, it increases the error rate.

Example:
```
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(true)
```