# Fruitful Functions

=======================Test Question #6======================
determine if a given string is a palindrome.

PROBLEM:
Determine if a given string is a palindrome.

PRECONDITIONS:
Given a string (an empty is acceptable)

POSTCONDITIONS:
Return True if the string is a palindrome, otherwise return False

ALGORITHM:

1. Remove any spaces and punctuation
2. If the length of the string is > 1, then:  
    &emsp; a. Create a copy of the string and then reverse it.  
    &emsp;b. Compare the original string to the reverse order.  
    &emsp;c. If they are equal, then:

   - Remove the first and last characters and then pass the new string to the same function  
     (i.e., make a recursive call)

   d. Otherwise,:

   - Not a palindrome

3. Otherwise,
   - It is a palindrome

## Ch. 06 - Fruitful Functions

Function that don't return a value are void (None)  
ex.

```{python}
def test_me():
	print( 'hello' )
result = test_me()
print( result )

# ==========================
# Function that don't return a value are void (None)
## ex.

def test_me():
    print("hello")

result = test_me()
print(result)
```

### ( Don't do this )

```{python}
def do_something_multiple(x):
    if x < 0:
        # Do something complicated
        return -1
    elif x > 0:
        # Do something complicated
        return 1
    else:
        # Do something complicated
        return 0

print(do_something_multiple(5))
```

### ( Do this instead )

```{python}
def do_something_single(x):
    result = 0
    if (x < 0):
        # Do something complicated
        result = -1
    elif (x > 10):
        # Do something complicated
        result = 1
    else:
        # Do something complicated
        result = 0
    return result

print(do_something_single(5))
```

## Incremental Development

### Boolean Functions

```{python}
def is_between(x, y, z):
    # Check if y is between x and z (inclusive).

    return (x <= y) and (y <= z)  # single return statement


print(is_between(1, 2, 3))  # True
print(is_between(1, 3, 2))  # False
```

### Sum of integers from 1 to n (iterative)

```{python}
def sum_integers_iterative(n):
    # Calculate the sum of integers from 1 to n (iterative)
    # define a variable total, to hold the total value
    total = 0
    # iterate from 1 to n (inclusive)
    for i in range(1, n + 1):
        # add the current value of i to total
        total += i
        print( 'total=', total )
        total = total + i
    # return the total value
    return total


print(sum_integers_iterative(5))  # Output: 15
print(sum_integers_iterative(3))  # Output: 6


def sum_integers_recursive(n):
    # Define a variable total, to hold the total value
    total = 0
    # If n <= 1, then total = 1
    if n <= 1:
        total = 1
    # otherwise,
    else:
        # Calculate the sum of integers from 1 to n-1
        total = sum_integers_recursive(n - 1)
        # Add n to the total
        total += n
    # Return the total value
    return total
```
