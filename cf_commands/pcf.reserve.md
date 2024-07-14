---
title: "PCF.RESERVE"
nav_order: 900
description: >
    Create a new cuckoo filter
parent: "Commands"
---

# PCF.RESERVE

Usage: `PCF.RESERVE key capacity [BUCKETSIZE bucketsize] [MAXITERATIONS maxiterations] [EXPANSION expansion]`

The `PCF.RESERVE` creates a new filter using parameters provided by 

## Optional arguments

### BUCKET_SIZE



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