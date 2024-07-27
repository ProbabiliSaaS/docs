---
title: "Cuckoo Filter"
description: Cuckoo Filter Commands
nav_order: 3
has_children: true
---

# Commands

## Approximate Membership Filter

Approximate Membership Filter (AMF) is a proprietary variant of filter similar to bloom and cuckoo filters. It supports sliding windows functionality which expire entries after a set time. Alternatively, it can expired old entries when the filter reaches capacity so there is no need to scale up.

This allows new use cases such as:

* Time-sensitive deduplication.
* Tracking users exposure to different ad campaigns.
* Clear old filter members.
* Get age of a member.
