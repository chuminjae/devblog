---
layout: post
title:  "Codeforces Round #784 (Div. 4)-4"
date:   2023-02-05 00:05:01 +0900
categories: Contest
---

## Introduction

A row of n cells is given, all initially white. Using a stamp, you can stamp any two neighboring cells such that one becomes red and the other becomes blue. A stamp can be rotated, i.e. it can be used in both ways: as BRand as RB.
During use, the stamp must completely fit on the given n cells (it cannot be partially outside the cells). The stamp can be applied multiple times to the same cell. Each usage of the stamp recolors both cells that are under the stamp.
For example, one possible sequence of stamps to make the picture BRBBW could be WWWWW→WWRB–––W→BR–––RBW→BRB–––BW. Here W, R, and B represent a white, red, or blue cell, respectively, and the cells that the stamp is used on are marked with an underline. Given a final picture, is it possible to make it using the stamp zero or more times?
Input
The first line contains an integer t (1≤t≤104) — the number of test cases.

The first line of each test case contains an integer n (1≤n≤105) — the length of the picture.

The second line of each test case contains a string s— the picture you need to make. It is guaranteed that the length of s is n and that s only consists of th characters W, R, and B, representing a white, red, or blue cell, respectively. It is guaranteed that the sum of n over all test cases does not exceed 105.

Output
Output t lines, each of which contains the answer to the corresponding test case. As an answer, output "YES" if it possible to make the picture using the stamp zero or more times, and "NO" otherwise.

You can output the answer in any case (for example, the strings "yEs", "yes", "Yes" and "YES" will be recognized as a positive answer).

## Link

[Link of the question](https://codeforces.com/contest/1669/problem/D)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n;
int k;
string s;
bool check1(int a1, int a2){
    int cnt1 = 0;
    int cnt2 = 0;
    for(int i = a1; i <= a2; i++){
        char k = s[i];
        if(k == 'B'){
            cnt1 ++;
        }
        else if(k == 'R'){
            cnt2++;
        }
        }
        if(cnt1 != 0 && cnt2 == 0){
            return false;
        }
        else if(cnt1 == 0 && cnt2 != 0){
            return false;
        }
        return true;
    }
 
bool check(){
    if(k == 1){
        if(s == "W"){
            return true;
        }
       return false;
    }
    else if(k == 2){
        bool a = true;
        a = check1(0, 1);
        return a;
    }
    else{
        bool a = true;
        int cnttr = 0;
        int n1 = 0;
        for(int i = 0; i < k; i++){
        if(i < k - 1){
            char p = s[i];
            if(p == 'W'){
            a = check1(n1, i);
            if(!a) cnttr ++;
            n1 = i;
        }
        }
        else if(i == k - 1){
            a = check1(n1, i);
            if(!a) cnttr ++;
            }
    }
    if(cnttr!= 0){
        return false;
    }
    return true;
    }
}
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        cin >> k;
        cin >> s;
        if(check()){
            cout << "Yes" << "\n";
        }
        else{
            cout << " No" << "\n";
        }
    }
}
```

## Demonstration
