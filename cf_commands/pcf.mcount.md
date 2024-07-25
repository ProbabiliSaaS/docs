---
title: "PCF.MCOUNT"
nav_order: 3
description: >
    Count items' insertions into a filter
parent: "Cuckoo Filter"
---

# PCF.COUNT

Usage: `PCF.COUNT key item1 [item2 ...]`

The `PCF.COUNT` command returns counts of items' copies in the filter. Results are within the error rate.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF CAPACITY 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.MADD PCF 42 18 42 42
1) (true)
2) (true)
3) (true)
4) (true)
127.0.0.1:6379> PCF.MCOUNT PCF 18 42
(integer) 1
(integer) 3
```
