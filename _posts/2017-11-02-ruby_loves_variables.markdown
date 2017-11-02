---
layout: post
title:      "Ruby loves Variables"
date:       2017-11-02 20:34:12 +0000
permalink:  ruby_loves_variables
---


In math and Ruby, a variable can point to almost any kind or type of value like:
1. numbers
2. strings
3. arrays
4. hashes

Variables allow us to store information.  We tell our computers to set aside some space to hold that info so we can retrieve it later.  Variables allow us to have a location where our stored info arises so we can find it easily when we need it. 

variables vs Constants 
variables begin with a lower case letter and Constants begin with a Capital Letter.

There are different ways to write variables:
1. Snake Case= this_is_an_example_of_snake_case (words seperated by underscores)
2. Camel Case= thisIsAnExampleOfCamelCase (uppercase letters indicate wordbreaks)

Interpolation
syntax of #{words} simply injects the value of the variable into the string
variable = "words"
puts "Hey I want to say #{words}."
"Hey I want to say" + variable + "."

Invalid Variable Names
1. no spaces ( ya ya ya)
2. no start with a number (1st_place)
3. no ruby reserved words (end)
4. no punctuation (charla's_age)

Variables have value
A variables name is like the label on a container.  Its value is stored inside that container.  The name points to that value.  But the value of a variable can change even though the name stays the same.

Variables have a type
Ruby is a Dynamically Typed Language (the value of a variable can change its type and doesn't need to be explicitly or permanently defined).  You can also change the value of sum from a number 21 to a string "what ever I want".

Ruby is a strongly typed language.  (a variable will never be automatically coerced to another type without you explicitly changing they type) So if A=2 and A=B then B=3 out put A=2 and B=3. 

You can add two number and you can add two strings but you CANNOT add a number to a string or you will get an error. 

Creating Variables with Assignment Operator
The assignment operator is = sign
variable = "words"

Variables can be Reassigned
x=1 
put 2 + x = 3
x=3
put 2 + x = 5

Pass by Values are cool
word = "word"
word will output "word"
word.upcase will output "WORD"
word will again output "word"








