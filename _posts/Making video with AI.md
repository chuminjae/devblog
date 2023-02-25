---
layout: post
title:  "Video made with AI"
date:   2023-01-12 00:05:01 +0900
categories: Programming
---

## Introduction

These days artifical intelligence is highly developed. AI such as Chatgpt, Midjounrey, echo helps people to live their life more comfortably. I saw a video about making a video with actual AI. I tried it, and it was a enjoyable journey.

## Link

These are the links that I have used during making this video.
[Link of the making avatar](https://midjourney.com/home/?callbackUrl=%2Fapp%2F)
[Link of the making script](https://chat.openai.com/chat)
[Link of making ]

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
