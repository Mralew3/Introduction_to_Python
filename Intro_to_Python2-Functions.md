# FUNCTIONS

## Algoirthm 1

```{python}
#Calculate the mean value (average) in a list of n numbers.

#Problem:
	Calculate the mean value
#Preconditions:
	have a list of n>0 numbers
#Postconditions
	Calculated the mean value (return)

#Algorithm():
	1. Define running_total as 0
	2. Define Total_numbers as 0
	3. Iterate each of the n numbers
	   A. add the current number to running_total
	   b. increment (add 1) total_numbers
	4. Mean is the running_total / total_numbers
```

## Types of Errors in Python

- Syntax = improper grammar for python ( 3 / )

- Runtime = valid sentence but does not make sense ( 3 / 0 )

- Semantic = programmer and python understand the grammar differently ( 3 / 1 )[ programmer wanted addition but wrote division.]

## Data Types

```{python}
print ( 42 )
print ( 55 - 13 )
print ( type( 42 ) )
```

#### convert int to float

```{python}
x = float( 42 )
print ( x )
print ( type( x ) )
```

#### convert float to int

```{python}
print( int( 42.0 ) )
print( int( 42.9 ) )
print( int( -42.9 ) )
```

#### convert String to float

```{python}
print( float( '42' ) )
```

## Importing Functions

import math ###calls math functions from the math library via the import command

```{python}
import math
radians = math.pi / 2
height = math.sin( radians )
print( height )
```

```{python}
# Calculate the circumference of a circle
# c = 2 (pi) r

radius = 4
circumference = 2 * radius * math.pi
print( circumference ) # ~25
```

## Composition

```{python}
# Define the function
def print_star_wars_greeting():
	print( "May the force be with you" )
	print( "And also with you" )

print( type( print_star_wars_greeting ) )

# Call the function to execute it
print_star_wars_greeting()


#flow of execution

# Use a function in another function

def print_we_will(): ##### function number one
	print( "We wil" )

def print_lyrics(): #### function number two
	print_we_will() #### calls function number one ####
	print_we_will() #### calls function number one ####
	print( "Rock you!" )
print_lyrics()
```

### Parameters and Arguments

```{python}
def greet( name ):        ## name is the parameter ##
    print( "hello" , name )
    print( "How are you doing?" )

greet( 'Boba Fett' )

greet( 2* "yo " + "Ma")

#############################

#### variables and parameters are local (pass by value)  ####
def git_r_done( x, y):
z = x * y
print( "z=[', z, ']" )

git_r_done( 3, 4 )

def git_r_done_again( x, y ):
	x = x + 2
	y = y - 1
	z = x * y
	print( "inside x=[', x, ']" )
	print( "inside y=[', y, ']" )
	print( "inside z=[', z, ']" )

x = 3
y = 4
def git_r_done_again( x, y )
print( "outside x=[', x, ']" )
print( "outside y=[', y, ']" )
#print( "outside z=[', z, ']" )

```

### Fruitful Functions

#### Calculate the area of a circle

```{python}
def calculate_area_circle( radius ):
	# Area = pi * r * r
	area = math.pi * radius * radius
	return area

area = calculate_area_circle( 2 )
print( area ) # ~12.5

# calculate the area of a donut
def calculate_area_donut( outer_radius, inner_radius ):
	# Area of a donut = area of the inner circle - the area of the outer circle
	outer_area = calculate_area_circle( outer_radius )
	inner_area = calculate_area_circle( inner_radius )
	area = outer_area - inner_area
	return area

area = calculate_area_donut( 3, 2 )
print( area ) # ~ 15.7
```
