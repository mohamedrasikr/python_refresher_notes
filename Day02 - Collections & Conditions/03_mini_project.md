# **Day 2 — Mini Project**

## **Project Overview**

Build a Grocery Price Tracker that allows users to add items, track prices, calculate totals, and manage their shopping list. This project combines lists, dictionaries, conditional logic, and loops to create a practical application.

---

## **Project Requirements**

Your program must:

1. **Display a welcome message** and menu with options

2. **Add grocery items** with:
   - Item name
   - Price per unit
   - Quantity
   - Category (e.g., "Fruits", "Vegetables", "Dairy", "Meat", "Other")

3. **View all items** in a formatted list showing:
   - Item name
   - Price per unit
   - Quantity
   - Total cost (price × quantity)
   - Category

4. **Calculate total cost** of all items

5. **Filter items by category** and display only items in that category

6. **Find the most expensive item** and least expensive item

7. **Remove an item** from the list

8. **Exit the program** gracefully

---

## **Step-by-Step Instructions**

1. **Set up your file**
   - Create `grocery_tracker.py`
   - Add a comment header with your name and project name

2. **Create data structure**
   - Use a list to store items
   - Each item should be a dictionary with keys: name, price, quantity, category
   - Initialize an empty list

3. **Create the main menu**
   - Display options: Add, View, Total, Filter, Find, Remove, Exit
   - Use a while loop to keep the program running
   - Get user choice with input()

4. **Implement each function**
   - Add item: Get input, create dictionary, append to list
   - View items: Loop through list, format and display
   - Calculate total: Loop through, sum up price × quantity
   - Filter: Loop and check category, display matches
   - Find max/min: Compare prices, find extremes
   - Remove: Find item, remove from list

5. **Add error handling**
   - Check if list is empty before operations
   - Validate numeric inputs
   - Handle invalid menu choices

6. **Test thoroughly**
   - Add multiple items
   - Test each function
   - Test edge cases (empty list, invalid input)

---

## **Example Interaction / Output**

```
╔══════════════════════════════════════╗
║   Grocery Price Tracker             ║
╚══════════════════════════════════════╝

Menu:
1. Add item
2. View all items
3. Calculate total
4. Filter by category
5. Find most/least expensive
6. Remove item
7. Exit

Enter your choice: 1

Item name: Apple
Price per unit: 2.50
Quantity: 5
Category: Fruits

Item added successfully!

Enter your choice: 1

Item name: Milk
Price per unit: 3.99
Quantity: 2
Category: Dairy

Item added successfully!

Enter your choice: 2

═══════════════════════════════════════
All Grocery Items:
═══════════════════════════════════════
1. Apple
   Price: $2.50 × 5 = $12.50
   Category: Fruits

2. Milk
   Price: $3.99 × 2 = $7.98
   Category: Dairy
═══════════════════════════════════════

Enter your choice: 3

Total Cost: $20.48

Enter your choice: 4

Enter category to filter: Fruits

Items in 'Fruits' category:
- Apple: $12.50

Enter your choice: 5

Most expensive: Milk ($7.98)
Least expensive: Apple ($12.50)

Enter your choice: 7

Thank you for using Grocery Price Tracker!
```

**Note:** Your output format can vary, but it should be clear and organized.

---

## **Bonus Challenges (Optional)**

1. **Save to file**: Save the grocery list to a text file
2. **Load from file**: Load a previously saved list
3. **Edit items**: Allow users to modify existing items
4. **Search function**: Search for items by name
5. **Statistics**: Show average price, total items, items per category
6. **Sorting options**: Sort by name, price, or category
7. **Discount calculator**: Apply percentage discounts to items

---

## **Tips & Hints**

- **Menu loop**: Use `while True:` with `break` to exit
- **Data structure**: List of dictionaries works well:
  ```python
  items = [
      {"name": "Apple", "price": 2.50, "quantity": 5, "category": "Fruits"},
      ...
  ]
  ```

- **Finding max/min**: Use a loop to compare prices:
  ```python
  max_price = 0
  max_item = None
  for item in items:
      total = item["price"] * item["quantity"]
      if total > max_price:
          max_price = total
          max_item = item
  ```

- **Filtering**: Use conditional check in loop:
  ```python
  for item in items:
      if item["category"] == category:
          # display item
  ```

- **Input validation**: Convert strings to floats for prices:
  ```python
  price = float(input("Price: "))
  ```

- **Formatting**: Use f-strings for clean output
- **Empty list check**: Always check `if len(items) == 0:` before operations

---

**Good luck building your grocery tracker!**

