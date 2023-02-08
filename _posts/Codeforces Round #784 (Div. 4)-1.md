---
layout: post
title:  "Codeforces Round #784 (Div. 4)-1"
date:   2023-02-05 00:05:01 +0900
categories: Programming
---

## Introduction

Codeforces separates its users into 4 divisions by their rating:
For Division 1: 1900≤rating
For Division 2: 1600≤rating≤1899
For Division 3: 1400≤rating≤1599
For Division 4: rating≤1399

Given a rating, print in which division the rating belongs.

Input
The first line of the input contains an integer t (1≤t≤104) — the number of testcases.

The description of each test consists of one line containing one integer rating (−5000≤rating≤5000).

Output
For each test case, output a single line containing the correct division in the format "Division X", where X is an integer between 1 and 4 representing the division for the corresponding rating.

## Link

[Link of the question](https://codeforces.com/contest/1669/problem/A)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n;
int k;
void check(){
    cin >> k;
    if(k >= 1900){
        cout << "Division 1" << "\n";
    }
    else if(k >= 1600){
        cout << "Division 2" << "\n";
    }
    else if(k >= 1400){
        cout << "Division 3" << "\n";
    }
    else if(k <= 1399){
        cout << "Division 4" << "\n";
    }
}
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        check();
    }
}
```

## Demonstration
