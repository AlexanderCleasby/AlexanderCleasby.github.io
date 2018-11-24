---
layout: post
title:      "Hashes in Ruby"
date:       2018-11-24 22:12:20 +0000
permalink:  hashes_in_ruby
---


Hashes are simple built in classes in Ruby that work in a way that will be familiar to you if you have used any other programming language (think Dictionaries in Python or Objects in Javascript).  They accept ****keys*** in the form of ***Stings*** or ***Symbols*** and ***Values*** in the form of any Ruby object (note that in Ruby functions are NOT objects and can't be set as the values to a hashs key, this threw me off coming from doing alot of coding using JS).

The hash is declared as an object using curly brackets, the declaration of a key then an arrow => then the value yo want to set that key to.  The hash is an object and can be stored all the places an object can be stored.  Including as the value to a key in another hash.

```
alex = {
    :age => 26,
    :cool => true,
    :eye_color => :hazel,
    :favorite_things =>
        {
            :color => :red,
            :number => 12 
        }
}

alex[:eye_color] #returns hazel
alex[:favorite_things][:color] #returns red
```


In the example above we declared a variable alex and stored a hash inside it.  Inside one of the keys ```:favorite_things```  we stored a hash with 2 of its own key value pairs.  Storing data like this is a usefull and necessary to organize data in your program.

