# <p align="center"> Strings

### <p align="center">Test Question 8

Given a list of n values, build a new list that is the reverse of the given list.
for example, if you are given a list
1,2,3,4,
the resulting list would be
4,3,2,1

Problem:  
Given a list of n values, build a new list that is the reverse of the given list.

Preconditions:  
Given a list of n values ( n >= 0 )

Postconditions:  
Return a new list of n values where the contents are reversed

Algorithm:

1. Build a new list
2. Iterate through the original list
   - A. Insert the current value into the first position of the new list

&emsp; Or:

1. Build a new list
2. Iterate through the original list in reverse:

   - A. add the current value to the end of the new list

## <p align="center">Ch. 08 - Strings

### String - a sequence of characters

```python
x = 42
y = "42"

fruit = "banana"
letter = fruit[1]
print(letter)
print(fruit[1 + 2])

# Off by one error
length = len(fruit)
# last_letter = fruit[length]
# print(last_letter)
```

### for loop

```python
print("For Loop")
for i in range(len(fruit)):
    print(fruit[i])


print("while loop")
index = 0
while index < len(fruit):
    print(fruit[index])
    index += 1

print("For Loop alternative")
for char in fruit:
    print(char)

print(type(char))
#


print("Building strings")
prefixes = "JKLMNOPQ"
suffix = "ack"
```

### Concatenation

```python
for letter in prefixes:
    print(letter + suffix)


print("----")
print("String slices")

funny = "Monty Python"
print("[ " + funny[1:3] + "]")  # prints 'on'
print("[ " + funny[0:5] + "]")  # prints 'Monty'
print("[ " + funny[3:9] + "]")  # prints 'ty Pyt'

print("[ " + funny[:5] + "]")  # prints 'Monty'
print("[ " + funny[6:] + "]")  # prints 'Python'
print("[ " + funny[-5:-1] + "]")  # prints 'ytho'
```

### Strings are immutable

```python
greetings = "Hello World"
# greetings[0] = "J"  # This will raise an error

new_greeting = "J" + greetings[1:]
print(new_greeting)  # prints 'Jello World'
```

### search for a given character in a string

```python
def find(word, letter):
    # Default to the letter is not in the string
    letter_index = -1

    # iterate through all characters in the string
    for i in range(len(word)):
        # check if the character is equal to the given letter
        if word[i] == letter:
            # Yes, save the index and break the loop
            letter_index = i
            print("found the letter [", letter, "] at index", letter_index)
            break

    return letter_index
```

### Test the find function

```python
print(find("Hello There", "T"))  # Should print the index of 'T'
print(find("Hello There", "X"))  # Should print -1 since 'X' is not in the string
print(find("Hello There", "e"))  # Should print the index of the first 'e'
```

### String methods

```python
print("String methods")

word = "banana"
```

### invoke the method

```python
new_word = word.upper()
print(new_word)  # prints 'BANANA'
```

### in operator

```python
print("an" in "banana")  # prints True
print("an" in "apple")  # prints False
```

### string comparison

```python
print ('string comparison')

word = apple
print(word == "apple")  # prints True
print(word == "banana")  # prints False
print(word < "banana")  # prints True, because 'a' < 'b'
print(word > "banana")  # prints False, because 'a' < 'b'
```
