# Conditionals and Recursion

### Test Question 4

Determine if a given integer is a prime number.

Problem:
Determine if a given integer is a prime number.

Preconditions:
Given a positive integer ( n >= 1 )

Postcondition:
Return "yes" if it is a prime number, otherwise, "no"

```
Algorithm:

1. Create a variable to store the result and default to "yes"
2. Iterate through the values 2 to n-1 (n = positive integer)
	a. is n evenly divided by the current number?
		I. Yes, it isn't
		II. Set the result to "no"
		III. Stop Iterating through values
	B. Otherwise,
		I. No, it can still be a prime.
3. Return the result
```

## CH.05 Conditionals and Recursion

```python
# Modulus operator

# Regular division
print( 7 / 3 )

# Floor Division
print( 7 // 3 )

# Modulus - remainder ### Gives the remainder
print( 7 % 3 )
```

### Boolean Data Type

```python
# only has 2 possible values: True and False

print( True ) ### True is a value not a string
print( False ) ### False is a value not a string
print(type(True))
print(type(False))
```

### Boolean Expressions

```python
# Assignment
x = 5

# Equality Test
print(5 == 5)
print(5 == 4)

# Inequality Test
print(5 != 5)
print(5 != 4)

# Greater than
print(5 > 4)

# Less than
print(5 < 4)

# Greater than or equal to
print(5 >= 5)
print(5 >= 4)

# Less than or equal to
print(5 <= 5)
print(5 <= 4)

# Is this number even
print( "Even?" )
n = 4
print (0 == (n % 2)) # True
n = 5
print ( 0 == ( n % 2 ) ) # False
```

### Logical Operators

```python
print("")
print("Logical operators")

# and
print(True and True)  # True
print(True and False)  # False
print(False and True)  # False
print(False and False)  # False

# or
print(True or True)  # True
print(True or False)  # True
print(False or True)  # True
print(False or False)  # False

# not
print(not True)  # False
print(not False)  # True

# Combining logical operators
print(True and (False or True))  # True
print((True and False) or True)  # True
```

### print('Conditional Execution')

```python
print('')
print('Conditional Execution')
# Simple if statement
x = 1
if x > 0:
    print("x is positive")

# if-else statement
x = 2
if 0 == (x % 2):
    print("x is even")
else:
    print("x is odd")

# if-elif-else statement
x = 6
y = 5
if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")

# Nested if statement
x = 4
y = 5
if x == y:
    print("x is equal to y")
else:
    if x < y:
        print("x is less than y")
    else:
        print("x is greater than y")

# If x is between 0 and 10
if 0 < x < 10:
    print("x is between 0 and 10")
# could also be written as:
if (x > 0) and (x < 10):
    print("x is between 0 and 10")
```

### Recursion

```python
print("")
print("Recursion")


# Function that calls itself
def countdown(n):
    if n <= 0:
        print("Blastoff!")
    else:
        print(n)
        # Recursive call
        countdown(n - 1)

    return


### Call the function
countdown(5)
countdown(5.5)  # This will also work, but will print the float value

```

### input and output

```python
print("")
print("Input")

input_year = input("What is the current year? ")
next_year = int(input_year) + 1
print("Next year will be", next_year)
```

### Fibonacci Sequence

```python
print("")
# n   = 0 1 2 3 4 5 6 7 8 9 10
# F(n) = 0 1 1 2 3 5 8 13 21 34 55

# F(n) = F(n-1) + F(n-2)
# F(0) = 1
# F(1) = 1

def calculate_fibonacci(n):
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    else:
        return calculate_fibonacci(n - 1) + calculate_fibonacci(n - 2)
```
