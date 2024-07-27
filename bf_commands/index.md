---
title: "Bloom Filter"
description: Bloom Filter Commands
nav_order: 2
has_children: true
---

# Commands

## ProbabiliSaaS Forgetful Bloom Filter Features

ProbabiliSaaS Forgetful Bloom Filter (FBF) is a variant of Bloom Filter with support for sliding windows functionality.
The filter has `CAPACITY` and `ERROR` arguments
Sliding windows can work in two modes:

* Time based - the filter has two additional arguments - `TIME_WINDOWS`, the number of sub bloom filters, and `INTERVAL`, the number of seconds between expiring the oldest sub bloom filter and the creation of a new one. Items expire after approximately `TIME_WINDOWS * INTERVAL`. The filter will scale up if more items than initial `CAPACITY` are added without an increase in the `ERROR` rate.
The filter optimizes sub bloom filters to conserve memory.

* Count based - the filter has an additional argument `RETENTION_BATCHES`, the number of sub bloom filters. This means items will be discarded in batches of `CAPACITY / RETENTION_BATCHES`. The filter will maintain its initial capacity.

Items in the filter expire after a set time or when the filter becomes full. This allows new use cases such as:

* Time-sensitive deduplication.
* Clear old filter members.
* Get age of a member.
