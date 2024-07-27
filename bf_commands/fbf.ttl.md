---
title: "FBF.TTL"
nav_order: 20
description: >
    Return TTL of an item.
parent: "Bloom Filter"
---

# FBF.TTL

Usage: `FBF.TTL item item`

The `FBF.TTL` command returns the Time-To-Live (TTL) of an item. '0' is returned if item was not found or it is expired.

Example:

```bash
127.0.0.1:6379> FBF.RESERVE FBF CAPACITY 64 ERROR 0.01 TIME_WINDOWS 10 INTERVAL 1
(true)
127.0.0.1:6379> FBF.ADD FBF 42
(true)
127.0.0.1:6379> DEBUG SLEEP 7
127.0.0.1:6379> FBF.TTL FBF 42
(integer) 3
```
