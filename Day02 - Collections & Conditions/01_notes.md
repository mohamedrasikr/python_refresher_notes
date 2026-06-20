# **Day 2 — Collections & Conditions**

## **Learning Objectives**

| # | Learning Objective | Description |
|---|-------------------|-------------|
| 1 | if-else Statements | Make decisions in code using conditional logic |
| 2 | List Basics | Store and manipulate ordered collections of items |
| 3 | Common List Methods | Use built-in methods to modify and work with lists |
| 4 | Dictionaries | Store key-value pairs for efficient data access |
| 5 | for Loop | Iterate through collections and sequences |

---

## **1. Introduction**

Today we're diving into collections and conditional logic. These concepts let you store multiple items together and make decisions in your code. When working with GenAI, you'll constantly need to process lists of data, make choices based on conditions, and iterate through information.

We'll cover if-else statements for decision-making, lists for storing sequences, dictionaries for key-value data, and for loops for iteration. These tools are essential for building practical applications.

---

## **2. Deep-Dive Explanation**

### **if-else: Making Decisions**

Conditional statements let your program choose different paths based on conditions. The `if` statement checks a condition, and if it's True, runs the code block.

```python
age = 18

if age >= 18:
    print("You can vote!")
```

You can add `elif` (else if) for multiple conditions and `else` for a default case:

```python
score = 85

if score >= 90:
    print("Grade: A")
elif score >= 80:
    print("Grade: B")
elif score >= 70:
    print("Grade: C")
else:
    print("Grade: F")
```

**Nested conditions** let you check multiple things:

```python
age = 20
has_license = True

if age >= 18:
    if has_license:
        print("You can drive!")
    else:
        print("You need a license first")
else:
    print("You're too young to drive")
```

### **Lists: Ordered Collections**

Lists store multiple items in order. You create them with square brackets and separate items with commas.

```python
fruits = ["apple", "banana", "orange"]
numbers = [1, 2, 3, 4, 5]
mixed = ["hello", 42, 3.14, True]
```

**Accessing items** uses index numbers (starting from 0):

```python
fruits = ["apple", "banana", "orange"]
print(fruits[0])  # Output: apple
print(fruits[1])  # Output: banana
print(fruits[-1])  # Output: orange (negative index counts from end)
```

**Slicing** gets multiple items:

```python
numbers = [0, 1, 2, 3, 4, 5]
print(numbers[1:4])  # Output: [1, 2, 3]
print(numbers[:3])   # Output: [0, 1, 2] (from start)
print(numbers[3:])    # Output: [3, 4, 5] (to end)
```

**Lists are mutable** - you can change them:

```python
fruits = ["apple", "banana"]
fruits[0] = "grape"  # Change first item
fruits.append("orange")  # Add to end
print(fruits)  # Output: ['grape', 'banana', 'orange']
```

### **Common List Methods**

Python provides many methods to work with lists:

**Adding items:**
```python
fruits = ["apple", "banana"]
fruits.append("orange")        # Add to end
fruits.insert(1, "grape")      # Insert at position 1
fruits.extend(["kiwi", "mango"])  # Add multiple items
```

**Removing items:**
```python
fruits = ["apple", "banana", "orange"]
fruits.remove("banana")        # Remove by value
fruits.pop()                   # Remove last item
fruits.pop(0)                  # Remove item at index 0
```

**Finding and counting:**
```python
numbers = [1, 2, 3, 2, 4, 2]
print(numbers.count(2))        # Count occurrences: 3
print(numbers.index(2))       # Find first index: 1
```

**Sorting and reversing:**
```python
numbers = [3, 1, 4, 1, 5]
numbers.sort()                 # Sort in place
numbers.reverse()              # Reverse in place
sorted_copy = sorted(numbers)   # Return sorted copy
```

**Other useful methods:**
```python
fruits = ["apple", "banana", "orange"]
print(len(fruits))             # Get length: 3
print("apple" in fruits)       # Check membership: True
fruits.clear()                 # Remove all items
```

### **Dictionaries: Key-Value Pairs**

Dictionaries store data as key-value pairs. They're perfect for structured data where you need to look things up by name.

```python
student = {
    "name": "Alice",
    "age": 20,
    "grade": "A"
}
```

**Accessing values** uses keys:

```python
print(student["name"])         # Output: Alice
print(student.get("age"))      # Output: 20
print(student.get("email", "N/A"))  # Default if key missing
```

**Adding and modifying:**
```python
student["email"] = "alice@example.com"  # Add new key
student["age"] = 21                      # Update existing
```

**Dictionary methods:**
```python
student = {"name": "Alice", "age": 20}
print(student.keys())          # Get all keys
print(student.values())        # Get all values
print(student.items())         # Get key-value pairs
student.pop("age")             # Remove key and return value
```

**Nested dictionaries** are common:

