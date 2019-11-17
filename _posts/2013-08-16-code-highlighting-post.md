---
layout: post
title: 1. A C++ Primer
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
{% endhighlight %} 

As a rule of thumb enum names and other constants are written in all CAPITAL LETTERS.

## Floating Point

A variable of type `float` holds a single-precision floating-point number, and a variable of type double holds a double-precision floating-point number. As mentioned before C++ leaves exact number of bits undefined.

By default, floating point Literals, such as 3.14159 and -1234.567 are type double. Notation may be specified as either `e` or `E` as in 1.32E4, meaning 1.32x10^4.

To force a literal to be a float, add the suffix `f` or `F`, as in 1.234e4F or 5.3f

## Pointer

Every program variable is stored in the computer's memory at some location or `Address`

A pointer is a variable that holds the value of the address.

> For example, `int*` denotes a pointer to an integer.

There are two main operators used to manipulate pointers. The first returns the specific address of the given object in the memory, the second returns the contents of the given address.

* First task is performed by the `addressof` operator ‘&’

*Second task is performed by by the `dereferencing `

{% highlight c++ %}

#include<iostream>

int main(){

int a = 6; // declares and stores values of 6 in variable a

int* p_a = &a; // declares the int pointer variable p_a as the address of variable a by using `&`

std::cout << p_a; // prints the address/location that variable is stored in the memory

int b = 7; // declares and stores values of 7 in variable b

int* p_b = *b; // declares the int pointer variable p_b as the address of variable a by using `*`

std::cout << p_b; // prints the contents of the variable b, which in this case is the value

// if both of the operators are used together will cancel out.

int c = 9; // declares and stores values of 9 in variable c

int* p_c = &*c; // declares the int pointer variable p_c as the address of variable a by using `&`

std::cout << p_c; // prints the contents of the variable c, which in this case is the value

}

{% endhighlight %}

## Visual Representation

