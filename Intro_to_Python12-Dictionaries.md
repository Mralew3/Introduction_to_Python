# <p align="center">Dictionaries

### <p align="center"> Test Question 12

Given Two strings, Find the lingest common substring.

Where is the substring?
I like the sub sandwich my mom makes.

PROMBLEM:  
Given Two strings, Find the longest common substring.

PRECONDITIONS:  
GIVEN TWO STRINGS

POSTCONDITIONS:  
the longest common substring is returned

ALGORITHM:

1. default to the longest common substring is ""

2. iterate through the characters in the shorter string

   A. iterate through the characters in the linger string

   &emsp; I. Does the current character from teh shorter string match
   the one from the longer string?

   - A. Yes

   B. Is the current substring longer than the previous longest?

   - i. yes, Save this as the current longest substring

   C. Check the next letter in the shorter string
   and longer string to see if they match

   - I. yes:  
      &emsp;continue comparing letters  
     II. Otherwise:  
      &emsp; go on to the next character in the longer string

3. Return the longest common substring

## <p align="center">Ch. 11 Dictionaries

### mapping between keys and values (key-value pairs)

```python
# AKA map (or Table / Hash / Hashtables / Associative array)

a_list = [1, 2, 3]
print(a_list[1])
a_list[1] = 42
print(a_list[1])
```

### Create an empty dictionary

```python
birthdays = dict()
print(birthdays)
```

### Add Key/Value pairs

```python
birthdays["0704"] = "Steve"
birthdays["0529"] = "Tony"
print(birthdays)
print(birthdays["0704"])

print(len(birthdays))
```

### Methods

```python
print(birthdays.keys()) # '0704', '0529'
print(birthdays.values()) # 'Steve', 'Tony'
```

```python
# Duplicates?

# Are keys unique? Yes

# Are values unique? No

birthdays["0704"] = "Sam"
print(birthdays["0704"])

# print(birthdays["1031"]) # print KeyError no key 1031 was created
```

### Reverse lookup

```python
# look for a key given a value

def reverse_lookup(a_dict, value):
key = None

    # Iterate through all the keys
    for current_key in a_dict.keys():

        # Get the value associated with the current key
        current_value = a_dict[current_key]
        print("Current value is[", current_value, "]")

        # Does the value match the given value?
        if current_value == value:
            # print( 'It matches.' )

            # Yes, we found the key
            key = current_key
            # Stop looking
            break
    return key

print(reverse_lookup(birthdays, "Tony")) # '0529'
```

```python
test_dict = {42: "The answer", 13: "Bad luck"}
print(test_dict)
```

## Dictionaries and Lists

```python
print("")
print("Dictionaries and Lists")

birthdays["0704"] = ["Steve", "Sam", "Nick"]
print(birthdays)

phone_book = dict()
phone_book["Bob"] = "123-4567"
phone_book["Jenny"] = "867-5309"
phone_book["Sally"] = "987-6543"
phone_book["Mike"] = "380-8004"
phone_book["Soulja"] = "999-8212"
```

### invert a dictionary

```python
def invert_dictionary(a_dict):
inverted = dict()

    # Iterate through the keys in the original
    for key in a_dict.keys():

        # Get the associated value
        value = a_dict[key]
        # Does the value exist as a key in the inverted dictionary?
        if value in inverted:
            # Yes, add the key as a value to the inverted dictionary
            inverted[value].append(key)

            print("Value existed as a key. Added key as another value")
        # Otherwise,
        else:
            # NO. Build a new list with the key and add it as a value
            # in the inverted dictionary
            inverted[value] = [key]

            print("Value did NOT exist as a key. Added key in a list.")
    return inverted

inverted_phone_book = invert_dictionary(phone_book)
print(inverted_phone_book)
```