```python
students = {
    "alice": {"age": 20, "grade": "A"},
    "bob": {"age": 19, "grade": "B"}
}
print(students["alice"]["grade"])  # Output: A
```

### **for Loop: Iterating Through Collections**

The `for` loop lets you go through each item in a collection. It's one of the most powerful tools in Python.

**Looping through lists:**
```python
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(fruit)
```

**Using range() for numbers:**
```python
for i in range(5):
    print(i)  # Prints 0, 1, 2, 3, 4

for i in range(1, 6):
    print(i)  # Prints 1, 2, 3, 4, 5

for i in range(0, 10, 2):
    print(i)  # Prints 0, 2, 4, 6, 8 (step by 2)
```

**Looping through dictionaries:**
```python
student = {"name": "Alice", "age": 20, "grade": "A"}

for key in student:
    print(f"{key}: {student[key]}")

for key, value in student.items():
    print(f"{key}: {value}")

for value in student.values():
    print(value)
```

**Using enumerate() for index:**
```python
fruits = ["apple", "banana", "orange"]
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```

**Loop control:**
```python
for i in range(10):
    if i == 3:
        continue  # Skip to next iteration
    if i == 7:
        break     # Exit loop completely
    print(i)
```

---

## **3. Instructor Examples**

### **Example 1: Conditional Logic with Lists**

```python
# Grade calculator with conditions
scores = [85, 92, 78, 96, 88]

for score in scores:
    if score >= 90:
        grade = "A"
    elif score >= 80:
        grade = "B"
    elif score >= 70:
        grade = "C"
    else:
        grade = "F"
    
    print(f"Score: {score} → Grade: {grade}")
```

**Output:**
```
Score: 85 → Grade: B
Score: 92 → Grade: A
Score: 78 → Grade: C
Score: 96 → Grade: A
Score: 88 → Grade: B
```

### **Example 2: Working with Lists**

```python
# Shopping list manager
shopping_list = []

# Add items
shopping_list.append("milk")
shopping_list.extend(["bread", "eggs", "butter"])
shopping_list.insert(1, "cheese")

print(f"Current list: {shopping_list}")

# Check and remove
if "eggs" in shopping_list:
    shopping_list.remove("eggs")
    print("Removed eggs")

# Sort alphabetically
shopping_list.sort()
print(f"Sorted list: {shopping_list}")

# Get first and last
print(f"First item: {shopping_list[0]}")
print(f"Last item: {shopping_list[-1]}")
```

**Output:**
```
Current list: ['milk', 'cheese', 'bread', 'eggs', 'butter']
Removed eggs
Sorted list: ['bread', 'butter', 'cheese', 'milk']
First item: bread
Last item: milk
```

### **Example 3: Dictionary Operations**

```python
# Student database
students = {
    "alice": {"age": 20, "grades": [85, 90, 88]},
    "bob": {"age": 19, "grades": [78, 82, 80]},
    "charlie": {"age": 21, "grades": [92, 95, 90]}
}

# Calculate average grades
for name, info in students.items():
    grades = info["grades"]
    average = sum(grades) / len(grades)
    info["average"] = average
    print(f"{name.capitalize()}: Age {info['age']}, Average: {average:.1f}")

# Find top student
top_student = max(students.items(), key=lambda x: x[1]["average"])
print(f"\nTop student: {top_student[0]} with {top_student[1]['average']:.1f}")
```

**Output:**
```
Alice: Age 20, Average: 87.7
Bob: Age 19, Average: 80.0
Charlie: Age 21, Average: 92.3

Top student: charlie with 92.3
```

### **Example 4: Combining Loops and Conditions**

```python
# Filter and process data
numbers = [12, 45, 8, 23, 56, 9, 34, 67, 3, 91]

even_numbers = []
odd_numbers = []

for num in numbers:
    if num % 2 == 0:
        even_numbers.append(num)
    else:
        odd_numbers.append(num)

print(f"Even numbers: {even_numbers}")
print(f"Odd numbers: {odd_numbers}")
print(f"Sum of evens: {sum(even_numbers)}")
print(f"Sum of odds: {sum(odd_numbers)}")
```

**Output:**
```
Even numbers: [12, 8, 56, 34]
Odd numbers: [45, 23, 9, 67, 3, 91]
Sum of evens: 110
Sum of odds: 238
```

---

## **4. Summary / Key Takeaways**

- **if-else** statements let your code make decisions based on conditions
- **Lists** store ordered collections of items, accessible by index
- **List methods** like `append()`, `remove()`, `sort()` help manipulate lists
- **Dictionaries** store key-value pairs for efficient data lookup
- **for loops** iterate through collections, processing each item
- Use `range()` to generate number sequences for loops
- `enumerate()` gives you both index and value when looping
- `continue` skips to the next iteration, `break` exits the loop
- Lists and dictionaries are mutable - you can modify them after creation
- Nested structures (lists in lists, dicts in dicts) are powerful for complex data

---

