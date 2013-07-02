---
layout: post
comments: true
title: 	"7 Languages In 7 Weeks Ruby Day 2"
date: 	2013-07-02 11:18:00
categories: update 7lang ruby
---


Day 2 of the Ruby section of this book gets a bit more in depth into what makes Ruby Ruby. Functions, Hashes, Blocks, Yield, Classes, and other built in datatypes are all briefly covered.

The ability to pass blocks of code around are in my opionion the most interesting part of this chapter. Blocks are essentailly closures that are being passed on to methods, proviiding greater functionality and flexibility to the programmer. When used correctly, blocks can be a powerful tool, leading to clear and concice code.

I would like to write more on this topic, but in the meantime, please check out the excellent tutorial, [Understanding Ruby Blocks, Procs, and Lambdas][understand], by Robert Sosinski.

Here are the answers to the exercises from the day:

{% highlight ruby %}
# Print the contents of an array of sixteen numbers, four numbers at a time, 
# using just each.
(1..16).each do |i| 
   print i
   print "\n" if i % 4 == 0
end

#Now do the same with each_slice from Enumerable
require 'enumerator'
(1..16).each_slice(4) {|i| p i}

# The Tree class was interesting, but it did not allow you to specify a new
# tree with a clean user interface. Let the initializer accept a nested·
# structure with hashes and arrays. You should be able to specify a tree like·
# this:·
x = {"grandpa" => { "dad" => {"child 1" => {}, "child 2" => {} },
	"uncle" => {"child 3" => {}, "child 4" => {}}}}

# changed the given initializer from:
def initialize(name, children=[])
  @children = children
  @node_name = name
end

# to:
def initialize(name, children=[])
  if name.respond_to? 'key?'
    @node_name = name.keys.first
    @children.push( name[@node_name].each {|node, child| Tree.new(node => child, [])}
  else
    @children = children
    @node_name = name
  end
end

# Write a simple grep that will print the lines of a file having any occurances
# of a phrase anywhere in that line.  You will need to do a simple regular·
# expression match and read lines from a file. (This is surprisingly simple
# in Ruby.) If you want, include the line numbers.

def print_file_line_if_present (file, word)
  line_num = 1
  File.open(file).each do |line|
    puts "#{line_num} #{line}" if line.match(word)
    line_num += 1
end
{% endhighlight %}

[understand]: http://www.robertsosinski.com/2008/12/21/understanding-ruby-blocks-procs-and-lambdas/
