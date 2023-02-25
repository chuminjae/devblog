---
layout: post
title:  "Chi square anaylsis program"
date:   2023-02-15 00:05:01 +0900
categories: Programming
---

## Introduction

These days I am studying Ap. biology. While studying this subject, I do a lot of chi square test to test the validity of the null hypothesis. I thought that a program that could do this test would be very convenient, so I started to build it.

## Link

This is the link for equations of chi square test.
[Link of chi square test](https://www.youtube.com/watch?v=CdM92yExsj0)

## Code Block 1

```c++
# include <bits/stdc++.h>
# include <fstream>
#include <windows.h>
using namespace std;
int n;
double ob[1000000];
double ex[1000000];
double wr[1000000];
int c;
double p;
bool check = true;
double sum;
string k;
int main(){
    cout<< "Please enter the total number of phenotypes and test cases" << "\n";
    cin >> n >> c;
    n--;
    Sleep(2000);
    while(check){
        cout << "Will you set the p value 0.05 or 0.01? Press Y for 0.05 N for 0.01" << "\n";
        cin >> k;
        if(k == "Y" || k =="N" || k == "y" || k == "n"){
            check = false;
            if(k == "Y" || k == "y"){
             p = 0.05;
            }
            else{
                p = 0.01;
            }
        }
        system("cls");
        Sleep(2000);
    }
    if(p == 0.05){
        if(n == 1){
            p = 3.84;
        }
        else if(n == 2){
            p = 5.99;
        }
        else if(n == 3){
            p = 7.82;
        }
        else if(n == 4){
            p = 9.49;
        }
        else if(n == 5){
            p = 11.07;
        }
        else if(n == 6){
            p = 12.59;
        }
        else if(n == 7){
            p = 14.07;
        }
        else if(n == 8){
            p = 15.51;
        }
 }
  if(p == 0.01){
        if(n == 1){
            p = 6.63;
        }
        else if(n == 2){
            p = 9.21;
        }
        else if(n == 3){
            p = 11.34;
        }
        else if(n == 4){
            p = 13.28;
        }
        else if(n == 5){
            p = 15.09;
        }
        else if(n == 6){
            p = 16.81;
        }
        else if(n == 7){
            p = 18.48;
        }
        else if(n == 8){
            p = 20.09;
        }
 }
    cout << "Please enter the expected value and observed value"  << "\n";
    for(int i = 0; i < c; i++){
        int k = i + 1;
        cout << "expected value" << k;
        cout << "       ";
        cout << "observed value" << k  << "\n";
        cin >> ex[i] >> ob[i];
        cout << "\n";
    }
    for(int i = 0; i < c; i++){
        wr[i] = pow((ex[i] - ob[i]), 2) / ex[i];
        sum += wr[i];
    }
    Sleep(2000);
    system("cls");
    write();
    if(sum > p){
        cout << "The critical value is ";
        cout << p << "\n";
        cout << "The chi square value is ";
        cout << sum << "\n";
        cout << "Sorry the hypothesis is rejected" << "\n";
        cout << "Your analysis is shown in analysis.txt";
    }
    else{
         cout << "The critical value is";
        cout << p << "\n";
        cout << "The chi square value is";
        cout << sum << "\n";
        cout << "The hypothesis is accepted" << "\n";
        cout << "Your analysis is shown in analysis.txt";
    }
}
```

## Example

This images explain the progression of the values when the computer uses the variable to do chi square test.
[chi](https://res.cloudinary.com/dgq2zzviv/image/upload/v1677345771/Screenshot_2023-02-26_021748_uijfou.png)

## Demonstration1

The code itself is very simple. If the user plugs in the number of test case, phenotype, p value, observed value, and expected value, the program will automatically tell you that the hypothesis is rejected or not which is very convenient. Making this code is very very very simple. The console needs the value of test case, phenotype number, p value, observed value, and expected value to calculate the chi square value and critical value. To make the programm more convenient to users, I had assigned each value that is depended on the p value and pheotype number, so it can determine the critical value without an extra input from the users. I used multiple for loops since the program needs to get a lot of different values and calculate. By comparing the critical value and chi square value, the program determines wheter the hypothesis is rejected or accepted.

## Code Block 2

```c++
void write(){
    fstream file("analysis.txt", ios::out | ios::app);
    if(file.fail()){
        cout << "failed to open the file";
    }
    file << "Chi square analysis" << "\n";
    for(int i = 0; i <c; i++){
        file << "The value of the chi square test of phenotype " << i << " is " << wr[i] << "\n";
    }
    if(sum > p){
        file << "The critical value is ";
        file << p << "\n";
        file << "The chi square value is ";
        file << sum << "\n";
        file << "Sorry the hypothesis is rejected";
    }
    else{
        file << "The critical value is";
        file << p << "\n";
        file << "The chi square value is";
        file << sum << "\n";
        file << "The hypothesis is accepted";
    }
}
```

## Demonstration2

To help the user to actually record the values that are calculated by the program, I had made a write function to let the program record the values at a text file named analysis.txt. Users will be able to see the values of each phenotype and could know the flow of the calculation.

## Results

This is the screenshot of the analysis.txt made based on the value of the example provided.
[example](https://res.cloudinary.com/dgq2zzviv/image/upload/v1677345771/Screenshot_2023-02-26_021853_zawnzp.png)
