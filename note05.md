# Data Structures and Algorithms note 5
## Dictionary in Python 3
Dictionary (Associative Array, map, symbol table) is a data type that keeps a collection of (key,value) pairs, every potential key occurs a maximum of 1 time within the collection 

**Common Operations:**
-Adding a pair
-getting rid of a pair 
-altering a pair that is already present
-seek a value that is part of a specific key 

>Aside: This concept is an introduction to concepts similar to: hash table and search trees

### Defining a Dictionary in Python 3
Similarily to sets, dictionaries also use {}, although their individual item format is much unlike

>Each item in a dictionary be a pair of key: value.
```
# Dictionary Example
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

# There are 3 items: each with their unique addresses and value
# Accessing
print('Sammy dict:', sammy)
print('Username:', sammy['username'])
print('Online Status:', sammy['online'])
print('Follower Count:', sammy['followers'])
```
Sammy dict: {'username': 'sammy', 'online': True, 'followers': 42}
Username: sammy
Online Status: True
Follower Count: 42

### Dictionary Properties
Every item within a dictionary is key, value pair 

#### Keys
Keys are a special address for a dictionary value's position
**Key Properties**
-Needs to be immutable (strings, numbers, tuples, frozenset)
-Special; thus, 2 identical key values are not able to exist in a single dictionary 
  ->NEWEST CREATED ITEM with a duplicate KEY superceeds the previous declaration
#### Values 
dictionaries are able to hold every data type as a value 
#### Updating a Dictionary 
-We are able to alter values that are present by mentioning the key 
-We are able to add new values to a disctionary via making a new key 
-We are able to overwrite a value at a key that is preseent by mentioning and remaking the value representing it 
```
# Update Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy['followers'] += 10 # We are adding 10 to the value located at key: 'followers'
sammy['verified'] = True # We added a new value at a new key: 'verified'
sammy['username'] = 'SammySammy'

print('Sammy Dict:', sammy)
```
Sammy Dict: {'username': 'SammySammy', 'online': True, 'followers': 52, 'verified': True}
#### Deletion With Dictionary 
-We are able to get rid of a key; thus, removing the value linked to the key 
-We are able to clear out the whole dictionary 
-We are able to remove the dictionary (rarely used)
```
# Deletion Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

del sammy
print('Deleting sammy, should create an error when referenced again', sammy)
```
# Deletion Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

del sammy['followers'] # del is a keyword used to help us to execute a removal
print('followers key deleted:', sammy)

sammy.clear() # {} is considered an empty dict
print('emptying out a dictionary', sammy)
print('--\n\n')

del sammy
print('Deleting sammy, should create an error when referenced again', sammy)

#### Membership
We are able to use the in & not in operators to see if a key is present within a dictionary 
```
# Membership Example

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

print('Checking for key username:', 'username' in sammy)
print('Checking if followers is not a key:', 'followers' not in sammy)
```
Checking for key username: True
Checking if followers is not a key: False

#### Built-in Functions’ Interactions w/ Dictionaries
```
# Built-in Function Interactions

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

print('Size of sammy dict:', len(sammy))
print('Largest Key:', max(sammy))
print('Smallest Key:', min(sammy))
print('Dict to string:', str(sammy))
print('Dict to list:', list(sammy))
```

Size of sammy dict: 3
Largest Key: username
Smallest Key: followers
Dict to string: {'username': 'sammy', 'online': True, 'followers': 42}
Dict to list: ['username', 'online', 'followers']

#### Duplicate a Dictionary and Copy Keys Only
```
# Duplicate a Dictionary

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy_copy1 = sammy.copy()
sammy_copy2 = sammy

sammy['verified'] = True

print('sammy_copy1:', sammy_copy1)
print('sammy_copy2:', sammy_copy2)
print('--')

# Duplicate keys only

tammy = tammy.fromkeys(sammy) # Notice that all key's values are None ... aka empty

print('tammy dict:', tammy)
```
sammy_copy1: {'username': 'sammy', 'online': True, 'followers': 42}
sammy_copy2: {'username': 'sammy', 'online': True, 'followers': 42, 'verified': True}
--
tammy dict: {'username': None, 'online': None, 'followers': None, 'verified': None}
#### Dictionary Methods
To aid in powering this fantastic data structure, it has an excellent set of methods for us to experiment 

