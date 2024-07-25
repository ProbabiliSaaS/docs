---
title: "PCF.MEXISTS"
nav_order: 5
description: >
    Check if multiple items exist in a filter
parent: "Cuckoo Filter"
---

# PCF.MEXISTS

Usage: `PCF.MEXISTS key item1 [item2 ...]`

The `PCF.MEXISTS` command checks whether multiple items exist in a filter.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.EXISTS PCF 18 42
1) (false)
2) (false)
127.0.0.1:6379> PCF.MADD PCF 18 42
1) (true)
2) (true)
127.0.0.1:6379> PCF.MEXISTS PCF 18 42
1) (true)
2) (true)
127.0.0.1:6379> PCF.DEL PCF 42
(true)
127.0.0.1:6379> PCF.MEXISTS PCF 18 42
1) (true)
2) (false)
```
