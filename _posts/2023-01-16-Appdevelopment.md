---
layout: post
title:  "App development"
date:   2023-01-20 00:05:01 +0900
categories: Calluscompany
---

## Introduction

After drawing UI/UX designs, our team started actual development. We had a chance to study Kotlin, which is an open-source programming language based on JVM, XML, and OOP. We also learned about object-oriented programming which is called OOP.

## What is OOP?

OOP as known as object-oriented programming has 4 main traits: encapsulation, abstraction, polymorphism, and inheritance. Object-oriented programming is a very important concept that computer science teaches. OOP is the most abstract and simplest version of programming real-life problems on the computer.

## Encapsulation

The first trait encapsulation is wrapping related variables or methods within a class. This will help hide the specific datas used in debugging. This is convenient because the programmer can only change the internal code in the class without changing every single code.

## Abstraction

The next trait is abstraction. Abstraction is kind of complex to understand, but it is easy to understand with an example. For example, I am trying to write some code related to animals. The common trait of animals is hunting. Without abstraction, I would have to write every code for hunting for each animal. However, if I write a code related to hunting, I could just add codes for hunting in animal traits. This is an example of abstraction. The effects of abstraction are simplifying the similarities between each object and increasing the efficiency of the program.

## Polymorphism

The next concept is polymorphism. This is complex but simple. If you need to make a constructor, you would only be able to make a constructor to accept the values within the same name. However, by using OOP (object-oriented programming), you could have different types of constructors within the same name which is called the overloaded method. To summarize, polymorphism allows the program to have different procedures depending on the situation which results in different types of outcomes.

## Inheritance

The next trait is inheritance. The concept of inheritance is very simple. This is just related to recycling the same code. For example, if you want to make a cookie. However, you would never try to make a cookie on your instinct. It would be very hard to make a cookie with your instinct, but you can refer to a recipe. Since you are making the same cookie using the same recipe would be very convenient. Using the same recipe is the concept of inheritance.

## Development

Our team is using XML instead of Kotlin because XML is more efficient than kotlin. XML is very effective since programmers can see the actual android page while programming the page. This is the code we have made to create the first page of our game.

## Code

```XML
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#DBE6E5"
    tools:context=".MainActivity">
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="두더지를 잡아보세요"
        android:textColor="#1C1E1E"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.6" />

    <ImageView
        android:id="@+id/imageView2"
        android:layout_width="200dp"
        android:layout_height="250dp"
        app:srcCompat="@drawable/mole"
        app:layout_constraintBottom_toBottomOf="@+id/textView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:layout_editor_absoluteX="103dp"
        tools:layout_editor_absoluteY="120dp"
        android:src="mole.png"
        />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="@color/cardview_dark_background"
        android:text="시작"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="@+id/textView"
        app:layout_constraintVertical_bias="0.4" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## Android page

This is the android page that is created through the code above.
![androidpage](https://res.cloudinary.com/dgq2zzviv/image/upload/v1674238727/Screenshot_2023-01-21_031748_q07uiy.png)
