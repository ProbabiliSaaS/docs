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

* Time based - the filter has a number of windows and an interval for shifting to the next windows. Items expire when their windows s 

Items in the filter expire after a set time or when the filter becomes full. This allows new use cases such as:

* Time-sensitive deduplication.
* Clear old filter members.
* Get age of a member.