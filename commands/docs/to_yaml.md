---
title: to yaml
categories: |
  formats
version: 0.84.0
formats: |
  Convert table into .yaml/.yml text.
usage: |
  Convert table into .yaml/.yml text.
---

# <code>{{ $frontmatter.title }}</code> for formats

<div class='command-title'>{{ $frontmatter.formats }}</div>

## Signature

```> to yaml ```


## Input/output types:

| input | output |
| ----- | ------ |
| any   | string |

## Examples

Outputs an YAML string representing the contents of this table
```shell
> [[foo bar]; ["1" "2"]] | to yaml
- foo: '1'
  bar: '2'

```
