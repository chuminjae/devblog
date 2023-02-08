---
layout: post
title:  "Codeforces Round #806 (Div. 4) -2"
date:   2023-02-07 00:05:01 +0900
categories: Programming
---

## Introduction

Luca has a cypher made up of a sequence of n wheels, each with a digit ai written on it. On the i-th wheel
he made bimoves. Each move is one of two types:
up move (denoted by U): it increases the i-th digit by 1. After applying the up move on 9, it becomes 0.down move (denoted by D): it decreases the i-th digit by 1. After applying the down move on 0, it becomes 9. Luca knows the final sequence of wheels and the moves for each wheel. Help him find the original sequence and crack the cypher.

Input
The first line contains a single integer t
 (1≤t≤100) — the number of test cases.
The first line of each test case contains a single integer n
 (1≤n≤100) — the number of wheels.
The second line contains n
 integers ai
 (0≤ai≤9) — the digit shown on the i-th wheel after all moves have been performed.

Then nlines follow, the i-th of which contains the integer bi(1≤bi≤10) and bi characters that are either U or D— the number of moves performed on the i-th wheel, and the moves performed. U and D represent an up move and a down move respectively.

Output
For each test case, output n space-separated digits  — the initial sequence of the cypher.

## Link

[Link of the question](https://codeforces.com/contest/1703/problem/C)

## code

``` c++
# include <bits/stdc++.h>
using namespace std;
int cqwe;
int n;
int k;
string s;
int a[100];
int check(){
    for(int i = 0; i < n; i++){
        int p;
        cin >> p;
        a[i] = p;
    }
    for(int i = 0; i < n; i++){
        int t1;
        char t2;
        cin >> t1;
        for(int j = 0; j < t1; j++){
            cin >> t2;
            if(t2 == 'D'){
                if(a[i] < 9){
                    a[i] ++;
                }
                else if(a[i] == 9){
                    a[i] = 0;
                }
            }
            else if(t2 == 'U'){
                if(a[i] == 0){
                    a[i] = 9;
                }
                else{
                    a[i] --;
                }
            }
        }
    }
    for(int i = 0; i < n; i++){
        cout << a[i] << " ";
        a[i] = 0;
    }
    cout << "\n";
}
int main(){
    cin >> cqwe;
    for(int i = 0; i < cqwe; i++){
        cin >> n;
        check();
    }
}
```

## Demonstration
