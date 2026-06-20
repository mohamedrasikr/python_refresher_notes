# **Day 4 — Working With Modules & Errors**

## **Learning Objectives**

| #   | Learning Objective | Description                                              |
| --- | ------------------ | -------------------------------------------------------- |
| 1   | Python Modules     | Import and use code from other modules and packages      |
| 2   | Exception Handling | Handle errors gracefully using try/except/finally blocks |
| 3   | HTTP Requests      | Make GET and POST requests to interact with APIs         |

---

## **1. Introduction**

Today we're learning about modules, error handling, and HTTP requests. These are essential skills for real-world programming. When working with GenAI, you'll often need to import libraries, handle errors from API calls, and make HTTP requests to interact with services.

We'll cover importing modules, handling exceptions to prevent crashes, and making HTTP requests to fetch and send data. These tools let you build robust applications that can handle errors and interact with external services.

---

## **2. Deep-Dive Explanation**

### **Python Modules: Reusing Code**

Modules are files containing Python code that you can import and use in your programs. Python comes with many built-in modules, and you can also create your own.

**Importing entire modules:**

```python
import math
import random
import datetime

print(math.pi)              # 3.14159...
print(random.randint(1, 10))  # Random number
print(datetime.datetime.now())  # Current date/time
```

**Importing specific items:**

```python
from math import sqrt, pow
from random import choice, shuffle

print(sqrt(16))             # 4.0
print(choice([1, 2, 3, 4]))  # Random choice
```

**Importing with aliases:**

```python
import datetime as dt
import math as m

print(dt.datetime.now())
print(m.sqrt(25))
```

**Importing everything (not recommended):**

```python
from math import *  # Imports all, but can cause naming conflicts
```

**Common built-in modules:**

```python
import math          # Mathematical functions
import random        # Random number generation
import datetime      # Date and time operations
import os            # Operating system interface
import sys           # System-specific parameters
import json          # JSON data handling
import csv           # CSV file operations
```

**Creating your own module:**

```python
# Save as my_module.py
def greet(name):
    return f"Hello, {name}!"

def add(a, b):
    return a + b

# In another file:
import my_module
print(my_module.greet("Alice"))
```

### **Exception Handling: Graceful Error Management**

Exceptions are errors that occur during program execution. Instead of letting your program crash, you can catch and handle them.

**Basic try/except:**

```python
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(f"Result: {result}")
except ValueError:
    print("That's not a valid number!")
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

**Catching multiple exceptions:**

```python
try:
    # Some code
    pass
except (ValueError, TypeError) as e:
    print(f"Error: {e}")
```

**Catching all exceptions:**

```python
try:
    # Some code
    pass
except Exception as e:
    print(f"An error occurred: {e}")
```

**try/except/else:**

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input")
else:
    print(f"You entered: {number}")
    # This runs only if no exception occurred
```

**try/except/finally:**

```python
try:
    file = open("data.txt", "r")
    content = file.read()
except FileNotFoundError:
    print("File not found")
finally:
    file.close()  # Always executes, even if error occurs
```

**Using with statement (better for files):**

```python
try:
    with open("data.txt", "r") as file:
        content = file.read()
        # File automatically closes when done
except FileNotFoundError:
    print("File not found")
```

**Raising exceptions:**

```python
def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero!")
    return a / b

try:
    result = divide(10, 0)
except ValueError as e:
    print(e)
```

**Custom exceptions:**

```python
class CustomError(Exception):
    pass

try:
    raise CustomError("Something went wrong")
except CustomError as e:
    print(e)
```

### **HTTP Requests: Interacting with APIs**

HTTP requests let you communicate with web services and APIs. The `requests` library makes this easy.

**Installing requests:**

```bash
pip install requests
```

**Making GET requests:**

```python
import requests

# Simple GET request
response = requests.get("https://api.github.com")
print(response.status_code)  # 200 means success
print(response.text)         # Response content
```

**Checking response status:**

```python
response = requests.get("https://api.github.com")

if response.status_code == 200:
    print("Success!")
    data = response.json()  # If response is JSON
else:
    print(f"Error: {response.status_code}")
```

**GET request with parameters:**

```python
import requests

params = {"q": "python", "page": 1}
response = requests.get("https://api.example.com/search", params=params)
data = response.json()
```

**GET request with headers:**

```python
import requests

headers = {
    "User-Agent": "MyApp/1.0",
    "Authorization": "Bearer token123"
}
response = requests.get("https://api.example.com/data", headers=headers)
```

**Making POST requests:**

```python
import requests

# POST with JSON data
data = {"name": "Alice", "age": 25}
response = requests.post("https://api.example.com/users", json=data)

# POST with form data
form_data = {"username": "alice", "password": "secret"}
response = requests.post("https://api.example.com/login", data=form_data)
```

