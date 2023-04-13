# Data Structures & Algorithms notes 1
## Matrices in Python 3
### What is a Matrix?
In the realm of math, a matrix is an illustration of numbers, symbols or expressions within a 2d array 

In the realm of computer science, specifically in python, we are able to begin to make a data strcuture that has values within rows as well as columns, similar to a table, by using a list inside of a list. 

There are extrinsic libraries/modules that are able to be imported into your python program to aid in this procedure; although, for now, we will be making them in the standalone python version 

This is a basic notion in the realm of math, specifically in the calculus/vectors as well as linear algebra 

### Mathematical Matrix Diagram
[image from mrparkonline](https://mrparkonline.github.io/figures/matrix_fig01.png)

This is a mathematical entry of what a matrix should appear as

a description proceeds as 
>Let A represent the matrix 

>Matrix A has m rows and n columns ... in this case 2 rows and 4 columns. 

>row 1 has values of 1 2 3 4 
>column 2 has values of 2 6

### Matrix A in Python 3 

```
# Python 3 representation of matrix A 

matrix_A = [[1,2,3,4],[5,6,7,8]]

# Accessing Matrix A 
print('Row 1: %s' % matrix_A[0]) # Recall: Indexing Starts at zero in Python
print('Value at Row 2 Column 2: %s' % matrix_A[1][1])
```
Row 1: [1,2,3,4]
Value at Row 2 Column 2: 6

There is no such data structure known as a "Matrix" within Python 3

Thus, we program a list inside of a list while satisfying all the policies of a normal matrix:
-Every row need to have an identical amount of values 
-Every column need to have an identical amount of values
-Every item within a 2d list need to have the identical data types 
-Due to indexing begins at 0 everytime, the first row is techincally positioned at matrix_A[0]

## List Comprehension in Python 3
A concise method to make a Python 3 list is known as list comprehension 

This approach is usually used when:
-The list is a product of some operations implimented to every item in it 
-It is created from another sequence/iterable data
-The list is a part of another list/sequence/iterable data that follows a specific constraint 

At a time like this, the ***lambda function*** would be used, however, another approach for readability will be known in the near future. 

### List Comprehension Example 1
We have the ability to make a list which applies a power of 2 onto numbers ranging from 0-10 (not including 10)

```
# Old Method
squares = []
for i in range(10):
  squares.append(i ** 2)

print('Our result: %s' % squares) 
```
output: [0,1,4,9,16,25,36,49,64,81]

```
# List Comprehension

squares = [1**2 for i in range(10)]

print('Our new result: %s' % squares)
```
output: [0,1,4,9,16,25,36,49,64,81]

### How Does it Work?
list comprehension has:
-expression that expresses the list within a **square bracket**
-1+ **"for"** to describe associated parts
-a 0+ **"if"**, amount relies on the list intricacy 

Analyze: [i**2 for i in range(10)]
-i**2 for i in range -> expression that illustrates the list 
-1**2 illustrstes every item in the list
-i is grabbed via the "for"
-for i in range(10) illustrates where i originated from 

### List Comprehension Example 2
make the list: [[1,3],[1,4],[2,3],[2,1],[2,4],[3,1]] 
from 
A = [1,2,3]
B = [3,1,4]

via list comprehension
```
# Solution 
a = [1,2,3]
b = [3,1,4]

result = [[x,y] for x in a for y in b if x != y]
print(result)
```
[[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]

**Explanation:**
Every item in the list has to be a list of 2 values; thus every item is illustrated as [x,y] 

There are 2 "for"s due to us making a list deriving from 2 sources
-x derives from a
-y derives from b 

There is a contraint to the item -> x !- y 
-Thus, as long as the constraint has been satisfied, we will put the item illustrated as x into the final list 
### List Comprehension Example 3
>Use list comprehension to turn a 2D array called vec to a single list 

vec = [[1,2,3],[4,5,6],[7,8,9]]
Output: [1,2,3,4,5,6,7,8,9]

```
# Solution 

vec = [[1,2,3],[4,5,6],[7,8,9]]

result = [value for row in vec for value in row]
print('Vec as a single list of values: %s' % result)
```
vec as single list of values: [1,2,3,4,5,6,7,8,9]

**Description**
vec is an illustration of a matrix within Python 3 by using list of lists 

To take every value one at a time from the rows we need to follow these steps 
1. describe what every item in the list comprehension is representing, in this case -> "value"
2. To now retrieve where value is, establish where it originates, in this case -> "row"; thus, for row in vec
3. Ending off, we assemble our final "for" to indicate that value derives from the row 

the order of "for"s makes a difference in list comprehension



