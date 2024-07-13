---
title: "ECF.TOUCH"
nav_order: 700
description: >
    Update a timestamp for an item in a filter. If the item does not exist, create the item. If the filter does not exist, create the filter.
parent: "Commands"
---

# ECF.TOUCH

Usage: `ECF.TOUCH key [PARAMS params] ITEMS item timestamp`

The `ECF.TOUCH` command updates a timestamp of an item in a filter. The the timestamp will update only if timestamp is newer than th current timestamp. If a filter does not exist, a new filter will be created.

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