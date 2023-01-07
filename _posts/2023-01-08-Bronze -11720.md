---
layout: post
title:  "[Bronze IV] 숫자의 합 - 11720"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2024 KB, 시간: 0 ms

분류
구현(implementation), 수학(math), 문자열(string)

문제 설명
N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.

입력
첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.

출력
입력으로 주어진 숫자 N개의 합을 출력한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/11720)

## Code Block

```c++
#include <iostream>
#include <string>

using namespace std;

int main()
{   int n;
    string s;
    int sum = 0;
    cin >> n;
    cin >> s;
    for(int i = 0; i < n; i ++){
        sum = sum + s[i] - '0';
    }
    cout << sum;

    return 0;
}
```

## Demonstration

Description ommited due to low difficulty.
