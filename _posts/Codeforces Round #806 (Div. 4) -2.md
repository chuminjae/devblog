---
layout: post
title:  "Codeforces Round #806 (Div. 4) -2"
date:   2023-02-07 00:05:01 +0900
categories: Programming
---

## Introduction

In an ICPC contest, balloons are distributed as follows:

Whenever a team solves a problem, that team gets a balloon.
The first team to solve a problem gets an additional balloon.
A contest has 26 problems, labelled A, B, C, ..., Z. You are given the order of solved problems in the contest, denoted as a string s, where the i-th character indicates that the problem si has been solved by some team. No team will solve the same problem twice.
Determine the total number of balloons that the teams received. Note that some problems may be solved by none of the teams.

Input
The first line of the input contains an integer t
 (1≤t≤100) — the number of testcases.

The first line of each test case contains an integer n
 (1≤n≤50) — the length of the string.

The second line of each test case contains a string s of length n consisting of uppercase English letters, denoting the order of solved problems.

Output
For each test case, output a single integer — the total number of balloons that the teams received.

## Link

[Link of the question](https://codeforces.com/contest/1703/problem/B)

## code

``` c++
# include <bits/stdc++.h>
using namespace std;
int n;
int k;
string s;
int ct[26];
int check(){
    int cnt = 0;
    for(int i = 0; i < k; i++){
        char x = s[i];
        if(ct[x - 'A'] == 0){
            cnt += 2;
            ct[x - 'A'] = 1;
        }
        else{
            cnt+= 1;
        }
    }
    for(int i = 0; i < 26; i++){
        ct[i] = 0;
    }
    return cnt;
}
 
 
 
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        cin >> k >> s;
        cout << check() << "\n";
    }
}
```

## Demonstration
