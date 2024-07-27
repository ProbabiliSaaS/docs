---
title: "PCF.MDEL"
nav_order: 21
description: >
    Delete multiple items from a filter
parent: "Cuckoo Filter"
---

# PCF.DEL

Usage: `PCF.MDEL key item1 [item2 ...]`

The `PCF.MDEL` command delete multiple items from the filter. If the filter has multiple copies of the same item, the oldest copy is removed.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.MDEL PCF 18 42
1) (false)
2) (false)
127.0.0.1:6379> PCF.MADD PCF 18  42
1) (true)
2) (true)
127.0.0.1:6379> PCF.MDEL PCF 42 2024 42
1) (true)
2) (false)
3) (false)
```
