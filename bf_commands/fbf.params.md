---
title: "FBF.PARAMS"
nav_order: 2
description: >
    Creates string representation of a filter initialization parameters.
parent: "Bloom Filter"
---

# FBF.PARAMS

Usage: `FBF.PARAMS key CAPACITY capacity ERROR error [GROWBY growby] [[TIME_WINDOWS time_windows] [INTERVAL interval]] [RETENTION_BATCHES retention_batches] [DEL_EMPTY bool]`

## Required arguments:

`key` - key name for the filter to be created.
`CAPACITY` - Estimated required capacity for the filter.
`ERROR` - The desired probability for false positives. The value is a floating value between 0 and 1.

## Optional arguments

`GROWBY` - The size of additional capacity when a filter scales up. If set to `0`, the filter cannot scale. Optional values are `0, 1, 2, 4, 8`.
`TIME_WINDOWS` - Number of time windows. Maximum value is `65530`.
`INTERVAL` - Time interval between time window shifts. Maximum value is `31536000` (1 year).
`RETENTION_BUCKET` - The number of `batches` that `capacity` is broken into. Maximum value is `65530`.
`DEL_EMPTY` - Delete a filter is it becomes empty. Default value is `false`.

Example:

```bash
127.0.0.1:6379> FBF.PARAMS CAPACITY 64 PROBABILITY 0.01 TIME_WINDOWS 7 BUCKET_SIZE 4
"JibR15h"
127.0.0.1:6379> FBF.RESERVE FBF JibR15h
"OK"
```
