---
title: "PBF.TTL"
nav_order: 850
description: >
    Return TTL of an item.
parent: "Bloom Filter"
---

# PBF.TTL

Usage: `PBF.TTL item item`

The `PBF.TTL` command returns the Time-To-Live (TTL) of an item. '0' is returned if item was not found is expired.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.TTL PBF 42
(integer) 10
```