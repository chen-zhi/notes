---
title: Python 101
date: 2018-01-01 21:40:05
tags: Python
---

# Indentations
Python uses indentation to **indicate a block of code** instead of brackets.

# Variables and Types

Python is a **strong, dynamically type**d language, while JavaScript is a weekly, dynamically typed language.

A language is **statically typed** if the type of a variable is known at compile time. For some languages this means that you as the programmer must specify what type each variable is (e.g.: Java, C, C++)

Unlike other programming languages, Python has **no command for declaring a variable**. The declaration happens automatically when you assign a value to a variable. 

## Numbers
There are three numeric types in Python:
1. int
2. long (long integer)
3. float
4. complex
```
x = 1    # int
y = 2.8  # float
z = 1j   # complex
```

## Strings
Strings are defined either with a single quote or a double quotes.
Use [] to slice string.
```
# This prints out prints out "llo".
b = "Hello, World!"
print(b[2:5])
```
### String Formatting
Python uses C-style string formatting to create new, formatted strings. 
```
# This prints out "Hello, John!"
name = "John"
print("Hello, %s!" % name)
```
* `%s` - String (or any object with a string representation, like numbers)

* `%d` - Integers

* `%f` - Floating point numbers

* `%.<number of digits>f` - Floating point numbers with a fixed amount of digits to the right of the dot.

* `%x/%X` - Integers in hex representation (lowercase/uppercase)
## Python Collections
1. List is a collection which is ordered and changeable. Allows duplicate members.
2. Tuple is a collection which is ordered and unchangeable. Allows duplicate members.
3. Set is a collection which is unordered and unindexed. No duplicate members.
4. Dictionary is a collection which is unordered, changeable and indexed. No duplicate members.

### Lists
Lists are enclosed in brackets [ ] and their elements and size **can be changed**.

### Tuples
Tuples are enclosed in parentheses ( ) and **cannot be updated**. Tuples can be thought of as read-only lists. 

### Sets
Sets are enclosed in curly brackets ( ). Sets are unordered, so the items will appear in a random order.

### Dictionaries
Dictionaries are enclosed by curly braces { } and values can be assigned and accessed using square braces [].
Python's dictionaries are kind of hash table type. They consist of key-value pairs. They are unodered.

# Function
In Python a function is defined using the **def** keyword:
```
def my_function():
  print("Hello from a function")
```

# Class
Example:
```
class Employee:
   'Common base class for all employees'
   empCount = 0

   def __init__(self, name, salary):
      self.name = name
      self.salary = salary
      Employee.empCount += 1
   
   def displayCount(self):
     print "Total Employee %d" % Employee.empCount

   def displayEmployee(self):
      print "Name : ", self.name,  ", Salary: ", self.salary
```
## `__init__()`
The first method `__init__()` is a special method, which is called class **constructor**.
## Built-In Class Attributes
Every Python class keeps following built-in attributes and they can be accessed using dot operator like any other attribute −

* `__dict__` − Dictionary containing the class's namespace.

* `__doc__` − Class documentation string or none, if undefined.

* `__name__` − Class name.

* `__module__` − Module name in which the class is defined. This attribute is "__main__" in interactive mode.

* `__bases__` − A possibly empty tuple containing the base classes, in the order of their occurrence in the base class list.

# Regular Expressions
## The match function
```
import re

re.match(pattern, string, flags=0)
```

# Lambda
A lambda function is a small **anonymous function**.
A lambda function can take any number of arguments, but can only have one expression.
Syntax:
```
lambda arguments : expression
```
Example:
```
x = lambda a : a + 10
print(x(5))
```
# Closure
Excerise:
```
# your code goes here

multiplywith5 = multiplier_of(5)
print (multiplywith5(9))
```
Find solution [here](https://www.learnpython.org/en/Closures)