---
layout: post
title: 1. A C++ PRIMER
excerpt: "A write up of notes made from the first section of Data Structures and Algorithms book"
categories: [Data Structures and Algorithms]
modified: 2019-11-15
comments: true
---

## 1.1.2 Fundamental types

Basic data types : or INTEGRAL TYPES

* bool - Boolean value, either true or false
* char - Character
* short - Short Integer
* int - Integer
* long - Long Integer
* float - single-precison floating-point number
* double - double-precison floating-point number
* enum - represents a set of discrete values.

## Character

A char variable holds a single character. A char in C++ is typically 8-bits, but it depends on implementation. This allows C++ to tailor its generated code to each machine architecture and so achieve maximum efficiency. 

A literal is a constant value appearing in a program. Character literals are enclosed in single quotes, as in “a” or “+”. 

A backslash is used to specify a number of special characters literals as follows :

'\n' newline

’\b’ backspace

‘\'' single quote

'\t' tab

‘\0’ null - sometimes used to indicate end of a string of characters. 

'\”’ double quote

Every character is associated with an integer code. The function int(ch) returns the integer value associated with a character variable ch.

## Integers

An int variable holds a integer. Integers come in three sizes : short int, (plain) int and long int. Short and long are synonyms of short int and long int respectively. 

Decimal number like 0,25,98764, and -3 are all integers 

`If all the digits after the decimal point are zeroes, the number is an integer` 

The suffix `I` or `L` can be added to indicate a long integer eg. 123456778`L`. 

* Suffix - is at the `End` 
* Prefix - is a the `Start`

Octal (base8) constants are specified by prefixing the number with the digit zero `0`
Hexadecimal (base16) constants can be specified by prefixing the number with `0x`

> For example, the literals 256,0400, and 0x100 all represent the integer value 256 in (decimal).

When declaring a variable we have the option of providing a definition, or initial value. If no definition is given the initial value is unpredicatable, so its important that the variable is assigned to a value before being used.

Variable names can consist of letters, digits, or the underscore (_) character, but cannot start with a digit.

C++ doesn’t specify the exact number of bits in each type, but a short is at least 16 bits, and a long is at least 32 bits. There is no requirement for a long to be longer than a short `but can never be shorter!` 

Given a type T , the expression sizeof(T) returns the size of type T, expressed as a multiple of the size of char. 

> For Example, on typical system, a `char` is 8 bits long, and an `int` is 32 bits long, and hence `sizeof(int)` is = 4 (32/8)

## Enumerations

An enumeration is a user-defined type that can hold any set of discrete values.

Once defined, behave much like an integer type, a common use is to provide meaningful names to a set of related values. Each element is assigned to an integer value.By default they count up from 0, but can be changed.

{% highlight c++ %}
enum Day {SUN, MON, TUES, WEDNESDAY, THURSDAY, FRIDAY};
enum Mood {HAPPY =3, SAD = 1, ANXIOUS = 4, SLEEPY = 2}; 

Day today = THURSDAY;  // as enum hold int value from 0 only the elements from 1-5 can be chosen MON,…,SAT
Mood myMood = SLEEPY; // myMood may be HAPPY,…….,SLEEPY
{ endhighlight } 

As a rule of thumb enum names and other constants are written in all CAPITAL LETTERS.

## Floating Point

A variable of type `float` holds a single-precision floating-point number, and a variable of type double holds a double-precision floating-point number. As mentioned before C++ leaves exact number of bits undefined.

By default, floating point Literals, such as 3.14159 and -1234.567 are type double. Notation may be specified as either `e` or `E` as in 1.32E4, meaning 1.32x10^4.

To force a literal to be a float, add the suffix `f` or `F`, as in 1.234e4F or 5.3f

END OF 1.1.2 SECTION


  






