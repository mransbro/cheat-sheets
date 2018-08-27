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
info = 1,2,3
inFo = 'Im a new variable as i have a capital F'

long_variables_like_me = 'Should be in camel_case'
```

```python



```
## Help

```python
# Functions can have a docstring
print.__doc__
```

```python
# Help function
help(print)
```

```python
dir()
```

```python
# Need to know what type an object is
type(creash_times)


```

## Data Structures

```python
# List are enclosed in square brackets are immuptable and contain different data types
random_data = [1,2,'friday',4.6,True]
```

```python
# Tuples are created with round brackets are immuptable and much faster to use
months = ('JAN','FEB','MAR','APR','MAY','JUN', 'JUL','AUG','SEP','OCT','NOV','DEC')
```

```python
# Dictonary or dict use curly brackets. 
members = {33333:'John Smith', 22222:'Monica Small'}
```

```python
# Sets are unordered collections of unique data
a = {1,2,3,4,5}
b = {4,5,6,7}

a | b # Union

a & b # 

a ^ b # Unique
  
a - b # difference
```

## Functions

# Lambda

```python
# Map syntax is map(function,iterable object)
nums = [89,6,78,100,32,16]
doubles = map(lambda x: x * 2, nums)
# This creates a map object. Printing the object wont do much good, we can either convert to a list or iterate over it.
print(list(doubles))
[178, 12, 156, 200, 64, 32]
# Map objects can only be itereated over once
for n in doubles:
    print(n)
178
12
156
200
64
32
```

```python
# Filter syntax is filter(function, iterable object)
# Function must return true or false
nums = [3,6,4,7,8,9,1,14]
odds = filter(lambda x: x % 2 == 0, nums)
```

```python
# All returns True or false if all elements in an iterable are True
l = [True,1,10]
all(l)
True
```

```python
# any()
# returns True is any of the elements in an iterable are True
any(l)
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
sorted(things)
['full', 'is', 'of', 'strings', 'this']
# We can reverse the iterable
nums = [7,8,9]
sorted(nums, reverse=True)
[9,8,7]
# We can also sort using functions
letters = ['aaaaaaaa','aa','aaaa','a']
sorted(letters, key=len)
['a', 'aa', 'aaaa', 'aaaaaaaa']
```

```python
# Min and Max

```

```python
# Reversed

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