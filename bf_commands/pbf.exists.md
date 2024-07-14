---
title: "PBF.EXISTS"
nav_order: 5
description: >
    Check if an element exists in a filter
parent: "Commands"
---

# PBF.EXISTS

Usage: `PBF.EXISTS filter element`

The `PBF.EXISTS` command checks whether an element exists in a filter.

Example:
```
127.0.0.1:6379> PBF.RESERVE PBF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PBF.EXISTS PBF 42
(false)
127.0.0.1:6379> PBF.ADD PBF 42
(true)
127.0.0.1:6379> PBF.EXISTS PBF 42
(true)
127.0.0.1:6379> PBF.DEL PBF 42
(true)
127.0.0.1:6379> PBF.EXISTS PBF 42
(false)
```