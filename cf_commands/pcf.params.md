---
title: "PCF.PARAMS"
nav_order: 2
description: >
    Creates string representation of a filter initialization parameters.
parent: "Cuckoo Filter"
---

# PCF.PARAMS

Usage: `PCF.PARAMS CAPACITY cap ERROR err [GROWBY growby] [[TIME_WINDOWS time_windows] [INTERVAL interval]] [RETENTION_BATCHES retention_batches] [NO_DEL bool] [DEL_EMPTY bool] [NO_CREATE bool]`

The `PCF.PARAMS` create a encoded string representation of the user parameters. The string can be then used with `PCF.RESERVE`, `PCF.TOUCH` and `PCF.MTOUCH` as a cleaner API.
Filter has two modes: 

* Time based - the filter shifts every `interval` seconds. An item will retire after `time_windows` number of shifts.
* Count based - the filter will maintain its original `capacity` and will shift after `capacity / retention_batches` insertions.

Notes:

* Time based arguments and count based arguments are mutually exclusive.

## Required arguments:

`CAPACITY` - Estimated required capacity for the filter.
`ERROR` - The desired probability for false positives. The value is a floating value between 0 and 1.

## Optional arguments:

`GROWBY` - The size of additional capacity when a filter scales up. If set to `0`, the filter cannot scale. Optional values are `0, 1, 2, 4, 8`.
`TIME_WINDOWS` - Number of time windows. Maximum value is `65530`.
`INTERVAL` - Time interval between time window shifts. Maximum value is `31536000` (1 year).
`RETENTION_BUCKET` - The number of `batches` that `capacity` is broken into. Maximum value is `65530`.
`NO_DEL` - items cannot be removed from the filter. If set to `true`, duplicate items will not be inserted. Instead, the time index will be updated. Default value is `false`.
`DEL_EMPTY` - Delete a filter is it becomes empty. Default value is `false`.
`NO_CREATE` - Avoid filter creation if it does not exist yet. Default value is `false`.

Example:

```bash
127.0.0.1:6379> PCF.PARAMS CAPACITY 64 PROBABILITY 0.01 TIME_WINDOWS 24 INTERVAL 3600
"JibR15h"
127.0.0.1:6379> PCF.RESERVE PCF1 JibR15h
"OK"
127.0.0.1:6379> PCF.TOUCH PCF2 PARAMS JibR15h ITEMS cuckoo 0
"OK"
```
