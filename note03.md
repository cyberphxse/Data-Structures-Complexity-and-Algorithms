# Data Structures and Algorithms note 3
## What are Tuples?
Strings & Lists are fundamental data types that are alike in some senses, with a few contrasts
-strings can only hold alphanumeric characters & special symbols to illustrate text
-Lists can hold every data type as its values
-strings are immutable, however lists are mutable 
These key differences may be a pain when you need a certain data structure 
-needs to be mutable 
-must be able to hold different datatypes of values 
-needs to be iterable 
-needs be nestable (list in a list)
every one of these are solved by using a data structure known as **tuple**
## How to use Tuples in Python 3
-Tuples are indicated by using parenthesis "()"
-() represents an empty tuple 
-(50,) represents a singleton tuple; the comma is mandatory 
-tuples can be sliced; thus, indexable via square brackets

> *A singleton is an iterable data structure with only single item.*
### Tuple Example 1
```
tup = ('C', ' Java', 'Python')
empty_tup = ()
single_tup = ('Park',)

print(tup)
print(empty_tup)
print(single_tup)
```
('C', ' Java', 'Python')
()
('Park',)
## Tuple Operators
```
# Concatenation: Joining two tuples
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)


# Repetition: Repeating a list multiple times
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)

# Membership: Check if a value exists in a tuple
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)
```
a+b: (1, 2, 3, 4, 5, 6)
c * 3 ('Hi!', 'Hi!', 'Hi!')
d: (1, 2, 3, 4, 5, 6, 'Hi!')
'Hi!' in d: True
7 in d: False
## Tuples are Iterable, Indexable, and Sliceable
```
# Iteration
example = ('C', 'Java', 'Python', 'C#', 'JavaScript')

print('Tuple example items:')
for language in example:
    print(language)
print('--')

# Indexing
print('Index 1:', example[1])
print('Last Value:', example[-1])

# Slicing
print('Backwards:', example[::-1])
print('Every other:', example[::2])
print('From 1 to end:', example[1:])
print('From 1 to 3:', example[1:3])
```
Tuple example items:
C
Java
Python
C#
JavaScript
--
Index 1: Java
Last Value: JavaScript
Backwards: ('JavaScript', 'C#', 'Python', 'Java', 'C')
Every other: ('C', 'Python', 'JavaScript')
From 1 to end: ('Java', 'Python', 'C#', 'JavaScript')
From 1 to 3: ('Java', 'Python')
## Built-in Functions with Tuple
```
example = ('C', 'Java', 'Python', 'C#', 'JavaScript')

print('Length:', len(example))
print('Minimum value:', min(example))
print('Maximum value:', max(example))
print('--')

word = 'Hello'
array = [1,2,3,4]
array_array = [[1],[2,3],[4]]

print('String to Tuple:', tuple(word))
print('List to Tuple:', tuple(array))
print('2D array to Tuple:', tuple(array_array))
print('--')

array_array[0][0] = 'p'
print(array_array)

# Note: don't have mutable data type as items in a tuple ...
```
Length: 5
Minimum value: C
Maximum value: Python
--
String to Tuple: ('H', 'e', 'l', 'l', 'o')
List to Tuple: (1, 2, 3, 4)
2D array to Tuple: ([1], [2, 3], [4])
--
[['p'], [2, 3], [4]]
## Tuple Comprehension
```
# Tuple of Even values from 1 to 100
even_tup = tuple(i for i in range(1,101) if i % 2 == 0)

print(even_tup)
```
(2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98, 100)

The parentheses were interpretted as a different functionality in python; thus, we need to do comprehesion similar to this.

The common format is 100% identical as list comprehension 
## Tuple & Python: Packing and Unpacking
```
# Examine the following code

# Packing
var_1 = 2
var_2 = 3
var_3 = 5

prime = var_1, var_2, var_3

print('Packed prime values:', prime)

# Unpacking and Repacking
fib = (0, 1, 1, 2, 3, 5, 8)

fib_0, fib_1, fib_n = fib[0], fib[1], fib[2:]
print('fib_0:', fib_0)
print('fib_1:', fib_1)
print('fib_n:', fib_n)
```
Packed prime values: (2, 3, 5)
fib_0: 0
fib_1: 1
fib_n: (1, 2, 3, 5, 8)

**Description:**
-packing grabs several variable's values as well as assigning it to 1 variable
-unpacking aids in assigning specific values deriving from a tuple to unlike variables 
-This turns into an essential skill when merged with variable arguments used for function defintion as well as calls

