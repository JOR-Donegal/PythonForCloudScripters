# Tuple Unpacking

Let's combine some of the things we've learned. I have a price list from the supermarket of the fruit I buy. I want to identify the most expensive single item.

```
def most_expensive(price_list):
    """
    Iterate through a list and find the most expensive item
    """
    # Set up the variables
    max_price = 0
    max_price_item = ""
    # Iterate, unpacking the tuple
    for description, price in price_list:
        # If this is the maximum price, record that in our variables
        if price > max_price:
            max_price = price
            max_price_item = description
        # If it is not the maximum price, do nothing
        else:
            pass
    # Return the maximum prices item and its price
    return max_price_item, max_price

# Provide the data
price_list = [("Pineapple", 1.0), ("Apples", .5), ("Pears", .7), ("Peaches", .8)]
# Call the function and unpack its return values
product, price  = most_expensive(price_list)
print(product, price)
```

Give this a go! Change the penultimate line to&#x20;

```
product, price, availability = most_expensive(price_list)
```

&#x20;What error do you get and why? 
