---
title: "PCF.TTL"
nav_order: 850
description: >
    Return TTL of an item.
parent: "Cuckoo Filter"
---

# PCF.TTL

Usage: `PCF.TTL key item`

The `PCF.TTL` command returns the Time-To-Live (TTL) of an item. '0' is returned if item was not found is expired.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.TTL PCF 42
(integer) 10
```