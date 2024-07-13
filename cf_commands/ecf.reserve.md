---
title: "ECF.RESERVE"
nav_order: 900
description: >
    Create a new cuckoo filter
parent: "Commands"
---

# ECF.RESERVE

Usage: `ECF.RESERVE key capacity [BUCKETSIZE bucketsize] [MAXITERATIONS maxiterations] [EXPANSION expansion]`

The `ECF.RESERVE` creates a new filter using parameters provided by 

## Optional arguments

### BUCKET_SIZE



Example:
```
127.0.0.1:6379> ECF.RESERVE ecf 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> ECF.EXISTS ecf 42
(false)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.EXISTS ecf 42
(true)
```