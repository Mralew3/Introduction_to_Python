# <p align="center">Files

### <p align="center"> Test question 9

Given a dictionary of words and their definitions, search for the definition
of a given Word.  
 (ex.) how would you find the definition of the word 'computer'

PROBLEM:
Given a dictionary of words and their definitions, search for the definition
of a given Word

PRECONDITIONS:
Given a dictionary and a search word

POSTCONDITIONS:
Returned a definition of the search word

ALGORITHM:

1.  search and find the word in the dictionary

    A. Iterate through each word in the dictionary.

    B. Is this the word we want?

    &emsp;I. Yes, break out of the loop

    C. Is this current word past (or greater than) the given word?

        I. yes, quit since we didn't find the word

    D. Otherwise

        I. Go to the next word

2.  Get the associated definition

3.  return the definition

## <p align="center">CH09 - Files

### Open the file

```{python}
input_file = open("short-words.txt")
print(input_file)
```

### Use a for loop to iterate over each line of text

```{python}
for line in input_file:
    word = line.strip()
    print(line)  # this will print the content of the file
```

### Close the file

```{python}
input_file.close()  # makes sure the content was saved to the file

print("------")
print("NO e test")
```

### Define a function that determines if a word does not have an 'e'

```{python}
def has_no_e(word):
    result = False
    # Does the word not have 'e' in it?
    if not ("e" in word):
        result = True

    return result


print(has_no_e("python"))
print(has_no_e("bobsled"))
```

### same as above, but not hardcoded to 'e'

```{python}
def has_no_letter(word, letter):
    result = False
    # Does the word not have 'letter' in it?
    if not (letter in word):
        result = True

    return result
```

### same as above, but check multiple letters

```{python}
def has_no_letters(word, letters):
    result = True
    # iterate through each letter in letters
    for letter in letters:
        # Does the word not have 'letter' in it?
        if not (letter in word):
            result = False

    return result
```

### Open the file

```{python}
input_file = open("short-words.txt")
```

### Process each line (i.e., word)

```{python}
for line in input_file:
    word = line.strip()

    # Does the word not have 'e' in it?
    # if has_no_e(word):
    if has_no_letter(word, "e"):
        # print(word)
        no_e_word_count += 1
```

### Close the file

```{python}
input_file.close()

print("There are[", str(no_e_word_count), "] words without an e")
```

### for / while loop

```{python}
fruit = "banana"

### for loop
for i in range(len(fruit)):
    letter = fruit[i]
    print("For: [", i, "]=[", letter, "]")

### while loop
i = 0
while i < len(fruit):
    letter = fruit[i]
    print("While: [", i, "] = [", letter, "]")
    i += 1
```

### recursion

```{python}
def recurse_through_string(word, index):
    # Base case: if index is >= length of the word
    if index < len(word):
        letter = word[index]
        print("Recursion: [", index, "] = [", letter, "]")
        recurse_through_string(word, index + 1) # Recursive call with incremented


recurse_through_string(fruit, 0)
```
