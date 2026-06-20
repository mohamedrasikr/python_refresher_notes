# **Day 1 — Python Building Blocks**

## **Learning Objectives**

| # | Learning Objective | Description |
|---|-------------------|-------------|
| 1 | Variables | Understand how to store and manage data using variables |
| 2 | Data Types | Learn about strings, integers, floats, booleans, and None |
| 3 | f-strings | Master string formatting using f-strings for clean output |
| 4 | User Input | Get input from users and convert between data types |
| 5 | Truthy & Falsy Values | Understand which values Python treats as True/False |
| 6 | Operators | Use arithmetic, comparison, and logical operators effectively |

---

## **1. Introduction**

Today we're covering the fundamental building blocks of Python. These are the concepts you'll use in every program you write, especially when working with GenAI tools.

When building GenAI applications, you'll constantly be storing information, working with different data types, formatting output, getting user input, and making decisions. These core concepts form the foundation for everything else.

We'll cover variables, data types, f-strings, user input, truthy/falsy values, and operators. Master these, and you'll have a solid base to build on.

---

## **2. Deep-Dive Explanation**

### **Variables: Your Data Containers**

A variable is like a labeled box where you store information. In Python, you create a variable by giving it a name and assigning a value.

```
┌─────────────┐
│   name      │  ← Variable name (the label)
│  "Alice"    │  ← Value stored inside
└─────────────┘
```

**Key Rules:**

- Variable names can contain letters, numbers, and underscores
- They cannot start with a number
- They are case-sensitive (Name and name are different)
- Use descriptive names (age instead of a)

**Example:**

```python
# Creating variables
name = "Alice"
age = 25
height = 5.6
is_student = True
```

### **Data Types: Different Kinds of Information**

Python automatically figures out what type of data you're storing. Here are the main types:

#### **1. Strings (str)**

Text data, always wrapped in quotes.

```python
name = "Python"
greeting = 'Hello'
message = """This is a
multi-line string"""
```

#### **2. Integers (int)**

