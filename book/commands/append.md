---
title: append
version: 0.65.1
usage: |
  Append any number of rows to a table.
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> append (row)```

## Parameters

 -  `row`: the row, list, or table to append

## Examples

Append one Int item
```shell
> [0,1,2,3] | append 4
```

Append three Int items
```shell
> [0,1] | append [2,3,4]
```

Append Ints and Strings
```shell
> [0,1] | append [2,nu,4,shell]
```
