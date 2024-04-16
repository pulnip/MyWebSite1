---
layout: post
title: Response Time and Throughput
subtitle: 컴퓨터의 퍼포먼스는 어떻게 측정할 수 있는가.
date: 2024-03-14 00:10:30 +0900
categories: Computer Structure
---
# Measuring Execution
- Elapsed time
	- **total** response time, including all aspects
	- ex. processing, i/o, os overhead, idle time, ...
	- determine sys performance
- CPU time
	- **only processing**

# CPU Time

총 연산을 끝내기 위해서 Clock Rate 대비 몇 Cycle이 필요한가?
- 2GHz만큼의 성능을 가진 컴퓨터보다는 4GHz만큼의 그것이 더 좋음.
- 같은 연산에 대해서, 200cycle에 끝내는 게 400cycle에 끝내는 게 더 좋음.

# Instruction Count and CPI
	Instruction마다 필요한 cycle수(혹은 소요시간) 다름.

CPU Time의 cycle을 Instruction 관점에서 좀 더 자세히 바라보면, cycle은 다음과 같다.
- instruction마다 소비하는 cycle이 있음.
	- cycle은 일종의 비용임.
- 해당 연산에 몇 개의 instruction을 소비하는가?
\(\text{CPU Time}=\frac{\text{CPU Clock Cycles}}{\text{Clock Rate}}=\frac{\Sigma(\text{Instruction n Count}*\text{Clock cycle Per Instruction})}{\text{Clock Rate}}\)

- Computer A: Cycle Time = 250ps, CPI = 2.0
- Computer B: Cycle Time = 500ps, CPI = 1.2
- In Same ISA, Which is faster, and by how much?

| instruction | clock cycle | IC in sequence 1 | IC in sequence 2 |
| :---------: | :---------: | :--------------: | :--------------: |
|      A      |      1      |        2         |        4         |
|      B      |      2      |        1         |        1         |
|      C      |      3      |        2         |        1         |

sequence 1에서 필요한 cycle수는 $1*2+2*1+3*2=10$이고, 평균 CPI는 $\frac{10}{2+1+2}=5$이다.


# 암달의 법칙
$$\text{T}_\text{improved}=\frac{\text{T}_\text{affected}}{\text{improvment factor}}+\text{T}_{\text{unaffected}}$$

총 100초가 걸리는 일이 있다고 하자. 이 일 중에 80초가 걸리는 어떤 부분을 5배 빠르게 했을 때, 전체 일로 보면 5배가 빨라진 게 아니라 3배가 빨라졌다. 여기에서 더 나아가, 이 80초가 걸리는 부분을 (거의) 0초만에 끝낼 수 있다고 하더라도, 나머지 20초가 있기에 전체 시간은 무조건 20초 이상이다.

## Fallacy: Low Power at Idle

100% 부하일 때 258W를 소모하고, 50% 부하일 때 170W(66%)를 소모하고, 10% 부하일 때 121W(47%)를 소모한다. 그렇다면, 0% 부하(Idle)일 때 소모하는 전력량은? 당연히 0W가 아니다!
