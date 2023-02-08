---
layout: post
title:  "Codeforces Round #784 (Div. 4)-3"
date:   2023-02-05 00:05:01 +0900
categories: Contest
---

## Introduction

Given an array a=[a1,a2,…,an] of n positive integers, you can do operations of two types on it:

Add 1 to every element with an odd index. In other words change the array as follows: a1:=a1+1,a3:=a3+1,a5:=a5+1,…
Add 1 to every element with an even index. In other words change the array as follows: a2:=a2+1,a4:=a4+1,a6:=a6+1,…
Determine if after any number of operations it is possible to make the final array contain only even numbers or only odd numbers. In other words, determine if you can make all elements of the array have the same parity after any number of operations.

Note that you can do operations of both types any number of times (even none). Operations of different types can be performed a different number of times.

Input
The first line contains an integer t (1≤t≤100) — the number of test cases.

The first line of each test case contains an integer n (2≤n≤50) — the length of the array.

The second line of each test case contains n integers a1,a2,…,an (1≤ai≤103) — the elements of the array.

Note that after the performed operations the elements in the array can become greater than 103.

Output
Output t lines, each of which contains the answer to the corresponding test case. As an answer, output "YES" if after any number of operations it is possible to make the final array contain only even numbers or only odd numbers, and "NO" otherwise.
You can output the answer in any case (for example, the strings "yEs", "yes", "Yes" and "YES" will be recognized as a positive answer).

## Link

[Link of the question](https://codeforces.com/contest/1669/problem/C)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n;
string check(){
    int a[100];
    int k = 0;
    int c = 0;
    cin >> k;
    for(int i = 0; i < k; i++){
        cin >> c;
        a[i] = c;
    }
    int e1 = a[1] % 2;
    int e2 = a[0] % 2;
    for(int i = 1; i < k; i += 2){
        if(a[i] % 2 != e1){
            return "No";
        }
    }
    for(int i = 0; i < k; i += 2){
        if(a[i] % 2 != e2){
            return "No";
        }
    }
    return "Yes";
}
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        cout << check() << "\n";
    }
}
```

## Demonstration
