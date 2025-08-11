## <p align="center"> Test Question #11

Given three numbers, find the median value.

42 13 55

PROBLEM:  
Given three numbers, find the median value.

PRECONDITIONS:  
we have 3 numbers (assume they are in a list)

POSTCONDITION:  
return the median value

ALGORITHM:

1. Create the median variable = 0 # zero is a good default

2. Sort the numbers

3. get the number of items in the list

4. if the number of items is odd, then.

   A.subract 1 from the number of items

   b. divide that by 2 and say that is the index of the median value

   c. store the value at that index in median

5. Otherwise:  
   the number of items is even.

   a. Divide the number of items by 2 and call it the high index

   b. Average the values at high index and high index -1

   c. store the average in median

6. return the median value  
   13 42 55
