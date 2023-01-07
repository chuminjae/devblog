---
layout: post
title:  [Bronze I] Triangles (Bronze) - 18786
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
브루트포스 알고리즘(bruteforcing), 기하학(geometry)

문제 설명
Farmer John would like to create a triangular pasture for his cows.

There are N fence posts (3≤N≤100) at distinct points (X1,Y1)…(XN,YN) on the 2D map of his farm. He can choose three of them to form the vertices of the triangular pasture as long as one of the sides of the triangle is parallel to the x-axis and another side is parallel to the y-axis.

What is the maximum area of a pasture that Farmer John can form? It is guaranteed that at least one valid triangular pasture exists.

입력
The first line of the input contains the integer N. Each of the next N lines contains two integers Xi and Yi, each in the range −104…104 inclusive, describing the location of a fence post.

출력
As the area itself is not necessarily an integer, output two times the maximum area of a valid triangle formed by the fence posts.

## Link

[Link of the question](https://www.acmicpc.net/problem/18768)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
int area;
int result;
int main(){
    int a;
    cin >> a;
    int x[a];
    int y[a];
    for(int i = 0; i < a; i++){
        cin >> x[i] >> y[i];
    }
    for(int j = 0; j < a; j++){
        for(int p = 0; p < a; p++){
          for(int k = 0; k < a; k++){
            if(x[j] == x[p] && y[p] == y[k]){
              area = abs((y[p] - y[j])) * abs((x[k] - x[p]));
              result = max(result, area);
            }
          }
        }
    }
     cout << result;
}
```

## Demonstration

Description ommited due to low difficulty.
