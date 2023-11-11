---
layout: single
title: "Lagrange multiplier"
categories: mathematics
tags: [calculus]
use_math: true
publish: false
author_profile: false
toc: true
---

# 0. Overview

## 0.1. Motivation

이번 주 수요일(11/8)에, 직장 선배분이 Lagrange multiplier(라그랑지 승수법)에 대해 물어보셨습니다.
정확하게는 constraint(제약조건)의 개수가 2개인 Lagrange multiplier에 대해 문의하셨습니다.
그날 밤에 퇴근하면서 핸드폰으로 세 개 자료 정도를 읽었고, 집에 도착해서 그 자료들을 A4용지에 써가면서 확인해보니 그 내용이 이해가 갔습니다.
다음 날 아침에 정리한 내용을 선배에게 공유해드릴 수 있었고, 그리고 공부한 김에 관련 내용을 정리해서 오늘 (11/11, 토요일) 블로그에 포스팅합니다.

## 0.2. 자료들

참고한 자료들은 다음의 세 개 입니다.
 - [[1] Paul's Online Notes / Section 14.5 : Lagrange Multiplier](https://tutorial.math.lamar.edu/classes/calciii/lagrangemultipliers.aspx)
 - [[2] MIT OpenCourseWare / Proof of Lagrange Multiplier](https://ocw.mit.edu/courses/18-02sc-multivariable-calculus-fall-2010/ebbeb8e61827a8058d2c45b674d003b3_MIT18_02SC_notes_22.pdf)
 - [[3] University of British Columbia / An Example with Two Lagrange Multiplier](https://personal.math.ubc.ca/~feldman/m226/multiLagrange.pdf)

[1]에는 Lagrange multiplier에 대한 아주 기본적인 설명과 예제가 있습니다.
[2]에는 Lagrange multiplier에 대한 증명 혹은 설명을 두 가지(기하학적인 설명, 해석적인 증명)로 제시하고 있습니다.
이때, [1]과 [2]는 모두 constraint의 개수가 1개인 Lagrange multiplier에 대해 다루고 있고 변수의 개수는 2개 또는 3개입니다.
[3]에서는 constraint의 개수가 2개이고 변수의 개수가 3개인 Lagrange multiplier의 방법론을 기하학적으로 증명하고, 예시도 들고 있습니다.

그러니까, 아주 일반적인 Lagrange multiplier에 대해서는 보지 않은 셈입니다.
다시 말해, 변수의 개수와 constraint의 개수가 임의로 주어지는 경우에 대해서는 보지 않았습니다.
이러한 일반적인 경우에 대해서는
- [[4] Carnegie Mellon University / A Proof of the method of Lagrangian Multiplier](https://www.math.cmu.edu/~gautam/sj/teaching/2016-17/269-vector-analysis/pdfs/lagrange.pdf)

에 자세히 설명되어 있는듯한데, 이 자료는 보지 않았습니다.

## 0.3. 이전 공부

학부 1학년 2학기에 Lagrange multiplier에 대해 배웠던 것 같습니다.
그런데 아마도 시험범위에는 속하지 않았던 것 같기도 합니다.
워낙 vector calculus에서 다루는 내용이 방대하니, Lagrange multiplier는 뒷전이었던 것 같습니다.
그 이후 해석학이나 다른 학부 수업에서는 이걸 다루는 걸 거의 못봤고, 기하학 수업에서 잠깐 K교수님이 언급하는 걸 들었던 것도 같습니다.
사실 1학년 수준에서 생각될 수 있는 기본적인 수학이라서 이후에 굳이 다룰 필요가 없었을는지도 모르겠습니다.

대학원에서, 매학기 초에 "미적분 조교자격시험"이라는 걸 치러야 했습니다.
이 시험은 한 번 통과하면 다음 학기에는 다시 치르지 않아도 됐는데, 제가 다닐 당시에는 이 시험을 너무 어렵게 내서 대학원생들 중 거의 아무도 시험에 통과하지 못했었습니다.
그러니까, 문제들 각각은 고민하면 풀리는 문제이긴 한데, 한시간 안에 풀려니 풀 수가 없었습니다.
그 때문에 거의 네 학기 정도 동안 (어느 순간엔가는 통과했습니다.) 매학기 초마다 1학년 미적분 전체 범위에 대해 시험을 봐야 했었고, 그때 Lagrange multiplier 문제가 꽤 자주 나왔었던 것 같습니다.

## 0.4. Overview

Lagrange multiplier는 다음과 같은 방법론을 지칭합니다.

다음과 같은 문제가 있다고 합시다.

---

이후에는 0.2에서 언급한 각 자료들에 대해 나열합니다.

## 1. Paul's Online Notes

 - [[1] Paul's Online Notes / Section 14.5 : Lagrange Multiplier](https://tutorial.math.lamar.edu/classes/calciii/lagrangemultipliers.

