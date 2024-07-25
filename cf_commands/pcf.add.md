---
title: "PCF.ADD"
nav_order: 1
description: >
    Add an element to a filter
parent: "Cuckoo Filter"
---

# PCF.ADD

Usage: `PCF.ADD key item`

The `PCF.ADD` command adds an item to a filter.

Example:
```
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(true)
```