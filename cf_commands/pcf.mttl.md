---
title: "PCF.MTTL"
nav_order: 13
description: >
    Return TTL of multiple items.
parent: "Cuckoo Filter"
---

# PCF.TTL

Usage: `PCF.MTTL key item1 [item2 ...]`

The `PCF.MTTL` command returns the Time-To-Live (TTL) of an item. '0' is returned if item was not found is expired.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.ADD PCF 18
(true)
127.0.0.1:6379> PCF.MTTL PCF 18 42
1) (integer) 10
2) (integer) 0
(... delay for 3 time shifts ...)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.MTTL PCF 18 42
1) (integer) 7
2) (integer) 10
```
