
**Table of Contents**

* [Lab 6: find the maximum of a list of numbers.](#lab-6-find-the-maximum-of-a-list-of-numbers)  
	* [Problem statement](#problem-statement)  
	* [Solution Key](#solution-key)  
	* [CloudCoder Exercise](#cloudcoder-exercise)  
	* [Pre-Lab Questions](#pre-lab-questions)  
	* [Post-Lab Questions](#post-lab-questions)  
	* [Bonus 1](#bonus-1)  
	* [Bonus 2](#bonus-2)  
	* [Bonus 3](#bonus-3)  
	* [Bonus 4](#bonus-4)  
	* [Interview Grade](#interview-grade)  
	* [Related Links](#related-links)  


# Lab 6: find the maximum of a list of numbers. 

[TOC]

## Problem statement 

Implement a python program that finds the maximum in a list of numbers. The program must call a python function `get_maxnumber` that takes as argument a list of numbers (maximum of 10 integers). It must then return the maximum number in that list. 

	Sample Input1: [5]
	Sample Output1: 5
	
	Sample Input2: [1,2]
	Sample Output2: 2
	
	Sample Input3: [1,2,3,4]
	Sample Output3: 4


## Solution Key

```python 

#!/usr/bin/python
# -*- coding: utf-8 -*-


def get_maxnumber(numbers):
    """returns the maximum number in the list
....The sequence of steps in the algorithm is:
....#1 - initialize the maximum value
....#2 - Loop through the entries in the list
........#3 - If maxval is not set, update with number
........#3 - If maxval is less than number, update
....#4 - Return the max value
...."""

    maxval = None  # 1
    for num in numbers:  # 2
        if not maxval or maxval < num:  # 3
            maxval = num
    return maxval  # 4


def get_list_of_numbers():
    """returns a list containing elements entered by user
....The sequence of steps in the algorithm is:
....#1 - initialize the list
....#2 - Start loop for maximum of 10 entries
........#3 - Get input from user. If not an number, break
........#4 - Append the number to the list
....#5 - Return the list containing numbers
...."""

    ilist = []  # 1
    for x in range(0, 10):  # 2
        try:  # 3
            userval = input('Enter number ' + str(x) + ': ')
            ilist.append(int(userval))  # 4
        except ValueError:
            break  # if user enters a non-integer

    return ilist  # 5


# Program starts here
ulist = get_list_of_numbers()
print ('List of numbers: ', ulist)
maxnum = get_maxnumber(userList)
print ('The largest number is ', maxnum)

# Functional programming style
print ('The largest number is ', get_maxnumber(get_list_of_numbers()))

```


## CloudCoder Exercise 

http://cloudcoder.kgisl.com/cloudcoder/#exercise?c=1,p=81 


## Pre-Lab Questions 

0. If the list is a sorted list in ascending order, for e.g. `[1, 2, 3, 4, 5, 6]`, what is the maximum value? What is the python code that will access the maximum value in the list? 
1. What is the single line python code that will return the maximum value any list that is sorted in the ascending order? 
1. If the list is a sorted list in descending order, for e.g. `[5, 4, 3, 2, -1]`, what is the maximum value? What is the python code that will access the maximum value in the list? 
2. What is the single line python code that will return the maximum value in any list that is sorted in the descending order? 
3. What is the code for finding out the index of the minimum value of the element in the list. Assume the list contains only integers. Is there a one-line code for this? 
3. Assume that the list is already sorted, but it is not known whether it is in ascending order or descending order. In that case, what is the single line python code that will return the maximum value in the list? 
4. What are some of the methods that are available to the `list` python data type? 
5. What is the output of the following python code?
 
		for x in [1, 3, 5, 7]: 
			print (x) 
		
6. What is the output of the following python code? 
		
		for elem in [ 1, 2, 3, 'abc', 99]: 
			print (elem*2) 

6. What is the code for printing the elements of a list in the reverse order, without actually modifying the list in any way? 

7. What is the python code for outputting all the odd integers from 3 to 44? 

8. A list contains `n` elements (where `n` is a positive integer and  `0 > n > 10`. Write the necessary python code to produce a list that contains only the last `n-1` elements. Is there a version of the code that does not use any `list` methods whatsoever to achieve the same result? 

9. Complete the Hackerrank problem - https://www.hackerrank.com/challenges/python-lists 

## Post-Lab Questions 
1. Both the functions `get_maxnumber` and `get_list_of_numbers` are not **fruitful** functions. True or False? 
1. How will you find the minimum of the values in a list of numbers? What change will you make to the code? 
2. If the list is empty, what will be the value returned from the function? 
3. If the list happens to be empty, then `get_maxnumber` function must return the string `"N.A.".`. What changes will you make to the code? 
		
		Sample Input: []     
		Sample Output: "N.A." 

3. For Point 2, refactor the code that you have written using a ternary operator. 

4. Write the recursive version for finding the maximum value in a list. 

5. How can you create a static variable inside a python function? Give an example. 



## Bonus 1 
4. Suppose the user wanted the freedom not to be restricted to a maximum of 10 numbers, what change would you do to the code? 

## Bonus 2 
1. How will you rewrite the function `get_maxnumber()` using the in-built function `max` (https://docs.python.org/3/library/functions.html?highlight=max#max)? 
2. Can you reduce the function to a one-liner? 
3. Under what conditions will the one-liner function fail? Can this failure be handled in a pythonic (aka graceful) fashion?  Clue: There are at least conditions.
4. How will the code be modified so that both the `max_value` and the `max_index` at which the `max_value` occurs is returned?


## Bonus 2.1 

Assume a list contains only lists as its elements. Write a program to return the element (i.e. a list) in that that contains the maximum number of elements. Use the built-in `max` to come up with the appropriate logic. 

For e.g., 
```
alist = [ [1, 2, 3], [3, 4, 5, 6], [100, 1] ] 
max_element(alist) -> [3, 4, 5, 6]
```



## Bonus 3

How will you find out the 2nd largest number in the list of numbers? Take into consideration that the list may contain duplicate numbers as well. 

## Bonus 4 

Write a program that asks the user to input 10 integers, and then prints the largest odd number that was entered. If no odd number was entered, it should print a message to that effect.

## Interview Grade 
If `n` is the size of the list, and `1 < k < n`, how will you find the `k`th largest number in the list of numbers? (a **#GTG** challenge, a Google interview question).

## Related Links

PythonTutor for visualizing the code related to list processing.  https://goo.gl/v7ephq