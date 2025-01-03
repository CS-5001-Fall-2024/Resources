Exam 3 Study Guide
==================

## Logistics

Exam 2 will take place in person on Thursday, December 5 from 3-4:40pm. It will be 8-14 questions in length. 

You **may** use resources including the Python interpreter, your notes, and online resources that you would use for your homework assignments. 

You **may not** submit code that has been copied from or generated by any other source, human or AI. Examples of tools that you may not use include but are not limited to:

- LLMs including Chat GPT and Bard
- Auto-complete tools including GitHub co-pilot and replit
- Your classmates
- Friends you contact via text, email, or a messaging app

You may not copy any part of any answer from any other resource. Any resources used (e.g., a StackOverflow post) must be cited.

## Topics

The exam may cover any topics we have discussed this semester. It is recommended that you review the Exam 1 and Exam 2 study guides as well.

The topics *emphasized* on Exam 3 will include the following:

* Classes and Objects
  - Define a class
  - Create instances of a class
  - Design a set of classes for a program.
* Testing
  - Design unit tests for a given program
* Stacks
  - Describe the result of applying one or more push/pop operations
  - Identify and fix bugs in a Stack implementation
  - Add additional operations to a Stack implementation
  - Use a Stack to solve a problem (e.g., determining whether parens are matching)
* Queues
  - Describe the result of applying one or more enqueue/dequeue operations
* Efficiency
  - Determine the runtime bounds of an algorithm or code snippet (e.g., understand running time of operations on lists versus dictionaries)
  - Design a data structure to ensure a particular runtime bound for a given operation 
* Linear search
  - Find an item in a list

## Example Problems

**Question**
Consider a ```Stack``` implementation that uses a list to store the items in the ```Stack```. One possible implementation for ```push``` is to insert the new item at the beginning of the list. The implementation of ```pop``` then removes the item at position 0. Another possible implementation for ```push``` is to append the new item at the end of the list. The implementation of ```pop``` then removes the last item. Which approach is better *and why*?

**Question**
[Partially generated by Chat GPT]

```python
class Item:
    def __init__(self, name, price):
        self.name = name
        self.price = price

class ShoppingCart:
    def __init__(self):
        self.items = []

    def add_item(self, item):
        self.items.append(item)

    def calculate_total_price(self):
        # Complete the implementation of this method to calculate the total price of all items in the shopping cart.
        pass

# Example usage:
# cart = ShoppingCart()
# cart.add_item(Item("Laptop", 1000))
# cart.add_item(Item("Mouse", 20))
# cart.add_item(Item("Keyboard", 50))
# total_price = cart.calculate_total_price()
# print("Total price of items in the cart:", total_price)
```

(a) Complete the implementation of the `calculate_total_price` method.
(b) Implement at least two unit test methods to test `calculate_total_price`.

**Question**
Consider a ```Gradebook``` application that stores```Student``` objects. The following logic adds a new score to a student's record.

```python

	def add_score(self, first, last, score):
		for student in self.students:
			if student.first == first and student.last == last:
				student.add_score(score)
				break
```
What is the big-oh running time of this method?

**Question**
Consider the ```Gradebook``` application described in the previous. Would it be possible to modify the data structure(s) that store the student records such that the add_score method as shown above could be implemented to execute in O(1) time? If so, describe how. If not, describe why not.

**Question**
Consider an email application. Assume the top-level data structured used in the application is a dictionary that maps a username to a data structure that stores a collection of individual messages. Would you choose to store the collection of individual messages in a list or a dictionary? Explain your answer.

**Question**
A common exercise is to implement a `Stack` using two `Queue` data structures. The following code implements this concept by using a list as a `Queue`, appending to the end and extracting only from the beginning.

```python
   def __init__(self):
        self.q1 = []
        self.q2 = []

    def push(self, x):
        self.q1.append(x)

    def pop(self):
        while len(self.q1) > 1:
           self.q2.append(self.q1.pop(0))
        item = self.q1.pop(0)
        while len(self.q2) > 0:
           self.q1.append(self.q2.pop(0))
        return item

```

What is the big-oh running time of `push` in this implementation?
 

What is the big-oh running time of `pop` in this implementation?

**Question**
[Partially generated by ChatGPT]

Write a recursive function that flattens a nested list into a single list of elements. The input list may contain both integers and other lists, and the result should be a list with all the integers in the same order, but without any sublists.

Function Signature:
```python
def flatten_list(nested_list: list) -> list[int]:
    pass
```

```
Example:
flatten_list([1, [2, 3], [4, [5, 6]], 7])

Output:
[1, 2, 3, 4, 5, 6, 7]
```

Notes:
The input list may contain integers and/or sublists of integers at any depth level.
The function should use recursion to handle the nested structure.

**Question**
In as much detail as possible, explain what happens when a user visits a web
page by typing a URL into their browser URL bar.

**Question**
What is the big-oh running time of the `check_rows` function you implemented for
Project 3? Make sure to provide your answer in terms of n *and* define what n
represents.

**Question**
The following code implements a sorting algorithm called bubble sort:

```python
def bubble_sort(things: list) -> list:
    '''
    Function: bubble_sort -- sorting the elements of a list by swapping
                             two consecutive elements that are out of order
    Parameters:
       things -- the elements to be sorted
    Returns a list with all of the elements in sorted order
    '''
    swapped = True
    count = 0
    while swapped:
        swapped = False
        for i in range(len(things)-1):
            if things[i] > things[i+1]:
                things[i], things[i+1] = things[i+1], things[i]
                swapped = True
    return things
```

The running time of the algorithm is O(n^2). The for loop will execute n-1 times each time around. In the worst case, the while loop will also execute n times. 

Give an example of a list that, when passed as input to this function, the while loop will execute the maximum number of times. 