---
title: "ECF.DEL"
description: >
    Delete an element from a filter
parent: "Commands"
---

# ECF.DEL

Usage: `ECF.DEL filter element`

The `ECF.DEL` command delete an element from the filter. If the filter has multiple copies, the oldest copy is removed.

Example:
```
127.0.0.1:6379> ECF.RESERVE ecf 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> ECF.DEL ecf 42
(false)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.DEL ecf 42
(true)
127.0.0.1:6379> ECF.DEL ecf 42
(false)
```