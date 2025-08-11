# <p align="center"> Ch12 Tuples

### <p align="center">Test Question #13

Given two sorted list, combine them into a new sorted list.

1, 3, 4, 7, 9
2, 4, 6, 8

--> 1, 2, 3, 4, 5, 6, 7, 8, 9

PROBLEM:  
Given two sorted list, combine them into a new sorted list.

POSTCONDITIONS:  
Given 2 sorted lists (n1 >= 0, n2 >= 0)

POSTCONDITIONS:  
Return a sorted list with the contents of both lists.

ALGORITHM:

1. Create an empty list and call it "all"

2. Iterate through the elements in the first list.

3. Iterate through the items in the first list,

   (this should remove the item from the list at the same time.)  
    A. Look at the first item in the second list

   B. If the item from the first list is less than the second,
   or the second list is empty.

   - I. Add the item from the first list to the 'all' list

   C. Otherwise:

   - I. Remove the first item from the second,
     and add it to the 'all' list.

   - II. Continue on with the new first item in the second list

4. If there are any items left in the second list,

   - A. Add to the all list in the same order.

5. Return the "all" list

## Ch12 Tuples

- A tuple is a sequence of values

- Tuples are immutable

- Tuples usually store data of different data types

```python
a_tuple = ("a", "b", "c", "d", "e") # Preferred
a_tuple = "a", "b", "c", "d", "e"
a_tuple = ("a",)

a_tuple = tuple()
print(a_tuple)
a_tuple = tuple("lupins")
print(a_tuple)

a_tuple = ("a", "b", "c", "d", "e")
print(a_tuple[2])
print(a_tuple[1:4])
print(a_tuple[2:])
print(a_tuple[:3])
```

### Tuple Assignment

```python
print("")
print("Tuple Assignment")

a = 5
b = 6
```

#### Swap the values

```python

temp = a
a = b
b = temp
print(a, b)
```

#### Swap with tuples

```python

(a, b) = (b, a)
print(a, b)
```

### Split a string

```python

email = "monty@python.org"
(name, domain) = email.split("@")
print(name)
print(domain)

student_info = "Bob,12345,Computer Science, 1970-01-01"
(name, student_id, major, birthdate) = student_info.split(",")
print(student_id)
print(birthdate)
```

### ("Tuple as a return value")

```python

quotient, remainder = divmod(7, 3)
print(quotient)
print(remainder)
```

### Returns the min and max of a tuple of numbers

```python

def min_max(a_tuple):
return (min(a_tuple), max(a_tuple))

numbers = (13, 7, 55, 42)
min_num, max_num = min_max(numbers)
print(min_num)
print(max_num)
```

### ("Variable-length argument tuples")

```python

# \* is the gather operator

def gather_args(\*args):
for item in args:
print(item)

gather_args(1, 42.0, "bob")
gather_args(13, 55, "Sally", "Fred", "Joe", True)
gather_args()

a_tuple = (7, 3)
result = divmod(\*a_tuple)
print(result)
```

### ("Lists and tuples")

```python

a_string = "abc"
a_list = [1, 2, 3]
for element in zip(a_string, a_list):
print(element)

print(type(zip(a_string, a_list)))

for element in zip("Peter", "Tony"):
print(element)

a_list = [("a", 1), ("b", 2), ("c", 3)]
for letter, number in a_list:
print(letter, "=>", number)
```

### ("Dictionaries and tuples")

```python

a_dict = {"a": 0, "b": 1, "c": 2}
dict_items = a_dict.items()
print(type(dict_items))
print(dict_items)

for element in dict_items:
print(element)

for key, value in dict_items:
print(key, "=>", value)
```

### tuples can be keys in a dictionary

```python

phone_directory = dict()
phone_directory["Smith", "Bob"] = "555-1234"
phone_directory["Smith", "Jenny"] = "867-5309"
```

#### Iterate through the phone directory

```python

for last, first in phone_directory:
print(last, first, phone_directory[last, first])

bob = ("Smith", "Bob")
also_bob = ("Smith", "Bob")
jenny = ("Smith", "Jenny")
print(bob < jenny)
print(bob == also_bob) # checks quantity
print(bob is also_bob) # checks if it is exactly the same
```
