# Exam 2 Debrief

<hr/>

`add_move`

This question was designed to assess understanding of how exceptions are raised; however, many students misunderstood the question.

Without exception handling, the body of this function would look as follows:

```python
def add_move(board: list[list[str]], row: int, col: int, play: str):
    board[row][column] = play

```

The exception handling piece required conditions to test for each possible error condition and raising of the appropriate exception, for example:

```python
if row < 0 or row > 2:
   raise ValueError('row is out of range.')
```


<hr/>

`no_vowel_words`

Many students used a tail recursive approach for the `no_vowel_words` function. Consider a sample solution below:

```python
VOWELS = 'aeiou'
def no_vowel_words(list, result = []):
    if len(list) == 0:
        return result
    if list[0][0].lower() in VOWELS:
        return no_vowel_words(list[1:])
    result.append(list[0])
    return no_vowel_words(list[1:]
```

This approach works in this case; however, the reason it works is because a *mutable* default argument in Python is created only once when the function in defined. In this case, the result list behaves like a global variable, and every call to the function modifies the same list. In general, use of mutable default arguments should be used very carefully.

<hr/>

`find_min`

A large number of solutions compared the first and second items at each recursive call and either returned the minimum of the list starting at position 1 or removed the list at position 1 and returned the minimum of the resulting list.

A more clear recursive solution returns the minimum of the first element and whatever is returned by finding the minimum of the rest of the list.

ChatGPT gives the following solution:

```python
def find_min(lst):
    # Base case: If the list has only one element, return it
    if len(lst) == 1:
        return lst[0]
    
    # Recursively find the minimum in the rest of the list
    min_rest = find_min(lst[1:])
    
    # Return the smaller of the first element or the minimum of the rest of the list
    return lst[0] if lst[0] < min_rest else min_rest
```

The return statement uses something called a [ternary operator](https://www.geeksforgeeks.org/ternary-operator-in-python/). We have not discussed this syntax, but it is a concise way to write an if statement. The statement above is equivalent to the following:

```python
if lst[0] < min_rest:
    return lst[0]
return min_rest
```