---
title: "PCF.EXISTS"
nav_order: 10
description: >
    Check if an item exists in a filter
parent: "Cuckoo Filter"
---

# PCF.EXISTS

Usage: `PCF.EXISTS key item`

The `PCF.EXISTS` command checks whether an item exists in a filter.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(true)
127.0.0.1:6379> PCF.DEL PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
```