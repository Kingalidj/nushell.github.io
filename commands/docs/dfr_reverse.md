---
title: dfr reverse
categories: |
  lazyframe
version: 0.84.0
lazyframe: |
  Reverses the LazyFrame
usage: |
  Reverses the LazyFrame
---

# <code>{{ $frontmatter.title }}</code> for lazyframe

<div class='command-title'>{{ $frontmatter.lazyframe }}</div>

## Signature

```> dfr reverse ```


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Reverses the dataframe
```shell
> [[a b]; [6 2] [4 2] [2 2]] | dfr into-df | dfr reverse
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 2 │ 2 │
│ 1 │ 4 │ 2 │
│ 2 │ 6 │ 2 │
╰───┴───┴───╯

```


**Tips:** Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag