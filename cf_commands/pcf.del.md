---
title: "PCF.DEL"
nav_order: 4
description: >
    Delete an element from a filter
parent: "Cuckoo Filter"
---

# PCF.DEL

Usage: `PCF.DEL key element`

The `PCF.DEL` command delete an element from the filter. If the filter has multiple copies, the oldest copy is removed.

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
