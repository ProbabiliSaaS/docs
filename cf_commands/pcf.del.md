---
title: "PCF.DEL"
nav_order: 4
description: >
    Delete an item from a filter
parent: "Cuckoo Filter"
---

# PCF.DEL

Usage: `PCF.DEL key item`

The `PCF.DEL` command delete an item from the filter. If the filter has multiple copies, the oldest copy is removed.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.DEL PCF 42
(false)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.DEL PCF 42
(true)
127.0.0.1:6379> PCF.DEL PCF 42
(false)
```
