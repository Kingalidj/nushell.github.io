---
title: dfr flatten
categories: |
  lazyframe
version: 0.84.0
lazyframe: |
  An alias for dfr explode
usage: |
  An alias for dfr explode
---

# <code>{{ $frontmatter.title }}</code> for lazyframe

<div class='command-title'>{{ $frontmatter.lazyframe }}</div>

## Signature

```> dfr flatten ...rest```

## Parameters

 -  `...rest`: columns to flatten, only applicable for dataframes


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Flatten the specified dataframe
```shell
> [[id name hobbies]; [1 Mercy [Cycling Knitting]] [2 Bob [Skiing Football]]] | dfr into-df | dfr flatten hobbies | dfr collect
╭───┬────┬───────┬──────────╮
│ # │ id │ name  │ hobbies  │
├───┼────┼───────┼──────────┤
│ 0 │  1 │ Mercy │ Cycling  │
│ 1 │  1 │ Mercy │ Knitting │
│ 2 │  2 │ Bob   │ Skiing   │
│ 3 │  2 │ Bob   │ Football │
╰───┴────┴───────┴──────────╯

```

Select a column and flatten the values
```shell
> [[id name hobbies]; [1 Mercy [Cycling Knitting]] [2 Bob [Skiing Football]]] | dfr into-df | dfr select (dfr col hobbies | dfr flatten)
╭───┬──────────╮
│ # │ hobbies  │
├───┼──────────┤
│ 0 │ Cycling  │
│ 1 │ Knitting │
│ 2 │ Skiing   │
│ 3 │ Football │
╰───┴──────────╯

```


**Tips:** Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag