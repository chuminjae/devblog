---
layout: post
title:  "Codeforces Round #784 (Div. 4)-2"
date:   2023-02-05 00:05:01 +0900
categories: Programming
---

## Introduction

Given an array a of n elements, print any value that appears at least three times or print -1 if there is no such value.

Input
The first line contains an integer t (1≤t≤10000) — the number of test cases.

The first line of each test case contains an integer n (1≤n≤200000) — the length of the array.

The second line of each test case contains n
 integers a1,a2,…,an (1≤ai≤n) — the elements of the array.

It is guaranteed that the sum of n over all test cases does not exceed 2⋅105 (200000).

Output
For each test case, print any value that appears at least three times or print -1 if there is no such value.

## Link

[Link of the question](https://codeforces.com/contest/1669/problem/B)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n;
int cnt1[200001];
void check(){
    int k;
    cin >> k;
    int p = 0;
    int b = -1;
    for(int i = 1; i <= k; i++){
        cin >> p;
        cnt1[p] ++;
    }
    for(int i = 1; i <= k; i++){
        if(cnt1[i] >= 3){
            b = i;
        }
    }
    for(int i = 0; i < 200001; i++){
        cnt1[i] = 0;
    }
    cout << b << "\n";
}
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        check();
    }
}
```

## Demonstration
