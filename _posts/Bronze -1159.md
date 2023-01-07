---
layout: post
title:  "[Bronze II] 농구 경기 - 1159"
date:   2022-12-28 10:40:42 +0900
categories: development
---

## Introduction

성능 요약
메모리: 2024 KB, 시간: 0 ms

분류
구현(implementation), 문자열(string)

문제 설명
상근이는 농구의 세계에서 점차 영향력을 넓혀가고 있다. 처음에 그는 농구 경기를 좋아하는 사람이었다. 농구에 대한 열정은 그를 막을 수 없었고, 결국 상근이는 농구장을 청소하는 일을 시작했다. 상근이도 농구장을 청소하면서 감독이 되기 위해 가져야할 능력을 공부해나갔다. 서당개 3년이면 풍월을 읊듯이 상근이는 점점 감독으로 한 걸음 다가가고 있었다. 어느 날 그에게 지방의 한 프로농구팀을 감독할 기회가 생기게 되었다. 그는 엄청난 지도력을 보여주며 프로 리그에서 우승을 했고, 이제 국가대표팀의 감독이 되었다.

내일은 일본과 국가대표 친선 경기가 있는 날이다. 상근이는 내일 경기에 나설 선발 명단을 작성해야 한다.

국가대표팀의 감독이 된 이후에 상근이는 매우 게을러졌다. 그는 선수의 이름을 기억하지 못하고, 각 선수의 능력도 알지 못한다. 따라서, 누가 선발인지 기억하기 쉽게 하기 위해 성의 첫 글자가 같은 선수 5명을 선발하려고 한다. 만약, 성의 첫 글자가 같은 선수가 5명보다 적다면, 상근이는 내일 있을 친선 경기를 기권하려고 한다.

상근이는 내일 경기를 위해 뽑을 수 있는 성의 첫 글자를 모두 구해보려고 한다.

입력
첫째 줄에 선수의 수 N (1 ≤ N ≤ 150)이 주어진다. 다음 N개 줄에는 각 선수의 성이 주어진다. (성은 알파벳 소문자로만 이루어져 있고, 최대 30글자이다)

출력
상근이가 선수 다섯 명을 선발할 수 없는 경우에는 "PREDAJA" (따옴표 없이)를 출력한다. PREDAJA는 크로아티아어로 항복을 의미한다. 선발할 수 있는 경우에는 가능한 성의 첫 글자를 사전순으로 공백없이 모두 출력한다.

## Link

[Link of the question](https://www.acmicpc.net/problem/1159)

## Code Block

```c++
#include <bits/stdc++.h>
using namespace std;
#include <iostream>
#include <string>

using namespace std;
int p[27];
int main()
{
    int a;
    cin >> a;
    string b[150];
    int x[150];
    for(int i = 0; i < a; i++){
        cin >> b[i];
    }

    for(int j =0; j < a; j++){
        x[j] = b[j][0];
    }

    int cnt = 0;
    int check = 1;
    for(int i = 0; i < a; i++){
        for(int j = 0; j < a; j++){
            if(x[i] == x[j]){
                cnt++;
            }
        }
        if(cnt >= 5){
            check = 0;
            p[x[i] - 96] = 1;
        }
        cnt = 0;
    }

    if(check == 1){
        cout << "PREDAJA";
    }else{
        for(int i = 1; i < 27; i++){
            if(p[i] == 1){
                cout << (char)(i + 96);
            }
        }
    }
    return 0;
    }
```

## Demonstration

Description ommited due to low difficulty.