Whole numbers (no decimal point.

```python
age = 25
count = -10
year = 2024
```

#### **3. Floats (float)**

Numbers with decimal points.

```python
price = 19.99
temperature = -5.5
pi = 3.14159
```

#### **4. Booleans (bool)**

Only two values: `True` or `False` (capitalized!).

```python
is_active = True
is_complete = False
```

#### **5. None**

Represents "nothing" or "empty".

```python
result = None
```

**Checking Data Types:**

```python
name = "Alice"
print(type(name))  # Output: <class 'str'>
```

### **f-strings: Beautiful String Formatting**

f-strings (formatted string literals) let you insert variables directly into strings. The `f` before the quotes tells Python: "Hey, look for variables inside curly braces!"

**Before f-strings (old way):**

```python
name = "Alice"
age = 25
message = "My name is " + name + " and I am " + str(age) + " years old"
```

**With f-strings (modern way):**

```python
name = "Alice"
age = 25
message = f"My name is {name} and I am {age} years old"
```

Much cleaner! The `{name}` and `{age}` are automatically replaced with their values.

### **User Input: Getting Information from Users**

The `input()` function pauses your program and waits for the user to type something and press Enter.

```python
name = input("What's your name? ")
print(f"Hello, {name}!")
```

**Important:** `input()` always returns a string, even if the user types a number!

```python
age = input("How old are you? ")  # User types: 25
print(type(age))  # Output: <class 'str'> (not int!)
```

To convert input to a number:

```python
age = int(input("How old are you? "))  # Converts string to integer
```

### **Truthy & Falsy Values: What Python Considers True/False**

Python treats certain values as "truthy" (treated as True) or "falsy" (treated as False) in conditions.

**Falsy values:**

- `False`
- `None`
- `0` (zero)
- `0.0` (zero float)
- `""` (empty string)
- `[]` (empty list)
- `{}` (empty dictionary)

**Everything else is truthy!**

```python
# Falsy examples
if 0:
    print("This won't print")
if "":
    print("This won't print")
if None:
    print("This won't print")

# Truthy examples
if 1:
    print("This will print!")
if "hello":
    print("This will print!")
if [1, 2, 3]:
    print("This will print!")
```

### **Operators: Tools for Working with Data**

#### **Arithmetic Operators**

Do math with numbers.

```python
a = 10
b = 3

print(a + b)  # Addition: 13
print(a - b)  # Subtraction: 7
print(a * b)  # Multiplication: 30
print(a / b)  # Division: 3.333...
print(a // b) # Floor division: 3 (rounds down)
print(a % b)  # Modulo (remainder): 1
print(a ** b) # Exponentiation: 1000 (10 to the power of 3)
```

#### **Comparison Operators**

Compare values and return True or False.

```python
a = 10
b = 5

print(a == b)  # Equal to: False
print(a != b)  # Not equal to: True
print(a > b)   # Greater than: True
print(a < b)   # Less than: False
print(a >= b)  # Greater than or equal: True
print(a <= b)  # Less than or equal: False
```

#### **Logical Operators**

Combine conditions.

```python
age = 25
has_license = True

# AND: Both must be True
if age >= 18 and has_license:
    print("You can drive!")

# OR: At least one must be True
if age < 18 or age > 65:
    print("Special considerations apply")

# NOT: Reverses True/False
if not has_license:
    print("You need a license!")
```

**Truth Table:**

```
AND:
True and True = True
True and False = False
False and True = False
False and False = False

OR:
True or True = True
True or False = True
False or True = True
False or False = False

NOT:
not True = False
not False = True
```

---

## **3. Instructor Examples**

### **Example 1: Variables and Data Types**

```python
# Storing different types of information
student_name = "Sarah"
student_age = 20
student_gpa = 3.8
is_enrolled = True
courses = None  # Not assigned yet

# Displaying information
print(f"Student: {student_name}")
print(f"Age: {student_age}")
print(f"GPA: {student_gpa}")
print(f"Enrolled: {is_enrolled}")
print(f"Courses: {courses}")

# Checking types
print(f"\nType of student_name: {type(student_name)}")
print(f"Type of student_age: {type(student_age)}")
print(f"Type of student_gpa: {type(student_gpa)}")
```

**Output:**

```
Student: Sarah
Age: 20
GPA: 3.8
Enrolled: True
Courses: None

Type of student_name: <class 'str'>
Type of student_age: <class 'int'>
Type of student_gpa: <class 'float'>
```

### **Example 2: f-strings in Action**

```python
# Creating a formatted message
product = "Laptop"
price = 999.99
discount = 0.15
final_price = price * (1 - discount)

# Using f-strings for clean output
receipt = f"""
=== RECEIPT ===
Product: {product}
Original Price: ${price}
Discount: {discount * 100}%
Final Price: ${final_price:.2f}
===============
"""

print(receipt)
```

**Output:**

```
=== RECEIPT ===
Product: Laptop
Original Price: $999.99
Discount: 15.0%
Final Price: $849.99
===============
```

### **Example 3: User Input and Type Conversion**

```python
# Getting user information
print("Welcome to the Registration System!")
print("-" * 40)

name = input("Enter your name: ")
age = int(input("Enter your age: "))
height = float(input("Enter your height (in feet): "))
is_member = input("Are you a member? (yes/no): ").lower() == "yes"

# Displaying collected information
print("\n" + "=" * 40)
print("REGISTRATION SUMMARY")
print("=" * 40)
print(f"Name: {name}")
print(f"Age: {age} years old")
print(f"Height: {height} feet")
print(f"Member Status: {is_member}")
print("=" * 40)
```

**Sample Run:**

```
Welcome to the Registration System!
----------------------------------------
Enter your name: John
Enter your age: 28
Enter your height (in feet): 5.9
Are you a member? (yes/no): yes

========================================
REGISTRATION SUMMARY
========================================
Name: John
Age: 28 years old
Height: 5.9 feet
Member Status: True
========================================
```

### **Example 4: Truthy/Falsy and Operators**

```python
# Demonstrating truthy/falsy values
values = [0, 1, "", "hello", [], [1, 2], None, True, False]

print("Truthy/Falsy Check:")
print("-" * 30)
for value in values:
    if value:
        print(f"{repr(value):15} → Truthy")
    else:
        print(f"{repr(value):15} → Falsy")

# Using operators
print("\n" + "=" * 30)
print("Operator Examples")
print("=" * 30)

num1 = 15
num2 = 7

print(f"Arithmetic:")
print(f"  {num1} + {num2} = {num1 + num2}")
print(f"  {num1} // {num2} = {num1 // num2}")
print(f"  {num1} % {num2} = {num1 % num2}")

print(f"\nComparison:")
print(f"  {num1} > {num2}: {num1 > num2}")
print(f"  {num1} == {num2}: {num1 == num2}")

print(f"\nLogical:")
print(f"  ({num1} > 10) and ({num2} < 10): {(num1 > 10) and (num2 < 10)}")
print(f"  ({num1} < 10) or ({num2} > 5): {(num1 < 10) or (num2 > 5)}")
```

**Output:**

```
Truthy/Falsy Check:
------------------------------
0               → Falsy
1               → Truthy
''              → Falsy
'hello'         → Truthy
[]              → Falsy
[1, 2]          → Truthy
None            → Falsy
True            → Truthy
False           → Falsy

==============================
Operator Examples
==============================
Arithmetic:
  15 + 7 = 22
  15 // 7 = 2
  15 % 7 = 1

Comparison:
  15 > 7: True
  15 == 7: False

Logical:
  (15 > 10) and (7 < 10): True
  (15 < 10) or (7 > 5): True
```

---

## **4. Summary / Key Takeaways**

- **Variables** are containers that store data. Name them descriptively!
- **Data types** include: strings (text), integers (whole numbers), floats (decimals), booleans (True/False), and None
- **f-strings** (`f"text {variable}"`) are the modern, clean way to format strings
- **input()** always returns a string; convert to int/float if needed
- **Falsy values** are: False, None, 0, 0.0, "", [], {}
- **Arithmetic operators**: +, -, \*, /, //, %, \*\*
- **Comparison operators**: ==, !=, >, <, >=, <=
- **Logical operators**: and, or, not
- Use `type()` to check what type of data you're working with
