---
title: "ECF.TTL"
nav_order: 850
description: >
    Return TTL of an item.
parent: "Commands"
---

# ECF.TTL

Usage: `ECF.TTL item item`

The `ECF.TTL` command returns the Time-To-Live (TTL) of an item. '0' is returned if item was not found is expired.

Example:
```
127.0.0.1:6379> ECF.RESERVE ecf 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.TTL ecf 42
(integer) 10
```