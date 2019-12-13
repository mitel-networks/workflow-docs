---
layout: default
title: Filters
parent: Advanced
nav_order: 1
---

# Filters

Most activities have a Filter [expression](../getting-started/expressions.md) that when set will direct the parent Flow to terminate under specific conditions.

An activity's Filter becomes active immediately after the activity finishes execution but **before** branching to children occurs.

Once active a Filter will evaluate to either TRUE or FALSE.

When **TRUE** the parent Flow and activity will continue execution as normal.
When **FALSE** the parent Flow will halt execution and immediately terminate.

## Usage Tips

Filters are intended as a shorthand for situations where a Flow needs to be immediately terminated if a certain condition is met.

Common uses include:

* Further filtering incoming events from a Trigger beyond the point the basic logic of the Trigger supports
* Quickly terminating a Flow if a bad/invalid/undesirable state is detected

If the binary logic of a Filter is too simple for a given situation, consider using the Condition Primitive which allows for more complex conditional branching.
