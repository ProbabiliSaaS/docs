---
title: "ECF.PARAMS"
nav_order: 800
description: >
    Creates string representation of a filter initialization parameters.
parent: "Commands"
---

# ECF.PARAMS

Usage: `ECF.PARAMS filter element`

The `ECF.PARAMS` command checks whether an element exists in a filter.

Example:
```
127.0.0.1:6379> ECF.PARAMS CAPACITY 64 PROBABILITY 0.01 TIME_WINDOWS 7 BUCKET_SIZE 4
"JibR15h"
127.0.0.1:6379> ECF.RESERVE ecf JibR15h
"OK"
```