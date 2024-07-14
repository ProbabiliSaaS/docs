---
title: "PCF.PARAMS"
nav_order: 800
description: >
    Creates string representation of a filter initialization parameters.
parent: "Commands"
---

# PCF.PARAMS

Usage: `PCF.PARAMS filter element`

The `PCF.PARAMS` command checks whether an element exists in a filter.

Example:
```
127.0.0.1:6379> PCF.PARAMS CAPACITY 64 PROBABILITY 0.01 TIME_WINDOWS 7 BUCKET_SIZE 4
"JibR15h"
127.0.0.1:6379> PCF.RESERVE PCF JibR15h
"OK"
```