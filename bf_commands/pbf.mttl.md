---
title: "FBF.MTTL"
nav_order: 21
description: >
    Return TTL of multiple items.
parent: "Bloom Filter"
---

# FBF.MTTL

Usage: `FBF.MTTL item item`

The `FBF.MTTL` command returns the Time-To-Live (TTL) of multiple items. '0' is returned if item was not found or if it is expired.

Example:

```bash
127.0.0.1:6379> FBF.RESERVE FBF CAPACITY 64 ERROR 0.01 TIME_WINDOWS 10 INTERVAL 1
(true)
127.0.0.1:6379> FBF.ADD FBF 18
(true)
127.0.0.1:6379> DEBUG SLEEP 3
127.0.0.1:6379> FBF.ADD FBF 42
(true)
127.0.0.1:6379> DEBUG SLEEP 4
127.0.0.1:6379> FBF.MTTL FBF 18 42
1) (integer) 3
2) (integer) 7
```
