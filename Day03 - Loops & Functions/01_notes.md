# **Day 3 — Loops & Functions**

## **Learning Objectives**

| #   | Learning Objective  | Description                                                   |
| --- | ------------------- | ------------------------------------------------------------- |
| 1   | while Loop          | Create loops that run until a condition is met                |
| 2   | List Comprehensions | Write concise code to create and transform lists              |
| 3   | Functions           | Define reusable code blocks with parameters and return values |
| 4   | Lambda Functions    | Create small anonymous functions for quick operations         |

---

## **1. Introduction**

Today we're learning about more advanced looping and functions. These concepts help you write cleaner, reusable code. Functions are especially important in GenAI work - you'll use them to process data, format prompts, and organize your code into logical pieces.

We'll cover while loops for conditional iteration, list comprehensions for elegant list creation, functions for code organization, and lambda functions for quick operations. These tools will make your code more powerful and maintainable.

---

## **2. Deep-Dive Explanation**

### **while Loop: Conditional Iteration**

The `while` loop repeats code as long as a condition is True. Unlike `for` loops that iterate through sequences, `while` loops continue until the condition becomes False.

```python
count = 0
while count < 5:
    print(count)
    count += 1
```

**Common patterns:**

**Counter pattern:**

```python
i = 0
while i < 10:
    print(i)
    i += 1
```

**User input validation:**

```python
while True:
    age = input("Enter your age (0-120): ")
    if age.isdigit() and 0 <= int(age) <= 120:
        break
    print("Invalid input. Try again.")
```

**Processing until condition:**

```python
total = 0
while total < 100:
    num = int(input("Enter a number: "))
    total += num
    print(f"Running total: {total}")
```

**Infinite loops with break:**

```python
while True:
    choice = input("Enter command (or 'quit' to exit): ")
    if choice == "quit":
        break
    print(f"Executing: {choice}")
```

**Using continue:**

```python
i = 0
while i < 10:
    i += 1
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)
```

### **List Comprehensions: Elegant List Creation**

List comprehensions provide a concise way to create lists. They're more readable and often faster than traditional loops.

**Basic syntax:**

```python
# Traditional way
squares = []
for x in range(10):
    squares.append(x ** 2)

# List comprehension
squares = [x ** 2 for x in range(10)]
```

**Basic examples:**

```python
# Create list of numbers
numbers = [x for x in range(10)]  # [0, 1, 2, ..., 9]

# Transform existing list
words = ["hello", "world", "python"]
lengths = [len(word) for word in words]  # [5, 5, 6]

# Filter and transform
evens = [x for x in range(20) if x % 2 == 0]  # [0, 2, 4, ..., 18]
```

**With conditions:**

```python
# Only even numbers
evens = [x for x in range(20) if x % 2 == 0]

# Numbers greater than 10
large = [x for x in range(20) if x > 10]

# Multiple conditions
filtered = [x for x in range(20) if x % 2 == 0 and x > 10]
```

**Nested comprehensions:**

```python
# Create pairs
pairs = [(x, y) for x in range(3) for y in range(3)]
# [(0,0), (0,1), (0,2), (1,0), (1,1), (1,2), (2,0), (2,1), (2,2)]

# Flatten a 2D list
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flat = [num for row in matrix for num in row]  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**With transformations:**

```python
# Convert to uppercase
words = ["hello", "world"]
upper = [word.upper() for word in words]  # ['HELLO', 'WORLD']

# Extract specific attributes
students = [{"name": "Alice", "age": 20}, {"name": "Bob", "age": 19}]
names = [s["name"] for s in students]  # ['Alice', 'Bob']
```

### **Functions: Reusable Code Blocks**

Functions let you organize code into reusable blocks. They take inputs (parameters) and can return outputs.

**Defining a function:**

```python
def greet(name):
    return f"Hello, {name}!"

message = greet("Alice")
print(message)  # Output: Hello, Alice!
```

**Function with multiple parameters:**

```python
def add_numbers(a, b):
    return a + b

result = add_numbers(5, 3)
print(result)  # Output: 8
```

**Default parameters:**

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))           # Hello, Alice!
print(greet("Bob", "Hi"))       # Hi, Bob!
```

**Keyword arguments:**

```python
def create_profile(name, age, city):
    return f"{name}, {age}, lives in {city}"

# Positional
profile1 = create_profile("Alice", 20, "NYC")

# Keyword
profile2 = create_profile(city="LA", name="Bob", age=25)
```

**Returning multiple values:**

```python
def calculate_stats(numbers):
    total = sum(numbers)
    average = total / len(numbers)
    maximum = max(numbers)
    return total, average, maximum

total, avg, max_val = calculate_stats([1, 2, 3, 4, 5])
```

**Functions without return:**

```python
def print_info(name, age):
    print(f"Name: {name}")
    print(f"Age: {age}")
    # No return statement - returns None

result = print_info("Alice", 20)  # Prints info, result is None
```

**Variable scope:**

```python
x = 10  # Global variable

def my_function():
    x = 5  # Local variable
    print(x)  # Prints 5

my_function()
print(x)  # Prints 10 (global unchanged)
```

**Using global variables:**

```python
count = 0

def increment():
    global count
    count += 1

increment()
print(count)  # 1
```

### **Lambda Functions: Quick Anonymous Functions**

