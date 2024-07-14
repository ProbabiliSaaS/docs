---
title: "PCF.EXISTS"
nav_order: 5
description: >
    Check if an element exists in a filter
parent: "Commands"
---

# PCF.EXISTS

Usage: `PCF.EXISTS filter element`

The `PCF.EXISTS` command checks whether an element exists in a filter.

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
127.0.0.1:6379> PCF.DEL PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
```