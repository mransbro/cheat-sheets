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

# List comprehension syntax is [expression for item in list if conditional]


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
# Dictonary Comprehension
# The syntax looks like {key:value for x in list}
word = 'comprehension'
letter_count = {letter:word.count(x) for letter in word}
{'c': 1, 'o': 2, 'm': 1, 'p': 1, 'r': 1, 'e': 2, 'h': 1, 'n': 2, 's': 1, 'i': 1}
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

