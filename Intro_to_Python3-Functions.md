# Functions Cont.

### Test Problem #2

```{python}
## Sort a list of N numbers from lowest to highest. ##

7 4 42 55 13
# Problem:
Sort a list of N numbers from lowest to highest.

# Preconditions:
a list of numbers

Postconditions:
A list of the same numbers now sorted from lowest to highest

Algorithm:
1. create a new empty list
2. start at the first number and call it the smallest so far
3. iterate through the rest of the list and look at each number
	a. is it smaller than the current smallest so far
		1. this number becomes the new current smallest so far
4. swap the current smallest so far with the first item in the list
5. move to the next position and call this number the smallest so far
6. Go to #2
```

### Test Problem #1 (answer)

```{python}
# App Store
# Problem: Given the app purchase price. compute the profit earned on app purchases
#
# Known Data:
	Refund rate: 5%
	Transaction const: $0.50
#
#	Price Trials: 	$2 -> 1,000
#			3$ -> 700
#			# Assume a Linear Relationship #
```

```{python}
def calculate_number_of_purchases(price):
    # $2 -> 1,000
    # 3$ -> 700
    # equation for a line: y = mx + b
    # m = -300
    # b = 1600
    # y = number of purchases
    # x = price
    number_of_purchases = -300 * price + 1600

    return number_of_purchases


test_number_of_purchases = calculate_number_of_purchases(2)  # 1000
print("Num of purchases $2 -> 1000 ?= [", test_number_of_purchases, "]")
test_number_of_purchases = calculate_number_of_purchases(3)  #  700
print("Num of purchases $3 ->  700 ?= [", test_number_of_purchases, "]")


def calculate_revenue(price):
    # calculate the number of purchases
    number_of_purchases = calculate_number_of_purchases(price)

    # Revenue = purchase price * number of purchases
    revenue = price * number_of_purchases

    return revenue


test_revenue = calculate_revenue(2)  # = $2,000
print("Revenue for $2 => $2,000 ?= [", test_revenue, "]")
test_revenue = calculate_revenue(3)  # = $2,100
print("Revenue for $3 => $2,100 ?= [", test_revenue, "]")


def calculate_costs(price):
    # Constants
    # refund_rate = 5% of purchases

    refund_rate = 0.05
    cost_of_each_transaction = 0.5  # cost of goods sold per item

    # calculate the number of purchases
    number_of_purchases = calculate_number_of_purchases(price)

    # calculate the number of refunds
    number_of_refunds = number_of_purchases * refund_rate

    # calculate the cost of refunds
    # refund_rate = (number of purchases * return rate) * price
    refund_costs = number_of_refunds * price

    # calculate the transaction costs
    # transaction costs = (number of purchases - number of refunds) * cost of each transaction
    transaction_costs = (
        number_of_purchases - number_of_refunds
    ) * cost_of_each_transaction

    # total costs = refund costs + transaction costs
    costs = refund_costs + transaction_costs

    return costs


test_costs = calculate_costs(2)
print("Costs for $2 => $575 ?= [", test_costs, "]")
test_costs = calculate_costs(3)
print("Costs for $3 => $437.50 ?= [", test_costs, "]")


def calculate_profit(price): # the price parameter can be passed into the other functions
    # Calculate the revenue
    revenue = calculate_revenue(price)

    # calculate the costs
    costs = calculate_costs(price)

    # Profit = revenue - Costs # we must create a function to calculate the revenue and const

    profit = revenue - costs # this is the answer
    return profit


test_profit = calculate_profit(2)
print("Profit for $2 => 1425[", test_profit, "]")
test_profit = calculate_profit(3)
print("Profit for $3 => 1662.50[", test_profit, "]")
```
