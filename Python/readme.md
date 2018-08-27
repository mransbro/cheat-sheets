# Python

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
# Functions can have a docstring
>>> print.__doc__
```

```python
# Help function
>>> help(print)
```

```python
# The dir() Method tries to return a list of valid attributes of the object
one = 1
>>> dir(1)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', '__format__', '__ge__', '__getattribute__', '__getnewargs__', '__gt__', '__hash__', '__index__', '__init__', '__init_subclass__', '__int__', '__invert__', '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__', '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__', '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__', '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__', '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__', '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__', '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__', 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag', 'numerator', 'real', 'to_bytes']
```

```python
# Need to know what type an object is
>>> data = "Fat cat on a mat"
>>> type(data)
<class 'str'>
```

## Data Structures

```python
# List are enclosed in square brackets are immuptable and contain different data types
>>> random_data = [1,2,'friday',4.6,True]

# List comprehension syntax is [expression for item in list if conditional]


```

```python
# Tuples are created with round brackets are immuptable and much faster to use
>>> months = ('JAN','FEB','MAR','APR','MAY','JUN', 'JUL','AUG','SEP','OCT','NOV','DEC')
```

```python
# Dictonary or dict use curly brackets. 
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
>>> a = {1,2,3,4,5}
>>> b = {4,5,6,7}

>>> a | b # Union

>>> a & b # 

>>> a ^ b # Unique
  
>>> a - b # difference
```

## Functions

```python
# Map syntax is map(function,iterable object)
>>> nums = [89,6,78,100,32,16]
>>> doubles = map(lambda x: x * 2, nums)
# This creates a map object. Printing the object wont do much good, we can either convert to a list or iterate over it.
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
# Returns True is any of the elements in an iterable are True
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