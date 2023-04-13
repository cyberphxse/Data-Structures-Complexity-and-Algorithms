# Data structures and algorithms note 4
## Sets in Python 3 
In python 3, set represents an unordered collection that cannot hold duplicate values

set is mathematical approach to illustrate collection of unlike special objects

By proceeding the procedures & atrributes of the mathematical set, we are able to use such data structure within our python code

### Using sets in Python 3 
**How to Define a set**
```
# Set definition examples:
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}

print('example_set1:', example_set1)
print('example_set2:', example_set2) # Notice there is only 1 'l'; Also notice the order of the values outputted
print('--')

singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.

print('Singleton:', singleton_set)
print('Empty Set:', empty_set)
```

example_set1: {1, 2, 3}
example_set2: {'o', 'e', 'h', 'l'}
--
Singleton: {7}
Empty Set: set()

**Basic Built-in Functions w/ Sets**
```
# Basic Built-in Functions w/ Sets

example_set = set('hello') # set() turns an iterable into a set
print('example_set:', example_set)
print('--')

print('Number of Values:', len(example_set)) # length function
print('Minimum Value:', min(example_set)) # min function
print('Maximum Value:', max(example_set)) # max function
print('--')

# tuple to set
tup = (2,3,5,7)
print('tup to set:', set(tup))

# list to set
array = ['orange']*2 +  ['watermelon', 'apple'] + ['kiwi'] * 10
print('Original Array:', array)
print('list to set:', set(array))
```
example_set: {'o', 'e', 'h', 'l'}
--
Number of Values: 4
Minimum Value: e
Maximum Value: o
--
tup to set: {2, 3, 5, 7}
Original Array: ['orange', 'orange', 'watermelon', 'apple', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi', 'kiwi']
list to set: {'watermelon', 'orange', 'apple', 'kiwi'}

**Basic Membership Operators**
Membership is 1 of the important operations with set due to:
-Sets contain no duplicate values
-A set's membership operation is the quickest operations when contrasted to strings, lists, or tuples (Will be expanded with the notion of **complexity**)
-using membership operators, we are able to see if a specific value exists within out data or not 
```
# Membership Example
example_set = set('hello')

print("Membership of: \'h\'", 'h' in example_set)
print("Non-Membership of: \'z\'", 'z' not in example_set)
```
Membership of: 'h' True
Non-Membership of: 'z' True
**Accessing Values in a Set**
-As a result of a set's unorderedness, there is no indexing or slicing in the set data type
-sets are iterable though

```
# Iteration of a Set
example_set = {2,3,5,7,11,13}

for v in example_set:
    print('Values of example_set:', v)
```
Values of example_set: 2
Values of example_set: 3
Values of example_set: 5
Values of example_set: 7
Values of example_set: 11
Values of example_set: 13
**Python 3 Sets are mutable: Adding and Removing Values**
-Sets are mutable; thus, we are able to add & get of rid of values 
-similar to list, there are set methods that can also alter the original sets
```
# Adding and Removing Values
languages = set() # empty set initialization

programming_languages = ['C', 'C#', 'Java', 'Python', 'HTML', 'CSS', 'JavaScript', 'Haskell']

for item in programming_languages:
    languages.add(item) # .add() method adds an item to a set

print('Languages set:', languages)
print('--')

languages.discard('HTML') # looks for the target value, if found, it will remove from the set
print('HTML deleted:', languages)

languages.remove('CSS') # remove can be used to delete a value;
# only difference is it will raise an error if the target is not found
print('CSS deleted:', languages)

random_remove = languages.pop() # .pop() method deletes a random value and return the value ... not recommended
print('Randomly Removed value:', random_remove)

languages.clear() # .clear() will empty out a set : output is set()
print('Empty languages:', languages)
```
Languages set: {'HTML', 'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
--
HTML deleted: {'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
CSS deleted: {'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
Randomly Removed value: JavaScript
Empty languages: set()
### Powering Up Sets: Set Operators
Similar to its mathematical equivalent, Python 3 sets can use its diverse amounts of operators to aid in hard calculations

Many of these operators will contain a method equivalent due to sets being mutable 

***important***: we will be illustrating these operators with a set of strings to ease our livelihoods, however we are able to do this with every type of set

**operators**
-Union
-Intersection
-Difference
-Symmetric Difference
-Proper Subset
-Subset
-Proper Superset
-Superset
**union**: The merging between 2 sets
```
# Union Example:
set1 = set('hello')
set2 = set('world')

result = set1 | set2 # | is the union operator ... all the members of both set are combined to a single set
# Recall that: there are no duplicates
print('set1 union set 2:', result)
```
set1 union set 2: {'h', 'w', 'e', 'r', 'l', 'd', 'o'}

**Intersection** : values that are only present in both sets
```
# Union Example:
set1 = set('hello')
set2 = set('world')

result = set1 & set2 # & is the intersection operator
print('Intersection of set1 and set2:', result)
```
Intersection of set1 and set2: {'o', 'l'}
**difference**: values that are only present in the first set, however not in the second set
```
# Difference Example:
set1 = set('hello')
set2 = set('world')

result1 = set1 - set2 # - is the difference operator ... this is set1 difference set2
result2 = set2 - set1 # set2 difference set1

print('set1 - set2:', result1)
print('set2 - set1:', result2)
```
set1 - set2: {'e', 'h'}
set2 - set1: {'w', 'd', 'r'}

**Symmetric Difference:** Values that are present in only one or the other set, however cannot be in both sets
```
# Symmetric Difference Example:
set1 = set('hello')
set2 = set('world')

result = set1 ^ set2 # ^ is the symmetric difference operator

print('Symmetric Difference of:', result)
```
Symmetric Difference of: {'e', 'h', 'w', 'd', 'r'}

**Proper Subset:** Boolean operator 
-A is proper subset of B if every member of A is in B, but A is not able to be identical to B
```
# Proper Subset Example:
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper subset of set2?:', set1 < set2) # < is the proper subset operator
print('Is set1 proper subset of set3?:', set1 < set3)
print('Is set1 proper subset of set4?:', set1 < set4)
```
Is set1 proper subset of set2?: True
Is set1 proper subset of set3?: False
Is set1 proper subset of set4?: False

**subset:** boolean operator 
-A is a proper subset of B if A < B is True, however, A is able to be identical to B which is like a proper subset
```
# Subset Example:
set1 = {1,2,3}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 a subset of set2?:', set1 <= set2) # <= is the subset operator
print('Is set1 a subset of set3?:', set1 <= set3) # Notice the difference in value here
print('Is set1 a subset of set4?:', set1 <= set4)
```
Is set1 a subset of set2?: True
Is set1 a subset of set3?: True
Is set1 a subset of set4?: False
**Proper Superset:** Boolean operator 
-A is a proper superset of B if A has every value in B & more, however are not identical to each other 
```
# Superset Example:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 proper superset of set2?:', set1 > set2) # > is the proper superset operator
print('Is set1 proper superset of set3?:', set1 > set3)
print('Is set1 proper superset of set4?:', set1 > set4)
```
Is set1 proper superset of set2?: False
Is set1 proper superset of set3?: True
Is set1 proper superset of set4?: False

**Superset**: boolean operator 
-A is a superset of B if A > B or A == B 
```
# Superset Example:
set1 = {1,2,3,4}
set2 = {1,2,3,4}
set3 = {1,2,3}
set4 = set('hello')

print('Is set1 superset of set2?:', set1 >= set2) # >= is the proper superset operator
print('Is set1 superset of set3?:', set1 >= set3)
print('Is set1 superset of set4?:', set1 >= set4)
```
Is set1 superset of set2?: True
Is set1 superset of set3?: True
Is set1 superset of set4?: False

## Disjoint: A Set Behaviour Property
2 sets are classified as disjointed when 2 sets have no common values 
>Let A and B both represent a set.
>If A & B is empty, then set A and B are considered disjointed.
>To check this in python there is a method called: isdisjoint()
**remember**: & is known as intersection operator
```
# Disjoint Example
# .isdisjoint() is a set method to check for such property between two sets.

set1 = {1,2,3,4}
set2 = {5,6,7}
set3 = {1,2,3,4,5}

print('set1 intersect set2:', set1 & set2) # Output is an empty set
print('set1 intersect set3:', set1 & set3) # Output is an non-empty set
print('--')
print('set 1 disjoint set 2 check:', set1.isdisjoint(set2)) # Therefore .isdisjoint() evaluates to True
print('set 1 disjoint set 3 check:', set2.isdisjoint(set3))
```
set1 intersect set2: set()
set1 intersect set3: {1, 2, 3, 4}
--
set 1 disjoint set 2 check: True
set 1 disjoint set 3 check: False
## Set Operators as Methods 
```
# Union
a = set('abracadabra')
b = set('alacazam')

a.union(b)
print('Union:', a)

# Intersection
a = set('abracadabra')
b = set('alacazam')

a.intersection(b)
print('Intersection:', a)

# Difference
a = set('abracadabra')
b = set('alacazam')

a.difference(b)
print('Difference:', a)

# Symmeteric Difference
a = set('abracadabra')
b = set('alacazam')

a.symmetric_difference(b)
print('Symmetric Difference:', a)

# Subset
a = set('abracadabra')
b = set('alacazam')

print('Subset:', a.issubset(b))

# Superset
a = set('abracadabra')
b = set('alacazam')

print('Superset:', a.issuperset(b))
print('--')

# There are no proper subset/superset methods

# copy
a = set('abracadabra')
b = a.copy()
c = a

a.add('z')
print('.copy() examples:')
print('set a:', a)
print('set b:', b)
print('set c:', c)
```
Union: {'b', 'a', 'r', 'd', 'c'}
Intersection: {'b', 'a', 'r', 'd', 'c'}
Difference: {'b', 'a', 'r', 'd', 'c'}
Symmetric Difference: {'b', 'a', 'r', 'd', 'c'}
Subset: False
Superset: False
--
.copy() examples:
set a: {'b', 'a', 'z', 'r', 'd', 'c'}
set b: {'b', 'a', 'd', 'r', 'c'}
set c: {'b', 'a', 'z', 'r', 'd', 'c'}

**Assignment Operation & Updating Methods**
An approach to modify an original set with another and assign the final outcome back to the initial set
```
# Union and Update --> Update the set, adding elements from all others.
a = set('abracadabra')
b = set('alacazam')

a |= b # same as: a.update(b)
print('Union Update:', a)

# Intersection and Update --> Update the set, keeping only elements found in it and all others.
a = set('abracadabra')
b = set('alacazam')

a &= b # same as: a.intersection_update(b)
print('Intersection Update:', a)

# Difference and Update --> Update the set, removing elements found in others.
a = set('abracadabra')
b = set('alacazam')

a -= b # same as: a.difference_update(b)
print('Difference Update:', a)

# Symmetric Difference and Update --> Update the set, keeping only elements found in either set, but not in both.
a = set('abracadabra')
b = set('alacazam')

a ^= b # same as: a.symmetric_difference_update(b)
print('Symmeteric Difference Update:', a)
```
Union Update: {'b', 'a', 'z', 'r', 'l', 'm', 'd', 'c'}
Intersection Update: {'c', 'a'}
Difference Update: {'b', 'r', 'd'}
Symmeteric Difference Update: {'b', 'z', 'r', 'l', 'm', 'd'}
## Set Comprehension
Similar to list comprehension, sets can also use comprehension 
```
# Set Comprehension Example
def isPalindrome(x):
    ''' isPalindrome() returns True if string X is a palindrome '''
    return x == x[::-1]

nums = list(range(1,10000))
palindromic_set = {num for num in nums if isPalindrome(str(num))}

print('Palindromic Numbers Set from 1 to 10000:')
print(palindromic_set)
```
Palindromic Numbers Set ranging from 1 to 10000:
{1, 2, 3, 4, 5, 6, 7, 8, 9, 515, 11, 6666, 525, 9229, 1551, 4114, 22, 535, 33, 545, 5665, 8228, 3113, 555, 44, 9779, 565, 55, 4664, 7227, 575, 2112, 66, 585, 8778, 77, 3663, 6226, 595, 1111, 88, 606, 7777, 99, 101, 2662, 616, 5225, 111, 626, 6776, 121, 9339, 636, 1661, 4224, 131, 646, 141, 5775, 656, 8338, 151, 3223, 666, 161, 9889, 676, 4774, 7337, 171, 686, 2222, 181, 696, 8888, 3773, 191, 6336, 707, 1221, 202, 717, 7887, 212, 2772, 727, 5335, 222, 737, 6886, 232, 9449, 747, 1771, 4334, 242, 757, 252, 5885, 767, 8448, 3333, 262, 777, 9999, 272, 787, 4884, 7447, 282, 2332, 797, 292, 8998, 808, 3883, 6446, 303, 9009, 818, 1331, 313, 828, 7997, 2882, 323, 5445, 838, 8008, 333, 848, 6996, 343, 9559, 1881, 858, 4444, 7007, 353, 868, 363, 5995, 878, 8558, 3443, 373, 6006, 888, 383, 898, 4994, 7557, 393, 2442, 909, 5005, 404, 919, 3993, 6556, 414, 9119, 929, 1441, 4004, 424, 939, 2992, 434, 5555, 949, 8118, 3003, 444, 959, 9669, 454, 1991, 969, 4554, 7117, 464, 2002, 979, 474, 8668, 989, 3553, 484, 6116, 999, 1001, 494, 7667, 2552, 505, 5115}

## Summary of sets in Python 3
>Sets aren’t sliceable nor indexable
>Sets cannot have sets inside them
>Sets do not have order; nor order of insertion
>Sets cannot guarantee that their values will be in order
>Sets do not record a value’s position





