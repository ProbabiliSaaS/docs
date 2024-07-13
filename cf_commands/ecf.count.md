---
title: "ECF.COUNT"
nav_order: 3
description: >
    Count item insertions into a filter
parent: "Commands"
---

# ECF.COUNT

Usage: `ECF.COUNT item element`

The `ECF.COUNT` command returns a count of how many times an item has been added to a cuckoo filter, with results within the error rate.

Example:
```
127.0.0.1:6379> ECF.RESERVE ecf 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.COUNT ecf 42
(integer) 1
```