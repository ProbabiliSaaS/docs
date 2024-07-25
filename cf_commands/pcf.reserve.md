---
title: "PCF.RESERVE"
nav_order: 900
description: >
    Create a new cuckoo filter
parent: "Cuckoo Filter"
---

# PCF.RESERVE

Usage: `PCF.RESERVE key CAPACITY cap ERROR err [GROWBY growby] [[TIME_WINDOWS time_windows] [INTERVAL interval]] [RETENTION_BATCHES retention_batches] [NO_DEL bool] [DEL_EMPTY bool]`

The `PCF.RESERVE` creates a new filter.

## Required arguments:

`key` - key name for the filter to be created.
`CAPACITY` - Estimated required capacity for the filter.
`ERROR` - The desired probability for false positives. The value is a floating value between 0 and 1.

## Optional arguments:

`GROWBY` - The size of additional capacity when a filter scales up. If set to `0`, the filter cannot scale. Optional values are `0, 1, 2, 4, 8`.
`TIME_WINDOWS` - Number of time windows. Maximum value is `65530`.
`INTERVAL` - Time interval between time window shifts. Maximum value is `31536000` (1 year).
`RETENTION_BUCKET` - The number of `batches` that `capacity` is broken into. Maximum value is `65530`.
`NO_DEL` - Elements cannot be removed from the filter. If set to `true`, duplicate elements will not be inserted. Instead, the time index will be updated. Default value is `false`.
`DEL_EMPTY` - Delete a filter is it becomes empty. Default value is `false`.

Example:

```bash
127.0.0.1:6379> PCF.RESERVE PCF 64 PROBABILITY 0.01
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(false)
127.0.0.1:6379> PCF.ADD PCF 42
(true)
127.0.0.1:6379> PCF.EXISTS PCF 42
(true)
```
