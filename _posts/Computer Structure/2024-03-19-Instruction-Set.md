---
layout: post
title: Instruction Set
subtitle: 컴퓨터가 사용하는 어휘
date: 2024-03-19 09:00:00 +0900
categories: Computer Structure
---
# Instruction Set

CPU의 종류마다 Instruction Set이 다르다. 물론, 완전히 다를 수도 공통된 부분이 있을 수도 있다. CPU를 특정 연산에 좀 더 특화시키기 위해서 복잡한 instruction을 사용하기도 한다.

## [The MIPS Instruction Set](www.mips.com)
### Arithmetic Operations
- Two Sources, One Destination
- Form (All Arithmetic op have this)
```
add a, b, c // a gets b + c
```
- Design Principle 1: Simplicity favors regularity
#### Arithmetic Example
```c
type f = (g + h) - (i + j);
```
```MIPS
add t0, g, h
add t1, i, j
sub f, t0, t1
```