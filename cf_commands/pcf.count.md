---
title: "PCF.COUNT"
nav_order: 14
description: >
    Count item insertions into a filter
parent: "Cuckoo Filter"
---

# PCF.COUNT

Usage: `PCF.COUNT key item`

The `PCF.COUNT` command returns a count of item copies in the filter, with results within the error rate.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.COUNT PCF 42
(integer) 1
```
