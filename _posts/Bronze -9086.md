---
layout: post
title:  "[Bronze V] 문자열 - 9086"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 1112 KB, 시간: 0 ms

분류
구현(implementation), 문자열(string)

문제 설명
문자열을 입력으로 주면 문자열의 첫 글자와 마지막 글자를 출력하는 프로그램을 작성하시오.

입력
입력의 첫 줄에는 테스트 케이스의 개수 T(1 ≤ T ≤ 10)가 주어진다. 각 테스트 케이스는 한 줄에 하나의 문자열이 주어진다. 문자열은 알파벳 A~Z 대문자로 이루어지며 알파벳 사이에 공백은 없으며 문자열의 길이는 1000보다 작다.

출력
각 테스트 케이스에 대해서 주어진 문자열의 첫 글자와 마지막 글자를 연속하여 출력한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/9086)

## Code Block

```c
#include <stdio.h>
//#include <iostream>
#include <string.h>

//using namespace std;

int main()
{
    int n;
    scanf("%d", &n);
    for(int i=0; i<n; i++){
        char ch[1001];
        scanf("%s", ch); // abcd
        int len = strlen(ch); // len : 4
        printf("%c%c\n", ch[0],ch[len-1]);
    }
    return 0;
}
```

## Demonstration

Description ommited due to low difficulty.
