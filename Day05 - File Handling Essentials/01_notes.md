# **Day 5 — File Handling Essentials**

## **Learning Objectives**

| # | Learning Objective | Description |
|---|-------------------|-------------|
| 1 | Working with .txt | Read from and write to text files |
| 2 | Working with .json | Parse and create JSON data files |
| 3 | Working with .csv | Read and write CSV files for data processing |

---

## **1. Introduction**

Today we're learning about file handling - reading from and writing to different file formats. This is essential for storing data, loading configurations, and processing datasets. In GenAI work, you'll frequently work with JSON files for API responses, CSV files for data analysis, and text files for logs and outputs.

We'll cover text files for simple data storage, JSON files for structured data, and CSV files for tabular data. These skills let you persist data and work with external data sources.

---

## **2. Deep-Dive Explanation**

### **Working with .txt Files**

Text files are the simplest way to store and retrieve data. Python makes it easy to read and write text files.

**Opening and reading files:**
```python
# Read entire file
with open("data.txt", "r") as file:
    content = file.read()
    print(content)

# Read line by line
with open("data.txt", "r") as file:
    for line in file:
        print(line.strip())  # strip() removes newline

# Read all lines into a list
with open("data.txt", "r") as file:
    lines = file.readlines()
```

**Writing to files:**
```python
# Write (overwrites existing content)
with open("output.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a new line.")

# Append (adds to existing content)
with open("output.txt", "a") as file:
    file.write("\nThis is appended.")
```

**File modes:**
- `"r"` - Read (default, file must exist)
- `"w"` - Write (creates file, overwrites if exists)
- `"a"` - Append (creates file, adds to end)
- `"x"` - Exclusive creation (fails if file exists)
- `"r+"` - Read and write
- `"b"` - Binary mode (e.g., `"rb"`, `"wb"`)

**Error handling:**
```python
try:
    with open("data.txt", "r") as file:
        content = file.read()
except FileNotFoundError:
    print("File not found!")
except PermissionError:
    print("Permission denied!")
```

### **Working with .json Files**

JSON (JavaScript Object Notation) is a popular format for structured data. Python's `json` module makes it easy to work with JSON.

**Reading JSON files:**
```python
import json

# Read JSON from file
with open("data.json", "r") as file:
    data = json.load(file)
    print(data)

# JSON string to Python object
json_string = '{"name": "Alice", "age": 25}'
data = json.loads(json_string)
print(data["name"])  # Alice
```

**Writing JSON files:**
```python
import json

# Python object to JSON file
data = {
    "name": "Alice",
    "age": 25,
    "hobbies": ["reading", "coding"]
}

with open("data.json", "w") as file:
    json.dump(data, file, indent=4)  # indent for readability

# Python object to JSON string
json_string = json.dumps(data, indent=4)
print(json_string)
```

**JSON formatting:**
```python
import json

data = {"name": "Alice", "age": 25}

# Compact (no spaces)
compact = json.dumps(data)  # {"name":"Alice","age":25}

# Pretty (with indentation)
pretty = json.dumps(data, indent=2)
# {
#   "name": "Alice",
#   "age": 25
# }

# Sort keys
sorted_json = json.dumps(data, indent=2, sort_keys=True)
```

**Nested JSON:**
```python
import json

data = {
    "users": [
        {"name": "Alice", "age": 25},
        {"name": "Bob", "age": 30}
    ],
    "settings": {
        "theme": "dark",
        "language": "en"
    }
}

with open("users.json", "w") as file:
    json.dump(data, file, indent=4)
```

### **Working with .csv Files**

CSV (Comma-Separated Values) files store tabular data. Python's `csv` module handles CSV files efficiently.

**Reading CSV files:**
```python
import csv

# Read as list of lists
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)  # Each row is a list

# Read as list of dictionaries (with headers)
with open("data.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(row["name"])  # Access by column name
        print(row)  # Each row is a dictionary
```

**Writing CSV files:**
```python
import csv

# Write as list of lists
data = [
    ["Name", "Age", "City"],
    ["Alice", "25", "NYC"],
    ["Bob", "30", "LA"]
]

with open("output.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Write as list of dictionaries
data = [
    {"name": "Alice", "age": 25, "city": "NYC"},
    {"name": "Bob", "age": 30, "city": "LA"}
]

with open("output.csv", "w", newline="") as file:
    fieldnames = ["name", "age", "city"]
    writer = csv.DictWriter(file, fieldnames=fieldnames)
    writer.writeheader()  # Write header row
    writer.writerows(data)
```

