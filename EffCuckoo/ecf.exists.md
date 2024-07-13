---
title: "ECF.EXISTS"
description: >
    Check if an element exists in a filter
parent: "Commands"
---

# ECF.EXISTS

Usage: `ECF.EXISTS filter element`

The `ECF.EXISTS` command checks whether an element exists in a filter.

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
127.0.0.1:6379> ECF.DEL ecf 42
(true)
127.0.0.1:6379> ECF.EXISTS ecf 42
(false)
```