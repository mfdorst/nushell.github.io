---
title: db join
version: 0.64.0
usage: |
  Joins with another table or derived table. Default join type is inner
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> db join (table) (on) --as --left --right --outer --cross```

## Parameters

 -  `table`: table or derived table to join on
 -  `on`: expression to join tables
 -  `--as {string}`: Alias for the selected join
 -  `--left`: left outer join
 -  `--right`: right outer join
 -  `--outer`: full outer join
 -  `--cross`: cross join

## Examples


```shell
>
```
