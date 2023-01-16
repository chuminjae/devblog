---
layout: post
title:  "[Silver III] N과 M (4) - 15652"
date:   2023-01-12 00:05:01 +0900
categories: Programming
---

## Introduction

성능 요약
메모리: 2020 KB, 시간: 8 ms

분류
백트래킹(backtracking)

문제 설명
자연수 N과 M이 주어졌을 때, 아래 조건을 만족하는 길이가 M인 수열을 모두 구하는 프로그램을 작성하시오.

1부터 N까지 자연수 중에서 M개를 고른 수열
같은 수를 여러 번 골라도 된다.
고른 수열은 비내림차순이어야 한다.
길이가 K인 수열 A가 A1 ≤ A2 ≤ ... ≤ AK-1 ≤ AK를 만족하면, 비내림차순이라고 한다.
입력
첫째 줄에 자연수 N과 M이 주어진다. (1 ≤ M ≤ N ≤ 8)

출력
한 줄에 하나씩 문제의 조건을 만족하는 수열을 출력한다. 중복되는 수열을 여러 번 출력하면 안되며, 각 수열은 공백으로 구분해서 출력해야 한다.

수열은 사전 순으로 증가하는 순서로 출력해야 한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/15652)

## Code Block

```c++
# include <bits/stdc++.h>
using namespace std;
int n, depth;
int store[100];
bool check[100];
void k(int q){
    int c = q;
    if(c == depth){
        for(int i = 0; i < depth; i++){
            cout << store[i] << " ";
        }
        cout << "\n";
    }
    else{
        for(int i = 1; i <= n; i++){
            if(!check[i]){
                for(int j = i - 1; j >= 0; j--){
                    check[j] = true;
                }
                store[c] = i;
                k(c + 1);
                for(int j = i - 1; j >= 0; j--){
                    check[j] = false;
                }
            }
        }
    }
}
int main(){
    cin >> n >> depth;
    k(0);
}
```

## Demonstration

People can use a basic backtracking algorithm to solve this question. This algorithm calls the k method a lot of times till it reaches the maximum node which can take till c equals depth. Once the method reaches one node, it turns the boolean value true of the node that has a smaller value than the reached value, so that it can remove getting the value smaller than the current value. This algorithm stores the node value and takes it to the array. As a result, we can have a sequence that fits with the answer.
