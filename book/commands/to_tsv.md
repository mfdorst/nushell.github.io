---
title: to tsv
version: 0.65.1
usage: |
  Convert table into .tsv text
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> to tsv --noheaders```

## Parameters

 -  `--noheaders`: do not output the column names as the first row

## Examples

Outputs an TSV string representing the contents of this table
```shell
> [[foo bar]; [1 2]] | to tsv
```
