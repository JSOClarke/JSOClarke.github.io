---
layout: post
title:  "Graph Theory : C++"
date:   2019-11-19 16:52:19
categories: [Self-Study]
comments: true
---
This is the section that im going to dedicate to learning `Graph Theory` for my self study.

The website im using to learn is `freecodecamps` youtube video `Algorithm Course - GraphTheory by a Google Engineer` 



<!--more-->

Below is a a basic C++ program that finds the `Answer from a given Base and Exponent `.


> I have decided to alongside C++, learn Java, with William Fisets assests and the Book "Data Structures and Algorithms in Java". 

The github repo : https://github.com/williamfiset/Algorithms


{% highlight c++ %}

#include<iostream>
using namespace std;
int power(int baseNum, int powNum){

	int result =  1; // declares and initializes the variable 
	for(int i =0; i<powNum; i++) // creates the for loops that will loop itself while i is greater than powNum
	{
		result = result * baseNum; /* as result is equal to 1 this is run (result = 1 * baseNum) which by algebra
		 will make result = baseNum (the result variable keeps the value in sum but will change the value after 
		 the operation is completed.), when this is set the loop will run again. this time with result being 
		 result = baseNum*baseNum or baseNum^2 */
	}

	return result; // saves the value of the result or (answer) 
}
int main(){
	int base; // declaring variable 
	int exponent;

	cout << "Please enter the base number : "; 
	cin >> base; // saves user-input as base variable
	cin.ignore(); // discards the return key pressed
	cout << "Please enter the exponent : ";
	cin >> exponent; 
	cin.ignore(); 
	cout << base << " to the power of " << exponent << " is equal to "<< power(base,exponent) << endl; // passing the function /power with the two variable base and exponent.
	return 0;
}

{% endhighlight %}

