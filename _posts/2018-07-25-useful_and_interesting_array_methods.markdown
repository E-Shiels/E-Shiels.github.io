---
layout: post
title:      "Useful (and Interesting) Array Methods"
date:       2018-07-25 09:23:21 -0400
permalink:  useful_and_interesting_array_methods
---


I recently decided to read through the documentation for the Ruby Array class. The Ruby documentation lists 98 instance methods, so here, I'll discuss some of the most interesting and unique ones. You can check out the official documentation [here.](https://docs.ruby-lang.org/en/2.0.0/Array.html)

### clear
array.clear removes all elements from th array.
```
a = [1,2,3,4,5]
a.clear     => [ ]
```
### compact and compact!
array.compact returns a new array witout any *nil* elements. array.compact! removes *nil* elemts from the array in place.
```
a = [1,2,nil,3,nil,4,5,6]
a.compact!     => [1,2,3,4,5,6]
```
### count
array.count returns the number of elements in the array.
```
a = [1,2,3,4,5]
a.count     #=> 5
```
### empty?
array.empty? returns true if the array contains no elements.
```
a = []
a.empty      => true
```
### keep_if
array.keep_if deletes every element og the array for which the block is false.
```
a = [1,2,3,4,5,6,7,8,9,10]
a.keep_if {|n| n < 8}     => [1,2,3,4,5,6,7]
```
### shuffle and shuffle!
array.shuffle returns a new array with the elements shuffled. shuffle! shuffles the elements in place.
```
a = [1,2,3,4,5,6,7,8,9,10]
a.shuffle!    => [4, 6, 9, 10, 1, 5, 3, 7, 8, 2]
```
### take(n)
array.take(n) returns *n* elements of the array as a new array.
```
a = [1,2,3,4,5,6,7,8,9,10]
b = a.take(5)     => [1,2,3,4,5]
```
### uniq and uniq! 
array.uniq returns a new array with duplicate values removed. array.uniq! removes duplicate items from the array in place (and returns nil if no changes duplicates were found).
```
a = ["one", "one", "two", "three", three", "three", "four"]
new_array = a.uniq      => ["one", "two", "three", "four"]

a = ["one", "one", "two", "three", three", "three", "four"]
a.uniq!      => ["one", "two", "three", "four"]
```