>Let A and B be a dictionary 
- >A.keys() –> Returns a sequence of keys/addresses in A
- >A.values() –> Returns a sequence of item values in A
- >A.items() –> Returns a sequence of key,item pairs in A
- >A.get(address) –> Returns the item value at address
- >A.update(B) –> Extends A with the dictionary of key,value pairs of B
```
# Dictionary Method Examples

sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

sammy_hidden = {
    'pwd' : 'qwerty',
    'location' : 'Toronto, Ontario'
}

# printing all the keys of a dict
print('Sammy Dict Keys:', sammy.keys()) # notice how it prints

sammy_keys = list(sammy.keys()) # we can listify the .keys() returned
print('List of sammy_keys', sammy_keys)
print('--')

# printing all the values of a dict
print('Sammy Dict Values:', sammy.values())
print('Sammy Dict Values as a list:', list(sammy.values()))
print('--')

# printing key, value pair of a dict
print('Sammy Dict key, value pairs:', sammy.items())
print('Sammy Dict key, value pairs as a list:', list(sammy.items()))
print('--')

# getting a value from a dict
print('Sammy followers value:', sammy.get('followers'))
print('Same as:', sammy['followers'])
print('--')

# updating / extending a dictionary
sammy.update(sammy_hidden)

print('Sammy extended with its hidden values:', sammy)
```
Sammy Dict Keys: dict_keys(['username', 'online', 'followers'])
List of sammy_keys ['username', 'online', 'followers']
--
Sammy Dict Values: dict_values(['sammy', True, 42])
Sammy Dict Values as a list: ['sammy', True, 42]
--
Sammy Dict key, value pairs: dict_items([('username', 'sammy'), ('online', True), ('followers', 42)])
Sammy Dict key, value pairs as a list: [('username', 'sammy'), ('online', True), ('followers', 42)]
--
Sammy followers value: 42
Same as: 42
--
Sammy extended with its hidden values: {'username': 'sammy', 'online': True, 'followers': 42, 'pwd': 'qwerty', 'location': 'Toronto, Ontario'}
#### Iterating a Dictionary
-We are using 3 iteration methods 
  > 1. iterating the keys
  > iterating the values
  > iterating the key, value pairs by unpacking
```
# Iteration Example 1: Keys
sammy = {
    'username': 'sammy',
    'online': True,
    'followers': 42
}

for k in sammy.keys():
    print('Current key:', k)
print('--\n')

# Iteration Example 2: Values

for v in sammy.values():
    print('Current value:', v)
print('--\n')

# Iteration Example 3: Key, Value Pair

for k, v in sammy.items():
    print('Current Key:', k)
    print('Current Value:', v)
    print()
```
Current key: username
Current key: online
Current key: followers
--

Current value: sammy
Current value: True
Current value: 42
--

Current Key: username
Current Value: sammy

Current Key: online
Current Value: True

Current Key: followers
Current Value: 42
#### dict() Constrcutor Dictionary Comprehension
We are able to switch other data types to dictionaries

In a similar manner to lists, tuples, and sets, you can also do comprehension 

**Note:**
-We need to identify the keys & values positions 
```
# dict() Example

example_data = [
    ('one', 3),
    ('two', 3),
    ('three', 5)
]

data_dict = dict(example_data)
print('data_dict:', data_dict)
print('--')

# Dictionary Comprehension
# Goal: Take string numerals and assign them with their integer square
# - keys : string numerals
# - values: integer squares

example_data2 = ['1', '2', '3', '4', '5']

data2_dict = {x : int(x)**2 for x in example_data2}

print('data2_dict:', data2_dict)
```
data_dict: {'one': 3, 'two': 3, 'three': 5}
--
data2_dict: {'1': 1, '2': 4, '3': 9, '4': 16, '5': 25}



