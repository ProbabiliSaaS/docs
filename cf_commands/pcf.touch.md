---
title: "PCF.TOUCH"
nav_order: 700
description: >
    Update a timestamp for an item in a filter. If the item does not exist, create the item. If the filter does not exist, create the filter.
parent: "Cuckoo Filter"
---

# PCF.TOUCH

Usage: `PCF.TOUCH key [PARAMS params] ITEMS item timestamp`

The `PCF.TOUCH` command updates a timestamp of an item in a filter. The the timestamp will update only if timestamp is newer than th current timestamp. If a filter does not exist, a new filter will be created.

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
```