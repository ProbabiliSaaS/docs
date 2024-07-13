---
title: "Efficient Cuckoo Filter"
description: Efficient Cuckoo Filter overview
nav_order: 2
has_children: true
---

# Commands

## Efficient Cuckoo Filter Features

Efficient Cuckoo Filter (ECF) is a proprietary variant of Cuckoo Filter. It supports sliding windows functionality which expire entries after a set time. This allows new use cases such as:

* Time-sensitive deduplication.
* Clear old filter members.
* Get age of a member.
