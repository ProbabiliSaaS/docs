---
title: "PCF.TOUCH"
nav_order: 7
description: >
    Update a timestamp for an item in a filter.
parent: "Cuckoo Filter"
---

# PCF.TOUCH

Usage: `PCF.TOUCH key [PARAMS params] ITEMS item timestamp`

The `PCF.TOUCH` command updates a timestamp of an item in a filter. The the timestamp will update only if timestamp is newer than th current timestamp. If an item does not exist, it will be created. If a filter does not exist, a new filter will be created.

Example:

```bash
127.0.0.1:6379> PCF.PARAMS CAPACITY 64 ERROR 0.01 TIME_WINDOWS 10 INTERVAL 1
"PaRAm$!%^&"
127.0.0.1:6379> PCF.EXISTS PCF bloom
(false)
127.0.0.1:6379> PCF.MTOUCH PCF PARAMS PaRAm$!%^& ITEMS bloom 4
(true)
127.0.0.1:6379> PCF.EXISTS PCF bloom
(true)
127.0.0.1:6379> PCF.TTL PCF bloom
(6)
127.0.0.1:6379> PCF.TTL PCF filter
(0)
```
