---
title: db over
version: 0.64.0
usage: |
  Adds a partition to an expression function
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> db over ...partition-by```

## Parameters

 -  `...partition-by`: columns to partition the window function

## Examples

Adds a partition to a function expresssion
```shell
> db function avg col_a | db over col_b
```
