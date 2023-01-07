---
layout: post
title:  [Bronze IV] Square Pasture - 14173
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
사칙연산(arithmetic), 수학(math)

문제 설명
Farmer John has decided to update his farm to simplify its geometry. Previously, his cows grazed in two rectangular fenced-in pastures. Farmer John would like to replace these with a single square fenced-in pasture of minimum size that still covers all the regions of his farm that were previously enclosed by the former two fences.

Please help Farmer John figure out the minimum area he needs to make his new square pasture so that if he places it appropriately, it can still cover all the area formerly covered by the two older rectangular pastures. The square pasture should have its sides parallel to the x and y axes.

입력
The first line in the input file specifies one of the original rectangular pastures with four space-separated integers x1 y1 x2 y2, each in the range 0…10. The lower-left corner of the pasture is at the point (x1,y1), and the upper-right corner is at the point (x2,y2), where x2>x1 and y2>y1.

The second line of input has the same 4-integer format as the first line, and specifies the second original rectangular pasture. This pasture will not overlap or touch the first pasture.

출력
The output should consist of one line containing the minimum area required of a square pasture that would cover all the regions originally enclosed by the two rectangular pastures.

## Link

[Link of the question](https://www.acmicpc.net/problem/14173)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
 int result1 , result2, result;
int main(){
    int x1, x2, y1, y2, z1,z2, p1, p2;
    cin >> x1 >> y1 >> x2 >> y2;
    cin >> z1 >> p1 >> z2 >> p2;
    result1= max(x2, z2) - min(x1, z1);
    result2 = max(y2, p2) - min(y1, p1);
    result = max(result1, result2);
    cout << result * result;
    return 0;
}
```

## Demonstration

Description ommited due to low difficulty.
