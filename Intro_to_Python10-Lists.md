### <p align="center">test question 10

Given a list of numbers. calculate the index of the number
in the list that is furthest from the mean:

1 2 3 4 42

Problem:
Given a list of numbers. calculate the index of the number
in the list that is furthest from the mean.

PRECONDITIONS:  
LIST OF NUMBERS (N >= 0)

POSTCONDITIONS:  
Return the index of the number in the list that is furthest away from the mean.
Otherwise, return -1 if the list is empty

Algorithm:

1.  create the variable that holds the index of the furthest number and set it to -1

2.  Create a variable that holds the biggest difference so far and set it to -1

3.  Calulate the mean

    A. Sum all the numbers in the list

    B. The mean is the sum dividend by the total number of items in the list

4.  Iterate through each number in the list

    a. Subtract the number from the mean (mean - number) and take absolute value

    b is it further from the biggest one so far?

        I. Yes, Save the difference as the new biggest so far and save the index.

    C. Otherwise,

        I. Move on to the next number in the list

5.  Return the index:

&emsp; 10.4 - 42 = 31.6

## CH.10 Lists

```{python}

# A list is sequence of values
# - Values are referred to as elements or items

numbers = [ 1, 2, 3, 4, 42 ]
animales = [ 'dog', 'fish', 'bird' ]

print( numbers )

# Data types of elements don't have to be the same
different = ['bob', 3, 14, 42, ['Sam', 55, 2, 1]]

print(different)
```

### empty list are valid

```{python}
empty = []
```

### Access individual elements using bracket notation

```{python}
print( animals[0] )
```

### imutable and mutable

```{python}
# Strings are imutable
# Lists are mutable
animals[1] = 'velociraptor'
print( animals )
animals[ -1 ] = 'dodo'
print( animals )

if( 'fish' in animals ):
	print('Fish is in the animals list')
```

### Traverse a list

```{python}
print('')
print('Traversing a list')

for animal in animals:
	print(animal)

for i in range(len(numbers)):
    print(numbers[i])

print(numbers)
```

### List operations

print("")
print("List operations")

a = [1, 2, 3]
b = [4, 5, 6]

### Concatenation

c = a + b
print(c)

### Repetition

d = a \* 3
print(d)

### slicing

```{python}
print(c[2:4])
print(c[2])
print(c[:4])
```

### slice to modify a list

```{python}
c[2:4] = [55, 42]
print(c)
C[2:4] = [101, 202, 303, 404, 505]
print(c)
```

## List methods

```{python}
print("")
print("List methods")

list1 = ["a", "b", "c"]
print(list1)
```

### Append an item to the end of the list

```{python}
list1.append("d")
print(list1)
```

### extend a list with another list

```{python}
list2 = ["e", "f", "g"]
print(list2)
list1.extend([list2])
print(list1)
print(list2)
```

### sort a list

```{python}
list3 = [3, 1, 4, 2]
list3.sort()
print(list3)
```

### reverse a list

```{python}
list3.reverse()
print(list3)
```

## Reduce: combine all elements into a single value.

### Reduce example:

### sum the numbers in a list

```{python}
def calculate_sum(a_list):
    # Define the variable to hold the sum
    sum_of_list = 0
    # Iterate through the list
    for element in a_list:
        # Add each element to the sum
        sum_of_list += element

    # Return the final sum
    return sum_of_list


list_of_numbers = [13, 42, 55]
print(calculate_sum(list_of_numbers))  # Output: 110
```

===

## mapping a list

```
# map: change the value of each element,
# but keep the same number of elements.
```

### Map example

### Capitalize all the words in the list

```{python}
def capitalize_all(a_list):
    # create a new list
    new_list = []
    # Traverse the list
    for word in a_list:
        # Capitalize the current word
        capitalized = word.capitalize()
        # Add it to the new list
        new_list.append(capitalized)
    # Return the new list
    return new_list


words = ["hello", "world", "python", "rocks"]
print(capitalize_all(words))  # Output: ['Hello', 'World', 'Python', 'Rocks']
capitalized_words = capitalize_all(words)
```

## Filter: choose which elements to keep,

### Filter example

```{python}
# Find the words that only contain uppercase letters
def find_uppercase(a_list):
    # Create a new list
    new_list = []
    # Traverse the original list
    for word in a_list:
        # does the word contain only uppercase letters?
        if word.isupper():
            # Yes, Add it to the new list
            new_list.append(word)
    # Return the new list
    return new_list


words = ["HELLO", "world", "PYTHON", "rocks"]
print(find_uppercase(words))
find_uppercase_words = find_uppercase(words)
print(find_uppercase_words)  # Output: ['HELLO', 'PYTHON']
```

## Deleting elements from a list

### Pop method removes the last element from the list and returns it

```{python}
a_list = ["a", "b", "c", "d", "e"]
value = a_list.pop(1)
print(value)  # Output: b
print(a_list)  # Output: ['a', 'c', 'd', 'e']
value = a_list.pop()
print(value)  # Output: e
print(a_list)  # Output: ['a', 'c', 'd']
```

### Delete operator removes the element at the specified index

```{python}
a_list = ["a", "b", "c", "d", "e"]
del a_list[1]
print(a_list)  # Output: ['a', 'c', 'd', 'e']
```

### delete operator can be used on slices

```{python}
a_list = ["a", "b", "c", "d", "e"]
del a_list[1:3]
print(a_list)  # Output: ['a', 'd', 'e']
```

### Remove method removes the specified element from the list

```{python}
a_list = ["a", "b", "c", "d", "e", "b"]
a_list.remove("c")
print(a_list)  # Output: ['a', 'b', 'd', 'e']
if "b" in a_list:
    a_list.remove("b")  # removes the first occurrence of "b"
if "q" in a_list:
    a_list.remove("q")  # does nothing, "q" is not in the list
print(a_list)  # Output: ['a', 'd', 'e']
```

### list and strings

```{python}
print("")
print("list and strings")

a_string = "hello world"
a_list = list(a_string)
print(a_list)  # Output: ['h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']

a_string = "spam,spam,spam"
a_list = a_string.split(",")
print(a_list)  # delimits are commas

a_string = "this is a test"
a_list = a_string.split()
print(a_list)  # delimits are whitespace by default
delimiter = "-=-"
new_string = delimiter.join(a_list)
print(new_string)  # Output: this-=-is-=-a-=-test
```

### Objects and Values

```{python}
print("")
print("Objects and Values")

a = "banana"
b = "banana"
print(a == b)
print(a is b)

a_list = [1, 2, 3]
b_list = [1, 2, 3]


print(a_list == b_list)  # Equivalence
print(a_list is b_list)  # Sameness
```

### Aliasing

```{python}
print("")
print("Aliasing") # reference variable vs primitive variable

a = [1, 2, 3]
b = a
b[0] = 17
print(a)

x = 5
y = x
y = 6
print(x)
```
