---
title: input
version: 0.65.1
usage: |
  Get input from the user.
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> input (prompt) --bytes-until --suppress-output```

## Parameters

 -  `prompt`: prompt to show the user
 -  `--bytes-until {string}`: read bytes (not text) until a stop byte
 -  `--suppress-output`: don't print keystroke values

## Examples

Get input from the user, and assign to a variable
```shell
> let user-input = (input)
```
