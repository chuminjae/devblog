---
layout: post
title:  "[Bronze V] 시험 성적 - 9498"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
구현(implementation)

문제 설명
시험 점수를 입력받아 90 ~ 100점은 A, 80 ~ 89점은 B, 70 ~ 79점은 C, 60 ~ 69점은 D, 나머지 점수는 F를 출력하는 프로그램을 작성하시오.

입력
첫째 줄에 시험 점수가 주어진다. 시험 점수는 0보다 크거나 같고, 100보다 작거나 같은 정수이다.

출력
시험 성적을 출력한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/20973)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
char check(int b){
    if( b >= 90 && b <= 100){
        return 'A';
    }
     if( b >= 80 && b <= 89){
        return 'B';
    }
     if( b >= 70 && b <= 79){
        return 'C';
    }
     if( b >= 60 && b <= 69){
        return 'D';
    }
     if( b <= 50){
        return 'F';
    }



    }
int main(){
   int a, b;
   cin >> a;
   cout << check(a);

}
```

## Demonstration

Description ommited due to low difficulty.