**Handling errors in requests:**

```python
import requests

try:
    response = requests.get("https://api.example.com/data", timeout=5)
    response.raise_for_status()  # Raises exception for bad status codes
    data = response.json()
except requests.exceptions.RequestException as e:
    print(f"Request failed: {e}")
except requests.exceptions.Timeout:
    print("Request timed out")
except requests.exceptions.HTTPError as e:
    print(f"HTTP error: {e}")
```

**Using http.client (built-in, more low-level):**

```python
import http.client
import json

conn = http.client.HTTPSConnection("api.github.com")
conn.request("GET", "/users/octocat")
response = conn.getresponse()
data = response.read().decode()
user_data = json.loads(data)
print(user_data)
conn.close()
```

---

## **3. Instructor Examples**

### **Example 1: Working with Modules**

```python
import math
import random
from datetime import datetime, timedelta

# Math operations
print(f"Square root of 16: {math.sqrt(16)}")
print(f"Pi: {math.pi}")
print(f"Power: {math.pow(2, 3)}")

# Random numbers
print(f"Random integer (1-10): {random.randint(1, 10)}")
print(f"Random choice: {random.choice(['apple', 'banana', 'orange'])}")

# Date operations
now = datetime.now()
print(f"Current time: {now}")
tomorrow = now + timedelta(days=1)
print(f"Tomorrow: {tomorrow}")
```

**Output:**

```
Square root of 16: 4.0
Pi: 3.141592653589793
Power: 8.0
Random integer (1-10): 7
Random choice: banana
Current time: 2024-01-15 10:30:45.123456
Tomorrow: 2024-01-16 10:30:45.123456
```

### **Example 2: Exception Handling**

```python
def safe_divide(a, b):
    """Safely divide two numbers with error handling."""
    try:
        result = a / b
        return result
    except ZeroDivisionError:
        return "Cannot divide by zero!"
    except TypeError:
        return "Invalid input types!"

def get_number():
    """Get a number from user with validation."""
    while True:
        try:
            number = float(input("Enter a number: "))
            return number
        except ValueError:
            print("Invalid input. Please enter a number.")
        except KeyboardInterrupt:
            print("\nOperation cancelled.")
            return None

# Usage
num1 = get_number()
num2 = get_number()

if num1 is not None and num2 is not None:
    result = safe_divide(num1, num2)
    print(f"Result: {result}")
```

### **Example 3: HTTP GET Request**

```python
import requests
import json

try:
    # Fetch data from a public API
    response = requests.get("https://jsonplaceholder.typicode.com/posts/1", timeout=5)
    response.raise_for_status()  # Check for HTTP errors

    # Parse JSON response
    post_data = response.json()

    print("Post Data:")
    print(f"Title: {post_data['title']}")
    print(f"Body: {post_data['body']}")
    print(f"User ID: {post_data['userId']}")

except requests.exceptions.RequestException as e:
    print(f"Request failed: {e}")
except KeyError as e:
    print(f"Missing key in response: {e}")
```

**Output:**

```
Post Data:
Title: sunt aut facere repellat provident occaecati excepturi optio reprehenderit
Body: quia et suscipit...
User ID: 1
```

### **Example 4: HTTP POST Request**

```python
import requests
import json

# Data to send
new_post = {
    "title": "My New Post",
    "body": "This is the content of my post",
    "userId": 1
}

try:
    # Make POST request
    response = requests.post(
        "https://jsonplaceholder.typicode.com/posts",
        json=new_post,
        timeout=5
    )
    response.raise_for_status()

    # Get created post data
    created_post = response.json()
    print("Post created successfully!")
    print(f"Post ID: {created_post['id']}")
    print(f"Title: {created_post['title']}")

except requests.exceptions.RequestException as e:
    print(f"Failed to create post: {e}")
```

**Output:**

```
Post created successfully!
Post ID: 101
Title: My New Post
```

---

## **4. Summary / Key Takeaways**

- **Modules** let you reuse code from other files and libraries
- Use `import module` or `from module import item` to import code
- **Exception handling** prevents crashes and provides graceful error management
- Use `try/except` to catch and handle exceptions
- `finally` blocks always execute, useful for cleanup
- `raise` lets you create your own exceptions
- **HTTP requests** let you interact with web APIs
- Use `requests.get()` for GET requests and `requests.post()` for POST requests
- Always check `response.status_code` or use `raise_for_status()`
- Handle `RequestException` and its subclasses for robust error handling
- Use `timeout` parameter to avoid hanging requests
- The `with` statement automatically handles file closing

---
