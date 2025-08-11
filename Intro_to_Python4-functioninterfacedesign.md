# Function Interface Design

### test question 2/3 (answer)

###Test question 2###

find a name in unordered list of n names

problem:
Find a name in an unordered list of n names.

Preconditions:
provided with a name to find
Provided a list of n names where n >= 0

Postcondition:
Return the index of the name in the list if it is in the list, otherwise, -1

```
Algorithm:
    1.) define the location of the name as -1.
    2.) start with the first name and iterate through all the names in the list.
	    a. Does the current name match the name provided:
		    I. Success! We found it.  Store the index of the current name in location.
		    II. Quit!
	    b. No it doesn't Match:
		    I. update the index of the current name +1
		    II. Go on to the next name
```

###Test question 3###

find a name in ordered list of n names

problem:
Find a name in an ordered list of n names.

Preconditions:
provided with a name to find
Provided a list of n names where n >= 0 ORDERED names

Postcondition:
Return the index of the name in the list if it is in the list, otherwise, -1

```
Algorithm:
    1.) define the location of the name as -1
    2.) atart with the first name and iterate through all the names in the list:
	    a. Does the current name match the name provided:
		    I. Success! We found it.  Store the index of the current name in location.
		    II. Quit!
	    B. Is the current name after the provided name?:
		    I. Yes.  Passed where the name should be. it isn't in the list.
		    II. Quit!
	    C. No it doesn't Match:
		    I. update the index of the current name +1
		    II. Go on to the next name
```

## CH.04 Function Interface Design

```{python}
import turtle # import the turtle package to start drawing

## Create a turtle
bob = turtle.Turtle()

print( bob )

# Move Forward
bob.fd( 100 )

# Turn 90 degrees to the left
bob.lt( 90 )

# Move Forward again
bob.fd ( 100 )
```

### Repetition

```{python}
# for loop / definite loop / iteration
for i in range( 4 ):
	print( "Hello" , i )

# Using i is a  programming idiom

# Use a for loop to draw a square

bob = turtle.Turtle()
for i in range(4):
	# Move forward 100 units
	bob.fd(100)
	# Turn left 90 degrees
	bob.lt(90)

```

### Encapsulation

```{python}
def draw_square( my_turtle ):
	for i in range( 4 ):
		my_turtle.fd( 100 )
		my_turtle.lt( 90 )

	print( "Done!" )
#draw_square( bob )
#bob.fd( 300 )
#draw_square( bob )
```

### Abstraction / Generalization

```{python}
def draw_square_any_size( my_turtle, length ):
	for i in range( 4 ):
		my_turtle.fd( length )
		my_turtle.lt( 90 )

	Print( "Done!" )

#draw_square_any_size( bob, 200 )
```

### Generalize even further and draw a n-sided polygon

```{python}
def draw_polygon(my_turtle, n, side_length):
	# Compute the angle. Each side takes 1/n of a full circle (360 degrees)
	angle = 360.0 / n
	#iterate over each of the sides
	for i in range( n ):
	# Move Forward
		my_turtle.fd( side_length )

	# Turn left by the correct angle
		my_turtle.lt( angle )

draw_polygon( bob, 8, 100)
```
