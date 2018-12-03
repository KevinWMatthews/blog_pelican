Title: Python List Comprehensions... In Ruby?
Date: 12/2/2018 19:26
Modified: 12/2/2018 19:26
Category: Ruby
Tags: ruby, arrays, python, lists
Slug: python-list-comprehensions-in-ruby
Author: Kevin W Matthews
Summary: Compare creating arrays from data in Python and Ruby

...what's the Ruby way?


## Python List Comprehensions

The Python language has one-line, built-in syntax for creating arrays
(and also dictionaries and sets).

```python
[x**2 for x in range(0, 10) if x % 2 != 0]
[1, 9, 25, 49, 81]
```

It's dense, but here is what's going on:

```
[expression for item in list if conditional]
```

In colloquial terms,

```
For each item in the list,
    if the conditional is met,
        execute the expression
```

In this specific case:

```
For each number in the range,
    if the number is even,
        square the number
```

Complex but simple, depending on your point of view. Powerful either way.


## Ruby Methods

How does Ruby do the same? There doesn't seem to be a single operation
to do this, though this
[has been considered](https://bugs.ruby-lang.org/issues/5663)
as a language feature.

Instead, Ruby forces (or allows) the user to specify the conditional and
the expression independently:

```ruby
(0..10).select { |i| i.odd? }.collect { |i| i**2 }
=> [1, 9, 25, 49, 81]
```

This is a fundamentally different way of thinking about the operation:
```
For each item in the enumerable,
    pass the block to the method
For each item in the enumerable,
    pass the block to the method
```

In this specific case
```
For each item in the range,
    if the conditional is met,
        put the item in an array
For each item in the array,
    execute the expression
```

The condition and expression are clearly two separate operations;
it requires two passes through the array! Cast aside performance
considerations for the moment, as we're concerned about idiomatic practice.

Ruby is primarily concerned with message passing. Rather than depending on a
special language feature, it simply calls a method on an object:

```ruby
Enumerable.select {}
List.collect {}
```

and passes each method a block.


## Real-World Example

The above example is straightforward. What could this look like in the wild?

Finish this later...
