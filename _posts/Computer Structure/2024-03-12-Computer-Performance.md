---
layout: post
title: Computer Performance
subtitle: 컴퓨터의 퍼포먼스에 대한 전반적인 이해
date: 2024-03-12 09:00 +0900
categories: Computer Structure
---
# Performance를 결정하는 여러가지 요소

- Algorithm
- Programming Lang, Compiler, Architecture
- Processor and Memory system
- I/O system (include OS)

# Seven Great Ideas

- *Abstraction*: 세부사항은 가리고, 디자인은 간단하게
- *Common case fast*: 많이 사용되는 것을 빠르게
- *Parallelism*:
- *Pipelining*: 명령어를 중첩시키기.
- *Prediction*
- *Hierarchy of memories*
- *Dependability via redundancy*

# Below Your Program...

- Application Software
- System Software
	- Compiler 기계어로 번역
	- Operating system 스케줄링...
- Hardware

# Levels of Program Code

- High-level Lang
	- 조금 더 읽기 쉬운 코드
	- 하드웨어 종속적이지 않은 코드(*Portability*)
- Assembly
	- instruction을 읽을 수 있는 형태로 표현.
	- 기계어 코드에 1:1로 대응.
- HW Representation

## [Response Time and Throughput](% post_url 2024-03-14-Response-Time-and-Throughput %)
	Cpu에서의 성능 평가
- Response Time: task를 끝내는 데 걸리는 시간
- Throughput: 단위 시간 당 완료된 task 수

- 성능이 좋지만 단일 task만 처리 가능한 cpu
	Response Time: Good, Throughput: Bad
- 성능은 좀 떨어지지만 병렬 처리 가능한 cpu
	Response Time: Bad, Throughput: Good

### Relative Performance
- Def: Performance = 1/Execute Time


