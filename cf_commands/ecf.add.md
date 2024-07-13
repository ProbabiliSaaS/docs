---
title: "ECF.ADD"
nav_order: 1
description: >
    Add an element to a filter
parent: "Commands"
---

# ECF.ADD

Usage: `ECF.ADD key item`

The `ECF.ADD` command adds an item to a filter. If a filter does not exist, a new one will be created.

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