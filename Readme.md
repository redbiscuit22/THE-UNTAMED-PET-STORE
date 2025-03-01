# The Untamed Pet Store

The Untamed Pet Store is a simple and fun website where users can buy pets and pet food. It is built using HTML, CSS, and JavaScript and follows the Functional Programming style to make the code organized and reusable.  

# Website Features  

Homepage  
   - A cute and colorful welcome page with pet images and a nice background.  
   - Encourages users to explore the store and shop for pets.  

Pet Page   
   - Shows different pets like Birds, Capybaras, Cats, Dogs, Monkeys, and Penguins with prices.  
   - Users can increase or decrease the number of pets they want to buy.  

Pet Food Page   
   - Lists pet food items like Seeds, Melons, Milk, Bones, Bananas, and Fish with prices.  
   - Users can increase or decrease the number of foods they want to buy.  


Payment Page  
   - Allows users to enter the total price and amount paid.
   - The system calculates the change and breaks it down into denominations (bills and coins).
   - Shows a summary of items bought.


Functional Programming is a way of writing code that Uses functions to perform tasks instead of changing values directly.  Makes the code reusable and easy to read.  Avoids using loops and variables that change (instead, we use functions that return new values).  

# For example, instead of using a loop to update the quantity of an item, we can use a function like this:  

const updateQuantity = (quantity, change) => quantity + change;

- This function takes the current quantity and adds or subtracts a value (`change`).  
- It returns a new quantity instead of changing the old one directly.  

# Adding or Removing Pets  

Here’s how we can change the number of pets a user wants to buy 

const increaseQuantity = (quantity) => quantity + 1;
const decreaseQuantity = (quantity) => (quantity > 0 ? quantity - 1 : 0);


- `increaseQuantity(2)` → Returns 3  
- `decreaseQuantity(2)` → Returns 1  
- If the quantity is already 0, `decreaseQuantity(0)` will stay at 0 (so users can’t buy negative pets).  

# Calculating Change  

If a user enters the amount they paid, we can calculate the change like this:  

const calculateChange = (amountPaid, totalPrice) => amountPaid - totalPrice;


- If total price = 120 and amount paid = 200, then  
  `calculateChange(200, 120)` → Returns 80  

We can also break this change into bills and coins using another function:  

const getDenominations = (change) => {
    const denominations = [100, 50, 20, 10, 5, 1];
    return denominations.map(bill => ({
        bill: bill,
        count: Math.floor(change / bill),
        remaining: change % bill
    }));
};


- If the change is 80, this function will return:  

  [{bill: 50, count: 1}, {bill: 20, count: 1}, {bill: 10, count: 1}]
  
  Meaning 1x 50 bill, 1x 20 bill, and 1x 10 bill.  