**CSV options:**
```python
import csv

# Custom delimiter
with open("data.csv", "r") as file:
    reader = csv.reader(file, delimiter=";")  # Use semicolon

# Skip header
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    next(reader)  # Skip first row
    for row in reader:
        print(row)

# Handle quotes
with open("data.csv", "r") as file:
    reader = csv.reader(file, quoting=csv.QUOTE_ALL)
    for row in reader:
        print(row)
```

---

## **3. Instructor Examples**

### **Example 1: Text File Operations**

```python
# Write to text file
with open("notes.txt", "w") as file:
    file.write("My Notes\n")
    file.write("========\n\n")
    file.write("1. Learn Python\n")
    file.write("2. Build projects\n")
    file.write("3. Practice daily\n")

# Read from text file
with open("notes.txt", "r") as file:
    content = file.read()
    print(content)

# Process line by line
with open("notes.txt", "r") as file:
    lines = file.readlines()
    for i, line in enumerate(lines, 1):
        print(f"Line {i}: {line.strip()}")
```

**Output:**
```
My Notes
========

1. Learn Python
2. Build projects
3. Practice daily

Line 1: My Notes
Line 2: ========
Line 3: 
Line 4: 1. Learn Python
...
```

### **Example 2: JSON File Operations**

```python
import json

# Create and save data
students = {
    "students": [
        {"name": "Alice", "age": 20, "grades": [85, 90, 88]},
        {"name": "Bob", "age": 19, "grades": [78, 82, 80]},
        {"name": "Charlie", "age": 21, "grades": [92, 95, 90]}
    ],
    "class": "Python 101",
    "instructor": "Dr. Smith"
}

# Save to file
with open("students.json", "w") as file:
    json.dump(students, file, indent=4)

# Load from file
with open("students.json", "r") as file:
    data = json.load(file)
    
    print(f"Class: {data['class']}")
    print(f"Instructor: {data['instructor']}")
    print("\nStudents:")
    for student in data["students"]:
        avg = sum(student["grades"]) / len(student["grades"])
        print(f"  {student['name']}: {avg:.1f}")
```

**Output:**
```
Class: Python 101
Instructor: Dr. Smith

Students:
  Alice: 87.7
  Bob: 80.0
  Charlie: 92.3
```

### **Example 3: CSV File Operations**

```python
import csv

# Write CSV file
students = [
    ["Name", "Age", "Grade"],
    ["Alice", "20", "A"],
    ["Bob", "19", "B"],
    ["Charlie", "21", "A"]
]

with open("students.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(students)

# Read CSV file
with open("students.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(f"{row['Name']}: Age {row['Age']}, Grade {row['Grade']}")

# Calculate average age
with open("students.csv", "r") as file:
    reader = csv.DictReader(file)
    ages = [int(row["Age"]) for row in reader]
    avg_age = sum(ages) / len(ages)
    print(f"\nAverage age: {avg_age:.1f}")
```

**Output:**
```
Alice: Age 20, Grade A
Bob: Age 19, Grade B
Charlie: Age 21, Grade A

Average age: 20.0
```

### **Example 4: Processing Data from Files**

```python
import json
import csv

# Load JSON data
with open("students.json", "r") as file:
    data = json.load(file)

# Convert to CSV
with open("students_export.csv", "w", newline="") as csvfile:
    fieldnames = ["name", "age", "average_grade"]
    writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
    writer.writeheader()
    
    for student in data["students"]:
        avg = sum(student["grades"]) / len(student["grades"])
        writer.writerow({
            "name": student["name"],
            "age": student["age"],
            "average_grade": f"{avg:.2f}"
        })

print("Data exported to CSV successfully!")
```

---

## **4. Summary / Key Takeaways**

- **Text files** use `open()` with modes `"r"`, `"w"`, `"a"`
- Always use `with` statement for automatic file closing
- **JSON files** use `json.load()` to read and `json.dump()` to write
- `json.loads()` converts JSON string to Python object
- `json.dumps()` converts Python object to JSON string
- Use `indent` parameter for readable JSON formatting
- **CSV files** use `csv.reader()` and `csv.writer()` for basic operations
- Use `csv.DictReader()` and `csv.DictWriter()` for dictionary-based access
- Always use `newline=""` when writing CSV files
- Handle file errors with try/except blocks
- File paths can be relative (same directory) or absolute (full path)

---

