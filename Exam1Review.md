Exam 1 Study Guide
==================

## Logistics

Exam 1 will take place in person on Thursday, October 3 from 3:00-4:40pm. It will be 8-12 questions in length. You may be asked to define terminology, trace code, explain code, and write code. 

## Topics

The topics covered on the exam will include the following:

* Algorithms 
  - What is an algorithm?
  - Develop an algorithm to solve a given problem
* Variables
  - Variable types
  - Create a variable and assign it a value
* Arithmetic operations
  - Use + - * / // % to perform calculations
* String concatenation
  - Using the + operator with strings
* Boolean expressions
  - Operators and, or, and not
  - Write a complex boolean expression
  - Determine the result of a complex boolean expression
* Conditionals
  - if/elif/else syntax
  - Trace a complex conditional statement
  - Write a conditional statement
* Functions
  - Syntax to define and call a function
  - Parameter passing and scope
  - Trace a program that calls a function
  - Write a function to solve a given problem
* Testing
  - Determine appropriate test cases for a given program or function
* Iteration
  - Identify the control variable, condition, and update for a while loop
  - Trace a while loop with a complex condition 
  - Write a while loop to solve a given problem
* Strings
  - Iterate over the characters in a string
  - Use appropriate string methods to perform various string operations
* Lists
  - Iterate over a list
  - Append to a list
* For loops
  - Trace a for loop 
  - Write a for loop to solve a given problem

## Example Problems

**Question 1**

Consider the following code fragment:

```python
fruit = "banana"
date = 1973
print(f"Your fruit is {fruit}. The year is {date}.")

animal = "dog"
score = 95.4
print(f"Your {animal} scored a {score}.")
 
response = "34"
print(f"You said {response}.")

```
For all variables created in the code fragment above list their name and type.


**Question 2**

What is the output of the following code fragment?

```python
a = 55
b = 5
c = a / b
print(c)
d =  a // 10
print(d)
e = 10 * b
print(e)
```

**Question 3**

What is the output of the following code fragment?

```python
string1 = "banana"
string2 = "apple"
integer1 = 42
integer2 = 987

if (string1 > string2) or (integer1 > integer2):
	print("tiger")
elif (integer1 == integer2) and (string2 > string1):
	print("giraffe")
elif integer2 > integer1:
	print("hyena")

if string2 > string1:
	if integer1 > integer2:
		print("hippo")
	else:
		print("elephant")
else:
	print("bear")
```

**Question 4**

There are two significant errors in the following code fragment. Identify at least one of them and describe it in detail.

```python

def function_one(param1):
	var1 = "cat"
	var2 = "dog"
	print(var1 + var2)

def function_two(param1):
	function_one()
	print(var1)

def main():
	function_two("test")

main()
```


**Question 5**

Write a function called check\_wordle\_guess that takes as input two strings -- a wordle word and a user guess at the wordle word. Return the number of characters that match, i.e., would be colored green in the wordle game. Return -1 if the words are not the same length. Examples:

	input1 = cow; input2 = cat; output = 1
	input1 = cow; input2 = bird; output = -1
	input1 = kitten; input2 = kitten; output = 6
	input1 = dog; input2 = dig; output = 2

**Question 6**

Consider the following Python function:

```python
def sleep_in(weekday, vacation):
	'''
	Returns True if we can sleep in and False if not
	Parameters
	weekday: boolean
		True if it is a weekday and False if not
	vacation: boolean
		True if it is a vacation day and False if not
	Returns:
	boolean
		True if we can sleep in and False if not
	'''
	
	if not weekday or vacation:
		return True
	return False
```

Write at least three test cases that would test different possible execution paths of this function. A test case will be a call to the function with appropriate parameters. *For each test case, briefly describe what the case tests.*

**Question 7**

Consider the following code fragment:

```python
index = 0
string = "a"
while index < 10:
	if len(string) % 2 == 0:
		print(string)
	string = string + "a"
	index += 1
```

(a) What is the name of the control variable for this loop?

(b) What would be the output of this loop?

**Question 8**

Write a Python function that will take as input two lists of integers -- list1 and list2 -- and will return a new list where the value at position i of the new list will be the value at position i of list1 plus the value at position i of list2.

**Question 9**

What is the output of the following code fragment?

```python
string = "one two three four"
result = ""
for letter in string:
	if letter == "t" or letter == " ":
		result = result + "-"
	elif letter == "e":
		result = result + "$"
	else:
		result = result + letter
print(result)
``` 

**Question 10**

```python
def print_string_backward(string):
	"""
	Implement a function that takes as input a str and prints 
	the characters of the str *in reverse* one per line. 
	"""
```

**Question 11**
Given a string, compute a new string where all the 'x' chars have been removed.

**Question 12**
Given a non-negative int n, return the sum of its digits. 

sum\_digits(126) → 9; sum\_digits(49) → 13; sum\_digits(12) → 3