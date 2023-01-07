---
layout: post
title:  "[Bronze I] Cow Gymnastics - 18268"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 0 ms

분류
브루트포스 알고리즘(bruteforcing), 구현(implementation)

문제 설명
In order to improve their physical fitness, the cows have taken up gymnastics! Farmer John designates his favorite cow Bessie to coach the N other cows and to assess their progress as they learn various gymnastic skills.

In each of K practice sessions (1≤K≤10), Bessie ranks the N cows according to their performance (1≤N≤20). Afterward, she is curious about the consistency in these rankings. A pair of two distinct cows is consistent if one cow did better than the other one in every practice session.

Help Bessie compute the total number of consistent pairs.

입력
The first line of the input file contains two positive integers K and N. The next K lines will each contain the integers 1…N in some order, indicating the rankings of the cows (cows are identified by the numbers 1…N). If A appears before B in one of these lines, that means cow A did better than cow B.

출력
Output, on a single line, the number of consistent pairs.

## Link

[Link of the question](https://www.acmicpc.net/problem/18268)

## Code Block

```c++
# include <bits/stdc++.h>
    # include <math.h>
    using namespace std;
    int a[11][21];
    int main(){
    ios_base::sync_with_stdio(0);
    cin.tie(0);
       int k, n;
       int r;
       bool check;
       int cnt = 0;
       cin >> k >> n;
       for(int i = 0; i < k; i++){
        for(int j = 0; j < n; j++){
            cin >> r;
            a[i][r] = j;
        }
       }
       for(int i = 1; i <= n; i++){
            for(int j = 1; j <= n; j++)
            {
                if(i == j) continue;
                check = true;
                for(int e = 0; e < k; e++)
                {
                if(a[e][i] > a[e][j])
                    {
                        check = false;
                    }
                }
                if(check)
                {
                cnt ++;
                }
            }
       }
        cout << cnt;
        return 0;
    }
```

## Demonstration

Description ommited due to low difficulty.
