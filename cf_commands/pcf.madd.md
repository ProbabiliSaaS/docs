---
title: "PCF.MADD"
nav_order: 1
description: >
    Add multiple items to a filter
parent: "Cuckoo Filter"
---

# PCF.MADD

Usage: `PCF.MADD key item1 [item2 ...]`

The `PCF.MADD` command adds multiple items to a filter.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01 NO_DEL true
(true)
127.0.0.1:6379> PCF.MEXISTS PCF 18 42 2024
1) (false)
2) (false)
3) (false)
127.0.0.1:6379> PCF.MADD PCF 18 2024 18
1) (true)
2) (true)
3) (false)
127.0.0.1:6379> PCF.MEXISTS PCF 18 42 2024
1) (true)
2) (false)
3) (true)
```
