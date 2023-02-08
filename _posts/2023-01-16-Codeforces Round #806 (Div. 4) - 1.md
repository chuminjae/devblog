---
layout: post
title:  "Codeforces Round #806 (Div. 4) - 1"
date:   2023-02-07 00:05:01 +0900
categories: Contest
---

## Introduction

There is a string s
 of length 3
, consisting of uppercase and lowercase English letters. Check if it is equal to "YES" (without quotes), where each letter can be in any case. For example, "yES", "Yes", "yes" are all allowable.

Input
The first line of the input contains an integer t
 (1≤t≤103) — the number of testcases.

The description of each test consists of one line containing one string s
 consisting of three characters. Each character of s
 is either an uppercase or lowercase English letter.

Output
For each test case, output "YES" (without quotes) if s
 satisfies the condition, and "NO" (without quotes) otherwise.

You can output "YES" and "NO" in any case (for example, strings "yES", "yes" and "Yes" will be recognized as a positive response).

## Link

[Link of the question](https://codeforces.com/contest/1703/problem/A)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n;
string s;
bool check(){
    char k = s[0];
    char k1 =s[1];
    char k2 =s[2];
    if(k != 'Y' &&  k!= 'y'){
        return false;
    }
    else if(k1 != 'E' && k1 != 'e'){
        return false;
    }
    else if(k2 != 's' && k2 != 'S'){
        return false;
    }
    return true;
}
int main(){
    cin >> n;
    for(int i = 0; i < n; i++){
        cin >> s;
        if(check()){
            cout << "Yes" << "\n";
        }
        else{
            cout << "No" << "\n";
        }
    }
}
```

## Demonstration
