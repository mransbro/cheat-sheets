# Python

* [Comments](#Comments)

* [Help](#Help)

* [Data Structures](#Data-Structures)

* [Built in Functions](#Built-in-Functions)

* [Errors](#Errors)

* [Iterators & Generators](#Iterators-and-Generators)

## Comments

```python
# Single line comment
```

```python
# No way to do
# multi line comments so
# just connect single line comments
```

```python
'''
Multi line
strings
are possible
'''
```

```python
# Variables in Python are case sensitive
>>> info = 1,2,3
>>> inFo = 'Im a new variable as i have a capital F'
>>> long_variables_like_me = 'Should be in camel_case'
```

## Help

```python
# help()
# You can find help on modules, functions, classes, methods, keywords etc.
>>> help(min)
Help on built-in function min in module builtins:

min(...)
    min(iterable, *[, default=obj, key=func]) -> value
    min(arg1, arg2, *args, *[, key=func]) -> value

    With a single iterable argument, return its smallest item. The
    default keyword-only argument specifies an object to return if
    the provided iterable is empty.
    With two or more arguments, return the smallest argument.

```

```python
# Passing no argument takes you into Python's help utlity.
>>> help()

Welcome to Python 3.7's help utility!

If this is your first time using Python, you should definitely check out
the tutorial on the Internet at https://docs.python.org/3.7/tutorial/.

Enter the name of any module, keyword, or topic to get help on writing
Python programs and using Python modules.  To quit this help utility and
return to the interpreter, just type "quit".

To get a list of available modules, keywords, symbols, or topics, type
"modules", "keywords", "symbols", or "topics".  Each module also comes
with a one-line summary of what it does; to list the modules whose name
or summary contain a given string such as "spam", type "modules spam".

help> print
Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.

```

```python
# Most objects have a docstring, which is a short description of its features.
>>> print.__doc__
'''print(value, ..., sep=' ', end='\\n', file=sys.stdout, flush=False)\n\nPrints the values to a stream,
or to sys.stdout by default.\nOptional keyword arguments:\nfile:  a file-like object (stream);
defaults to the current sys.stdout.\nsep:   string inserted between values, default a space.\nend:
string appended after the last value, default a newline.\nflush: whether to forcibly flush the stream.'''
```

```python
# dir()
# The dir() Method returns a list of valid attributes of the object.
one = 1
>>> dir(1)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
```

```python
# type()
# The type method returns an object's type.
>>> data = "Fat cat on a mat"
>>> type(data)
<class 'str'>
```

## Data Structures

```python
# Lists are enclosed in square brackets, are immuptable and contain different data types
>>> random_data = [1,2,'friday',4.6,True]
# Empty lists are allowed
>>> empty = []
# Items in the list can be accessed by the index operator
>>> random_data[3]
4.6
# List comprehension is used to transform any list or iterable into another list.
# The syntax can be confusing at first [expression for item in list if conditional]
days = ['mon','tues','wednes','thurs','fri']
new_days = [x + 'day' for x in days]
>>> new_days
['monday', 'tuesday', 'wednesday', 'thursday', 'friday']
# Conditionals are placed at the back
>>> o = [print(f"{x} is even") for x in range(1,11) if x % 2 == 0]
2 is even
4 is even
6 is even
8 is even
10 is even

# List comprehension can also be used on nested lists
numbers = [[1,2,3],[4,5,6],[7,8,9]]
new_nums = [num for numlist in numbers for num in numlist]
# Breaking it down over several lines can often improve readability
[
    num
    for numlist in numbers
    for num in numlist
]
```

```python
# Tuples are created with round brackets are immuptable and much faster to use
>>> months = ('JAN','FEB','MAR','APR','MAY','JUN', 'JUL','AUG','SEP','OCT','NOV','DEC')
```

```python
# Dictonary or dict use curly brackets
>>> members = {33333:'John Smith', 22222:'Monica Small'}
```

```python
# Dictonary Comprehension
# The syntax looks like {key:value for x in list}
>>> word = 'comprehension'
>>> letter_count = {letter:word.count(x) for letter in word}
>>> {'c': 1, 'o': 2, 'm': 1, 'p': 1, 'r': 1, 'e': 2, 'h': 1, 'n': 2, 's': 1, 'i': 1}
```

```python
# Sets are unordered collections of unique data
>>> s = {1,2,2,2,3,3,4}
>>> type(s)
<class 'set'>
>>> s
{1, 2, 3, 4}
# Set operations
>>> a = {1,2,3,4,5,6}
>>> b = {10,9,8,7,6,5}
>>> a | b # Union
{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
>>> a & b # Intersection
{5, 6}
>>> a ^ b # Unique
{1, 2, 3, 4, 7, 8, 9, 10}
>>> a - b # difference
{1, 2, 3, 4}
```

## Built in Functions

```python
# lambda
# Lambdas are anonymous functions and not to be confused with Amazon's serverless function platform.
# lambda arguments: expression
>>> l = lambda x,y : x * y
>>> l(5,5)
25
# Lambda Functions are generally used as an argument to a higher-order function, 
# a function that takes in other functions as arguments.
# There used along with built-in functions like filter(), map() etc.
```

```python
# map()
# Map executes a specified function for each given item
# map(function, iterable object)
>>> nums = [89,6,78,100,32,16]
>>> doubles = map(lambda x: x * 2, nums)
# This creates a map object. Printing the object wont do much good, we can either convert to a list or loop through it.
>>> print(list(doubles))
[178, 12, 156, 200, 64, 32]
# Map objects can only be itereated over once
>>> for n in doubles:
>>>    print(n)
178
12
156
200
64
32
```

```python
# filter()
# Filter syntax is filter(function, iterable object)
# Function must return true or false
>>> nums = [3,6,4,7,8,9,1,14]
>>> odds = filter(lambda x: x % 2 == 0, nums)
```

```python
# all()
# All returns True or false if all elements in an iterable are True
>>> l = [True,1,10]
>>> all(l)
True
```

```python
# any()
# Returns True if any of the elements in an iterable are True
>>> any(l)
True
# a more complex example
things = ['is','1','False',[1,2,3],'99']
any(type(x) == str for x in things)
True
```

```python
# sorted()
# Sorts the elements of an iterable
# sorted(iterable[, key][, reverse])
>>> sorted(things)
['full', 'is', 'of', 'strings', 'this']
# We can reverse the iterable
>>>nums = [7,8,9]
>>> sorted(nums, reverse=True)
[9,8,7]
# We can also sort using functions
>>> letters = ['aaaaaaaa','aa','aaaa','a']
>>> sorted(letters, key=len)
['a', 'aa', 'aaaa', 'aaaaaaaa']
```

```python
# min()
# The min method returns the smallest element in an iterable
>>> nums = [45,68,2,11,85]
>>> min(nums)
2
# max()
# The max method returns the largest element in an iterable
```

```python
# The reversed method return the reversed iterator of a sequence
# reversed(seq)
letters = ['a','b','c','d','e','f','g','h']
>>> print(reversed(letters))
<list_reverseiterator object at 0x00000194ACFA0A20>

>>> print(list(reversed(letters)))
['h', 'g', 'f', 'e', 'd', 'c', 'b', 'a']
```

## Errors

```python
# To throw our own error we use the raise statement
# raise <error> (error message)
def print_string(s):
    if type(s) != 'str':
        raise ValueError ('I told you i needed a string input')
    print(s)
# The error has to be a valid Python error type but the error message can be whatever we wish
```

```python
# try except else finally
# Except runs when try fails. It can accept all errors or just a type we specify.
# Adding an int and str will produce a TypeError. If we specify a ValueError except wont run.
>>> try:
    1 + '1'
except ValueError:
    print('Stop messing around please')
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: unsupported operand type(s) for +: 'int' and 'str'

>>> try:
>>>    1 + '1'
>>> except:
>>>    print('Stop messing around please')
>>> else:
>>>    print('I run when the except block doesnt')
Stop messing around please
# Else will run when except doesnt
>>> try:
>>>    1 + 1
>>> except:
>>>    print('Stop messing around please')
>>> else:
>>>    print('I run when the except block doesnt')
2
I run when the except block doesnt
```

## Iterators and Generators

```python
# Iterators
# An iterable is something you can loop over
# An iterator is the object that does the looping
>>> word = 'sunshine'
>>> word_iter = iter(word)
>>> word_iter
<str_iterator object at 0x103317ba8>
# Iterators have a next function which provides the next object
>>> next(word_iter)
's'
>>> next(word_iter)
'u'
>>> next(word_iter)
'n'
# To make a custom Class or object iterable we need to make use of two dunder methods, __iter__ and __next__.
class TimesTen:
    def __init__(self, max = 0):
        self.max = max
        self.i = 0
    # This method initalizes the iterator object
    def __iter__(self):
        return self
    # This method returns the next value for the iterable. When it reaches the end it should raise a StopIteration error
    def __next__(self):
        if self.i <= self.max:
            result = self.i * 10
            self.i += 1
            return result
        else:
            raise StopIteration
>>> for i in TimesTen(10):
...   print(i)
...
0
10
20
30
40
50
60
70
80
90
100
```

```python
# Generators are functions that can be paused, resumed and return an object which can be iterated over.
# generators introduce the yield statement. Its smiliar to return in that it returns a value but differs in that it saves the state of the function.
# This means the function execution continues where it left off.

```