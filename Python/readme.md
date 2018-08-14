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
# Any returns True is any of the elements in an iterable are True
any(l)
True

```