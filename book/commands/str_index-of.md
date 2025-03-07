---
title: str index-of
version: 0.65.1
usage: |
  Returns start index of first occurrence of pattern in string, or -1 if no match
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> str index-of (pattern) ...rest --range --end```

## Parameters

 -  `pattern`: the pattern to find index of
 -  `...rest`: optionally returns index of pattern in string by column paths
 -  `--range {any}`: optional start and/or end index
 -  `--end`: search from the end of the string

## Examples

Returns index of pattern in string
```shell
>  'my_library.rb' | str index-of '.rb'
```

Returns index of pattern in string with start index
```shell
>  '.rb.rb' | str index-of '.rb' -r '1,'
```

Returns index of pattern in string with end index
```shell
>  '123456' | str index-of '6' -r ',4'
```

Returns index of pattern in string with start and end index
```shell
>  '123456' | str index-of '3' -r '1,4'
```

Alternatively you can use this form
```shell
>  '123456' | str index-of '3' -r [1 4]
```

Returns index of pattern in string
```shell
>  '/this/is/some/path/file.txt' | str index-of '/' -e
```
