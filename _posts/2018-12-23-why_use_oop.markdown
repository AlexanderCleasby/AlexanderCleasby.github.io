---
layout: post
title:      "Why use OOP"
date:       2018-12-23 22:34:09 +0000
permalink:  why_use_oop
---


Object oriented programing is more or less necessary when writing any even somewhat complex program.  Thoughtfully carried out allows for:
* Reuse of common functionality -  Code that performs common functionality can be reused endlessly.  This can be accomplished in a way by functional programming, but the class structure makes it easier to keep track of and avoids creating a ton of global variables.
* Abstraction - Creates a better experience for developers by abstracting away previously solved problems, and makes debugging easier by separating concerns.  A module can be imported into another and the dev can use the methods of the child module without understanding it’s inner workings.  Standing on the shoulders of giants.
* Separation of Concerns - By separating your code into classes, you can create a pattern that is way easier to maintain, debug and add to by making your code more modular.

The common pattern that you see in Ruby gems and the one exemplified to Flatiron School Students is to declare all your Classes in their own file in /lib and ‘require’ them into the parent modules or parent classes where they are used.  For instance, if I have a class Student, to be used to instantiate an object containing data about a student. and a class Cohort, to be used to instantiate an object containing data about a Cohort.  I would declare each in its own file and if I wanted to be able to call either from one module I would require both from one parent module.  Then you will be able to instantiate new Students from your Cohort Class and new Cohorts from your Student class.


