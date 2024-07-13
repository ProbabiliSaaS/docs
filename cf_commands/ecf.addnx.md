---
title: "ECF.ADDNX"
nav_order: 2
description: >
    Add an item to a cuckoo filter if the item does not exists
parent: "Commands"
---

# ECF.ADDNX

Usage: `ECF.ADDNX key item`

The `ECF.ADDNX` command adds an item to a filter if the item does not exists. If a filter does not exist, a new one will be created.

Example:
```
127.0.0.1:6379> ECF.RESERVE ecf 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> ECF.COUNT ecf 42
(1)
127.0.0.1:6379> ECF.ADDNX ecf 42
(true)
127.0.0.1:6379> ECF.COUNT ecf 42
(1)
127.0.0.1:6379> ECF.ADDNX ecf 42
(false)
127.0.0.1:6379> ECF.COUNT ecf 42
(1)
127.0.0.1:6379> ECF.ADD ecf 42
(true)
127.0.0.1:6379> ECF.COUNT ecf 42
(2)
```