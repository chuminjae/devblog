---
layout: post
title:  [Bronze I] Do You Know Your ABCs? - 20650
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
수학(math), 정렬(sorting)

문제 설명
Farmer John's cows have been holding a daily online gathering on the "mooZ" video meeting platform. For fun, they have invented a simple number game to play during the meeting to keep themselves entertained.

Elsie has three positive integers A, B, and C (A≤B≤C). These integers are supposed to be secret, so she will not directly reveal them to her sister Bessie. Instead, she gives Bessie seven (not necessarily distinct) integers in the range 1…109, claiming that they are A, B, C, A+B, B+C, C+A, and A+B+C in some order.

Given a list of these seven numbers, please help Bessie determine A, B, and C. It can be shown that the answer is unique.

입력
The only line of input consists of seven space-separated integers.

출력
Print A, B, and C separated by spaces.

## Link

[Link of the question](https://www.acmicpc.net/problem/20650)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
int nums[7];
for (int i = 0; i < 7; i++) {
   cin >> nums[i];
}
sort(nums, nums + 7);
int a = nums[0], b = nums[1];
int c = nums[6] - a - b;
cout << a << ' ' << b << ' ' << c << '\n';
}
```

## Demonstration

Description ommited due to low difficulty.
