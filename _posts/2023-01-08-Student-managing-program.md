---
layout: post
title:  "Student managing program"
date:   2023-01-08 00:05:01 +0900
categories: development
---

## Introduction

This program is the first program for me to develop a program by myself. This program is used to manage students. It is able to record , the name of each students, the scores of each students, birthday of each students, grade of each students. The point is that this data is converted to an .csv form which is similar with the normal .xls(excel) file we use. By converting some variables this program could be used by anyone who needs this program

## Image of the program

![image1](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20215801.png?raw=true)
![image2](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20215818.png?raw=true)
![image3](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20215836.png?raw=true)
![image4](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20215925.png?raw=true)
![image5](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20220047.png?raw=true)
![image6](https://github.com/chuminjae/Student-managing-program/blob/main/Screenshot%202022-10-06%20220115.png?raw=true)

## Code Block - main.cpp

```c++
#include <bits/stdc++.h>
#include <windows.h>
# include "mainsource.h"

using namespace std;
int cnt;
string Id1;
string password1;
void check()
{
    string Id = "Chuminjae"; // can change the Id by putting in new Id;
    string password =  "123456"; // can change the password by putting in new password;
    int cnt;
    string Id1;
    string password1;

    while (cnt <= 2){
        cout << "\n\n\n\n\n\n\n\n\n" <<"Please enter you Id and password" << "\n";
        cout << "\n"<< "                              Id" << "    ";
        getline(cin , Id1);
        cout << "                              password" <<"   ";
        getline(cin , password1);
        Sleep(1000);
        system("cls");

         if(Id == Id1 && password == password1){
            cout << "log-in succeed" << "\n";
            cout << "Welcome      " <<  "***" << Id << "***";
            Sleep(2000);
            system("cls");
            mainmenu();
        }
        else if((Id == Id1 && password != password1) ){
        cout << "log-in fail" << "\n";
        cout << "password is incorrect";
        Sleep(2000);
        system("cls");
        cnt ++;
        }
        else if((Id != Id1 && password != password1) ){
        cout << "log-in fail" << "\n";
        Sleep(2000);
        system("cls");
        cnt ++;
        }


    }
    if(cnt > 2){
        cout << "Too many attempt shut down program" << "\n";
        for(int i = 1; i < 6; i++){
            cout << i << "\n";
            Sleep(1000);
        }
        system("cls");
    }

}
int main(){
    SetConsoleTitle("Student information");
    system("color A1");

    check();
    return 0;


    }
```

## Code Block - mainsource.h

```c++
# include <bits/stdc++.h>
# include <fstream>
# include <Windows.h>
#include <stdlib.h>
#include <iostream>
using namespace std;
void addData();
void deleteAllData();
void viewingData();
void mainmenu();
void identification();
void teacherpage();
void studentpage();


void teacherpage(){
 system ("cls");
    cout << "You are logged in as teacher" << "\n";
    cout << "\n\n\n\n" << "                         " <<    "choose you choice";
    cout << "\n\n\n\n" << "                        " <<    "1. Add information";
    cout << "\n\n\n\n" << "                        " <<    "2. View information";
    cout << "\n\n\n\n" << "                        " <<    "3. Delete Allstudent";
    cout << "\n\n\n\n" << "                       " << " 4.Return to main menu";
    cout << "\n\n\n\n" << "                       " << " 5.exit";
    int choice;
    cout << "\n\n\n\n" << "                        " <<    "Enter your choice";
    do{
         cin >>  choice;
    switch(choice){
case 1:
    addData();
    break;
case 2:
    viewingData();
    break;
case 3:
    deleteAllData();
    break;
case 4:
    mainmenu();
    break;
case 5:
     system("cls");
     cout << "\n\n\n\n\n\n\n" << "Quitting the program";
    for(int i = 1; i < 4; i++){
            Sleep(1000);
            cout << "....";
        }
        exit(0);
        break;
default:
    system("cls");
    cout << "You are logged in as teacher" << "\n";
    cout << "\n\n\n\n" << "                         " <<    "choose you choice";
    cout << "\n\n\n\n" << "                        " <<    "1. Add information";
    cout << "\n\n\n\n" << "                        " <<    "2. View information";
    cout << "\n\n\n\n" << "                        " <<    "3. Delete Allstudent";
    cout << "\n\n\n\n" << "                     " << "4.Return to main menu";
    cout << "\n\n\n\n" << "                      " << "5.exit";
    cout << "\n\n\n\n" << "                 " << "wrong input";
    cout << "\n\n\n\n" << "                 " << "Enter your choice";

}
    }while(choice != 6);
}


void identification(){
    system("cls");
    string password = "12345";
    string password1;
    cout << "\n\n\n\n\n\n\n\n\n\n" << "               " << "enterpassword: ";
    do
    {
        cin >> password1;
        if(password != password1){
            system("cls");
            cout << "\n\n\n\n\n" << "           wrong password, try one more time or type" << "\"Exit\" to go back to menu";
            cout << "\n\n\n\n" << "               " << "enter password:";
        }
        if(password == "Exit")
            {
            mainmenu();
        }



    }while(password != password1);
    teacherpage();
}

void mainmenu(){
    system("cls");
    cout << "welcome! You are logged in" ;
    system("cls");
    cout << "\n\n\n\n" << "                         " <<    "choose you choice";
    cout << "\n\n\n\n" << "                        " <<    "1. Teacher";
    cout << "\n\n\n\n" << "                        " <<    "2. Student";
    cout << "\n\n\n\n" << "                        " <<    "3. Exit";
    cout << "\n\n\n\n" << "                        " <<    "Enter your choice";
    int a;
    cin >> a;
    switch(a){
    case 1:
        system("cls");
        identification();
        break;
    case 2:
        system("cls");
        cout << "logged in as a student";
        studentpage();
        break;
    case 3:
        system("cls");
        cout << "exiting";
        for(int i = 1; i < 4; i++){
            Sleep(1000);
            cout << "....";
        }
        exit(0);
        break;
    default:
        system("cls");
        cout << "invalid input";
    }
     system("pause");
}


void addData(){
    system("cls");
    fstream file("info.csv", ios::out | ios::app);
    if(file.fail()){
        cout << "failed to open the file";
    }

    else{
        string c, studentname, grade, birthday, chliterature, Enliterature, biology, calculus, history, AcademicEnglish;
        cout << "\n\n\n\n\n" << "           " << "Please enter data" << "\n";
        cout << "Please enter the number of the student" << "\n";
        cin >> c;
        file <<"\n"<< c << ',';
        cout << "Please enter the name of the student" << "\n";
        cin >> studentname;
        file << studentname << ',';
        cout << "Please enter the grade of the student" << "\n";
        cin >> grade;
        file << grade << ',';
        cout << "Please enter the birthday of the student" << "\n";
        cin >> birthday;
        file << birthday << ',';
        cout << "Please enter the score of chinese literature of the student" << "\n";
        cin >> chliterature;
        file << chliterature << ',';
        cout << "Please enter the score of English literature of the student" << "\n";
        cin >> Enliterature;
        file << Enliterature << ',';
        cout << "Please enter the score of Biology of the student" << "\n";
        cin >> biology;
        file << biology << ',';
        cout << "Please enter the score of Calculus of the student" << "\n";
        cin >> calculus;
        file << calculus << ',';
        cout << "Please enter the score of history of the student" << "\n";
        cin >> history;
        file << history << ',';
        cout << "Please enter the score of Academic English of the student" << "\n";
        cin >> AcademicEnglish;
        file << AcademicEnglish;
    }
    file.close();
        char more;
        cout << "Do you want to add more data?" << "\n";
        cout << "(Y|N)" << "\n";
        cin >> more;
        if (more == 'Y')
        {
            addData();
        }
    else if (more == 'N'){
        teacherpage();
    }

    else{
         cout << "Enter a valid option";
         teacherpage();

    }
}
void viewingData(){
        system("cls");
        string number, studentname, grade, birthday, chineseliterature, Englishliterature, biology,calculus, history, AcademicEnglish;
        fstream file("info.csv");
        cout << "            #Student Record" << "\n";
        cout << "                        " << "\n" << "\n";
        cout << "number" << "  " << "name" << "    " << "grade   " << "birthday " << "chineseliterature "  << "Englishliterature  " << "biology    " << "calculus   " << "history    " << "AcademicEnglish"  << "\n";
        if(file.fail()){
            cout << "failed to open the file";
        }
        while(!file.eof()){
            getline(file, number, ',');
            getline(file, studentname, ',');
            getline(file, grade, ',');
            getline(file, birthday, ',');
            getline(file, chineseliterature, ',');
            getline(file, Englishliterature, ',');
            getline(file, biology, ',');
            getline(file, calculus, ',');
            getline(file, history, ',');
            getline(file, AcademicEnglish, '\n');
            cout << number << "   " << studentname << "    " << grade << "      " << birthday << "    " << chineseliterature << "    " << Englishliterature << "    " << biology << "     " <<calculus << "    " << history << "    " << AcademicEnglish << "\n";

        }

        cout << "\n";
        cout << "______________________________________" << "\n";
        file.close();
        Sleep(3000);
        cout << "\n\n\n\n" << "                         " <<    "choose you choice";
        cout << "\n\n\n\n" << "                        " <<    "1. Add information";
        cout << "\n\n\n\n" << "                        " <<    "2. Delete Allstudent";
        cout << "\n\n\n\n" << "                     " << "3.Return to main menu";
        cout << "\n\n\n\n" << "                      " << "4.exit program";
        cout << "\n\n\n" << "                    ";
        int f;
        cin >> f;
        switch(f){
    case 1:
        addData();
        break;
    case 2:
        deleteAllData();
        break;
    case 3:
        mainmenu();
    case 4:
          system("cls");
        cout << "exiting";
        for(int i = 1; i < 4; i++){
            Sleep(1000);
            cout << "....";
        }
        exit(0);
        break;
    }
    }


void deleteAllData(){
    system ("cls");
    int number = 1;
    fstream fin;
    fstream fout;
    string line;
    fin.open ("info.csv", ios::in);
    fout.open("newfile.csv", ios :: out);
    vector<string> w;
    while(!fin.eof()){
        w.clear();
        getline(fin, line);
        w.push_back(line);
    }
    int k = w.size();
    for(int i = 1; i < k + 1; i ++){
        if(i != number){
            fout << w[i - 1];
        }
    }
    fin.close();
    fout.close();
    remove("info.csv");
    rename("newfile.csv", "info.csv");

    Sleep(2000);
    teacherpage();
}
void studentpage(){
    system("cls");
        string number, studentname, grade, birthday, chineseliterature, Englishliterature, biology,calculus, history, AcademicEnglish;
        fstream file("info.csv");
        cout << "            #Student Record" << "\n";
        cout << "                        " << "\n" << "\n";
        cout << "number" << "  " << "name" << "    " << "grade   " << "birthday " << "chineseliterature "  << "Englishliterature  " << "biology    " << "calculus   " << "history    " << "AcademicEnglish" << "\n";
        if(file.fail()){
            cout << "failed to open the file";
        }
        while(!file.eof()){
            getline(file, number, ',');
            getline(file, studentname, ',');
            getline(file, grade, ',');
            getline(file, birthday, ',');
            getline(file, chineseliterature, ',');
            getline(file, Englishliterature, ',');
            getline(file, biology, ',');
            getline(file, calculus, ',');
            getline(file, history, ',');
            getline(file, AcademicEnglish, '\n');
            cout << number << "   " << studentname << "    " << grade << "      " << birthday << "    " << chineseliterature << "    " << Englishliterature << "    " << biology << "     " <<calculus << "    " << history << "    " << AcademicEnglish << "\n";

        }
         cout << "______________________________________" << "\n";
         file.close();
         system("pause");
         mainmenu();
}
```

## Reflection

It was the first actual complex program that I made. It took a lot of time, and some parts were very hard to solve or think about. However, it was a great chance for me to challenge myself and expand my thoughts. I also was able to learn lots of functions such as system, Sleep, fstream...etc. Even if the process was kind of making my head sick, I really liked the process. I will build another project soon.
