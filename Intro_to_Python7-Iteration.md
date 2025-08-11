# Iteration (While Loops)

### <p style="text-align:center;"> Test Question 7

Given a list of numbers, possibly containing duplicates, build a new list
containing only the unique numbers (i.e., no duplicates). for example,
if you are given the list
1,3,4,2,3
the resulting list would be
1,2,3,4

PROBLEM:  
Given a list of numbers, possibly containing duplicates, build a new list
containing only the unique numbers

PRECONDITIONS:  
given a list of numbers (allow an empty list)

POSTCONDITIONS:  
Return a new list of that has no duplicates

ALGORITHM:

1. If the list is empty, return empty
2. Create a new list to all the non-duplicate numbers
3. Iterate through all the numbers in the given list ## algorithm to see if a number is in the list:

   &emsp;A. If the current number is not in the new list, then:

   - I. Add it

   &emsp;B. Otherwise:

   - I. Go on to the next number

4. Return the new list

## Ch. 07 Iteration (While loops)

```{python}
import random # Importing the random module to generate random numbers
```

### Multiple assignment

```{python}
a = 2
a = 4
a = 5
b = a # Copying the value means this initial value remains constant to the b variable
a = 3
```

### Updating variable

```{python}
x = 0
x = x + 1 # Increment
x += 1 # Increment
x = x - 1 # Decrement
x -= 1 # Decrement
```

## Iteration

```{python}
# For loop - definite loop
# While loop - indefinite loop

def countdown( n ):
    # Iterate through the numbers n to 1
    while ( n > 0 ):
		# the loop body will execute while n > 0 == True
        print( n )
		# Update n
        n -= 1
    print( 'Blastoff!')

def countdown_alt(n):
    # done is a sentinel variable
    # that indicates when the loop should stop
    done = False
    while not done:
        print(n)
        # Update n
        n -= 1
        # update done
        done = n <= 0
    print("Blastoff!")
```

### Break Statement

```{python}
def echo():
    # Intentional infinite loop
    while True: # This loop will run indefinitely until we break out of it
        # Get user input
        line = input("> ") # Prompt the user for input
        # Did the user enter "quit"
        if "quit" == line:
            break # Exit the loop if the user types "quit"
        # Print it out
        print(line)
    # We are done!
    print("Done!")

# Uncomment the line below to run the echo function
#echo()

def echo_without_break():
    # default to not done
    done = False
    # continue user input until done
    while not done:
        # Get user input
        line = input("> ")
        # Did the user enter "quit"
        if "quit" == line:
            done = True
        else:
            # Print it out
            print(line)
    # We are done!
    print("Done!")

# Uncomment the line below to run the echo_without_break function
#echo_without_break()
```

### Guessing game

```{python}
def start_guessing(low, high):
    # Randomly guessing a number
    random.seed(42)  # Set seed for reproducibility
    chosen_number = random.randint( low, high ) # Generate a random number between low and high
    print("Chosen number [", chosen_number, "]") # Debugging line to see the chosen number
    # Default to being done
    done = False # Sentinel variable to control the loop
    # Repeatedly ask the user for a number
    while not done:
        # Ask the user for a number
        guess = int(input("Guess a number: "))

        # Check the number
        # Is the number too high?
        if guess > chosen_number:
            # Yes,too high
            print("Too high")
        # Otherwise, is the number too low?
        elif guess < chosen_number:
            # Yes, too low
            print("Too low")
        # Otherwise, they got the number right
        else:
            # just right
            print("You got it right!")
            done = True


# Uncomment the line below to run the start_guessing function
# start_guessing(1, 100)
```
