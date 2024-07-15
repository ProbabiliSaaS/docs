---
title: "PCF.ADDNX"
nav_order: 2
description: >
    Add an item to a cuckoo filter if the item does not exists
parent: "Cuckoo Filter"
---

# PCF.ADDNX

Usage: `PCF.ADDNX key item`

The `PCF.ADDNX` command adds an item to a filter if the item does not exists. If a filter does not exist, a new one will be created.

Example:
```
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.COUNT PCF 42
(1)
127.0.0.1:6379> PCF.ADDNX PCF 42
(true)
127.0.0.1:6379> PCF.COUNT PCF 42
(1)
127.0.0.1:6379> PCF.ADDNX PCF 42
(false)
127.0.0.1:6379> PCF.COUNT PCF 42
(1)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.COUNT PCF 42
(2)
```