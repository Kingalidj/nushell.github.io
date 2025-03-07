---
title: random
categories: |
  random
version: 0.84.0
random: |
  Generate a random value.
usage: |
  Generate a random value.
---

# <code>{{ $frontmatter.title }}</code> for random

<div class='command-title'>{{ $frontmatter.random }}</div>

## Signature

```> random ```


## Input/output types:

| input   | output |
| ------- | ------ |
| nothing | string |

## Notes
You must use one of the following subcommands. Using this command as-is will only produce this help message.

## Subcommands:

| name                                                 | type    | usage                                                |
| ---------------------------------------------------- | ------- | ---------------------------------------------------- |
| [`random bool`](/commands/docs/random_bool.md)       | Builtin | Generate a random boolean value.                     |
| [`random chars`](/commands/docs/random_chars.md)     | Builtin | Generate random chars.                               |
| [`random decimal`](/commands/docs/random_decimal.md) | Builtin | Generate a random decimal within a range [min..max]. |
| [`random dice`](/commands/docs/random_dice.md)       | Builtin | Generate a random dice roll.                         |
| [`random integer`](/commands/docs/random_integer.md) | Builtin | Generate a random integer [min..max].                |
| [`random uuid`](/commands/docs/random_uuid.md)       | Builtin | Generate a random uuid4 string.                      |