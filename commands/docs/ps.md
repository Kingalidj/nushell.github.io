---
title: ps
categories: |
  system
version: 0.84.0
system: |
  View information about system processes.
usage: |
  View information about system processes.
---

# <code>{{ $frontmatter.title }}</code> for system

<div class='command-title'>{{ $frontmatter.system }}</div>

## Signature

```> ps --long```

## Parameters

 -  `--long` `(-l)`: list all available columns for each entry


## Input/output types:

| input   | output |
| ------- | ------ |
| nothing | table  |

## Examples

List the system processes
```shell
> ps

```

List the top 5 system processes with the highest memory usage
```shell
> ps | sort-by mem | last 5

```

List the top 3 system processes with the highest CPU usage
```shell
> ps | sort-by cpu | last 3

```

List the system processes with 'nu' in their names
```shell
> ps | where name =~ 'nu'

```

Get the parent process id of the current nu process
```shell
> ps | where pid == $nu.pid | get ppid

```
