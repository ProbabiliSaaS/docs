---
title: "PCF.MTOUCH"
nav_order: 8
description: >
    Update a timestamp for multiple items in a filter. If an item does not exist, create the item. If the filter does not exist, create the filter.
parent: "Cuckoo Filter"
---

# PCF.TOUCH

Usage: `PCF.TOUCH key [PARAMS params] ITEMS item timestamp`

The `PCF.TOUCH` command updates a timestamp of multiple items in a filter. The the timestamp will update only if timestamp is newer than th current timestamp. If an item does not exist, it will be created. If a filter does not exist, a new filter will be created.

Example:

```bash
127.0.0.1:6379> PCF.PARAMS CAPACITY 64 ERROR 0.01 TIME_WINDOWS 10 INTERVAL 1
"PaRAm$!%^&"
127.0.0.1:6379> PCF.EXISTS PCF bloom
(false)
127.0.0.1:6379> PCF.MTOUCH PCF PARAMS PaRAm$!%^& ITEMS bloom 5 filter 7
(true)
127.0.0.1:6379> PCF.MEXISTS PCF bloom filter forever
1) (true)
2) (true)
3) (false)
127.0.0.1:6379> PCF.MTTL PCF bloom filter forever
1) (5)
2) (3)
3) (0)
```
