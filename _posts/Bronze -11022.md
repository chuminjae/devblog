---
layout: post
title:  "[Bronze V] A+B - 8 - 11022"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 4 ms

분류
구현(implementation), 사칙연산(arithmetic), 수학(math)

문제 설명
두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

입력
첫째 줄에 테스트 케이스의 개수 T가 주어진다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

출력
각 테스트 케이스마다 "Case #x: A + B = C" 형식으로 출력한다. x는 테스트 케이스 번호이고 1부터 시작하며, C는 A+B이다.

## Link

[Link of the question](https://www.acmicpc.net/problem/11022)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n;
    int a, b;
    cin >> n;
    for(int i = 0; i < n; i++){
        cin >> a >> b;
        cout << "Case #" << i + 1 << ": "<< a<<" + " << b << " = " << a + b << "\n";
    }
    return 0;
}
```

## Demonstration

Description ommited due to low difficulty.
