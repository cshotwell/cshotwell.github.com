---
layout: post
title: 	"7 Languages In 7 Weeks Day 1"
date: 	2013-07-01 3:07:00
categories: update 7lang ruby
---


Today I am beginning work on the book [Seven Languages in Seven Weeks][7-lang] by Bruce Tate. For those of you not familiar, this book is broken up into 7 
different languages, each further broken into 3 day segments. It is my plan to write a bit about each day those things that I find interesting about the exercises presented, as both an attempt to expand on those things I find curious, and to share with others my take. It also seems like a good opportunity to improve my blog-post writing, which is entirely new to me. I'd say leave a comment, but at this time there is nobody reading this, nor a way to leave comments.

The first language covered is [Ruby][rubylang], which of all the languages presented in this book, I am most comfortable with. Dynamically typed, interpreted, and object oriented are all traits that I am very familiar with, and it has made these exercises rather painless.

The first day's exercises covered the basics of the language, including syntax, duck typing, and some basic looping and conditionals. Below you can find the answers from day 1.

{% highlight ruby %}
# Print the string "Hello, world."
puts "Hello, world."

#For the string "Hello, Ruby," find the index of the word "Ruby"
"Hello, Ruby".index("Ruby")

#Print your name ten times.
x = 0 
while x < 10
  puts "carl"
  x += 1
end

# print the string "This is sentence number 1" where the number 1 changes from 1 to 10
(1..10).each do |i| 
  puts "This is sentence number #{i}"
end

# run a ruby program from a file
# Just did the previous problem in a file called day1.rb, ran it with: $ ruby day1.rb

# Bonus problem: If you’re feeling the need for a little more, write a program that 
# picks a random number. Let a player guess the number, telling the player whether the 
# guess is too low or too high.
x = rand(10)
guess = 0 
while guess != x
  puts "Guess a number 1-10"
  guess = gets.chomp.to_i
  puts "Too high" if guess > x 
  puts "Too low" if guess < x 
end
puts "Correct!"
{% endhighlight %}

[7-lang]: http://pragprog.com/book/btlang/seven-languages-in-seven-weeks
[rubylang]: http://www.ruby-lang.org/en/
