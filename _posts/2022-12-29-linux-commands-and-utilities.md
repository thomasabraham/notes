---
layout: post
title: Linux commands and utilities
date: 2022-12-29
categories: cli
---

Some linux commands like `ls` and `cd` are used every day, while others like
`find` is not that commonly used. Here I try to collect notes on the not so
commonly used linux commands that I have to look up every once in a while. These
notes cover only the simple usecases that I might encounter. For more complex
usage, there is always the man pages and the Internet.

## find - search for files in a directory hierarchy
### Syntax
```
find <where-to-look> -name <pattern-to-look>
```
### Example 
Look for any files with `Client.java` suffix in the name in current directory
and its subdirectories.

```
find . -name *Client.java
```

## ss - socket scan
### Syntax
```
ss <options -l, -t, -u>
```

- `-l` : Display listening sockets
- `-t` : Display TCP sockets
- `-u` : Display UDP sockets

### Example
List sockets where a TCP server is listening.
```
ss -lt
```
