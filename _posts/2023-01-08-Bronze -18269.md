---
layout: post
title:  "[Bronze I] Where Am I? - 18269"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2024 KB, 시간: 12 ms

분류
브루트포스 알고리즘(bruteforcing), 문자열(string)

문제 설명
Farmer John has gone out for a walk down the road and thinks he may now be lost!

Along the road there are N farms (1≤N≤100) in a row. Farms unfortunately do not have house numbers, making it hard for Farmer John to figure out his location along the road. However, each farm does have a colorful mailbox along the side of the road, so Farmer John hopes that if he looks at the colors of the mailboxes nearest to him, he can uniquely determine where he is.

Each mailbox color is specified by a letter in the range A..Z, so the sequence of N mailboxes down the road can be represented by a string of length N containing letters in the range A..Z. Some mailboxes may have the same colors as other mailboxes. Farmer John wants to know what is the smallest value of K such that if he looks at any sequence of K consecutive mailboxes, he can uniquely determine the location of that sequence along the road.

For example, suppose the sequence of mailboxes along the road is 'ABCDABC'. Farmer John cannot set K=3, since if he sees 'ABC', there are two possible locations along the road where this consecutive set of colors might be. The smallest value of K that works is K=4, since if he looks at any consecutive set of 4 mailboxes, this sequence of colors uniquely determines his position along the road.

입력
The first line of input contains N, and the second line contains a string of N characters, each in the range A..Z.

출력
Print a line containing a single integer, specifying the smallest value of K that solves Farmer John's problem.

## Link

[Link of the question](https://www.acmicpc.net/problem/18269)

## Code Block

```c++
 # include <bits/stdc++.h>
    # include <math.h>
    using namespace std;
    int main(){
        ios_base::sync_with_stdio(0);
        cin.tie(0);
        int n;
        string k;
        string tmp;
        cin >> n >> k;
        bool check;
        for(int i = 1; i <= n; i++){
            check = true;
            for(int j = 0; j <= n - i; j++){
                tmp = k.substr(j, i);
                for(int p = 0; p <= n - i; p++){
                     if(j==p) continue;
                    if(tmp == k.substr(p,i)){
                        check = false;
                    }
                }

            }
            if(check){
                cout << i;
                return 0;
                    }
        }
    }
```

## Demonstration

Description ommited due to low difficulty.