![Pointers Represented](http://i2.wp.com/mycodinglab.com/wp-content/uploads/2013/08/Screen-Shot-2013-08-02-at-5.30.53-PM.png?resize=406%2C206)

>Best way to think is that p* is the alias of the variable its pointing to.

## Arrays

A collection of elements of the same type. Given any type T and a constant N, a variable of type T[N], holds an array of `N` elements each of type `T`.

Each element is referenced by its index, number from 0 to N-1

> For example, an array of integers {1,2,3,4,5}, you call the first element the `Zeroth` and so (0,1,2,3) respectively

Here are some examples of array declarations : 

{%highlight c++%}

double f[5]; // creates a type array of 5 doubles: f[0], f[4] look above for explanation 

int m[10]; // creates a type array of 10 integers: f[0]...f[9]

f[4] = 2.5; // defines the variable f’s fourth element

m[2] = 4; // defines the variable m’s second element

cout << f[m[2]]; // as m[2] holds the value 4, so now identical to cout << f[4]

{% endhighlight %} 

After once declared you cannot increase the number of elements in an array. As consistent with C++ 's general philosophy, there is no built in run time check for array subscripting (research topic)

A two-dimensional array is implemented as an “`array of arrays”.

> For examples, int A[15][30]; declares A to be a array of 30 objects, each of which is an array of 15 integers. 

>An elements is indexed as A[i][j], where `i` is the range between 0-15, and `j` between the range 0, 29.

Declaring Array rules : 

Initializes its values by enclosing in curly braces `({.....})`

The size of the array does not need to be specified.

{%highlight c++%}

int[] = {10,11,12,13}; // declares and initializes a[4]

bool b = {false, true}; // declares and initializes b[2]

char c = {‘c’, ‘b’, ‘t’} // declares and initializes c[3]

{%endhighlight%}

As an array can be any type you can declare an array of pointers to integers.

> For example, int* r[17] declares an array r consisting of 17 pointers to objects of type `int`.

As before you can deference an element of the array by using `*` operator 

>For example,*r[16] is the value of the integer pointed to by the last element

## Pointer and Arrays


There is an inherit connection between pointers and arrays, brought over from the C language. The name of the array is equivalent to a pointer to the array's initial element and vise versa. Below is an example of how it looks : 


>  ////.. = means that small pieces of code missed to get to the point  eg. #include<iostream>

{%highlight c++%}

////....

char c[] = {'c', 'a', 't'}; // creates and array c with 3 elements 

char* p = c; // char pointer p directed to array c  *=> c[0]

char* q = &c[0]; // char pointer q directed to the address of c[0] *=>c[0] 

cout << c[2] <<p[2] <<q[2] <<endl; // prints out the 2nd element in array *=> ttt

{%endhighlight%}


## Strings


String literals, such as "Hello world" is represented by a fixed-length array of characters that ends with a null character, these character strings are called `C-Style Strings`. This however doesn't support string types like concatenation and comparison (lexicographical).


This is the reason that C++provides a string type as part of its STL `Standard Template Libary`. In order to use these string you need to include the header <string> and adding {%hightlight c++%}using std::string; {%endhighlight%}


> STL strings are able to be concatenated and they may be compared with eachother levciographically(or dictionary) order. 


{%hightlight c++%}

string s = "to be"; // declares and defines string

string t = "not " + s; // declares and defines string with concatination

string u = s + " or " + t; // declares and defines strin with concatinatino

if (s>t) // conditon to be meet, LEXIOGRAPHICALLY, easy way to think compares first leter( a = 0, b = 1,) so (c)arrot > (a)pple Lexiographically just 2>0 element wise 

cout << u ; // print the string variable u

{%endhighlight%}


> STL strings also have other properties, one of which are appenment of the string by using the += operator.

> STL string can also be indexed like an array and give number of characters in a string by `(variable_name).size`


{%highlight%}

///.....

string s = "John"; // declares the string variable and defines it with string =>John

int i = s.size(); // declares the int variable and defines it with the number of characters in s => 'John' => 5

char c = s[3]; // declares the char variable and defines with the 3rd index/element of s varaible => n

s += " Doe"

{%endhighlight%}


## C-Style Structures


A storing is useful for storing aggregation of elements.


* Unlike and array, the elements of a structure can be of different types. #

* Each member/field of a structure is referred to by a given name.


> For example,consider a structure for storing information about an airline passangers. The member/fields of the structure can be passanger name, food preferences, frequent fyler....etc 


{%highlight c++%}


enum MealType {NO_PREF, REGULAR, LOW_FAT, VEGETARIAN}; // Declares a enumeration type and fills its with meal types

struct Passanger {

    string  name; // Declares this field as a string variable and will store the passanger names

    MealType mealpref; // refrences the enum MealType variable as the field and stores the customer meal preferences from the selection

    bool    isFreqFyler; // declares the field as a boolean variable - so will show FALSE OR  TRUE

    string  freqFylerNo; // declares this field as a string variable and will store the passanger freqfylernumber if boolean true

};

Passanger pass = {"John Smith", VEGETARIAN, true, "293233"}; // initialize a variable pass of this type

};

{%endhighlight %}


The individual members of the structure are accessed using `member selection operator`, form of struct_name.member


{%highlight c++ %}


pass.name = "Richmond"; // Change name

pass.mealPref = REGULAR; // Change meal preference


{%endhighlight %}


## Pointers, Dynamic Memory, and the "new" Operator


Its useful in data structures to to create objects dynamically when the needs arises


A large block of memory called the `Free memory` also sometimes called the `Heap Memory`. 


The operator `new` dynamically allocates the correct amount of storage for a given object of any given from the free store and returns the pointer to this object.


DONT GET TOO CONFUSED BELOW IS AN EXAMPLE,C H I L L 


> For example, suppose that in the airline system we encounter a new passanger. We would like to dynamically create a new instance using the new operator.


> Let p be a pointre to a Passenger structure. This implies that *p refers to the actual structure; hence, we could access one of its members/fields, eg mealPref, using the expression (*p).mealPref.


C++ provides a shorter way to access members using the `"->"` operator

> pointer_name->member       `(is equivalent to)`     (*pointer_name).member


>For example we can allocate a new passenger object and inititalize its members as follows 


{%highlight c++%}


Passenger* p;

//////....

p = new Passenger; // p points to new Passenger

p ->name = "Keaton"; // sets the structure members 

p->mealPref = REGULAR;

p->isFreqFyler = false;

p->freqFylerNo = "NONE";

{%endhighlight%}


36/738 (It would....)
