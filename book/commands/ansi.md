---
title: ansi
version: 0.65.1
usage: |
  Output ANSI codes to change color.
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> ansi (code) --escape --osc --list```

## Parameters

 -  `code`: the name of the code to use like 'green' or 'reset' to reset the color
 -  `--escape`: escape sequence without the escape character(s)
 -  `--osc`: operating system command (ocs) escape sequence without the escape character(s)
 -  `--list`: list available ansi code names

## Notes
```text
For escape sequences:
Escape: '\x1b[' is not required for --escape parameter
Format: #(;#)m
Example: 1;31m for bold red or 2;37;41m for dimmed white fg with red bg
There can be multiple text formatting sequence numbers
separated by a ; and ending with an m where the # is of the
following values:
    attribute_number, abbreviation, description
    0     reset / normal display
    1  b  bold or increased intensity
    2  d  faint or decreased intensity
    3  i  italic on (non-mono font)
    4  u  underline on
    5  l  slow blink on
    6     fast blink on
    7  r  reverse video on
    8  h  nondisplayed (invisible) on
    9  s  strike-through on

    foreground/bright colors    background/bright colors
    30/90    black              40/100    black
    31/91    red                41/101    red
    32/92    green              42/102    green
    33/93    yellow             43/103    yellow
    34/94    blue               44/104    blue
    35/95    magenta            45/105    magenta
    36/96    cyan               46/106    cyan
    37/97    white              47/107    white
    39       default            49        default
    https://en.wikipedia.org/wiki/ANSI_escape_code

OSC: '\x1b]' is not required for --osc parameter
Example: echo [(ansi -o '0') 'some title' (char bel)] | str collect
Format: #
    0 Set window title and icon name
    1 Set icon name
    2 Set window title
    4 Set/read color palette
    9 iTerm2 Grown notifications
    10 Set foreground color (x11 color spec)
    11 Set background color (x11 color spec)
    ... others
```
## Examples

Change color to green
```shell
> ansi green
```

Reset the color
```shell
> ansi reset
```

Use ansi to color text (rb = red bold, gb = green bold, pb = purple bold)
```shell
> echo [(ansi rb) Hello " " (ansi gb) Nu " " (ansi pb) World (ansi reset)] | str collect
```

Use ansi to color text (italic bright yellow on red 'Hello' with green bold 'Nu' and purple bold 'World')
```shell
> echo [(ansi -e '3;93;41m') Hello (ansi reset) " " (ansi gb) Nu " " (ansi pb) World (ansi reset)] | str collect
```

Use ansi to color text with a style (blue on red in bold)
```shell
> $"(ansi -e { fg: '#0000ff' bg: '#ff0000' attr: b })Hello Nu World(ansi reset)"
```
