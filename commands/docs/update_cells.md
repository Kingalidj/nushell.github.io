---
title: update cells
categories: |
  filters
version: 0.84.0
filters: |
  Update the table cells.
usage: |
  Update the table cells.
---

# <code>{{ $frontmatter.title }}</code> for filters

<div class='command-title'>{{ $frontmatter.filters }}</div>

## Signature

```> update cells (closure) --columns```

## Parameters

 -  `closure`: the closure to run an update for each cell
 -  `--columns {table}`: list of columns to update


## Input/output types:

| input | output |
| ----- | ------ |
| table | table  |

## Examples

Update the zero value cells to empty strings.
```shell
> [
        ["2021-04-16", "2021-06-10", "2021-09-18", "2021-10-15", "2021-11-16", "2021-11-17", "2021-11-18"];
        [          37,            0,            0,            0,           37,            0,            0]
    ] | update cells { |value|
          if $value == 0 {
            ""
          } else {
            $value
          }
    }
╭───┬────────────┬────────────┬────────────┬────────────┬────────────┬────────────┬────────────╮
│ # │ 2021-04-16 │ 2021-06-10 │ 2021-09-18 │ 2021-10-15 │ 2021-11-16 │ 2021-11-17 │ 2021-11-18 │
├───┼────────────┼────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤
│ 0 │         37 │            │            │            │         37 │            │            │
╰───┴────────────┴────────────┴────────────┴────────────┴────────────┴────────────┴────────────╯

```

Update the zero value cells to empty strings in 2 last columns.
```shell
> [
        ["2021-04-16", "2021-06-10", "2021-09-18", "2021-10-15", "2021-11-16", "2021-11-17", "2021-11-18"];
        [          37,            0,            0,            0,           37,            0,            0]
    ] | update cells -c ["2021-11-18", "2021-11-17"] { |value|
            if $value == 0 {
              ""
            } else {
              $value
            }
    }
╭───┬────────────┬────────────┬────────────┬────────────┬────────────┬────────────┬────────────╮
│ # │ 2021-04-16 │ 2021-06-10 │ 2021-09-18 │ 2021-10-15 │ 2021-11-16 │ 2021-11-17 │ 2021-11-18 │
├───┼────────────┼────────────┼────────────┼────────────┼────────────┼────────────┼────────────┤
│ 0 │         37 │          0 │          0 │          0 │         37 │            │            │
╰───┴────────────┴────────────┴────────────┴────────────┴────────────┴────────────┴────────────╯

```


**Tips:** Command `update cells` was not included in the official binaries by default, you have to build it with `--features=extra` flag