Lambda functions are small, anonymous functions defined in a single line. They're useful for simple operations.

**Basic syntax:**

```python
# Regular function
def square(x):
    return x ** 2

# Lambda equivalent
square = lambda x: x ** 2

print(square(5))  # 25
```

**Common use cases:**

**With map():**

```python
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))  # [1, 4, 9, 16, 25]
```

**With filter():**

```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
evens = list(filter(lambda x: x % 2 == 0, numbers))  # [2, 4, 6, 8, 10]
```

**With sorted():**

```python
students = [{"name": "Alice", "age": 20}, {"name": "Bob", "age": 19}]
sorted_by_age = sorted(students, key=lambda s: s["age"])
```

**Multiple parameters:**

```python
add = lambda x, y: x + y
multiply = lambda x, y, z: x * y * z

print(add(3, 5))        # 8
print(multiply(2, 3, 4))  # 24
```

**Conditional logic:**

```python
max_value = lambda x, y: x if x > y else y
print(max_value(5, 3))  # 5
```

---

## **3. Instructor Examples**

### **Example 1: while Loop for User Interaction**

```python
# Simple calculator with while loop
while True:
    print("\n=== Calculator ===")
    print("1. Add")
    print("2. Subtract")
    print("3. Multiply")
    print("4. Divide")
    print("5. Exit")

    choice = input("Enter choice: ")

    if choice == "5":
        print("Goodbye!")
        break

    if choice in ["1", "2", "3", "4"]:
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))

        if choice == "1":
            result = num1 + num2
        elif choice == "2":
            result = num1 - num2
        elif choice == "3":
            result = num1 * num2
        elif choice == "4":
            if num2 != 0:
                result = num1 / num2
            else:
                print("Cannot divide by zero!")
                continue

        print(f"Result: {result}")
    else:
        print("Invalid choice!")
```

### **Example 2: List Comprehensions**

```python
# Process student data
students = [
    {"name": "Alice", "scores": [85, 90, 88]},
    {"name": "Bob", "scores": [78, 82, 80]},
    {"name": "Charlie", "scores": [92, 95, 90]}
]

# Calculate averages using list comprehension
averages = [sum(s["scores"]) / len(s["scores"]) for s in students]

# Get names of students with average > 85
top_students = [s["name"] for s in students if sum(s["scores"]) / len(s["scores"]) > 85]

# Create list of (name, average) tuples
student_averages = [(s["name"], sum(s["scores"]) / len(s["scores"])) for s in students]

print(f"Averages: {averages}")
print(f"Top students: {top_students}")
print(f"Student averages: {student_averages}")
```

**Output:**

```
Averages: [87.67, 80.0, 92.33]
Top students: ['Alice', 'Charlie']
Student averages: [('Alice', 87.67), ('Bob', 80.0), ('Charlie', 92.33)]
```

### **Example 3: Functions for Data Processing**

```python
def calculate_grade(score):
    """Calculate letter grade from numeric score."""
    if score >= 90:
        return "A"
    elif score >= 80:
        return "B"
    elif score >= 70:
        return "C"
    elif score >= 60:
        return "D"
    else:
        return "F"

def process_student_scores(scores):
    """Process a list of scores and return statistics."""
    if not scores:
        return None

    total = sum(scores)
    average = total / len(scores)
    maximum = max(scores)
    minimum = min(scores)
    grades = [calculate_grade(score) for score in scores]

    return {
        "total": total,
        "average": average,
        "max": maximum,
        "min": minimum,
        "grades": grades
    }

# Usage
scores = [85, 92, 78, 96, 88]
stats = process_student_scores(scores)

print(f"Average: {stats['average']:.2f}")
print(f"Grades: {stats['grades']}")
```

**Output:**

```
Average: 87.80
Grades: ['B', 'A', 'C', 'A', 'B']
```

### **Example 4: Lambda Functions in Action**

```python
# Process numbers with lambda
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Square all numbers
squared = list(map(lambda x: x ** 2, numbers))

# Filter even numbers
evens = list(filter(lambda x: x % 2 == 0, numbers))

# Filter numbers greater than 5
large = list(filter(lambda x: x > 5, numbers))

# Sort by absolute difference from 7
sorted_nums = sorted(numbers, key=lambda x: abs(x - 7))

print(f"Squared: {squared}")
print(f"Evens: {evens}")
print(f"Large: {large}")
print(f"Sorted by distance from 7: {sorted_nums}")
```

**Output:**

```
Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
Evens: [2, 4, 6, 8, 10]
Large: [6, 7, 8, 9, 10]
Sorted by distance from 7: [7, 6, 8, 5, 9, 4, 10, 3, 2, 1]
```

---

## **4. Summary / Key Takeaways**

- **while loops** repeat code until a condition becomes False
- Use `break` to exit a loop early, `continue` to skip to next iteration
- **List comprehensions** provide concise syntax for creating and transforming lists
- Syntax: `[expression for item in iterable if condition]`
- **Functions** organize code into reusable blocks with `def function_name(parameters):`
- Functions can return values with `return`, or return `None` by default
- Use default parameters and keyword arguments for flexibility
- **Lambda functions** are anonymous, single-expression functions
- Lambdas are useful with `map()`, `filter()`, and `sorted()`
- Functions have local scope; use `global` to modify global variables
- List comprehensions are often more readable than equivalent loops

---
