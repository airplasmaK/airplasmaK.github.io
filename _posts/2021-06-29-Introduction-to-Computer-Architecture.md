---
layout: post
title:  "Introduction ot Computer Architecture"
date:   2021-07-03 13:14:12 +0900
categories: Arch CPU
---

# Computer Architecture - Introduction

컴퓨터 아키텍쳐란 뭘까? 필자가 재학 중인 학교에서는 전산과 아키 / 전자과 아키의 명칭이 서로 다른데, 전산과의 경우 `Computer Organization / 전산기조직` 이라는 명칭을 사용하며, 전자과의 경우 `Computer Arhctitecture` 라는, 더 익숙한 명칭을 사용하고 있다. 
실상을 뜯어보면 거의 같은 이야기를 하고 있음을 알 수 있다. 엄연히 다른 두 개념이지만, 구분되어 불리는 사례는 그렇게 많지 않은듯 하다.

흔히 Architecture 하면 떠오르는 ISA 와 uArch 가 주된 내용을 이룰 것이다. ISA와 uArch가 무엇인지로부터 시작하여 Computer Architecture의 Bible이라 부를 수 있는 `David A. Patterson & John L. Hennessy Compuer Organization and Design, Sixth Edition` 순으로 이야기를 풀어나가고자 한다.

참고로, 필자는 전문 용어의 한글화를 매우 싫어하는 사람 중 하나이다. 컴퓨터도 결국 하나의 학문으로 인정받고 있고, 이를 위해서는 세계적으로 논문으로 대화하는 것이 정석이다. 그렇다면 영어로 커뮤니케이션이 이루어지는 것은 당연한 일이고, 이를 억지로 한자어/순우리말로 바꾸어 이야기하는 것은 매우 비효율적이고 쓸데 없는 짓이라고 생각된다. 그렇기에 본 블로그에선 최대한 용어를, 영어 그 자체로 대화하고자 한다.

## ISA? 𝜇Arch?

### ISA

ISA는 Instruction Set Architecture 의 acronym 이다. 얼마 전 애플의 맥북이 M1을 달고 나왔을 때, ISA 에 관한 논의가 활발하게 진행되었었는데, 이때 말하는 ARM, x86, x86-64, amd64 등이 모두 ISA의 일종이다. 이들은 𝜇processor(𝜇P)가 이해할 수 있는 bit 단위의 이진수 명령어들의 집합이라고 볼 수 있다.

예시를 들어 보자. 만약 A 라는 ISA는 총 4비트로 이루어져 있고, `1101` 이라는 instruction 이 `ADD r1 r2`를 의미한다고 치자. 그러나, B 라는 다른 ISA에선 `1101`은 `SUB r1 r2`를 의미할 수도 있다. 저 숫자로 이루어진 것이 아닌, `ADD r1 r2`라는 최소한 사람이 알아먹을 수 있는 형태를 갖춘 것을 어셈블리어라고 부르고, 숫자로 이루어진 것은 기계어라고 볼 수 있다. 이 때 저 단순한 숫자로 보이는 것들을 어떻게 이해하고 𝜇P가 이해할 수 있는지를 정의해놓은 것을 ISA라고 부를 수 있는 것이다. 예시로 든 이진수는 단순히 4비트로 이루어져 있는데, 현대 𝜇P 들은 최소 16비트에서 부터 64비트까지 다양한 명령어 크기를 갖고 있다. 이때 A, B ISA가 `1101`을 이해하는 방식이 다르듯 각 𝜇P 별로 이해할 수 있는 방식이 다를 것이다. 바로 그것을 ISA라고 부른다.

### 𝜇Arch

ISA가 기계어에 대한 interface 같은 느낌이 강했다면, 𝜇Arch 는 하드웨어의 느낌이 강하다. 인텔이나 AMD의 x86 CPU 들을 예시로 들어보자. 인텔의 Core i7-11700K 와 AMD의 Ryzen 7 5800X 모두 거의 동일한 아키텍쳐인 x86-64 / amd64 ISA를 채용하고 있다. 그러나 둘의 L1/2/3 cache의 용량, bus, core의 clock 모두 다르다. 이렇듯 어떤 ISA를 기반으로 하드웨어 implementaion을 𝜇Arch 라고 한다.

## Summary

이렇듯 ISA와 𝜇Arch는 다른 분야에서 있다고 볼 수 있다. 다음 장에서는 ISA에 관련된 내용을 주로 알아보자.