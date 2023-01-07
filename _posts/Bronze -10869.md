---
layout: post
title:  [Bronze V] 사칙연산 - 10869
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
구현(implementation), 사칙연산(arithmetic), 수학(math)

문제 설명
두 자연수 A와 B가 주어진다. 이때, A+B, A-B, A*B, A/B(몫), A%B(나머지)를 출력하는 프로그램을 작성하시오.

입력
두 자연수 A와 B가 주어진다. (1 ≤ A, B ≤ 10,000)

출력
첫째 줄에 A+B, 둘째 줄에 A-B, 셋째 줄에 A*B, 넷째 줄에 A/B, 다섯째 줄에 A%B를 출력한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/10869)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
int main(){
    int n, k;
    cin >> n >> k;
    cout << n + k << "\n";
    cout << n - k << "\n";
    cout << n * k << "\n";
    cout << n / k<< "\n";
    cout <<  n % k << "\n";


    }
```

## Demonstration

Description ommited due to low difficulty.
